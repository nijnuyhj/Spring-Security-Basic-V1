# Spring Security Basic V1

---
### MySQL DB및 사용자 생성
```
create user 'cos'@'%' identified by 'cos1234';
GRANT ALL PRIVILEGES ON *.* TO 'cos'@'%';
create database security;
use security;
```
### yml파일 설정
```
server:
  port: 8080
  servlet:
    context-path: /
    encoding:
      charset: UTF-8
      enabled: true
      force: true

spring:
  datasource:
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://localhost:3306/security?serverTimezone=Asia/Seoul&useSSL=false&allowPublicKeyRetrieval=true
    username: cos
    password: cos1234

  jpa:
    hibernate:
      ddl-auto: create # create, update, none
      naming:
        physical-strategy: org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
    show-sql: true
    properties:
      hibernate:
        dialect: org.hibernate.dialect.MySQLDialect
```
### localhost:8080/login창

ID : user

PW : 터미널 security password
