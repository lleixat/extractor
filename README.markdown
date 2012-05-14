### Description

The script `balsa_extractor` is a shell trick which allows you to fetch all searched arguments in on [BalsaCM]() project files.

### Depends on ...

* _core-utils_
* shell environment like \[sh|bash|dash\]
* _grep_ or _egrep_ 

### Installation

[Download this repository](http://lab.thomaslleixa.fr/balsa_extractor/repository/archive) or clone it if you prefer.

You can keep this script in your root development project directory or copy it in your `$HOME/bin/`.

> Be sure to add `$HOME/bin/` to your `$PATH` and logout+login to your shell to reload it!

Or make an alias or... Whatever...

Don't forget to _chmod_ it :

    chmod u+x $HOME/bin/extractor
  

### Usage

#### General usage:

    extractor [option] [file]
  
If _file_ isn't specified ...  ← wip

#### Example

    extractor --class

will fetch recursively all _php classes_ on project files. 

### Options available
  
     -sc,  --style-class     Search for html "class" attribute.
      -c,  --class           Search for php classes.
      -f,  --function        Search for php method/function name.
      -p,  --parameters      Search for php method/functions parameters.
     -fp,  --function-param  Search for php method/functions and parameters.
    -com,  --comments        Search for php comments.
      -h,  --help            This help.
  

> You can retrieve this help doing...
>     extractor --help
> ...in your command line interface.

Have fun !
