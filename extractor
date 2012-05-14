#!/bin/sh
SVR_ROOT=$HOME'/Dev/bois_en_jouet/nw/'
INCLUDE="*.php"
EXCLUDE="*\.git*"
OPT="-Po" # Man grep for options

function_construct ()
{
	echo -e "## Extracting '$1' :\n"
	grep $OPT $2 $SVR_ROOT -R --include=$INCLUDE --exclude=$EXCLUDE | sort -u
	echo -e "\n"
}

show_help ()
{
saveIFS=$IFS
IFS='\n' read -r -d '' HELP << 'EOF'
Usage:  extractor [option] [file] <-wip
        extractor --class

Options :
 -sc,  --style-class     Search for html "class" attribute.
  -c,  --class           Search for php classes.
  -f,  --function        Search for php method/function name.
  -p,  --parameters      Search for php method/functions parameters.
 -fp,  --function-param  Search for php method/functions and parameters.
-com,  --comments        Search for php comments.
  -h,  --help            This help.

EOF

echo "$HELP"

IFS=$saveIFS

}


case "$1" in
	-sc|--style-class)
		COM="Style Class"
		PATTERN='class="\K.*?(?=")'
		;;
	-c|--class)
		COM="Classes"
		PATTERN='class \K.*?(?=\n)'
		;;
	-f|--function)
		COM="function"
		PATTERN='function \K.*?(?=\()'
		;;
	-p|--parameters)
		COM="Functions parameters"
		PATTERN='function .*\(\K.*?(?=\))'
		;;
	-fp|--function-param)
		COM="Functions with parameters"
		PATTERN='function .*\(\K.*?(?=\n)'
		;;
	-com|--comments)
		COM="Functions with parameters"
		PATTERN='\/\*\K.*?(?=(\*\/\n))'
		;;
	-h|--help)
		show_help
		exit 0
		;;
	*)
		show_help
		exit 0
		;;
esac

function_construct $COM $PATTERN

exit 0
