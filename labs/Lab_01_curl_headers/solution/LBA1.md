# ПЕРВАЯ ЛАБА

## Цель работы

Научиться кушать курл и понять как с помощью него посмотреть основную информацию о интернет ресурсе.

### РГУПС

Простой запрос curl будет выдавать нам ответ `301 Moved Permanently`, а нам нужно узнавать Айпи и прочие очень важные для нашей лабораторной вещи. 

*Исходя из этого немного модифицируем строчку запроса добавив следующие флажки:*
* -L `Автоматическое перенаправление, что бы не получать 301 ответ`
* -I `Получать только заголовок, без тела сайта`
* -v `Детализация запроса, что бы выписать необходимую нам информацию`

Таким образом итоговая строчка будет выглядеть так: 
> curl rgups.ru -L -I -v

А ответ будет выглядеть как то так:
```shell
* processing: rgups.ru
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 80.72.224.90:80...
* Connected to rgups.ru (80.72.224.90) port 80
> HEAD / HTTP/1.1
> Host: rgups.ru
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Server: nginx/1.19.1
< Date: Tue, 26 Sep 2023 15:56:25 GMT
< Content-Type: text/html
< Content-Length: 169
< Connection: keep-alive
< Location: https://rgups.ru/
<
  0   169    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host rgups.ru left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://rgups.ru/'
*   Trying 80.72.224.90:443...
* Connected to rgups.ru (80.72.224.90) port 443
* schannel: disabled automatic use of client certificate
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: rgups.ru
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Server: nginx/1.19.1
< Date: Tue, 26 Sep 2023 15:56:26 GMT
< Content-Type: text/html; charset=utf-8
< Connection: keep-alive
< X-Powered-By: ProcessWire CMS
< Set-Cookie: wire=cf1c739321102a5f3d1470f5531aef06; path=/; HttpOnly; SameSite=Lax
< Expires: Thu, 19 Nov 1981 08:52:00 GMT
< Cache-Control: no-store, no-cache, must-revalidate
< Pragma: no-cache
```

