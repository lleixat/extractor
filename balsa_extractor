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

case "$1" in
	-sc|style-class)
		COM="Style Class"
		PATTERN='class="\K.*?(?=")'
		;;
	-c|class)
		COM="Classes"
		PATTERN='class \K.*?(?=\n)'
		;;
	-f|function)
		COM="function"
		PATTERN='function \K.*?(?=\()'
		;;
	-p|funcparam)
		COM="Functions parameters"
		PATTERN='function .*\(\K.*?(?=\))'
		;;
	-fp|funcandparam)
		COM="Functions with parameters"
		PATTERN='function .*\(\K.*?(?=\n)'
		;;
	-com|comments)
		COM="Functions with parameters"
		PATTERN='\/\*\K.*?(?=(\*\/\n))'
		;;
esac

function_construct $COM $PATTERN

exit 0