mysql（linux）
  
查看数据库状态:  
  
    systemctl status mysql  


手动启动页面：

    systemctl start mysql  


调用默认用户名密码：

    sudo cat /etc/mysql/debian.cnf  

    1oWxqUkYk2GBIEiW  

连接服务：

    mysql -u debian-sys-maint -p  
    
