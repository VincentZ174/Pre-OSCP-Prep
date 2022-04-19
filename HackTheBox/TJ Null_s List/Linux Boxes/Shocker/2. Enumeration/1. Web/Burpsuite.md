## Burpsuite
Request
```
GET /cgi-bin/user.sh HTTP/1.1
Host: 10.10.10.56
User-Agent: 
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

Response

```
HTTP/1.1 200 OK
Date: Tue, 19 Apr 2022 02:11:59 GMT
Server: Apache/2.4.18 (Ubuntu)
Connection: close
Content-Type: text/x-sh
Content-Length: 119

Content-Type: text/plain

Just an uptime test script

 22:11:59 up 14 min,  0 users,  load average: 0.00, 0.00, 0.00
```




