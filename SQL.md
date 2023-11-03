# mysql（linux）  
 
## 外部指令
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




查询数据库列表：

    SHOW DATABASES;


进入数据库：

    USE database_name;  


创建数据库：

    CREATE DATABASE database_name;


查询数据库中的表：

    SHOW TABLES;    

## SQL语言

### 核心功能和动词   
> 数据查询   SELECT（选）  
> 数据定义   CREATE（创），DROP(删)，ALTER（改）  
> 数据操纵   INSERT，UPDATE，DELETE  
> 数据控制   GRANT，REVOKE   （给予权限）  

### 数据类型  
#### 数值型  
> INT 整数  
> NUMBERIC() 定点数  
#### 字符串型  
> CHAR() 定长字符串  
> VARCHAR(最大长度) 变长字符串

piont：如果数据字节不够，CHAR会补零在末尾，而VARCHAR不会，直接接上下一个数据   
#### 操作表

    //增加表
    CREATE TABLE S_C
    (sno NUMBERIC(6) NOT NULL ,
     cno VARCHAR(3),
     PRIMARY KEY(sno ));
    //减少表
    DROP TABLE S_C CASCADE/RESTRICT  ;


出现 **NOT NULL**的列不能出现空值  
**KEY ()** 键
**CASCADE** 所有引用改列的视图和约束也删除，**RESTRICT** 在没有视图和约束时，才能删  
  
#### 键  
主键  PRIMARY KEY ( )  
外键  

#### 改变表内内容（列）  

    //删除列
    ALTER TABLE S_C DROP COLUMN sno ；
    //加列
    ALTER TABLE S_C ADD(sex (1),addr VARCHAR(20)) ；
    //修改列
    ALTER TABLE S_C 
    MODIFY sno NUMBERIC(9)；//修改长度  

    

### 查询
