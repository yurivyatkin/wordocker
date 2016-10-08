## Wordocker ##

This is a minimalistic setup which should allow to run Wordpress
locally under the control of Docker.

The Wordpress files are to be placed into the 'site' directory here.

In Linux, in order to develop in 'site', one needs to adjust permissions:

```
$ sudo usermod -aG www-data $USER
$ sudo chgrp -R www-data site
$ chmod g+rwxs site
```

Run `docker-compose up -d` and visit http://localhost:8000
