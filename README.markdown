### Description

The script `balsa_extractor` is a shell trick which allows you to fetch all searched arguments in on [BalsaCM]() project files.

### Depends on ...

* _core-utils_
* shell environment like \[sh|bash|dash\]
* _grep_ or _grep-color_ 

### Installation

[Download this repository](http://lab.thomaslleixa.fr/balsa_extractor/repository/archive) or clone it if you prefer.

You can keep this script in your root development project directory or copy it in your `$HOME/bin/`.

> Be sure to add `$HOME/bin/` to your `$PATH` and logout+login to your shell to reload it!

Or make an alias or copy/paste or... whatever.

Don't forget to _chmod_ it :

    chmod u+x $HOME/bin/extractor
  
### Configuration

There is couple of variables to change in top of the script :

```bash
SVR_ROOT=$HOME'/Dev/bois_en_jouet/nw/'
INCLUDE="*.php"
EXCLUDE="*\.git*"
OPT="-Po"
```

Change them to your needs.

> `INCLUDE`, `EXCLUDE` and `OPT` are all `grep`'s options you can customize. Do `man grep` for more infos.

### Usage

#### General usage:

    extractor [option] [-o file]
  
#### Example

    lex@fry:~/Dev/bois_en_jouet/
    > extractor -c

    ## Extracting 'PHP Classes' [(class \K.*?(?={)|class \K.*?(?=\n)|class \K.*?(?=extends))]:

    nw/admin/plugin/bcm/fonction/bcm_category.class.php:5:bcm_category 
    nw/admin/plugin/bcm/fonction/bcm_comment.class.php:4:bcm_comment 
    nw/admin/plugin/bcm/fonction/bcm_publication.class.php:4:bcm_publication 
    nw/admin/plugin/bcm/fonction/bcm_shop_category.class.php:5:bcm_shop_category 
    nw/admin/plugin/bcm/fonction/bcm_tags.class.php:4:bcm_tags 
    nw/admin/plugin/forum/fonction/forum_categories.class.php:4:forum_categories 
    nw/admin/plugin/forum/fonction/forum_message.class.php:4:forum_message 
    nw/admin/plugin/forum/fonction/forum_thread.class.php:4:forum_thread 
    nw/admin/plugin/media_manager/media_manager.class.php:4:media_manager 
    nw/admin/plugin/media_manager/mm_folder.class.php:4:mm_folder 
    nw/admin/plugin/media_manager/mm_media.class.php:4:mm_media 
    nw/fonction/bcm_cart.class.php:15:bcm_cart 
    nw/fonction/bcm_category.class.php:5:bcm_category 
    nw/fonction/bcm_comment.class.php:4:bcm_comment 
    nw/fonction/bcm_order.class.php:29:bcm_order 
    nw/fonction/bcm_product.class.php:22:bcm_product 
    nw/fonction/bcm_publication.class.php:4:bcm_publication 
    ....    

will fetch recursively all _php classes_ on project files. 

### Options available

    -s,  --style-class     Search for html "class" attribute.
    -c,  --class           Search for php classes.
    -f,  --function        Search for php method/function name.
    -p,  --parameters      Search for php method/functions parameters.
    -F,  --function-param  Search for php method/functions and parameters.
    -k,  --comments        Search for php comments.
    -o,  --out             Write output in file.
    -h,  --help            This help.  
  

> You can retrieve this help doing...
>     extractor --help
> ...in your command line interface.

Have fun !
