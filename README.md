Русскоязычное описание ниже (Russian below).

English description
===================
Reverse-proxy server to handle https-requests transparent. By default `lets-proxy` handles
https requests to port 443 and proxies them as http to port 80 with same IP. It adds http header: X-Real-IP with ip address
of remote client and X-Forwarded-Proto=https - for https detection. It obtain valid certificates from lets encrypt and
handle https free, automated and without warning in browsers.

It has tcp mode, that doesn't parse traffic and proxy it as usual tcp-connection without modify.

The program created for shared hosting and can handle many thouthands domain per server.
From other side - it simple and doesn't need settings to start program on personal server/vps.

Quick start:

    ./lets-proxy or lets-proxy.exe
    
Install for autostart (daemon for linux or windows-service for linux)
    
    ./lets-proxy --service-name=lets-proxy --service-action=install
    lets-proxy.exe --service-name=lets-proxy --service-action=install
    

Remove from autostart

    ./lets-proxy --service-name=lets-proxy --service-action=uninstall
    lets-proxy.exe --service-name=lets-proxy --service-action=uninstall

Use --help key for details:

    ./lets-proxy --help or lets-proxy.exe --help


Русский (Russian):
==================

Реверс-прокси сервер для прозрачной обработки https-запросов. Для начала использования достаточно просто запустить его на сервере с 
запущенным http-сервером. При этом lets-proxy начнёт слушать порт 433 и передавать запросы на порт 80 с тем же IP-адресом.
К запросу будут добавляться заголовки X-Real-IP с IP-адресом источника запроса и X-Forwarded-Proto=https - для определения
что запрос пришел по https. Сертификаты для работы https получаются в реальном времени от letsencrypt.org. Это правильные
(не самоподписанные) бесплатные сертификаты, которым браузеры доверяют.

Есть режим tcp-прокси, в этом случае входящий трафик никак не анализируется и не меняется, а просто передается на указанный порт, но
уже в расшифрованном виде.

Программа разрабатывается для использования на виртуальном хостинге и может работать с тысячами доменов на каждом сервере.
С другой стороны она проста и не требует начальных настроек для запуска на персональном сервере.

Быстрый старт:

    ./lets-proxy или lets-proxy.exe

Установить в автозапуск (домен в linux, служба в windows)
    
    ./lets-proxy --service-name=lets-proxy --service-action=install
    lets-proxy.exe --service-name=lets-proxy --service-action=install
    

Удалить из автозапуска

    ./lets-proxy --service-name=lets-proxy --service-action=uninstall
    lets-proxy.exe --service-name=lets-proxy --service-action=uninstall

Для получения подробной справки воспользуйтесь --help:

    ./lets-proxy --help or lets-proxy.exe --help


Used libraries (alphabet ordered):
==================================

* http://github.com/hashicorp/golang-lru - memory cache
* http://github.com/hlandau/acme/acmeapi - used for work with lets encrypt
* http://github.com/kardianos/service - working as service, especially for windows.
* http://github.com/miekg/dns - direct dns requests, IDN decode
* http://github.com/sevlyar/go-daemon - unix daemonize
* http://github.com/Sirupsen/logrus - logging
* http://gopkg.in/natefinch/lumberjack.v2 - log rotate
