### java -version

#### 计算机(右键)->属性->高级系统设置->环境变量
#### 系统变量：新建：变量名：JAVA_HOME  变量值：C:\Program Files\Java\jdk1.7.0_80 （java jdk目录）

```bash
java version "1.8.0_211"
Java(TM) SE Runtime Environment (build 1.8.0_211-b12)
Java HotSpot(TM) 64-Bit Server VM (build 25.211-b12, mixed mode)
```

### mvn -v

#### 计算机(右键)->属性->高级系统设置->环境变量
#### 系统变量：新建：变量名：MAVEN_HOME  变量值：D:\maven\bin （maven目录） 注意：Path 增加 D:\maven\bin

```bash
Apache Maven 3.5.4 (1edded0938998edf8bf061f1ceb3cfdeccf443fe; 2018-06-18T02:33:14+08:00)
Maven home: D:\maven
Java version: 1.7.0_80, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jdk1.7.0_80\jre
Default locale: zh_CN, platform encoding: GBK
OS name: "windows 8.1", version: "6.3", arch: "amd64", family: "windows"
```

# 参考文档：http://blog.didispace.com/books/spring-boot-reference/
# 11. 开发你的第一个Spring Boot应用
# http://blog.didispace.com/books/spring-boot-reference/II.%20Getting%20started/11.%20Developing%20your%20first%20Spring%20Boot%20application.html

### 新建 pom.xml-->mvn package-->mvn dependency:tree-->mvn spring-boot:run

```bash
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>myproject</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.4.1.RELEASE</version>
    </parent>

    <!-- Additional lines to be added here... -->
    
    <dependencies>
	    <dependency>
	        <groupId>org.springframework.boot</groupId>
	        <artifactId>spring-boot-starter-web</artifactId>
	    </dependency>
	</dependencies>
	
	<build>
	    <plugins>
	        <plugin>
	            <groupId>org.springframework.boot</groupId>
	            <artifactId>spring-boot-maven-plugin</artifactId>
	        </plugin>
	    </plugins>
	</build>

</project>
```



1. 使用webpack快速构建SPA应用
链接：https://v.youku.com/v_show/id_XNDE3OTk5NzEyMA==.html?spm=a2h3j.8428770.3416059.1
密码：955684

2.使用webpack快速构建MPA应用
链接：https://v.youku.com/v_show/id_XNDE4MTA4OTkxMg==.html?spm=a2h3j.8428770.3416059.1
密码：168126


3.webpack在一线开发中的优化
链接：https://v.youku.com/v_show/id_XNDE4MTI2MzcwNA==.html?spm=a2h3j.8428770.3416059.1
密码 975018

4.前端工程化与Jenkins
链接：https://v.youku.com/v_show/id_XNDE4MTI2Nzc2NA==.html?spm=a2h3j.8428770.3416059.1
密码:469748

5.从0带你实现自己的的CLI
链接：https://v.youku.com/v_show/id_XNDE4MTA5NTI2MA==.html?spm=a2h3j.8428770.3416059.1
密码：662446

