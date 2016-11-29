---
layout: post
title: Oracle 常用脚本
pid: 124
tags: [oracle]
---

# udpate varchar2 to clob
alter table [TABLE_NAME] add temp varchar2(4000);
update [TABLE_NAME] set temp = [VARCHAR2_NAME];
update [TABLE_NAME] set [VARCHAR2_NAME] = null;
commit;

alter table [TABLE_NAME] modify [VARCHAR2_NAME] long;
alter table [TABLE_NAME] modify [VARCHAR2_NAME] clob;
update [TABLE_NAME] set [VARCHAR2_NAME] = temp;
alter table [TABLE_NAME] drop column temp;
commit;

//----某些情况下，是需要对已有索引更新
alter index [INDEX_NAME] rebuild;
