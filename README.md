# lu-stack-maven-repository

## 使用说明

### Maven setting.xml配置

排除`lu-stack-maven-repository`仓库

```xml
 <mirrors>
   <!-- 阿里云仓库 -->
   <mirror>
     <id>aliyunmaven</id>
      <!-- 增加排除仓库 -->
     <mirrorOf>*,!lu-stack-maven-repository</mirrorOf>
     <name>阿里云公共仓库</name>
     <url>https://maven.aliyun.com/repository/public</url>
   </mirror>
</mirrors>
```

### 项目pom.xml配置

增加一下内容

```xml
 <repositories>
   <repository>
     <id>lu-stack-maven-repository</id>
     <url>https://github.com/ShowLuu/lu-stack-maven-repository/raw/master</url>
     <releases>
       <updatePolicy>always</updatePolicy>
       <enabled>true</enabled>
     </releases>
     <snapshots>
       <updatePolicy>always</updatePolicy>
       <enabled>true</enabled>
       <checksumPolicy>fail</checksumPolicy>
     </snapshots>
   </repository>
</repositories>
```

