### 根据数据库表生成java实体类，有多种方法，下面是其中的3种（以下方法在idea IDE中)：
1. 单个数据库表生成实体类  
数据库表，右击=》Scripted Extensions =》Generate POJOs.clj 或 Generate POJOs.groovy =》选择保存的文件夹。
2. spring boot 的 jpa（低层是hibernate技术）   
多个数据库表生成多个实体类
3. MyBatis 插件：mybatis-generator-maven-plugin  
多个数据库表生成多个实体类

* 此处介绍的是：第2种，使用spring boot 的 jpa技术

* 详细步骤，参考：http://www.souvc.com/?p=2555

### mysql数据库需要做的操作
1. mysql中新建数据库(schema):mybatis
2. 执行创建table user和插入数据的操作：
```
Create TABLE `user` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `userName` varchar(50) DEFAULT NULL,
  `userAge` int(11) DEFAULT NULL,
  `userAddress` varchar(200) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8;
```
```
Insert INTO `user` VALUES ('1', 'summer', '100', 'shanghai,pudong');
```
3. 执行创建table article和插入数据的操作：
```
Drop TABLE IF EXISTS `article`;
Create TABLE `article` (
  `id` int(11) NOT NULL auto_increment,
  `userid` int(11) NOT NULL,
  `title` varchar(100) NOT NULL,
  `content` text NOT NULL,
  PRIMARY KEY  (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8;
```
```
Insert INTO `article` VALUES ('1', '1', 'test_title', 'test_content');
```
```
Insert INTO `article` VALUES ('2', '1', 'test_title_2', 'test_content_2');
```
```
Insert INTO `article` VALUES ('3', '1', 'test_title_3', 'test_content_3');
```
```
Insert INTO `article` VALUES ('4', '1', 'test_title_4', 'test_content_4');
```
