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
