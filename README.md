# PHP Yii2 Basic Application

## Getting started:

Clone docker to a folder (ex: php-workspace)
```
# change to your working directory
cd <path-to-a-working-directory>

git clone git@github.com:rahimrahman/docker-php-yii2-application.git php-workspace
```
Clone Yii2 Basic Application to a folder
```
git clone git@github.com:rahimrahman/php-yii2-basic.git php-workspace/php-yii2/yii2-basic
```

Within the php-workspace directory, to start all the services (yii2, mysql and phpmyadmin), and have the ability to modify the files on your local filesystem (which is mounted to yii2 php docker container), do (you do need to have composer installed on your machine):

```
cd php-workspace/php-yii2/yii2-basic
composer install --ignore-platform-reqs --prefer-dist

docker-compose -f docker-compose.local.yml up -d
```

Viola!  You now have a Yii2 Basic application that you can modify directly on your local filesystem.

You can also create a docker image of the Yii2 basic application without mounting the yii2-basic folder.

```
docker-compose up -d
```


