## Maven加速
打开maven的配置文件(windows机器一般在maven安装目录的conf/settings.xml)，在<mirrors></mirrors>标签中添加mirror子节点:

```xml
<mirror>
    <id>aliyunmaven</id>
    <mirrorOf>*</mirrorOf>
    <name>阿里云公共仓库</name>
    <url>https://maven.aliyun.com/repository/public</url>
</mirror>
```

如果想使用其它代理仓库,可在<repositories></repositories>节点中加入对应的仓库使用地址。以使用spring代理仓为例：

```xml
<repository>
    <id>spring</id>
    <url>https://maven.aliyun.com/repository/spring</url>
    <releases>
        <enabled>true</enabled>
    </releases>
    <snapshots>
        <enabled>true</enabled>
    </snapshots>
</repository>
```

## Gradle加速

在build.gradle文件中加入以下代码:

```gradle
allprojects {
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public/' }
        mavenLocal()
        mavenCentral()
    }
}
```

```gradle
allProjects {
    repositories {
        maven { url 'https://maven.aliyun.com/repository/public/' }
        maven { url 'https://maven.aliyun.com/repository/spring/'}
        mavenLocal()
        mavenCentral()
    }
}
```

## 仓库代理地址
| 仓库名称 | 代理源地址 | 使用地址 | 说明 |
|:----------:|:-------------:| ------ | :------: |
| central |  https://repo1.maven.org/maven2/ | https://maven.aliyun.com/repository/central | 中央仓库 |
| jcenter |  http://jcenter.bintray.com/   |   https://maven.aliyun.com/repository/jcenter |  |
| public | 	central仓和jcenter仓的聚合仓 |  https://maven.aliyun.com/repository/public | 常用 |
| google | https://maven.google.com/ | https://maven.aliyun.com/repository/google |  |
| gradle-plugin	 | https://plugins.gradle.org/m2/ | https://maven.aliyun.com/repository/gradle-plugin |  |
| spring | http://repo.spring.io/libs-milestone/ | https://maven.aliyun.com/repository/spring |  |
| spring-plugin	 | http://repo.spring.io/plugins-release/ | https://maven.aliyun.com/repository/spring-plugin |  |
| grails-core | https://repo.grails.org/grails/core | https://maven.aliyun.com/repository/grails-core |  |
| apache snapshots	 | https://repository.apache.org/snapshots/ | https://maven.aliyun.com/repository/apache-snapshots |  |


**一份常用Maven配置**

```xml
    <mirror>
      <id>public</id>
      <mirrorOf>*</mirrorOf>
      <name>central仓和jcenter仓的聚合仓</name>
      <url>https://maven.aliyun.com/repository/public</url>
    </mirror>

  <mirror>
      <id>central</id>
      <mirrorOf>central</mirrorOf>
      <name>中央仓库</name>
      <url>https://maven.aliyun.com/repository/central</url>
    </mirror>

    <mirror>
      <id>jcenter</id>
      <mirrorOf>jcenter</mirrorOf>
      <name>jcenter仓库</name>
      <url>https://maven.aliyun.com/repository/jcenter</url>
    </mirror>

    <mirror>
      <id>gradle-plugin</id>
      <mirrorOf>gradle-plugin</mirrorOf>
      <name>gradle-plugin仓库</name>
      <url>https://maven.aliyun.com/repository/gradle-plugin</url>
    </mirror>
    <mirror>
      <id>spring</id>
      <mirrorOf>spring</mirrorOf>
      <name>spring仓库</name>
      <url>https://maven.aliyun.com/repository/spring</url>
    </mirror>
```


## 参考
- [阿里云Maven仓库](https://help.aliyun.com/document_detail/102512.html?spm=a2c40.aliyun_maven_repo.0.0.36183054treBkX)