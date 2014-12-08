###面向对象

面向对象(Object Oriented,OO)是软件开发方法。

在面向对象领域，"对象"这个概念与"类的实例"是等同的，它们指代同一事物。我们有时会将"创建对象"称为"类的实例化"。

####一、基本概念

#####1.什么是类

具有相同特性（数据元素）和行为（功能）的对象的抽象就是类。因此，对象的抽象是类，类的具体化就是对象，也可以说类的实例是对象，类实际上就是一种数据类型。
#####2.什么是对象

对象是人们要进行研究的任何事物，从最简单的整数到复杂的飞机等均可看作对象，它不仅能表示具体的事物，还能表示抽象的规则、计划或事件。

#####3.什么是实例

实例就是一个对象的具体实现，也就是所谓的对象的实例化。比如你是人类的一员，而每个个体就是一个实例。

#####4.三者关系：类>>对象>>实例

####二、面象对象三大特性

#####1.封装

隐藏实现的一些细节，提供一种公共的访问方式。
* [Javascript 面向对象编程：封装](http://www.ruanyifeng.com/blog/2010/05/object-oriented_javascript_encapsulation.html)

#####2.继承

可以具备某些已经存在的功能。
* [Javascript面向对象编程：构造函数的继承](http://www.ruanyifeng.com/blog/2010/05/object-oriented_javascript_inheritance.html)
* [Javascript面向对象编程：非构造函数的继承](http://www.ruanyifeng.com/blog/2010/05/object-oriented_javascript_inheritance_continued.html)

```javascript
function Person(name,age,sex){
  this.name=name;
  this.age=age;
  this.sex=sex;
}
function Female(name,age){
Person.call(this,name,age,'Female');
}
Female.prototype=Object.create(Person.prototype);
Female.prototype.constructor=Female;
var lady = new Female('sunny',20);
console.log(lady);
```

#####3.多态
对象在不同时刻体现的不同状态。
```javascript
//在javascript中体现
var lady = new Female('sunny',20,'female');
var lady2=new Female('danny',18,'female');
var ladies = [lady,lady2];

var eachlady;
for(i = 1,i < ladies.length, i ++){
eachlady=ladies[i];
console.log(eachlady.name);
console.log(eachlady.age);
console.log(eachlady.sex);
}
```
```java
//在java中体现
List list=new ArrayList();

     list=new LinkedList();
```

####三、面向对象基本原则（SOLID）

######1.  单一职责

系统中的每一个对象应该只有一个单独的职责，所有对象关注的应该是自身职责的完成。```基本思想：高内聚，低耦合。```

######2.  开闭原则

一个对象对扩展开放，对修改关闭。```基本思想：对类的改动是通过增加代码进行的，而不是修改现有的代码。```

######3.  里氏替换原则

在任意父类出现的地方，都可以使用子类来代替。
######4.  接口分离原则

不要去使用一些不需要使用的功能。```基本思想：一个接口不要提供太多的行为。```

######5.  依赖注入原则

要依赖于抽象，不要依赖于具体的实现。```基本思想：在开发中尽量的面向接口编程。```

###四、JS中如何定义

####1.定义属性
```javascript
function Person(name,age,sex){
  this.name=name;
  this.age=age;
  this.sex=sex;
}
```

####2.定义方法

```javascript

function Person(name,age,sex){
  this.name=name;
  this.age=age;
  this.sex=sex;
}
Person.hello = function(){
  return 'Hello World';
}
Person.prototype.getName = function() {
  return this.name;
}

```

```javascript
//实例方法
var person = new Person('joes',20,'Male');
var name = person.getName();
console.log(name);

```

```javascript
//类方法
var helloWorld = Person.hello();
console.log(helloWorld);
```
