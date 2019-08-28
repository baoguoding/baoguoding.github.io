---
layout: post
title: Sphinx Coreseek
pid: 107
tags: [sphinx]
---


直接上配置吧

D:\Software\coreseek-4.1-win32\etc\csft_mysql.conf

	#MySQL数据源配置，详情请查看：http://www.coreseek.cn/products-install/mysql/
	#请先将var/test/documents.sql导入数据库，并配置好以下的MySQL用户密码数据库

	#源定义
	source question
	{
	    type                    = mysql

	    sql_host                = localhost
	    sql_user                = root
	    sql_pass                = root
	    sql_db                    = segment
	    sql_port                = 3306
	    sql_query_pre            = SET NAMES utf8
	    sql_query_pre       = SET SESSION query_cache_type=OFF #禁用查询缓冲，提高查询速度  

	    sql_query                = SELECT qid, typename, title, nicheng, finished FROM question
								      #sql_query第一列id需为整数
								      #title、content作为字符串/文本字段，被全文索引
	    #sql_attr_uint            = qid           #从SQL读取到的值必须为整数


	    sql_query_info_pre      = SET NAMES utf8                                        #命令行查询时，设置正确的字符集
	    sql_query_info            = SELECT * FROM question WHERE qid=$id #命令行查询时，从数据库读取原始数据信息
	}

	#index定义
	index question
	{
	    source            = question             #对应的source名称
	    path            = D:/Software/coreseek-4.1-win32/var/data/question/ #请修改为实际使用的绝对路径，例如：/usr/local/coreseek/var/...
	    docinfo            = extern
	    mlock            = 0
	    morphology        = none
	    min_word_len        = 1
	    html_strip                = 0

	    #中文分词配置，详情请查看：http://www.coreseek.cn/products-install/coreseek_mmseg/
	    #charset_dictpath = /usr/local/mmseg3/etc/ #BSD、Linux环境下设置，/符号结尾
	    charset_dictpath = D:/Software/coreseek-4.1-win32/etc/                             #Windows环境下设置，/符号结尾，最好给出绝对路径，例如：C:/usr/local/coreseek/etc/...
	    charset_type        = zh_cn.utf-8
	}

	#全局index定义
	indexer
	{
	    mem_limit            = 128M
	}

	#searchd服务定义
	searchd
	{
	    listen                  =   9312
	    read_timeout        = 5
	    max_children        = 30
	    max_matches            = 1000
	    seamless_rotate        = 0
	    preopen_indexes        = 0
	    unlink_old            = 1
	    pid_file = D:/Software/coreseek-4.1-win32/var/log/searchd_mysql.pid  #请修改为实际使用的绝对路径，例如：/usr/local/coreseek/var/...
	    log = D:/Software/coreseek-4.1-win32/var/log/searchd_mysql.log        #请修改为实际使用的绝对路径，例如：/usr/local/coreseek/var/...
	    query_log = D:/Software/coreseek-4.1-win32/var/log/query_mysql.log #请修改为实际使用的绝对路径，例如：/usr/local/coreseek/var/...
	    binlog_path =                                #关闭binlog日志
	}


# 跑的命令

	cd D:\Software\coreseek-4.1-win32\
	bin\indexer -c etc\csft_mysql.conf --all  #生成全部索引  
	OR
	bin\indexer -c etc\csft_mysql.conf question #只生成question索引  