*И так, что мы имеем:*
* IP:`80.72.224.90`
* Port: `80`
* Host: `rgups.ru`
* Cache-Control: `no-store, no-cache, must-revalidate`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1`

### GITHUB

Выполняем аналогичный запрос:
> curl github.com -L -I -v

И получаем ~~аналогичный~~ ответ:

```shell
* processing: github.com
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 140.82.121.3:80...
* Connected to github.com (140.82.121.3) port 80
> HEAD / HTTP/1.1
> Host: github.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Content-Length: 0
< Location: https://github.com/
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host github.com left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://github.com/'
*   Trying 140.82.121.3:443...
* Connected to github.com (140.82.121.3) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: github.com
> User-Agent: curl/8.2.1
> Accept: */*
>
* schannel: failed to decrypt data, need more data
< HTTP/1.1 200 OK
< Server: GitHub.com
< Date: Tue, 26 Sep 2023 16:31:56 GMT
< Content-Type: text/html; charset=utf-8
< Vary: X-PJAX, X-PJAX-Container, Turbo-Visit, Turbo-Frame, Accept-Language, Accept-Encoding, Accept, X-Requested-With
< content-language: en-US
< ETag: W/"9fc12640994e0dddfe33a2fb4eb682f3"
< Cache-Control: max-age=0, private, must-revalidate
< Strict-Transport-Security: max-age=31536000; includeSubdomains; preload
< X-Frame-Options: deny
< X-Content-Type-Options: nosniff
< X-XSS-Protection: 0
< Referrer-Policy: origin-when-cross-origin, strict-origin-when-cross-origin
< Content-Security-Policy: default-src 'none'; base-uri 'self'; child-src github.com/assets-cdn/worker/ gist.github.com/assets-cdn/worker/; connect-src 'self' uploads.github.com www.githubstatus.com collector.github.com raw.githubusercontent.com api.githubcopilot.com api.github.com github-cloud.s3.amazonaws.com github-production-repository-file-5c1aeb.s3.amazonaws.com github-production-upload-manifest-file-7fdce7.s3.amazonaws.com github-production-user-asset-6210df.s3.amazonaws.com cdn.optimizely.com logx.optimizely.com/v1/events objects-origin.githubusercontent.com *.actions.githubusercontent.com productionresultssa0.blob.core.windows.net/ productionresultssa1.blob.core.windows.net/ productionresultssa2.blob.core.windows.net/ productionresultssa3.blob.core.windows.net/ productionresultssa4.blob.core.windows.net/ productionresultssa5.blob.core.windows.net/ productionresultssa6.blob.core.windows.net/ productionresultssa7.blob.core.windows.net/ productionresultssa8.blob.core.windows.net/ productionresultssa9.blob.core.windows.net/ wss://*.actions.githubusercontent.com github-production-repository-image-32fea6.s3.amazonaws.com github-production-release-asset-2e65be.s3.amazonaws.com insights.github.com wss://alive.github.com github.githubassets.com; font-src github.githubassets.com; form-action 'self' github.com gist.github.com objects-origin.githubusercontent.com; frame-ancestors 'none'; frame-src viewscreen.githubusercontent.com notebooks.githubusercontent.com support.github.com; img-src 'self' data: github.githubassets.com media.githubusercontent.com camo.githubusercontent.com identicons.github.com avatars.githubusercontent.com github-cloud.s3.amazonaws.com objects.githubusercontent.com secured-user-images.githubusercontent.com/ user-images.githubusercontent.com/ private-user-images.githubusercontent.com opengraph.githubassets.com github-production-user-asset-6210df.s3.amazonaws.com customer-stories-feed.github.com spotlights-feed.github.com objects-origin.githubusercontent.com *.githubusercontent.com; manifest-src 'self'; media-src github.com user-images.githubusercontent.com/ secured-user-images.githubusercontent.com/ private-user-images.githubusercontent.com github.githubassets.com; script-src github.githubassets.com; style-src 'unsafe-inline' github.githubassets.com; upgrade-insecure-requests; worker-src github.com/assets-cdn/worker/ gist.github.com/assets-cdn/worker/
< Set-Cookie: _gh_sess=XqFtlJMG3om7%2BIlBu6YZTOT6fg%2BjF%2BgSVaEuBLOjEO57y0yCmOV4rucTpNIQue7YqgkRWhVrCA2YBLy%2Fo9h2ZGC4Qgb7dHeC9qn%2F9q1WJU4M8bbzHMHkeI1kcSHANnl6gMr5xivQ7cffJY%2BM92aU0DmWRKIVozy3o6R5g%2F43kkVSuNyITj2zmvqRfWHSj6nAtJZm1bzNISzb9KiR66W5gVoWoz18ezgi6ABDUbG5mXJz18ozNv6o2f4z16Yn8QihinyQJVrCWmcWVDK7qoh1MA%3D%3D--nfWrgvmZCqq2o59C--A3GMEZQn9zTQKsA%2FtXqWFQ%3D%3D; Path=/; HttpOnly; Secure; SameSite=Lax
< Set-Cookie: _octo=GH1.1.615289264.1695745919; Path=/; Domain=github.com; Expires=Thu, 26 Sep 2024 16:31:59 GMT; Secure; SameSite=Lax
< Set-Cookie: logged_in=no; Path=/; Domain=github.com; Expires=Thu, 26 Sep 2024 16:31:59 GMT; HttpOnly; Secure; SameSite=Lax
< Accept-Ranges: bytes
< X-GitHub-Request-Id: 2327:62B6:2270C4:22DB81:6513077F
```

*Из этого следует:*
* Ip: ` 140.82.121.4`  
* Port: `443`  
* Host: `github.com`  
* Cache-Control: `max-age=0, private, must-revalidate`  
* Content-Type: `text/html;charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1` 

### РЖД

РЖД не дает ничего знать если попробовать простой curl, поэтому прикинемся Яндексом, отправив следующий запрос:
> curl rzd.ru -L -I -v --User-agent "Yandex"

Получим следующий ответ:

```shell
 0   150    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host rzd.ru left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://rzd.ru:443/'
*   Trying 212.164.138.126:443...
* Connected to rzd.ru (212.164.138.126) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: rzd.ru
> User-Agent: Yandex
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Content-Type: text/html
< Content-Length: 185
< Connection: keep-alive
< Date: Tue, 26 Sep 2023 16:56:44 GMT
< Location: https://www.rzd.ru/
< Set-Cookie: session-cookie=1788814797c7a707637d8d5e18991a24b90b0ada9bc3eca49c6db311bc3d31a9b23936d58998e4639464627a44c94ad6; Max-Age=86400; Path=/; secure; HttpOnly
< X-XSS-Protection: 1; mode=block
<
  0   185    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #1 to host rzd.ru left intact
* Issue another request to this URL: 'https://www.rzd.ru/'
*   Trying 212.164.138.129:443...
* Connected to www.rzd.ru (212.164.138.129) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0> HEAD / HTTP/1.1
> Host: www.rzd.ru
> User-Agent: Yandex
> Accept: */*
>
< HTTP/1.1 200
< Content-Type: text/html;charset=utf-8
< Content-Length: 206815
< Connection: keep-alive
< Date: Tue, 26 Sep 2023 16:56:44 GMT
< Vary: Accept-Encoding
< X-UCM-Pod-Name: inex-ucm-776d97f9d-lpczs
< Strict-Transport-Security: max-age=15724800; includeSubDomains
< Via: nginx3
< X-Frame-Options: sameorigin
< Set-Cookie: session-cookie=17888147a79b7073637d8d5e18991a24d39fafabd52d97a9b17f2def154ab1ca621e05792c9ac18a271f55c517a1f838; Max-Age=86400; Path=/; secure
< X-XSS-Protection: 1; mode=block
```

*Из этого следует:*

* Ip: `212.164.138.130`  
* Port: `443`  
* Host: `rzd.ru`  
* Cache-Control: `?`  
* Content-Type: `text/html;charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1`  

### ЯНДЕКС

Запрос для Яндекса будет иметь вид:
> curl yandex.ru -L -I -v

Ответ будет иметь вид:
```shell
* processing: yandex.ru
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 5.255.255.70:80...
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0* Connected to yandex.ru (5.255.255.70) port 80
> HEAD / HTTP/1.1
> Host: yandex.ru
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 302 Moved temporarily
< Accept-CH: Sec-CH-UA-Platform-Version, Sec-CH-UA-Mobile, Sec-CH-UA-Model, Sec-CH-UA, Sec-CH-UA-Full-Version-List, Sec-CH-UA-WoW64, Sec-CH-UA-Arch, Sec-CH-UA-Bitness, Sec-CH-UA-Platform, Sec-CH-UA-Full-Version, Viewport-Width, DPR, Device-Memory, RTT, Downlink, ECT
< Cache-Control: max-age=1209600,private
< Date: Tue, 26 Sep 2023 17:02:16 GMT
< Location: https://dzen.ru/?yredirect=true
< NEL: {"report_to": "network-errors", "max_age": 100, "success_fraction": 0.001, "failure_fraction": 0.1}
< P3P: policyref="/w3c/p3p.xml", CP="NON DSP ADM DEV PSD IVDo OUR IND STP PHY PRE NAV UNI"
< Portal: Home
< Report-To: { "group": "network-errors", "max_age": 100, "endpoints": [{"url": "https://dr.yandex.net/nel", "priority": 1}, {"url": "https://dr2.yandex.net/nel", "priority": 2}]}
< X-Content-Type-Options: nosniff
< X-Robots-Tag: unavailable_after: 12 Sep 2022 00:00:00 PST
< X-Yandex-Req-Id: 1695747736446121-13200951217914238206-balancer-l7leveler-kubr-yp-vla-75-BAL-156
< set-cookie: is_gdpr=0; Path=/; Domain=.yandex.ru; Expires=Thu, 25 Sep 2025 17:02:16 GMT
< set-cookie: is_gdpr_b=CKDSYBDU0AEoAg==; Path=/; Domain=.yandex.ru; Expires=Thu, 25 Sep 2025 17:02:16 GMT
< set-cookie: _yasc=TvxeTArcdvBEmqgOaaFSymg/iXxaBmq/75clFiGElBHGAgxteJu61GYEcOrjQ5Ni0/Ts; domain=.yandex.ru; path=/; expires=Fri, 23 Sep 2033 17:02:16 GMT; secure
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host yandex.ru left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://dzen.ru/?yredirect=true'
*   Trying 62.217.160.2:443...
* Connected to dzen.ru (62.217.160.2) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD /?yredirect=true HTTP/1.1
> Host: dzen.ru
> User-Agent: curl/8.2.1
> Accept: */*
>
* schannel: failed to decrypt data, need more data
* schannel: failed to decrypt data, need more data
* schannel: failed to decrypt data, need more data
< HTTP/1.1 200 Ok
< Cache-Control: no-cache, no-store, max-age=0, must-revalidate
< Content-Security-Policy-Report-Only: default-src 'none'; connect-src 'self' an.yandex.ru strm.yandex.ru *.strm.yandex.net mc.yandex.ru yandex.st yastatic.net matchid.adfox.yandex.ru adfox.yandex.ru ads.adfox.ru ads6.adfox.ru jstracer.yandex.ru yastat.net yandex.ru awaps.yandex.net awaps.yandex.ru verify.yandex.ru *.verify.yandex.ru favicon.yandex.net pixel.adsafeprotected.com tps.doubleverify.com ad.adriver.ru amc.yandex.ru *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru mc.yandex.az mc.yandex.by mc.yandex.co.il mc.yandex.com mc.yandex.com.am mc.yandex.com.ge mc.yandex.com.tr mc.yandex.ee mc.yandex.fr mc.yandex.kg mc.yandex.kz mc.yandex.lt mc.yandex.lv mc.yandex.md mc.yandex.tj mc.yandex.tm mc.yandex.ua mc.yandex.uz mc.admetrica.ru yandexmetrica.com yandexmetrica.com:29009 yandexmetrica.com:30102 forms-ext-api.yandex.ru strm.yandex.net *.strm.yandex.ru *.cdn.ngenix.net zen-rc3.yandex.ru frontend.vh.yandex.ru https://vh.test.yandex.ru/live/ wss://push.yandex.ru api.passport.yandex.ru api.passport-test.yandex.ru suggest-maps.yandex.ru/suggest-geo vk.ru static.dzeninfra.ru avatars.dzeninfra.ru cdn.dzen.ru video.dzen.ru log.dzen.ru playlog.dzen.ru cdn.dzeninfra.ru *.cdn.dzeninfra.ru *.extcdn.dzeninfra.ru *.hot-video.dzeninfra.ru cold-video.dzeninfra.ru *.cold-video.dzeninfra.ru s3.dzeninfra.ru *.s3.dzeninfra.ru *.ms.dzen.ru notify.dzen.ru clck.dzen.ru static-mon.yandex.net cloud-api.yandex.ru yandex.ru dzen.ru *.adlooxtracking.com *.adlooxtracking.ru *.adsafeprotected.com *.doubleverify.com *.moatads.com *.serving-sys.com *.serving-sys.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net; frame-src awaps.yandex.net yandexadexchange.net *.yandexadexchange.net yastatic.net *.yandex.ru banners.adfox.ru yastat.net yandex.ru storage.mds.yandex.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru blob: mc.yandex.ru mc.yandex.md zenadservices.net sso.passport.yandex.ru id.vk.com *.dzen.ru sso.dzen.ru static.dzeninfra.ru suggest.dzen.ru 'self' yandex.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net *.doubleverify.com *.doubleclick.net; img-src 'self' data: avatars-fast.yandex.net favicon.yandex.net an.yandex.ru banners.adfox.ru content.adfox.ru ads6.adfox.ru tns-counter.ru *.tns-counter.ru s3.mds.yandex.net ads.adfox.ru amc.yandex.ru mc.admetrica.ru wcm-ru.frontend.weborama.fr wcm.solution.weborama.fr ad.adriver.ru bs.serving-sys.com ad.doubleclick.net counter.yadro.ru gdeby.hit.gemius.pl mc.yandex.ru verify.yandex.ru *.verify.yandex.ru yastatic.net yastat.net avatars.mds.yandex.net yandex.ru px.moatads.com awaps.yandex.net awaps.yandex.ru gdero.hit.gemius.pl pixel.adlooxtracking.com tps.doubleverify.com impression.appsflyer.com rgi.io track.rutarget.ru ssl.hurra.com pixel.adsafeprotected.com storage.mds.yandex.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru mc.yandex.az mc.yandex.by mc.yandex.co.il mc.yandex.com mc.yandex.com.am mc.yandex.com.ge mc.yandex.com.tr mc.yandex.ee mc.yandex.fr mc.yandex.kg mc.yandex.kz mc.yandex.lt mc.yandex.lv mc.yandex.md mc.yandex.tj mc.yandex.tm mc.yandex.ua mc.yandex.uz mc.webvisor.org *.mediascope.mc.yandex.ru avatars.mdst.yandex.net zen.s3.yandex.net strm.yandex.ru strm.yandex.net sso.passport.yandex.ru dzen.ru avatars.dzeninfra.ru static.dzeninfra.ru cdn.dzen.ru video.dzen.ru log.dzen.ru playlog.dzen.ru s3.dzeninfra.ru *.ms.dzen.ru *.s3.dzeninfra.ru *.zen.yandex.com *.m-counter.ru www.m-counter.ru www.tns-counter.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net *.doubleverify.com *.adsafeprotected.com *.serving-sys.com *.serving-sys.ru *.weborama.fr *.weborama-tech.ru *.hit.gemius.pl consentmanager.mgr.consensu.org cdn.consentmanager.mgr.consensu.org *.adlooxtracking.com *.adlooxtracking.ru vk.com vk.ru *.userapi.com *.vk.com *.vk.ru; media-src *.yandex.net strm.yandex.ru *.strm.yandex.ru yandex.ru yandex.st yastatic.net banners.adfox.ru content.adfox.ru data: yastat.net *.mycdn.me *.vkuser.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru blob: *.strm.yandex.net *.cdn.ngenix.net cdn.dzen.ru video.dzen.ru *.cdn.dzeninfra.ru *.extcdn.dzeninfra.ru *.hot-video.dzeninfra.ru cold-video.dzeninfra.ru *.cold-video.dzeninfra.ru *.s3.dzeninfra.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net; script-src 'unsafe-inline' 'unsafe-eval' an.yandex.ru yandex.st yastatic.net mc.yandex.ru banners.adfox.ru ads.adfox.ru ads6.adfox.ru yastat.net yandex.ru z.moatads.com storage.mds.yandex.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru mc.yandex.az mc.yandex.by mc.yandex.co.il mc.yandex.com mc.yandex.com.am mc.yandex.com.ge mc.yandex.com.tr mc.yandex.ee mc.yandex.fr mc.yandex.kg mc.yandex.kz mc.yandex.lt mc.yandex.lv mc.yandex.md mc.yandex.tj mc.yandex.tm mc.yandex.ua mc.yandex.uz chat.s3.yandex.net sso.dzen.ru sso.passport.yandex.ru static.dzeninfra.ru 'self' *.zen.yandex.com dzen.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net *.adlooxtracking.com *.adlooxtracking.ru *.adsafeprotected.com *.doubleverify.com *.moatads.com *.dvtps.com *.doubleclick.net *.serving-sys.ru *.userapi.com vk.com vk.ru *.vk.com *.vk.ru; style-src 'unsafe-inline' 'unsafe-eval' yandex.st yastatic.net banners.adfox.ru content.adfox.ru yastat.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru yandex.ru static.dzeninfra.ru 'self' *.zen.yandex.com dzen.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net; font-src 'self' data: an.yandex.ru yastatic.net yastat.net *.tunneler-si.dzen.ru *.tun.si.dzen.ru http-check-headers.yandex.ru static.dzeninfra.ru *.mail.ru *.mradx.net *.imgsmail.ru *.criteo.com *.criteo.net *.mycdn.me *.vkuser.net fonts.gstatic.com; child-src blob: mc.yandex.ru; manifest-src *.dzen.ru/manifest.webmanifest 'self'; report-uri https://csp.yandex.net/csp?from=zen_old&project=zen&yandex_login=&yandexuid=8363690711695747736&requestid=750704388.367232.1695747736980.57969&page=site_desktop;
< Content-Type: text/html; charset=utf-8
< Set-Cookie: _yasc=XXrGWCzSm4J84j3+QbjIZvdYCMdFioN1f+wI9n85SW1WhVHtmO/oXwDB8FZvN3f6; domain=.dzen.ru; path=/; expires=Fri, 23 Sep 2033 17:02:16 GMT; secure
< X-Content-Type-Options: nosniff
< X-Frame-Options: deny
< X-Requestid: 750704388.367232.1695747736980.57969
< X-XSS-Protection: 1; mode=block
< X-Yandex-Req-Id: 1695747736950528-1021854818682043866200117-production-app-host-vla-zen-334
```

*Из этого следует:*
* Ip: `213.180.193.56`  
* Port: `80`  
* Host: `yandex.ru`  
* Cache-Control: `max-age=1209600,private`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `302`  
* Protocol: `HTTP/1.1`

### PYTHON

Запрос для питона будет иметь вид:
> curl python.org -L -I -v

Ответ будет иметь вид:
```shell
* processing: python.org
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 151.101.0.223:80...
* Connected to python.org (151.101.0.223) port 80
> HEAD / HTTP/1.1
> Host: python.org
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Connection: close
< Content-Length: 0
< Server: Varnish
< Retry-After: 0
< Accept-Ranges: bytes
< Date: Tue, 26 Sep 2023 17:05:36 GMT
< Via: 1.1 varnish
< X-Served-By: cache-fra-eddf8230062-FRA
< X-Cache: HIT
< X-Cache-Hits: 0
< X-Timer: S1695747937.882887,VS0,VE0
< Location: https://www.python.org/
< Strict-Transport-Security: max-age=315360000; preload
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Closing connection
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://www.python.org/'
*   Trying 146.75.116.223:443...
* Connected to www.python.org (146.75.116.223) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: www.python.org
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Connection: keep-alive
< Content-Length: 50197
< Server: nginx
< Content-Type: text/html; charset=utf-8
< X-Frame-Options: SAMEORIGIN
< Via: 1.1 vegur, 1.1 varnish, 1.1 varnish
< Accept-Ranges: bytes
< Date: Tue, 26 Sep 2023 17:05:37 GMT
< Age: 156
< X-Served-By: cache-iad-kiad7000025-IAD, cache-fra-eddf8230128-FRA
< X-Cache: HIT, HIT
< X-Cache-Hits: 2, 1
< X-Timer: S1695747937.421552,VS0,VE5
< Vary: Cookie
< Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
```

*Из этого следует:*
* Ip: `146.75.120.223`  
* Port: `443`  
* Host: `www.python.org`  
* Cache-Control: `?`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1`  

### GIT

Запрос для git будет иметь вид:
> curl git-scm.org -L -I -v

Ответ будет иметь вид:
```shell
* processing: git-scm.org
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 188.114.98.229:80...
* Connected to git-scm.org (188.114.98.229) port 80
> HEAD / HTTP/1.1
> Host: git-scm.org
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Date: Tue, 26 Sep 2023 17:08:48 GMT
< Connection: keep-alive
< Cache-Control: max-age=3600
< Expires: Tue, 26 Sep 2023 18:08:48 GMT
< Location: https://git-scm.com/
< Server: cloudflare
< CF-RAY: 80cd1c692d8c5b48-VIE
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host git-scm.org left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://git-scm.com/'
*   Trying 188.114.98.229:443...
* Connected to git-scm.com (188.114.98.229) port 443
* schannel: disabled automatic use of client certificate
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: git-scm.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Date: Tue, 26 Sep 2023 17:08:48 GMT
< Content-Type: text/html; charset=utf-8
< Connection: keep-alive
< X-Frame-Options: SAMEORIGIN
< X-Xss-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Download-Options: noopen
< X-Permitted-Cross-Domain-Policies: none
< Referrer-Policy: strict-origin-when-cross-origin
< Cache-Control: public, max-age=14400
< Etag: W/"db69273d9410cbf4536e9d4b3a59685d"
< X-Request-Id: 03ec24d5-4d96-40db-8b58-76d76dd7d77d
< X-Runtime: 0.011384
< Via: 1.1 vegur
< CF-Cache-Status: HIT
< Age: 8920
< Server: cloudflare
< CF-RAY: 80cd1c6c1a6b5b82-VIE
```

*Из этого следует:*
* Ip: `188.114.99.224`  
* Port: `443`  
* Host: `git-scm.com`  
* Cache-Control: `public, max-age=14400`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1` 

### JETBRAINS

Запрос для git будет иметь вид:
> curl jetbrains.com -L -I -v

Ответ будет иметь вид:
```shell
* processing: jetbrains.com
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 13.33.243.77:80...
* Connected to jetbrains.com (13.33.243.77) port 80
> HEAD / HTTP/1.1
> Host: jetbrains.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 301 Moved Permanently
< Server: CloudFront
< Date: Tue, 26 Sep 2023 17:11:34 GMT
< Content-Type: text/html
< Content-Length: 167
< Connection: keep-alive
< Location: https://jetbrains.com/
< X-Cache: Redirect from cloudfront
< Via: 1.1 75db592bac77e8a29aaf9f30658e363c.cloudfront.net (CloudFront)
< X-Amz-Cf-Pop: HEL50-C1
< Alt-Svc: h3=":443"; ma=86400
< X-Amz-Cf-Id: ElhcHG1BeSImj9nH0UFGWZDmfrEiILJS33DSUiRXNRXoSMcS2A_jKg==
<
  0   167    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host jetbrains.com left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://jetbrains.com/'
*   Trying 13.33.243.77:443...
* Connected to jetbrains.com (13.33.243.77) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0> HEAD / HTTP/1.1
> Host: jetbrains.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 308 Found
< Server: CloudFront
< Date: Tue, 26 Sep 2023 17:11:35 GMT
< Content-Length: 0
< Connection: keep-alive
< Location: https://www.jetbrains.com/
< Strict-Transport-Security: max-age=31536000;
< X-Cache: FunctionGeneratedResponse from cloudfront
< Via: 1.1 4b3b9541fe386ba754a368a9d0694d7a.cloudfront.net (CloudFront)
< X-Amz-Cf-Pop: HEL50-C1
< Alt-Svc: h3=":443"; ma=86400
< X-Amz-Cf-Id: Rr4ZVMF9KArzy4Rtkte_yXrtsD8xo41TYcF3-CYk-0aFvDO26th27A==
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #1 to host jetbrains.com left intact
* Issue another request to this URL: 'https://www.jetbrains.com/'
*   Trying 13.33.243.120:443...
* Connected to www.jetbrains.com (13.33.243.120) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: www.jetbrains.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Content-Type: text/html; charset=utf-8
< Content-Length: 48040
< Connection: keep-alive
< Date: Tue, 26 Sep 2023 17:09:27 GMT
< Server: nginx
< X-Content-Type-Options: nosniff
< Referrer-Policy: same-origin
< Expires: Tue, 26 Sep 2023 17:09:27 GMT
< Cache-Control: max-age=0
< Pragma: no-cache
< X-Frame-Options: DENY
< X-Content-Type-Options: nosniff
< X-Xss-Protection: 1; mode=block
< Strict-Transport-Security: max-age=31536000;
< Vary: Accept-Encoding
< Via: 1.1 dfcd0c19a3793bae8dea2fb7f4deb8e8.cloudfront.net (CloudFront)
< Alt-Svc: h3=":443"; ma=86400
< Age: 128
< Set-Cookie: cf_country-region=RU-ROS; Domain=jetbrains.com; Path=/; Secure
< X-Cache: Hit from cloudfront
< X-Amz-Cf-Pop: HEL50-C1
< X-Amz-Cf-Id: _DSz0lo2JR1vRuEBop4hmsoWD2BRD6rsVHYTEkX_L0YFxEBZJtRGQA==
```

*Из этого следует:*
* Ip: `108.157.229.51`  
* Port: `443`  
* Host: `www.jetbrains.com`  
* Cache-Control: `max-age=0`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1`

### VS CODE

Запрос для VSC будет иметь вид:
> curl code.visualstudio.com -L -I -v

Ответ будет иметь вид:
```shell
* processing: code.visualstudio.com
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 13.107.213.44:80...
* Connected to code.visualstudio.com (13.107.213.44) port 80
> HEAD / HTTP/1.1
> Host: code.visualstudio.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 307 Temporary Redirect
< Date: Tue, 26 Sep 2023 17:14:12 GMT
< Content-Type: text/html
< Content-Length: 0
< Connection: keep-alive
< Location: https://code.visualstudio.com/
< x-azure-ref: 20230926T171412Z-81c9dcrw6t2mbaek8smy45twy400000001kg00000000kbgy
< X-Cache: CONFIG_NOCACHE
<
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
* Connection #0 to host code.visualstudio.com left intact
* Clear auth, redirects to port from 80 to 443
* Issue another request to this URL: 'https://code.visualstudio.com/'
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0*   Trying 13.107.213.44:443...
* Connected to code.visualstudio.com (13.107.213.44) port 443
* schannel: disabled automatic use of client certificate
* using HTTP/1.x
> HEAD / HTTP/1.1
> Host: code.visualstudio.com
> User-Agent: curl/8.2.1
> Accept: */*
>
< HTTP/1.1 200 OK
< Date: Tue, 26 Sep 2023 17:14:12 GMT
< Content-Type: text/html; charset=utf-8
< Content-Length: 50213
< Connection: keep-alive
< ETag: W/"c425-XBxswsHoV0dlJCAKuBbwZ9s5rjQ"
< Strict-Transport-Security: max-age=31536000; includeSubDomains
< Content-Security-Policy: frame-ancestors 'self'
< X-Frame-Options: SAMEORIGIN
< X-XSS-Protection: 1; mode=block
< X-Content-Type-Options: nosniff
< X-Content-Type-Options: nosniff
< X-Powered-By: ASP.NET
< x-azure-ref: 20230926T171412Z-9geayhaak94gx7k1998rctqxdw0000000h50000000018qmk
< X-Cache: CONFIG_NOCACHE
< Accept-Ranges: bytes
```

*Из этого следует:*
* Ip: `13.107.246.45`  
* Port: `443`  
* Host: `code.visualstudio.com`  
* Cache-Control: `?`  
* Content-Type: `text/html; charset=utf-8`  
* Response code: `200 OK`  
* Protocol: `HTTP/1.1`
