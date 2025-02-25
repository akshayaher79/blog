
Personal Blog
=============

Basic personal blog written in PHP which uses the file
system as storage.

Built according to the requirements specified in the
roadmap.sh project assignment
[Personal Blog](https://roadmap.sh/projects/personal-blog).


Installation
------------

First install and configure a webserver like Apache or
Nginx and install PHP if you haven't already.

**Basic example Apache setup**
```
$ # Installation on Debian/Ubuntu
$ sudo apt-get install apache2 libapache2-mod-php
$ sudo systemctl start apache2.service
```

**Custom setups**: You can use other webservers and custom
configurations including those with PHP-FPM etc. Please
look up the appropriate sources for documentation on the
systems of your choice.


### Install blog PHP package
Depending on your setup, you might choose to install the
PHP backend in a certain directory. Nevertheless, the
package will want to move certain public assets into your
webroot. It's recommmended to keep the blog package
alongside the default webroot (viz, in `/var/www/blog`
besides `/var/www/html`).

The installer will prompt for basic information. Assuming
a basic envirnoment *(fresh Debian/Ubuntu, default Apache
config)*, you must follow these instructions to install
and configure the blog:

1. Navigate to `/var/www` and clone the repo.
   ```
   $ cd /var/www/
   $ git clone https://github.com/akshayaher79/blog
   ```

2. [Download Composer](https://getcomposer.org/download/)
   and run the `install` sub-command.
   ```
   $ # Unwary way of downloading composer:
   $ curl -sS https://getcomposer.org/installer | php
   $ php composer.phar install
   ```

3. Optionally enter custom installation directories, and
   set the blog title and subtitle and your name when
   prompted.
   ```
   Enter absolute path of webroot [/var/www/html/]: 
   Assets moved to /var/www/html/.
   Title the blog: John's Blog
   Give it a subtitle: 
   Set personal details.
   Blog owner's name: John Doe
   Blog owner's screen name: @jdoe
   You can edit settings from /var/www/blog/config.json.
   ```

4. Restart Apache (or your webserver).
   ```
   $ systemctl restart apache2.service
   ```
You may need to be the super user to run these.
