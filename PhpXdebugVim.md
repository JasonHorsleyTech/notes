## How to get xdebug debugging a lamp stack php script from vim

> sudo apt-get install php-xdebug
> sudo vim /etc/php/7.2/mods-available/xdebug.ini

Replace with

zend_extension=xdebug.so
xdebug.remote_autostart = 1
xdebug.remote_enable = 1
xdebug.remote_handler = dbgp
xdebug.remote_host = localhost
xdebug.remote_log = /tmp/xdebug_remote.log
xdebug.remote_mode = req
xdebug.remote_port = 9000

> sudo system apache2 restart

* Open the vim script in question, F5, vim is waiting for a connection, refresh .php page


All that stuff about DBGp plugin and python signs... This works fine with a regular apt-get install vim build
