# Oracle11g安装，卸载与环境配置

## 1.安装Oracle11g

### a.解压文件

![image-20210726114952294](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210726114952294.png)

将两个文件夹共同解压到一个文件夹下,**此处是为了确保database_2里面的文件，能解压到database_1里面，并且将其替换**[目录为win64_11gR2_database_2of2.zip\database\stage\Components\]

### b.Setup.exe安装

![image-20210810230629475](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810230629475.png)

~~可能会出现的情况~~

![image-20210726115625765](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210726115625765.png)

解决办法->

打开当前文件夹下的**stage\cvu\cvu_prereq.xml**，在**<CERTIFIED_SYSTEMS>**增加入一下内容

```xml
<OPERATING_SYSTEM RELEASE="6.2">
            <VERSION VALUE="3"/>
            <ARCHITECTURE VALUE="64-bit"/>
            <NAME VALUE="Windows 10"/>
           <ENV_VAR_LIST>
                     <ENV_VAR NAME="PATH" MAX_LENGTH="1023" />
            </ENV_VAR_LIST>
  </OPERATING_SYSTEM>
```

### c.配置安全与更新

取消勾选我希望通过~~~

![image-20210722095146557](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210722095146557.png)

### d.安全选项

创建和配置数据库

![image-20210810223240970](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810223240970.png)

### e.系统类

选择->桌面类

![image-20210810223306230](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810223306230.png)

### f.典型安装

Oracle基目录：选择自己自定义的目录文件，**文件夹路径不要有中文**

全局数据库名：一般默认，自己修改的话要记牢<**orcl(orcl.168.56.1)**>

管理口令：自行设置<此处设置为：**Szws0719**>

![image-20210726115921279](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210726115921279.png)

### g.自行安装

![image-20210722101032248](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210722101032248.png)

### h.口令管理

将**sys，system，hr，Scott**解锁并且设置相应的密码

|     User     |   Sys    |  System  |  Hr  | Scott |
| :----------: | :------: | :------: | :--: | :---: |
| **password** | Root1234 | Root1234 |  hr  | tiger |

![image-20210722102302676](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210722102302676.png)

## 2.环境变量配置

### α.主目录

> 变量名：ORACLE_HOME
>
> 变量值：E:\WorkFiles\Orcl\product\11.2.0\dbhome_1

![image-20210810233153711](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810233153711.png)

### β.监听数据库TNS

> 变量名：TNS_ADMIN
>
> 变量值：E:\WorkFiles\Orcl\product\11.2.0\dbhome_1\NETWORK\ADMIN

![image-20210810233517922](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810233517922.png)

### γ.实例名配置

> 变量名：ORACLE_SID
>
> 变量值：ORCL

![image-20210810233825202](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810233825202.png)

### δ.配置客户端的字符集

> 变量名：NLS_LANG
>
> 变量值：SIMPLIFIED CHINESE_CHINA.ZHS16GBK

![image-20210810233950001](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810233950001.png)



以上

## 3.检测是否安装成功

### ①.开始->所有应用里面找到Oracle

![image-20210810234338162](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810234338162.png)

### ②打开文件夹下的SQL Plus

![image-20210810234608907](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810234608907.png)

### ③命令提示符中输入用户和登录密码

**提示连接成功，则说明安装完成**

![image-20210810234711797](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210810234711797.png)





-----

# Oracle11g的完全卸载

## 1.关闭所有的Oracle所有服务

可以在windows的服务器中关闭

![image-20210812092743620](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210812092743620.png)

## 2.打开注册表删除注册表下的所有Oracle相关文件

> 在运行窗口使用`regedit`打开注册表编辑器

1. 计算机\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Oracle11

2. 计算机\HKEY_LOCAL_MACHINE\SOFTWARE\ORACLE

3. 计算机\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\EventLog\Application\

   以下所有文件

   ![image-20210812093432400](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210812093432400.png)

## 3.删除环境变量Path里面关于Oracle的所有内容

**具体变量值见上面安装环境变量内容**

## 4.重启操作系统

## 5.删除Oracle_Home下所有数据

## 6.删除`C:\Program Files`下所有Oracle数据

## 7.删除开始菜单文件
 路径： `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Oracle - OraDb11g_home1`

