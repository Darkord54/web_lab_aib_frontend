# Лабораторная работа №1

## Ргупс  

Скрипт с помощью которого получил информацию о РГУПС -  __[‍РГУПС](https://www.rgups.ru)__:  `curl rgups.ru -I -v -L -k`  

### При выполнение лабораторной работы использовал такие ключи как:  

```
`-k` - Этот ключ отключает проверку SSL-сертификата.
`-v` - Этот ключ делает подробный вывод информации о запросе.  
`-I` - Этот ключ указывает отправить только заголовки HTTP-ответа сервера, без тела ответа.  
`-L` - Этот ключ указывает следовать перенаправлениям при запросе, если сервер возвращает код (301 или 302).
`-User-agent "Yandex"` -  Это строка, которую клиент  отправляет на сервер, чтобы указать серверу, какое программное обеспечение или устройство отправляет запрос, в данном случае "Yandex".  
```

После введении команды вывело следующее:  
* * *
```shell
Host: rgups.ru - хост сайта
User-Agent: curl/7.87.0
Accept: */*
* Mark bundle as not supporting multiuse
< HTTP/1.1 301 Moved Permanently - протокол и ответ сервера
< Server: nginx/1.19.1
< Date: Tue, 12 Sep 2023 22:34:53 GMT
< Content-Type: text/html - тип содержимого
< Content-Length: 169
< Connection: keep-alive
< Location: https://rgups.ru/
<
0   169    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0HTTP/1.1 301 Moved Permanently
Server: nginx/1.19.1
Date: Tue, 12 Sep 2023 21:34:53 GMT
Content-Type: text/html
Content-Length: 169
Connection: keep-alive
Location: https://rgups.ru/
```
* * *
Получаем следующую информацию:
+  Ip: ``80.72.224.90``
+  Port: ``80``
+  Host: ``rgups.ru``
+  Cache-Control: ``-``
+  Content-Type: ``text/html``
+  Response code: ``301 - the page has been permanently moved to a different address``
+  Protocol: ``HTTP/1.1``
* * *
  ### GitHub

Скрипт с помощью которого получил информацию о ГитХабе  __[GitHub](https://github.com/)__:  `curl github.com -I -v -L -k`
* * *
После введении команды вывело следующее:  

```shell
> HEAD / HTTP/1.1
> Host: github.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: GitHub.com
< Date: Tue, 12 Sep 2023 22:35:34 GMT
< Content-Type: text/html; charset=utf-8
< Vary: X-PJAX, X-PJAX-Container, Turbo-Visit, Turbo-Frame, Accept-Language, Accept-Encoding, Accept, X-Requested-With -
< content-language: en-US 
< ETag: W/"aa79b40beb07f510ff7a2bb5f2081380" 
< Cache-Control: max-age=0, private, must-revalidate
< Strict-Transport-Security: max-age=31536000; includeSubdomains; preload 
< X-Frame-Options: deny 
< X-Content-Type-Options: nosniff 
< X-XSS-Protection: 0
< Referrer-Policy: origin-when-cross-origin, strict-origin-when-cross-origin
< Set-Cookie: logged_in=no; Path=/; Domain=github.com; Expires=Wed, 12 Sep 2023 22:35:42 GMT; HttpOnly; Secure; SameSite=Lax 
< Accept-Ranges: bytes 
< X-GitHub-Request-Id: 2E8B:15B8:5BC1C76:5D0480A:64FF2779 
```
* * *
Получаем следующую информацию:
+ Ip: ``140.82.121.4``
+ Port: ``443``
+ Host: ``github.com``
+ Cache-Control: ``max-age=0, private, must-revalidate``
+ Content-Type: ``text/html; charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.3``
* * *
### РЖД
Скрипт с помощью которого получил информацию о РЖД  __[РЖД](https://www.rzd.ru/)__: `curl rzd.ru -I -v -L -k --User-agent "Yandex"`
* * *
После введении команды вывело следующее:  

```shell
> HEAD / HTTP/1.1
> Host: www.rzd.ru
> User-Agent: Yandex
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Type: text/html;charset=utf-8
< Content-Length: 210102 -  Этот заголовок указывает на длину (размер) содержимого ответа в байтах (210102 байта).
< Connection: keep-alive
< Date: Tue, 12 Sep 2023 22:37:41 GMT
< Vary: Accept-Encoding
< X-UCM-Pod-Name: inex-ucm-776d97f9d-4mqxf - Этот заголовок связан с идентификацией серверного подключения.
< Strict-Transport-Security: max-age=15724800; includeSubDomains
< Via: nginx3 - Этот заголовок указывает на прокси-сервер, через который прошел запрос.
< X-Frame-Options: sameorigin
< Set-Cookie: session-cookie=1783e109d75ab07a7230195f18991a243b5b5e67db63b1a4c0cd0129b3473d2627ead013828923624e868b9cc3b51475; Max-Age=86400; Path=/; secure
< X-XSS-Protection: 1; mode=block - Этот заголовок говорит браузеру о включенной защите от XSS и указывает ему блокировать скрипты, 
которые могут представлять угрозу безопасности. 
```
* * *
Получаем следующую информацию:
+ Ip: ``212.164.138.126``
+ Port: ``443``
+ Host: ``www.rzd.ru``
+ Cache-Control: ``-``
+ Content-Type: ``text/html;charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.2``
* * *
### Yandex

Скрипт с помощью которого получил информацию о Яндексе  __[Яндекс](https://yandex.ru/)__:  `curl yandex.ru -I -v -L -k`
* * *
После введении команды вывело следующее:  

```shell
> HEAD /?yredirect=true HTTP/1.1 - Этот запрос будет направлен на сервер с указанием пути / и параметра запроса yredirect=true, и сервер должен ответить только заголовками ресурса, без передачи фактического содержимого.
> Host: dzen.ru
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 Ok
< Cache-Control: no-cache, no-store, max-age=0, must-revalidate
< Content-Type: text/html; charset=utf-8
< Set-Cookie: _yasc=lEL1OdfoCCl7jklQgIf8S+Optkf45jvhWHzi3fU4FfbSajUWSDPA9wu8Y7Vyrzr74Q==; domain=.dzen.ru; path=/; expires=Thu, 08 Sep 2033 15:33:37 GMT; secure
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< X-Requestid: 379459519.223.1694446417520.59980 -  Этот заголовок содержит идентификатор запроса, который может быть полезен для отслеживания запроса на стороне сервера.
< X-XSS-Protection: 1; mode=block
< X-Yandex-Req-Id: 1694446417486451-151878967925589959100109-production-app-host-sas-zen-518 - Заголовок представляет собой уникальный идентификатор запроса, который полезен для отслеживания запроса на стороне сервера Yandex или системы, которая обрабатывает запросы.
```
* * *
Получаем следующую информацию:
+ Ip: ``77.88.55.60``
+ Port: ``443``
+ Host: ``yandex.ru``
+ Cache-Control: ``max-age=1209600,private``
+ Content-Type: ``nosniff``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.3``
### Python
* * *
Скрипт с помощью которого получил информацию о Питоне  __[Python](https://www.python.org/)__:  `curl python.org -I -v -L -k`
* * *
После введении команды вывело следующее:  

```shell
> HEAD / HTTP/1.1
> Host: www.python.org
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Connection: keep-alive
< Content-Length: 50434
< Server: nginx
< Content-Type: text/html; charset=utf-8
< X-Frame-Options: SAMEORIGIN
< Via: 1.1 vegur, 1.1 varnish, 1.1 varnish
< Accept-Ranges: bytes
< Date: Tue, 12 Sep 2023 22:38:44 GMT
< Age: 2224 - Этот заголовок указывает на время в секундах, прошедшее с момента кэширования ответа на сервере или прокси.
< X-Served-By: cache-iad-kiad7000025-IAD, cache-bma1622-BMA - Этот заголовок указывает на серверы и прокси, которые обслуживали запрос.
< X-Cache: HIT, HIT - Этот заголовок указывает, что ответ был получен из кэша как минимум дважды.
< X-Cache-Hits: 2, 7 - Этот заголовок указывает на количество "попаданий" в кэш для данного запроса
< X-Timer: S1694448225.673560,VS0,VE0 - Этот заголовок содержит информацию о времени, затраченном на обработку запроса на сервере.
< Vary: Cookie
< Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```
* * *
Получаем следующую информацию:
+ Ip: ``146.75.116.223``
+ Port: ``443``
+ Host: ``www.python.org``
+ Cache-Control: ``-``
+ Content-Type: ``text/html; charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.3``
* * *
### Git

Скрипт с помощью которого получил информацию о Гите  __[Git](https://git-scm.com/)__:  `curl git-scm.com -I -v -L -k`
* * *
После введении команды вывело следующее: 

```shell
> HEAD / HTTP/1.1
> Host: git-scm.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Date: Tue, 12 Sep 2023 22:39:13 GMT
< Content-Type: text/html; charset=utf-8
< Connection: keep-alive
< X-Frame-Options: SAMEORIGIN
< X-Xss-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Download-Options: noopen - Этот заголовок указывает, что файлы не должны открываться автоматически после загрузки.
< X-Permitted-Cross-Domain-Policies: none - Этот заголовок указывает, что политики, связанные с кросс-доменными запросами, отсутствуют.
< Referrer-Policy: strict-origin-when-cross-origin
< Cache-Control: public, max-age=14400
< Etag: W/"db69273d9410cbf4536e9d4b3a59685d"
< X-Request-Id: 08e865a2-bae1-4a5d-90cb-b387a1e71555
< X-Runtime: 0.012125 - Этот заголовок указывает на время, затраченное на выполнение запроса на стороне сервера
< Via: 1.1 vegur
< CF-Cache-Status: HIT
< Age: 5122
< Server: cloudflare
< CF-RAY: 805130f80da00e89-AMS - Этот заголовок может содержать информацию о запросе и обработке на стороне Cloudflare.
```
* * *
Получаем следующую информацию:
+ Ip: ``188.114.98.224``
+ Port: ``443``
+ Host: ``git-scm.com``
+ Cache-Control: ``public, max-age=14400``
+ Content-Type: ``text/html; charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.3``
* * *
### JetBrains

Скрипт с помощью которого получил информацию о ДжетБреинс  __[JetBrains](https://www.jetbrains.com/)__:  `curl jetbrains.com -I -v -L -k`
* * *
После введении команды вывело следующее: 

```shell
> HEAD / HTTP/1.1
> Host: www.jetbrains.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Type: text/html; charset=utf-8
< Content-Length: 47113
< Connection: keep-alive
< Date: Tue, 12 Sep 2023 22:40:01 GMT
< Server: nginx
< X-Content-Type-Options: nosniff
< Referrer-Policy: same-origin
< Expires: Mon, 11 Sep 2023 16:23:58 GMT - Этот заголовок указывает на дату и время истечения срока действия ответа в кэше.
< Cache-Control: max-age=0
< Pragma: no-cache
< X-Frame-Options: DENY
< X-Content-Type-Options: nosniff
< X-Xss-Protection: 1; mode=block
< Strict-Transport-Security: max-age=31536000;
< Vary: Accept-Encoding
< Via: 1.1 c26999728b9b80253ea8308df470deba.cloudfront.net (CloudFront)
< Age: 167
< Set-Cookie: cf_country-region=RU-MOW; Domain=jetbrains.com; Path=/; Secure
< X-Cache: Hit from cloudfront
< X-Amz-Cf-Pop: ARN56-P2 - Этот заголовок содержит информацию о Point of Presence CloudFront, через который прошел запрос.
< X-Amz-Cf-Id: nzXFCf6XZGkdhF33CihLxVYacKmATuF9KgLJfqJNR609Qxa5-ux39A== - Этот заголовок может содержать идентификатор запроса и обработки на стороне CloudFront.
```
* * *
Получаем следующую информацию:
+ Ip: ``13.33.243.7``
+ Port: ``443``
+ Host: ``www.jetbrains.com``
+ Cache-Control: ``max-age=0``
+ Content-Type: ``text/html; charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ se SSL: ``TLSv1.3``
* * *
### VSC

Скрипт с помощью которого получил информацию о VSC  __[VSC](https://code.visualstudio.com/)__: `curl code.visualstudio.com -I -v -L -k`
* * *
После введении команды вывело следующее: 

```shell
> HEAD / HTTP/1.1
> Host: code.visualstudio.com
> User-Agent: curl/8.0.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Length: 50213
< Content-Type: text/html; charset=utf-8
< Accept-Ranges: bytes
< ETag: W/"c425-XBxswsHoV0dlJCAKuBbwZ9s5rjQ"
< Strict-Transport-Security: max-age=31536000; includeSubDomains
< Content-Security-Policy: frame-ancestors 'self' -  Этот заголовок определяет политику безопасности контента и разрешает встраивание ресурсов только с текущего домена.
< X-Frame-Options: SAMEORIGIN
< X-XSS-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Powered-By: ASP.NET
< x-azure-ref: 0MUH/ZAAAAAASb7vV5T3+TLJL4hpnRGDlQU1TMDRFREdFMTkyMgBiZTg3ZGM2ZC00MGY5LTQ1YjAtODgxMC05OTEwODdlZjhiMjk=
< X-Cache: CONFIG_NOCACHE
< Date: Tue, 12 Sep 2023 22:41:52 GMT
```
* * *
Получаем следующую информацию:
+ Ip: ``13.107.246.45``
+ Port: ``443``
+ Host: ``code.visualstudio.com``
+ Cache-Control: ``CONFIG_NOCACHE``
+ Content-Type: ``text/html; charset=utf-8``
+ Response code: ``200 - OK. The client's request was completed successfully.``
+ Protocol: ``HTTP/1.1``
+ Use SSL: ``TLSv1.2``

##Конец лабораторной работы
