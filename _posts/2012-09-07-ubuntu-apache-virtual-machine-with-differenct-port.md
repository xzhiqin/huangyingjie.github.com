---
layout: post
title: "ubuntu apache virtual machine with differenct port"
description: ""
category: 
tags: []
---
基本配置
---
    Listen 8000 #监听8000端口
    <VirtualHost *:8000>#监听8000端口
        ServerAdmin webmaster@localhost
        ServerName localhost #url

        DocumentRoot /home/huangyingjie/code/huangyingjie/seajs #根目录
        
        <Directory />
            Options FollowSymLinks
            AllowOverride All 
        </Directory>
        <Directory /home/huangyingjie/code/huangyingjie/seajs>#根目录
            Options -Indexes FollowSymLinks MultiViews
            AllowOverride All 
            Order allow,deny
            allow from all
        </Directory>

        
        ErrorLog ${APACHE_LOG_DIR}/error.log

        # Possible values include: debug, info, notice, warn, error, crit,
        # alert, emerg.
        LogLevel warn

        CustomLog ${APACHE_LOG_DIR}/access.log combined

    </VirtualHost>
{% include JB/setup %}
