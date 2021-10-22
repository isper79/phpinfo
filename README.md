[![CI](https://github.com/isper79/phpinfo/actions/workflows/ci.yaml/badge.svg?branch=santander)](https://github.com/isper79/phpinfo/actions/workflows/ci.yaml) 

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
# Instrucciones para clonar repositorio 
```
git clone https://github.com/isper79/phpinfo
cd phpinfo
git checkout santander

```
# Instrucciones para construir
```

docker build --file Dockerfile --tag isper79/phpinfo:santander .
```
```
docker run -d --entrypoint /usr/bin/php --name phpinfo -p 8080:8080 -v ${PWD}/src/index.php:/src/index.php:ro paularestrepo/phpinfo:santander -f src/index.php -S 0.0.0.0:8080

```
# Instrucciones para construir imagen docker optimizado
```
git pull
git checkout santander
docker build --file Dockerfile_optimizado --tag isper79/phpinfo:santander-optimizado .
docker push paularestrepo/phpinfo:santander-optimizado
```
```
```
# Instrucciones para ejecutar el contenedor 

docker run -d --entrypoint /usr/bin/php --name phpinfo -p 8080:8080 --restart always -v ${PWD}/src/index.php:/src/index.php:ro paularestrepo/phpinfo:santander-optimizado -f src/index.php -S 0.0.0.0:8080
```
```
```
# Instrucciones para desplegar la aplicacion en Swarm
docker stack deploy -c docker-compose.yaml phpinfo
