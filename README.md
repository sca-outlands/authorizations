# Outlands Marshal Authorization Site

## Usage
Install Docker.
* Mac: https://store.docker.com/editions/community/docker-ce-desktop-mac

From the root of this directory, do
```
docker-compose -f docker-compose.yml up
```
This sets up a full copy of the site at http://localhost:8080

The admin user and password for the site are 'admin'.


# Run composer in the container
```
php -d memory_limit=2048M /usr/local/bin/composer install --prefer-dist
```

# copy updated db to container
* download copy of db locally, replace outlands_auth.sql in /etc/mysql
```
docker exec -i authorizations_mysql_1 mysql -uroot -p12345 outlands_auth < outlands_auth.sql
```

