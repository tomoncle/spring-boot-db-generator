# spring-boot-db-generator
> 通过数据库生成数据模型及简单xml映射


## install
```bash
$ git clone https://github.com/tomoncle/spring-boot-db-generator
```

## Test
* 1.create database
```mysql
create database db_test;
alter database db_test character set utf8;
```

* 2.import sql data
```bash
$ mysql -p -Ddb_test < ./db/test.sql 
```

* 3.generator
```bash
$ cd spring-boot-db-generator
$ mvn clean mybatis-generator:generate
```

* 4.find generator files in target folder.
```
$ tree target/
target/
└── generated-sources
    └── mybatis-generator
        ├── com
        │   └── tomoncle
        │       └── project
        │           └── provider
        │               ├── entity
        │               │   ├── TMajor.java
        │               │   ├── TStudent.java
        │               │   └── TUser.java
        │               └── repository
        │                   ├── TMajorMapper.java
        │                   ├── TStudentMapper.java
        │                   └── TUserMapper.java
        └── mybatis
            ├── TMajorMapper.xml
            ├── TStudentMapper.xml
            └── TUserMapper.xml

9 directories, 9 files
``` 