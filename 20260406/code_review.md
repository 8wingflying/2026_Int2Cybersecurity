### /var/www/html/vulnerabilities
```
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 brute
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 captcha
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 csp
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 csrf
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 exec
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 fi
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 javascript
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 sqli
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 sqli_blind
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 upload
-rw-r--r-- 1 www-data www-data  632 Oct 12  2018 view_help.php
-rw-r--r-- 1 www-data www-data 2294 Oct 12  2018 view_source.php
-rw-r--r-- 1 www-data www-data 2728 Oct 12  2018 view_source_all.php
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 weak_id
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 xss_d
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 xss_r
drwxr-xr-x 1 www-data www-data 4096 Oct 12  2018 xss_s
```
##
```
root@fa2230a50882:/var/www/html/vulnerabilities/exec# cat index.php
<?php

define( 'DVWA_WEB_PAGE_TO_ROOT', '../../' );
require_once DVWA_WEB_PAGE_TO_ROOT . 'dvwa/includes/dvwaPage.inc.php';

dvwaPageStartup( array( 'authenticated', 'phpids' ) );

$page = dvwaPageNewGrab();
$page[ 'title' ]   = 'Vulnerability: Command Injection' . $page[ 'title_separator' ].$page[ 'title' ];
$page[ 'page_id' ] = 'exec';
$page[ 'help_button' ]   = 'exec';
$page[ 'source_button' ] = 'exec';

dvwaDatabaseConnect();

$vulnerabilityFile = '';
switch( $_COOKIE[ 'security' ] ) {
	case 'low':
		$vulnerabilityFile = 'low.php';
		break;
	case 'medium':
		$vulnerabilityFile = 'medium.php';
		break;
	case 'high':
		$vulnerabilityFile = 'high.php';
		break;
	default:
		$vulnerabilityFile = 'impossible.php';
		break;
}

require_once DVWA_WEB_PAGE_TO_ROOT . "vulnerabilities/exec/source/{$vulnerabilityFile}";

$page[ 'body' ] .= "
<div class=\"body_padded\">
	<h1>Vulnerability: Command Injection</h1>

	<div class=\"vulnerable_code_area\">
		<h2>Ping a device</h2>

		<form name=\"ping\" action=\"#\" method=\"post\">
			<p>
				Enter an IP address:
				<input type=\"text\" name=\"ip\" size=\"30\">
				<input type=\"submit\" name=\"Submit\" value=\"Submit\">
			</p>\n";

if( $vulnerabilityFile == 'impossible.php' )
	$page[ 'body' ] .= "			" . tokenField();

$page[ 'body' ] .= "
		</form>
		{$html}
	</div>

	<h2>More Information</h2>
	<ul>
		<li>" . dvwaExternalLinkUrlGet( 'http://www.scribd.com/doc/2530476/Php-Endangers-Remote-Code-Execution' ) . "</li>
		<li>" . dvwaExternalLinkUrlGet( 'http://www.ss64.com/bash/' ) . "</li>
		<li>" . dvwaExternalLinkUrlGet( 'http://www.ss64.com/nt/' ) . "</li>
		<li>" . dvwaExternalLinkUrlGet( 'https://www.owasp.org/index.php/Command_Injection' ) . "</li>
	</ul>
</div>\n";

dvwaHtmlEcho( $page );

?>

```
