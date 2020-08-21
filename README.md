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

## How to start DKR

```
$ docker-compose up -d
Creating network "dkr_dkr-network" with driver "bridge"
Creating dkr_db        ... done
Creating dkr_webserver ... done
Creating dkr_app        ... done
Creating dkr_phpmyadmin ... done
```

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
`./websites`

Put all your PHP files and folders under `./websites/` directory. For example if you want to create a new project called `myproject`, create that like this `./websites/myproject` and create `index.php` under that.
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
