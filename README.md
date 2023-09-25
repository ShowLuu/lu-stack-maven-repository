# lu-stack-maven-repository

## 集成使用说明

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

## 组件列表

| 名称                                               | 简介                                                         |
| -------------------------------------------------- | ------------------------------------------------------------ |
| \|- `lu-cloud-stack`                               | 所有技术栈的底层依赖，主要负责依赖库的版本管理，打包发布管理， |
| \|- \|- `lu-component`                             | 所有组件的底层依赖，本身依赖`lu-cloud-stack`，负责不同组件统一管理 |
| \|- \|- \|- `lu-component-crypto`                  | 数据库加解密组件，基于Mybatis、Spring框架，数据写操作加密，读操作解密 |
| \|- \|- \|- `lu-component-rpc-spring-boot-starter` | 基于SpringBoot、OpenFeign的RPC组件，支持注册中心的负载均衡调用，支持服务降级 |
| \|- \|- \|- `lu-component-http-proxy`              | 基于http协议的轻量级rpc组件，无其它依赖，支持服务降级、限流  |
| \|- \|- \|- `lu-component-grpc-proxy`**开发中**    | 基于netty框架的轻量级rpc组件，无其它依赖，支持服务降级、配额限流 |

