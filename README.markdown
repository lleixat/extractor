### Description

This script is a wrapper for Ack which allows you to fetch all searched arguments in on any php project files.

### Depends on ...

* [ack](http://betterthangrep.com/) (see below)
* shell environment like \[z|ba|da\]sh
* _core-utils_
* a computer with all his stuff working (like CPU or mother board... the mouse is not needed)
* a piece of brain
* your hands

### Installation

Before trying the awesome extractor's script be sure to have the _ack_ (or _ack-grep_) Perl script installed on your system. 
Ack-grep (or ack) is packaged for many distributions so do your _apt-get_ or _yum_ or _yaourt_ thing and don't make me cry... thx.

[Download this repository]() or clone it if you prefer.

You can keep this script in your root development project directory or copy it in your `$HOME/bin/`.

> Be sure to add `$HOME/bin/` to your `$PATH` and logout+login to your shell to reload it!

Or make an alias or copy/paste or... whatever.

Don't forget to _chmod_ it :

    chmod u+x $HOME/bin/extractor
  
### Configuration

There is couple of variables to change in top of the script :

```bash
SVR_ROOT='nw/'
EXEC='/usr/bin/vendor_perl/ack' # path to the ack script
INCLUDE="php"
OPT="i"                         # `ack` or `ack-grep` --help for more options
#DEBUG="echo -E"                # Comment/uncomment to disable/enable debug
```

Change them to your needs.

> `INCLUDE`, `EXCLUDE` and `OPT` are all `grep`'s options you can customize. Do `man grep` for more infos.

### Usage

#### General usage:

    extractor option [-o file]
  
#### Example

    lex@fry:~/Dev/bois_en_jouet/
    > extractor -F
    ## Extracting 'Functions with parameters' [.*function \K.*]: ##
    
    ....
    104:get_stats()
    112:chgParam($dbName,$host="",$user="",$pass="")
    127:get_primkey()

    nw/install/void_mail.php
    3:mail_de_base($adr,$subject,$message,$from='someone@yopmail.com',$reply='no_reply@yopmail.com')
    36:mail_plus_piece_jointe($adr,$subject,$message,$pj,$pjn,$from='someone@yopmail.com',$reply='no_reply@yopmail.com')

    nw/fonction/sc_connect.class.php
    5:get_svc_list()
    24:__construct($provider='')
    38:set_conf($arr)
    60:set_provider($provider)
    68:redirect($uri='', $type=null, $time='0')
    83:display_menu()
    113:sc_notify()
    123:sc_deco($type, $redirect_uri = '')
    137:sc_connect_req()
    233:get_user_info($provider)
    341:is_oauth_logged($provider)

    nw/fonction/bdd.class.php
    31:Bdd()
    45:connect()
    71:disconnect()
    ....
    

will fetch recursively all _php functions_ on project files. 

Usefull or not ?

### Options available

    -s,  --style-class     Search for html "class" attribute.
    -c,  --class           Search for php classes.
    -f,  --function        Search for php method/function name.
    -p,  --parameters      Search for php method/functions parameters.
    -F,  --function-param  Search for php method/functions and parameters.
    -k,  --comments        Search for php comments.
    -o,  --out             Write output in file. Disable color output automagically.
    -h,  --help            This help.
  

> You can retrieve this help doing...
>   
>     extractor --help
>   
> ...in your awesome command line interface.

Have fun !
