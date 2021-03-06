## Wordocker ##

### Introduction ###

Wordocker is a minimalistic setup which allows to run Wordpress
locally under the control of Docker.
The main purpose of it is to have a quick way of creating a local
development environment for Wordpress.


### How to install ###

The Wordpress files are to be placed into the 'wordpress' directory here.

For a new copy just run the following commands in the 'wordocker' directory:

```
$ wget http://wordpress.org/latest.tar.gz
$ tar xfz latest.tar.gz
$ rm latest.tar.gz
```

By default, Wordocker uses the latest version of Wordpress (from the
official image).
If necessary, the version can be adjusted by editing 'docker-compose.yml'.

### How to run ###

Run `docker-compose up -d` to start the services.

In Linux, visit http://localhost:8000 to access Wordpress.
This also applies to Windows 10 Professional with Docker for Windows
(running as a service).

If Docker Toolbox is used, visit `http://<Your Docker Machine IP>:8000`

Of course, the ports can be changed in 'docker-compose.yml'

### Permissions ###

In Linux, one needs to adjust permissions:

```
$ sudo chown -R www-data:www-data wordpress
$ sudo find wordpress -type f -exec chmod ug+rw,o+r {} \;
$ sudo find wordpress -type d -exec chmod ug+rwxs,o+rx {} \;
```

If non yet done, also add your user to 'www-data' group:

```
$ sudo usermod -aG www-data $USER
```

This will allow your user to edit files in 'wordpress' directory.

### phpMyAdmin ###

Wordocker also provides phpmyadmin in a separate container,
exposed on port 8080.
