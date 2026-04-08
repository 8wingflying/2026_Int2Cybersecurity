# LOW
```php
<?php

if( isset( $_POST[ 'Submit' ]  ) ) {
    // Get input
    $target = $_REQUEST[ 'ip' ];

    // Determine OS and execute the ping command.
    if( stristr( php_uname( 's' ), 'Windows NT' ) ) {
        // Windows
        $cmd = shell_exec( 'ping  ' . $target );
    }
    else {
        // *nix
        $cmd = shell_exec( 'ping  -c 4 ' . $target );
    }

    // Feedback for the end user
    echo "<pre>{$cmd}</pre>";
}

?> 
```
```
172.17.0.1 - - [08/Apr/2026:03:45:59 +0000] "GET /vulnerabilities/view_source.php?id=exec&security=low HTTP/1.1" 200 1362 "http://127.0.0.1:8888/vulnerabilities/exec/" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
172.17.0.1 - - [08/Apr/2026:03:45:59 +0000] "GET /dvwa/css/source.css HTTP/1.1" 200 500 "http://127.0.0.1:8888/vulnerabilities/view_source.php?id=exec&security=low" "Mozilla/5.0 (X11; Linux x86_64; rv:60.0) Gecko/20100101 Firefox/60.0"
```
