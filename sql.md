mysql（linux）
  
查看数据库状态:  
  
    systemctl status mysql  


手动启动页面：

    systemctl start mysql  


调用默认用户名密码：

    sudo cat /etc/mysql/debian.cnf  
  

连接服务：

    mysql -u debian-sys-maint -p  
    
登陆：

    sudo mysql -u root -p  

    

SQL


查询数据库列表：

    SHOW DATABASES;


进入数据库：

    USE database_name;  

创建数据库：

    CREATE DATABASE database_name;


查询数据库中的表：

    SHOW TABLES;


