### 根据数据库表生成java实体类，有多种方法，下面是其中的3种（以下方法在idea IDE中)：
1. 单个数据库表生成实体类  
数据库表，右击=》Scripted Extensions =》Generate POJOs.clj 或 Generate POJOs.groovy =》选择保存的文件夹。
2. spring boot 的 jpa（低层是hibernate技术）   
多个数据库表生成多个实体类
3. MyBatis 插件：mybatis-generator-maven-plugin  
多个数据库表生成多个实体类

* 此处介绍的是：第2种，使用spring boot 的 jpa技术

* 详细步骤，参考：http://www.souvc.com/?p=2555
