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
### 操作表

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

### 改变表内内容（列）  

    //删除列
    ALTER TABLE S_C DROP COLUMN sno ；
    //加列
    ALTER TABLE S_C ADD(sex (1),addr VARCHAR(20)) ；
    //修改列
    ALTER TABLE S_C 
    MODIFY sno NUMBERIC(9)；//修改长度  

    

### 查询

    SELECT
    FROM
    WHERE
    //SELECT * 代表选择表中的所有列

    //结果按选出的该列的值分组，列值相等的为一个组
    GROUP BY
    
    //带having为特定条件的组才会输出
    GROUP BY    HAVING 

    //排序（升或降）
    ORDER BY sno ASC/DESC 

WHERE后可接运算符：  
比较运算符：**= > < >=  <>**(这个是不等于)     
逻辑运算符： **AND   NOT OR**
谓词 **BETWEEN  (NOT)IN** (列值属于制定集合的元组)  
字符匹配 **（NOT）LIKE**    
**_**代表任意单个字符  **%**任意长度字符（可为0）
    
    （NOT）LIKE ‘<匹配串>’[ESCAPE'<换码字符>']  

    ex:
    WHERE SNAME LIKE '刘%' OR SNAME LIKE ‘_ _刘%’
    //一个汉字占两个字符位
    WHERE CNO =‘004’ AND PLACE IN ('湖南')  

### 约束  
##### 约束分类
not null 非空约束   
unique 唯一性约束  
primary key 主键约束  
foreign key 外键约束  
check 检查约束  
default 默认值约束  

 #### 如何查看表中约束？

    SELECT * FROM information_schema.`TABLE_CONSTRAINTS`
    WHERE table_name='employees';

    DESC test1;
    //返回有关的结构信息，例如列名、数据类型和约束等
    //vs below
    SELECT * FROM test1;
    //返回数据

    MODIFY email VARCHAR(25) NULL;
    //表述可以有空值，不是一定


#### UNIQUE
限制某个字段或某列的值不能重复  
分为列级和表级  
表级约束：constraint 约束名称 关键字(字段名)  
ex：CONSTRAINT uk_test2_email UNIQUE(email)
https://blog.csdn.net/weixin_44016186/article/details/124320138?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522170106697816800222831210%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=170106697816800222831210&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-124320138-null-null.142^v96^pc_search_result_base6&utm_term=%E7%BA%A6%E6%9D%9F%20sql&spm=1018.2226.3001.4187  
