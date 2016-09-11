---
author: wiadmin
comments: true
date: 2015-07-03 12:49:53+00:00
layout: post
slug: configure-mssql-recovery-mode
title: 设置和查询MSSQL数据库的recovery mode ( 使用T-SQL设置）
categories:
- MSSQL
tags:
- MSSQL
---

今天在做MSSQL的设置的检查，其中有一项是检查数据库 recovery model 是否为 Full Recovery Model。常规只需要登录客户端之后，在数据库属性中Option里面就可以设置了。

![MSSQL-Database-Preperties-Options](https://res.cloudinary.com/lpmqxk4nr/image/upload/v1473576497/1E9C1673-DEF7-4776-A945-A3B6B2C0E0D2_iraxku.png)

但是为了自动化这些琐碎的检查，使用命令是必要的。

#### 设置recovery model 为Full

    USE [master]
    GO
    ALTER DATABASE [RSA] SET RECOVERY FULL WITH NO_WAIT
    GO


#### 检查所有数据库的recovery model 的配置


    select name, recovery_model_desc from sys.databases

[![Verify database recovery mode](https://res.cloudinary.com/lpmqxk4nr/image/upload/v1473576497/E70ADE92-0E7E-4ACB-A34C-435CECC28523_jektgx.png)

###### 参考
	
1. [sys.databases (Transact-SQL)](http://www.weiliy.net/2015/07/03/configure-mssql-recovery-mode/)
