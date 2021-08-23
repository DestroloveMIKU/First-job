# Java版本切换

**由于工作要求，公司需求，业务需求的java版本都各不相同，所以在此做了一个版本切换log**

## 1.环境配置区分

> 将原本的JAVA_HOME的变量值更改为**%JAVA_HOME??%**
>
> ??用于写JAVA版本，例如此处为NC6.5所需版本*[实际为JAVA1.7]*
>
> 而各个版本的Java环境的变量值就对应的设置为`jdk`所在的位置，切换版本只需要切换JAVA_HOME后面的数字变量即可达到

![image-20210721102602399](C:\Users\Destro\AppData\Roaming\Typora\typora-user-images\image-20210721102602399.png)

## 2.切换后版本查询

`cmd`->查询

错误反馈

``` java
C:\Users\Destro>java --version
Unrecognized option: --version
Error: Could not create the Java Virtual Machine.
//无法创建java虚拟机
Error: A fatal exception has occurred. Program will exit.
//程序退出
```

>其他可以在命令行里面运行的软件，包括java的早期版本。都是使用 `--version` 来查看软件版本的，而不是 `-version`。 而目前的最流行的java8系列，版本号查看方式却是 `-version`

切换查询方式后

```java
C:\Users\Destro>java -version
java version "1.7.0_51"
Java(TM) SE Runtime Environment (build 1.7.0_51-b13)
Java HotSpot(TM) Client VM (build 24.51-b03, mixed mode)
```



切换完成

