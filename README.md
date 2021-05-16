# DKR - Spin Nginx, PHP, Mysql and PHPmyadmin in one command on any system
## Prerequisits
```
- Docker
- Docker Compose
```

## Package includes
```
 - Nginx
 - PHP 7.2
 - Mysql 5.7.22
 - PHPmyadmin
```

## How it works
```
$ git clone https://github.com/simaranjit/dkr.git
$ cd dkr
$ docker-compose up -d
Creating dkr_db        ... done
Creating dkr_webserver ... done
Creating dkr_app        ... done
Creating dkr_phpmyadmin ... done
```
That's all 😁

`Note:` It may take few minutes to start when you run it first time because it downlaods images

## URL to acesss DKR after starting
http://localhost

## How to access PhpMyadmin
http://localhost:8081

## Default MySQL Credentials
```
host: db
user: root
password: password
```

## php.ini path
./php/local.ini

## PHP Working directory
`./www`

Put all your PHP files and folders under `./www/` directory. For example if you want to create a new project called `myproject`, create that like this `./www/myproject` and create `index.php` under that.
Now access project like http://localhost/myproject/index.php

## How to create VirtualHosts
Put all you virtualhosts under `nginx/conf.d/` directory and make sure that you add entry in `hosts` file to access those virtual hosts

## How to stop DKR
```
$ docker-compose down
Stopping dkr_phpmyadmin ... done
Stopping dkr_db         ... done
Stopping dkr_app        ... done
Stopping dkr_webserver  ... done
Removing dkr_phpmyadmin ... done
Removing dkr_db         ... done
Removing dkr_app        ... done
Removing dkr_webserver  ... done
Removing network dkr_dkr-network
```

### DKR CLI
DKR has a built in CLI to provide easy support with the below commands (dkr)

Syntax 
`php dkr {command}`

Example 
`php dkr start`

Supported commands
```
start -> To start the server. E.g. php dkr start
stop -> To stop the server. E.g. php dkr stop
restart -> To restart the server. E.g. php dkr restart
rebuild -> To rebuild the server. E.g. php dkr rebuild
vhost:create -> To create virtual host. E.g. php dkr vhost:create domain.com
vhost:delete -> To delete the virtual host. E.g. dkr vhost:delete domain.com
vhost:remove -> Alias to delete the virtual host. E.g. dkr vhost:remove domain.com
```