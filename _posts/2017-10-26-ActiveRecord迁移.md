# Active Record 基础

1 Active Record是什么？
Active Record是MVC中的model，是一种关系对象映射系统ORM(object relation mapping),模型实例与数据库是对应的。


2 Active Record 中的“多约定少配置”原则
   在实作不同的应用时，每次需要重复相同的配置，ActiveRecord将这些配置进行抽象形成规则,个人需要尽量遵循这些原则，只有当原则不能满足需求才进行配置，常见原则如下：
-命名约定：model名字和数据库名字时单复数的关系
-模式约定：每笔数据都有保留的字段：主键、外键、created_at、created_at

3 创建Active Record
只需要继承ApplicationRecord就行
class Product < ApplicationRecord
end 

Product的模型实例对应products数据库表名
Product的模型实例属性对应products数据库的字段

4 CRUD:读写数据
对数据库进行增删查改

-增（新建对象）：new、create，new需要save才能保存对象,create会调用数据验证
-删（删除对象）：destroy、delete
-查（查找记录）：find、find_by、select、where
-改（修改记录）：update、save,二者都会调用数据验证

Active Record 对象可以使用散列创建，在块中创建，或者创建后手动设置属性。

5 数据验证
数据存入数据库之前会进行验证，以确保其合法性。
save、create、update都会调用数据验证的方法

6 回调
暂时不懂

7 迁移
每一次迁移都是对数据库的验证。
