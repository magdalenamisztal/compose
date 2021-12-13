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

Dodatkowo w celu prawidłowego działania strony, został utworzony plik konfiguracyjny str.conf.

Po utworzeniu katalogów, plików dockerfile, pliku konfiguracyjnego strony oraz utworzeniu pliku docker-compose.yml,przeszłam do uruchomienia serwisu. W tym celu i ze względu na posiadaną wersję Docker'a użyłam polecenia: docker-compose up.

Następnie:

-sprawdzenie działania phpMyAdmin poprzez wejście w localhosta na porcie 6001 i przeprowadzenie testu działania bazy danych
![spr](https://user-images.githubusercontent.com/94804536/145884526-9ec0bc71-62e5-4267-b63f-c7e71fb6b783.png)

![spr2](https://user-images.githubusercontent.com/94804536/145884649-ba9bb398-6194-46b7-96b0-f8bf4aad2127.png)

-sprawdzenie działania strony na porcie 6666.

![witaj](https://user-images.githubusercontent.com/94804536/145884732-65549ff2-bf98-4c77-a03f-94c99c72f676.png)

-wygenerowanie reprezentacji graficznej poleceniem: docker container run --rm -it --name mgraph -v $(pwd):/input pmsipilot/docker-compose-viz render -m image docker-compose.yml

![docker-compose](https://user-images.githubusercontent.com/94804536/145884829-f84e377a-110f-4485-b72d-a2618f1631b8.png)
