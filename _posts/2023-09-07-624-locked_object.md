---
layout: post
title: locked_object
pid: 624
tags: [oracle, kali]
---



```
SELECT
    s.USERNAME ,
    s.STATUS ,
    s.SCHEMANAME ,
    s.OSUSER ,
    s.PROCESS ,
    s.MACHINE ,
    s.PROGRAM
FROM
    v$session s
WHERE
    s.STATUS = 'ACTIVE';

SELECT * FROM "V$TRANSACTION" ;

SELECT
    s.username,
    s.status,
    s.OSUSER,
    do.object_name,
    do.object_type,
    s.process,
    s.machine,
    s.PROGRAM,
    lo.PROCESS
FROM
    v$locked_object lo
LEFT JOIN DBA_OBJECTS do ON
    lo.OBJECT_ID = do.OBJECT_ID
LEFT JOIN v$session s ON
    lo.ORACLE_USERNAME = s.USERNAME
    AND lo.OS_USER_NAME = s.OSUSER;

ALTER TABLE <表名> UNLOCK;
```

