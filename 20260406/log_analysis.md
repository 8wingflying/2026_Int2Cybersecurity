
## access.log
```
root@fa2230a50882:/var/log/apache2# cat access.log 
172.17.0.1 - - [08/Apr/2026:03:36:17 +0000] "GET / HTTP/1.1" 302 479 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:36:17 +0000] "GET /login.php HTTP/1.1" 200 1049 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:36:17 +0000] "GET /dvwa/css/login.css HTTP/1.1" 200 741 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:36:17 +0000] "GET /dvwa/images/login_logo.png HTTP/1.1" 304 182 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:36:17 +0000] "GET /favicon.ico HTTP/1.1" 304 180 "-" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "POST /login.php HTTP/1.1" 302 337 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /setup.php HTTP/1.1" 200 2034 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /dvwa/css/main.css HTTP/1.1" 200 1446 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /dvwa/js/dvwaPage.js HTTP/1.1" 200 815 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /dvwa/js/add_event_listeners.js HTTP/1.1" 200 625 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /dvwa/images/logo.png HTTP/1.1" 304 181 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:37:17 +0000] "GET /dvwa/images/spanner.png HTTP/1.1" 304 181 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:38:07 +0000] "POST /setup.php HTTP/1.1" 302 338 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:38:07 +0000] "GET /setup.php HTTP/1.1" 200 2170 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:38:12 +0000] "GET /login.php HTTP/1.1" 200 1048 "http://127.0.0.1:8888/setup.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:38:32 +0000] "POST /login.php HTTP/1.1" 302 337 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:38:32 +0000] "GET /index.php HTTP/1.1" 200 3037 "http://127.0.0.1:8888/login.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:41:21 +0000] "GET /security.php HTTP/1.1" 200 2457 "http://127.0.0.1:8888/index.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:41:21 +0000] "GET /dvwa/images/lock.png HTTP/1.1" 304 181 "http://127.0.0.1:8888/security.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:41:45 +0000] "POST /security.php HTTP/1.1" 302 425 "http://127.0.0.1:8888/security.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:41:45 +0000] "GET /security.php HTTP/1.1" 200 2470 "http://127.0.0.1:8888/security.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:41:56 +0000] "GET /vulnerabilities/exec/ HTTP/1.1" 200 1716 "http://127.0.0.1:8888/security.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:42:20 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1921 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:44:03 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1933 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:44:42 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 2431 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:45:09 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1919 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:45:36 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1945 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:45:59 +0000] "GET /vulnerabilities/view_source.php?id=exec&security=low HTTP/1.1" 200 1362 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:45:59 +0000] "GET /dvwa/css/source.css HTTP/1.1" 200 500 "http://127.0.0.1:8888/vulnerabilities/view_source.php?id=exec&security=low" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:51:57 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1921 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:52:52 +0000] "GET /security.php HTTP/1.1" 200 2454 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:53:32 +0000] "GET /vulnerabilities/exec/ HTTP/1.1" 200 1716 "http://127.0.0.1:8888/security.php" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:54:44 +0000] "POST /vulnerabilities/exec/ HTTP/1.1" 200 1929 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"

```
## error log
```
root@fa2230a50882:/var/log/apache2# cat error.log 
[Wed Apr 08 03:35:17.146683 2026] [mpm_prefork:notice] [pid 303] AH00163: Apache/2.4.25 (Debian) configured -- resuming normal operations
[Wed Apr 08 03:35:17.146724 2026] [core:notice] [pid 303] AH00094: Command line: '/usr/sbin/apache2'
[Wed Apr 08 03:38:07.369995 2026] [:error] [pid 316] [client 172.17.0.1:41668] PHP Notice:  Constant DVWA_WEB_PAGE_TO_ROOT already defined in /var/www/html/dvwa/includes/DBMS/MySQL.php on line 9, referer: http://127.0.0.1:8888/setup.php
cat: /etc/shadow: Permission denied
ping: unknown host
```
