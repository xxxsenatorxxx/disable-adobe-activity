@echo off
SETLOCAL ENABLEEXTENSIONS
set HOSTS_FILE=%SystemRoot%\System32\drivers\etc\hosts
set "TAG=# === Block Adobe Activation ==="

echo.
echo [*] Adding Adobe domains to hosts file...

:: Check if the tag already exists
findstr /C:"%TAG%" "%HOSTS_FILE%" >nul
if %errorlevel%==0 (
    echo [!] Adobe block entries already exist in hosts file. Skipping.
    goto END
)

:: Append Adobe block entries
(
    echo.
    echo %TAG%
	echo 127.0.0.1 lcs-cops.adobe.io
	echo 127.0.0.1 cc-api-data.adobe.io
	echo 127.0.0.1 cc-api-storage.adobe.io
	echo 127.0.0.1 genuine.adobe.com
	echo 127.0.0.1 assets.adobe.com
	echo 127.0.0.1 oobesaas.adobe.com
	echo 127.0.0.1 adobeereg.com
	echo 127.0.0.1 wip.adobe.com
	echo 127.0.0.1 wip1.adobe.com
	echo 127.0.0.1 wip2.adobe.com
	echo 127.0.0.1 wip3.adobe.com
	echo 127.0.0.1 wip4.adobe.com
	echo 127.0.0.1 wip5.adobe.com
	echo 127.0.0.1 wip6.adobe.com
	echo 127.0.0.1 wip7.adobe.com
	echo 127.0.0.1 wip8.adobe.com
	echo 127.0.0.1 wip9.adobe.com
	echo 127.0.0.1 hl2rcv.adobe.com
	echo 127.0.0.1 t.adobe.com
	echo 127.0.0.1 id.adobe.com
	echo 127.0.0.1 adobe.io
	echo 127.0.0.1 prod-rel-ffc-ccm.oobesaas.adobe.com
	echo 127.0.0.1 adobe.demdex.net
	echo 127.0.0.1 lmlicenses.wip4.adobe.com 
	echo 127.0.0.1 lm.licenses.adobe.com 
	echo 127.0.0.1 na1r.services.adobe.com 
	echo 127.0.0.1 hlrcv.stage.adobe.com 
	echo 127.0.0.1 practivate.adobe.com 
	echo 127.0.0.1 activate.adobe.com 
	echo 127.0.0.1 lm-prd-da1.licenses.adobe.com 
	echo 127.0.0.1 activate.wip4.adobe.com 
	echo 127.0.0.1 practivate-da1.adobe.com 
	echo 127.0.0.1 uds.licenses.adobe.com 
	echo 127.0.0.1 licenses.adobe.com 
	echo 127.0.0.1 license.adobe.com 
	echo 127.0.0.1 helpexamples.com 
	echo 127.0.0.1 activate-sea.adobe.com 
	echo 127.0.0.1 activate-sjc0.adobe.com 
	echo 127.0.0.1 ereg.adobe.com 
	echo 127.0.0.1 activate.wip3.adobe.com 
	echo 127.0.0.1 ereg.wip3.adobe.com 
	echo 127.0.0.1 wwis-dubc1-vip60.adobe.com 
	echo 127.0.0.1 ims-na1.adobelogin.com
	echo 127.0.0.1 lcs-cops.adobe.io
	echo 127.0.0.1 cc-api-data.adobe.io
	echo 127.0.0.1 cc-api-storage.adobe.io
	echo 127.0.0.1 auth.services.adobe.com
	echo 127.0.0.1 westus-0.in.applicationinsights.azure.com
	echo 127.0.0.1 ic.adobe.io
	echo 127.0.0.1 cc-cdn.adobe.com
	echo 127.0.0.1 web-chat-e2ee.instagram.com
	echo 127.0.0.1 adobeid-na1.services.adobe.com
	echo 127.0.0.1 www.msftncsi.com
	echo 127.0.0.1 adobe.tt.omtrdc.net
	echo 127.0.0.1 d1swly8pgrbhu5.cloudfront.net
	echo 127.0.0.1 signaler-pa.clients6.google.com
	echo 127.0.0.1 o1383653.ingest.sentry.io
	echo 127.0.0.1 assets.adobedtm.com
	echo 127.0.0.1 geo2.adobe.com
	echo 127.0.0.1 fp-afd-nocache-ccp.azureedge.net
	echo 127.0.0.1 2ftem87osk.adobe.io
	echo 127.0.0.1 sstats.adobe.com
	echo 127.0.0.1 gxrwd8hxqi.adobe.io
	echo 127.0.0.1 019n8v7a8f.adobestats.io
	echo 127.0.0.1 use.typekit.net
) >> "%HOSTS_FILE%"

echo [✓] Adobe domains have been added to hosts file.

:: Flush DNS
ipconfig /flushdns >nul
echo [*] DNS cache flushed.

:END
pause
exit
