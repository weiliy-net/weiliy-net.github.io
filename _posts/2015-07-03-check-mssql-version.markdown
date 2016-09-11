---
author: wiadmin
comments: true
date: 2015-07-03 13:08:28+00:00
layout: post
slug: check-mssql-version
title: 通过T-SQL查询MSSQL数据库软件的版本信息
categories:
- MSSQL
tags:
- MSSQL
- T-SQL
---

在更新完数据库的补丁之后，通常需要核对下更新后的版本号来确认已经完成了更新。通常在管理器的Help -> About 里面可以找到。但对于很多批量来说，使用命令来查询会更方便。


##### 执行
    
    select serverproperty ('productversion') as "Version",
        serverproperty('productlevel' ) as "Service Pack",
        serverproperty('edition' ) as "Edition"

##### 结果示例

![result of mssql version](https://res.cloudinary.com/lpmqxk4nr/image/upload/v1473576497/8E6912D0-2F3C-47B3-A393-F55618E1308C_mqaqdx.png)

###### 参考
	
  1. [SERVERPROPERTY (Transact-SQL)](https://technet.microsoft.com/zh-cn/library/ms174396(v=sql.110).aspx)
