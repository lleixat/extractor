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

Or make an alias or copy/paste or... whatever.

Don't forget to _chmod_ it :

    chmod u+x $HOME/bin/extractor
  
### Configuration

There is couple of variables to change in top of the script :

    SVR_ROOT=$HOME'/Dev/bois_en_jouet/nw/'
    INCLUDE="*.php"
    EXCLUDE="*\.git*"
    OPT="-Po"

Change them to your needs.

> `INCLUDE`, `EXCLUDE` and `OPT` are all `grep`'s options you can customize. Do `man grep` for more infos.

### Usage

#### General usage:

    extractor [option] [file]
  
If _file_ isn't specified ...  ← wip

#### Example

    extractor --class
    \#\# Extracting 'Classes' :

    /home/lex/Dev/bois_en_jouet/nw/admin/page/footer.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/page/header.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/balsa_shell/balsa_shell.js.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/balsa_shell/index.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm_category.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm_comment.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm_publication.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm_shop_category.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/bcm/fonction/bcm_tags.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/chrysa_cache/gestion_cache.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/controll_panel/controll_panel.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/controll_panel/menu.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/DUI/DUI_main.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/DUI/page/DUI.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/editor/editor.js.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/editor/index.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/editor/menu.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/forum/fonction/forum_categories.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/forum/fonction/forum_message.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/forum/fonction/forum_thread.class.php:class
    /home/lex/Dev/bois_en_jouet/nw/admin/plugin/gestion_plugin/gestion.php:class
    ....    

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
