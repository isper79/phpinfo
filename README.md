# phpinfo

```
git clone https://github.com/isper79/phpinfo
cd phpinfo
git checkout main
```
```
php -f src/index.php -S 0.0.0.0:8080
```
```
curl localhost:8080/src/index.php
```
Instrucciones para construir imagen docker
```
git checkout santander
docker build --file Dockerfile --tag isper79/phpinfo:santander .
```
```
docker run -d --entrypoint /usr/bin/php --name phpinfo -p 8080:8080 -v ${PWD}/src/index.php:/src/index.php:ro paularestrepo/phpinfo:santander -f src/index.php -S 0.0.0.0:8080
