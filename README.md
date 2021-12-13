# compose
Należy zbudować prosty plik docker-compose.yml, który
pozwoli na uruchomienie znanej z innych zajęć, uslugi LEMP wraz z phpMyAdmin. Stack
LEMP składa się z następujących usług składowych:
---- L – dla Linux;
---- E – dla Nginx;
---- M – dla MySQL;
---- P – dla PHP.
Wobec tego projekt powinien zawierać cztery kontenery (usługi):
- jeden kontener dla Nginx;
- jeden kontener dla PHP (PHP-FPM) https://php-fpm.org/ ;
- jeden kontener dla MySQL;
- jeden kontener dla phpMyAdmin. 

Założenia dla uslugi:
- serwery są budowane zgodnie z dokumentacją obrazów bazowych dostępnych na
DockerHub i umieszczonych tam plików Dockerfile (zbudowanie własnych obrazów a nie
wykorzystanie z gotowych obrazów będzie wyżej oceniane).
- serwery PHP, MySQL, phpMyAdmin są przyłączone do sieci backend a Nginx do
backend oraz frontend. Nginx ma wystawiony na świat zewnętrzy port 6666.
- serwer Nginx ma wyświetlać stronę startową php (index.php).
- serwer phpMyAdmin ma być dostępny na porcie 6001 i powinno być możliwe
zalogowanie się do niego i założenie testowej bazy

Katalog zawierający projekt zawiera plik docker-compose oraz dwa foldery:

-str- folder zawierający plik index.php, czyli stronę, która będzie wyświetlana przez serwer po połączeniu z bazą danych
-uslugi- folder zawierający pliki dockerfile do tworzenia danych usług

![docker_compose_up](https://user-images.githubusercontent.com/94804536/145884149-dbbafdd7-70a9-4f40-be6b-4a98c258e381.png)
