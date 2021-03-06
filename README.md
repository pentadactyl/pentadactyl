Pentadactyl for Pale Moon
=========================

This is a community-maintained fork of one of the best XUL-based
Firefox extensions, targeting [Pale Moon](https://www.palemoon.org/)
28.5+.

Binary Releases
---------------

* [GitHub Releases Page](https://github.com/pentadactyl/pentadactyl/releases)
* [Pale Moon Website](https://addons.palemoon.org/addon/pentadactyl-community/)

Building from Source
--------------------

### Build XPI from sources ###

``` shell
git clone --depth 1000 https://github.com/pentadactyl/pentadactyl.git
cd pentadactyl/
make -C pentadactyl xpi
```

This resulting XPI will be placed in the `downloads/` folder.

#### Build dependencies ####

  * zip
  * gmake
  * Standard POSIX commands: awk, echo, sed, sh

While most developers use a Unix-like operating system, you can also build Pentadactyl on Windows with the help of MinGW's MSYS, Cygwin, or SFU. 

### Install without XPI ###

As creating and installing a new XPI file after each update is cumbersome, most developers run Pentadactyl directly from their working copies. This is achieved with [Firefox extension proxy file][1], which is a plain text file named after the extension ID and its contents is just a path to the extension source directory.

Assuming you use the `default` profile, the following command will create the proxy file:

``` shell
cd /path/to/cloned/pentadactyl/
# On clean profile, ensure that 'extensions' directory exists inside of the profile directory.
echo "$(pwd)/pentadactyl" >~/'.moonchild productions/pale moon'/*.default/extensions/pentadactyl@addons.palemoon.org
```

Once you installed Pentadactyl via the proxy file, restart the browser. Afterwards, you can use `:rehash` command to reload the extension without further browser restarts. Moreover, you can bind it to a key chord in your `~/.pentadactylrc`:

``` viml
nmap -ex <C-r> :rehash
```

[1]: https://developer.mozilla.org/en-US/Add-ons/Setting_up_extension_development_environment#Firefox_extension_proxy_file
