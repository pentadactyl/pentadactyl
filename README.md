Pentadactyl for Pale Moon
=========================

This is a port of one of the best XUL-based Firefox extensions, targeting [Pale Moon](https://www.palemoon.org/) 27. The goal of this project is to make Pentadactyl compatible with Pale Moon, while staying as close to the upstream as possible.

Install
-------

You can find the latest XPI file for download [here](https://github.com/madand/pentadactyl-pm/releases/latest). For older versions see the [Releases](https://github.com/madand/pentadactyl-pm/releases) page.

Development
-----------

### Build XPI from sources ###

``` shell
git clone --depth 1000 https://github.com/madand/pentadactyl-pm.git
cd pentadactyl-pm/
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
cd /path/to/cloned/pentadactyl-pm/
# On clean profile, ensure that 'extensions' directory exists inside of the profile directory.
echo "$(pwd)/pentadactyl" >~/'.moonchild productions/pale moon'/*.default/extensions/pentadactyl@addons.palemoon.org
```

Once you installed Pentadactyl via the proxy file, restart the browser. Afterwards, you can use `:rehash` command to reload the extension without further browser restarts. Moreover, you can bind it to a key chord in your `~/.pentadactylrc`:

``` viml
nmap -ex <C-r> :rehash
```

[1]: https://developer.mozilla.org/en-US/Add-ons/Setting_up_extension_development_environment#Firefox_extension_proxy_file
