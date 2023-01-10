# Java-Design-Patterns

## 设计模式

### 背景

1990年软件工程界开始研讨设计模式的话题，后来召开了多次关于设计模式的研讨会。直到1995 年，艾瑞克·伽马（ErichGamma）、理査德·海尔姆（Richard Helm）、拉尔夫·约翰森（Ralph Johnson）、约翰·威利斯迪斯（John Vlissides）等 4 位作者合作出版了《设计模式：可复用面向对象软件的基础》一书，在此书中收录了 23 个设计模式，这是设计模式领域里程碑的事件，导致了软件设计模式的突破。这 4 位作者在软件开发领域里也以他们的“四人组”（Gang of Four，GoF）著称。  

### 概念

软件设计模式（Software Design Pattern），又称设计模式，是一套被反复使用、多数人知晓的、经过分类编目的、代码设计经验的总结。它描述了在软件设计过程中的一些不断重复发生的问题，以及该问题的解决方案。也就是说，它是解决特定问题的一系列套路，是前辈们的代码设计经验的总结，具有一定的普遍性，可以反复使用。
### 分类
#### 构建模式

怎么创建对象，将对象的创建和使用分离

- 单例
- 原型
- 简单工厂
- 工厂方式
- 抽象工厂
- 建造者

#### 结构模式

如何将类或对象按某种布局组成更大的结构

- 代理
- 适配器
- 桥接
- 装饰
- 外观
- 享元
- 组合

#### 行为模式

类或对象之间怎样互相协作共同完成单个对象无法单独完成的任务

- 模板方法
- 策略
- 命令
- 职责链
- 状态
- 观察者
- 中介者
- 迭代器
- 访问者
- 备忘录
- 解释器

## UML

Unifield Modeling Language，统一建模语言

### 类图

类图是面向对象建模的主要组成部分。类图显示了模型的静态结构。

#### 作用

- 描述系统中类的集合，类的属性和类之间的关系，简化理解
- 系统分析和设计阶段的重要产物，系统编码和测试的重要模型

#### 表示方式 

在UML类图中，类使用包含类名、属性(field) 和方法(method) 且带有分割线的矩形来表示，比如下图表示一个Employee类，它包含name,age和address这3个属性，以及work()方法。 

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/Employee.jpg)

属性/方法名称前加的加号和减号表示了这个属性/方法的可见性，UML类图中表示可见性的符号有三种：

* +：表示public

* -：表示private

* #：表示protected

属性的完整表示方式是： **可见性  名称 ：类型 [ = 缺省值]**  

方法的完整表示方式是： **可见性  名称(参数列表) [ ： 返回类型]**

> 注意：
>
> 	1，中括号中的内容表示是可选的
> 										
> 	2，也有将类型放在变量名前面，返回值类型放在方法名前面

**举个栗子：**

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/demo.png)

上图Demo类定义了三个方法：

* method()方法：修饰符为public，没有参数，没有返回值。
* method1()方法：修饰符为private，没有参数，返回值类型为String。
* method2()方法：修饰符为protected，接收两个参数，第一个参数类型为int，第二个参数类型为String，返回值类型是int。

#### 类与类之间关系的表示方式

##### 关联关系

关联关系是对象之间的一种引用关系，用于表示一类对象与另一类对象之间的联系，如老师和学生、师傅和徒弟、丈夫和妻子等。关联关系是类与类之间最常用的一种关系，分为一般关联关系、聚合关系和组合关系。我们先介绍一般关联。

关联又可以分为单向关联，双向关联，自关联。

###### 单向关联

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/customer_address.png)

在UML类图中单向关联用一个带箭头的实线表示。上图表示每个顾客都有一个地址，这通过让Customer类持有一个类型为Address的成员变量类实现。

###### 双向关联

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/customer_product.png)

从上图中我们很容易看出，所谓的双向关联就是双方各自持有对方类型的成员变量。

在UML类图中，双向关联用一个不带箭头的直线表示。上图中在Customer类中维护一个List\<Product>，表示一个顾客可以购买多个商品；在Product类中维护一个Customer类型的成员变量表示这个产品被哪个顾客所购买。

###### 自关联

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/node.png)

自关联在UML类图中用一个带有箭头且指向自身的线表示。上图的意思就是Node类包含类型为Node的成员变量，也就是“自己包含自己”。

##### 聚合关系

聚合关系是关联关系的一种，是强关联关系，是整体和部分之间的关系。

聚合关系也是通过成员对象来实现的，其中成员对象是整体对象的一部分，但是成员对象可以脱离整体对象而独立存在。例如，学校与老师的关系，学校包含老师，但如果学校停办了，老师依然存在。

在 UML 类图中，聚合关系可以用带空心菱形的实线来表示，菱形指向整体。下图所示是大学和教师的关系图：

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20191229173422328.png)

##### 组合关系

组合表示类之间的整体与部分的关系，但它是一种更强烈的聚合关系。

在组合关系中，整体对象可以控制部分对象的生命周期，一旦整体对象不存在，部分对象也将不存在，部分对象不能脱离整体对象而存在。例如，头和嘴的关系，没有了头，嘴也就不存在了。

在 UML 类图中，组合关系用带实心菱形的实线来表示，菱形指向整体。下图所示是头和嘴的关系图：

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20191229173455149.png)



##### 依赖关系

依赖关系是一种使用关系，它是对象之间耦合度最弱的一种关联方式，是临时性的关联。在代码中，某个类的方法通过局部变量、方法的参数或者对静态方法的调用来访问另一个类（被依赖类）中的某些方法来完成一些职责。

在 UML 类图中，依赖关系使用带箭头的虚线来表示，箭头从使用类指向被依赖的类。下图所示是司机和汽车的关系图，司机驾驶汽车：

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20191229173518926.png)

##### 继承关系

继承关系是对象之间耦合度最大的一种关系，表示一般与特殊的关系，是父类与子类之间的关系，是一种继承关系。

在 UML 类图中，泛化关系用带空心三角箭头的实线来表示，箭头从子类指向父类。在代码实现时，使用面向对象的继承机制来实现泛化关系。例如，Student 类和 Teacher 类都是 Person 类的子类，其类图如下图所示：

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20191229173539838.png)



##### 实现关系

实现关系是接口与实现类之间的关系。在这种关系中，类实现了接口，类中的操作实现了接口中所声明的所有的抽象操作。

在 UML 类图中，实现关系使用带空心三角箭头的虚线来表示，箭头从实现类指向接口。例如，汽车和船实现了交通工具，其类图如图 9 所示。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20191229173554296.png)

## 软件设计原则

> 提供系统的可维护性和可复用性，增加软件的可扩展性和灵活性

### 开闭原则

#### 原理

**对扩展开放，对修改关闭**。在程序需要进行拓展的时候，不能去修改原有的代码，实现一个热插拔的效果。简言之，是为了使程序的扩展性好，易于维护和升级。

想要达到这样的效果，我们需要使用接口和抽象类。

因为抽象灵活性好，适应性广，只要抽象的合理，可以基本保持软件架构的稳定。而软件中易变的细节可以从抽象派生来的实现类来进行扩展，当软件需要发生变化时，只需要根据需求重新派生一个实现类来扩展就可以了。

#### Eg.

![image-20230107201149789](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/image-20230107201149789.png)

### 里氏代换原则

#### 原理

里氏代换原则是面向对象设计的基本原则之一。

里氏代换原则：任何基类可以出现的地方，子类一定可以出现。通俗理解：子类可以扩展父类的功能，但不能改变父类原有的功能。换句话说，子类继承父类时，除添加新的方法完成新增功能外，尽量不要重写父类的方法。

如果通过重写父类的方法来完成新的功能，这样写起来虽然简单，但是整个继承体系的可复用性会比较差，特别是运用多态比较频繁时，程序运行出错的概率会非常大。

#### Eg.

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E6%AD%A3%E6%96%B9%E5%BD%A2%E4%B8%8D%E6%98%AF%E9%95%BF%E6%96%B9%E5%BD%A2.png)

改进为如下情况，避免了子类对于父类的重写而导致在子类替换父类时，会引起与预期函数调用效果不同的结果发生。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/正方形不是长方形改进.png)

### 依赖倒转原则

#### 原理

高层模块不应该依赖低层模块，两者都应该依赖其抽象；抽象不应该依赖细节，细节应该依赖抽象。简单的说就是要求对抽象进行编程，不要对实现进行编程，这样就降低了客户与实现模块间的耦合。

#### Eg.

其他的例子还如平时我们在Java开发中各层之间的依赖，我们只会注入抽象类，而不会注入具体Impl实现类。

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E4%BE%9D%E8%B5%96%E5%80%92%E8%BD%AC%E5%8E%9F%E5%88%99%E6%94%B9%E8%BF%9B.png">

### 接口隔离原则

#### 原理

客户端不应该被迫依赖于它不使用的方法；一个类对另一个类的依赖应该建立在最小的接口上。

#### Eg. 

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E6%8E%A5%E5%8F%A3%E9%9A%94%E7%A6%BB%E5%8E%9F%E5%88%99.png">

将不同方法的接口进行拆解，防止单一接口类导致一个类实现接口方法时被迫依赖于不使用的方法之上。

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E6%8E%A5%E5%8F%A3%E9%9A%94%E7%A6%BB%E5%8E%9F%E5%88%991.png">

### 迪米特法则

#### 原理

迪米特法则又叫最少知识原则。

只和你的直接朋友交谈，不跟“陌生人”说话（Talk only to your immediate friends and not to strangers）。

其含义是：如果两个软件实体无须直接通信，那么就不应当发生直接的相互调用，可以通过第三方转发该调用。其目的是降低类之间的耦合度，提高模块的相对独立性。

迪米特法则中的“朋友”是指：当前对象本身、当前对象的成员对象、当前对象所创建的对象、当前对象的方法参数等，这些对象同当前对象存在关联、聚合或组合关系，可以直接访问这些对象的方法。

#### Eg.

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E8%BF%AA%E7%B1%B3%E7%89%B9%E6%B3%95%E5%88%99.png" alt="image-20191229173554296">



### 合成复用原则

#### 原理

合成复用原则是指：尽量先使用组合或者聚合等关联关系来实现，其次才考虑使用继承关系来实现。

通常类的复用分为继承复用和合成复用两种。

继承复用虽然有简单和易实现的优点，但它也存在以下缺点：

1. 继承复用破坏了类的封装性。因为继承会将父类的实现细节暴露给子类，父类对子类是透明的，所以这种复用又称为“白箱”复用。
2. 子类与父类的耦合度高。父类的实现的任何改变都会导致子类的实现发生变化，这不利于类的扩展与维护。
3. 它限制了复用的灵活性。从父类继承而来的实现是静态的，在编译时已经定义，所以在运行时不可能发生变化。


采用组合或聚合复用时，可以将已有对象纳入新对象中，使之成为新对象的一部分，新对象可以调用已有对象的功能，它有以下优点：

1. 它维持了类的封装性。因为成分对象的内部细节是新对象看不见的，所以这种复用又称为“黑箱”复用。
2. 对象间的耦合度低。可以在类的成员位置声明抽象。
3. 复用的灵活性高。这种复用可以在运行时动态进行，新对象可以动态地引用与成分对象类型相同的对象。

#### Eg.

继承复用：不同能源类型与不同颜色类型，仅聚合复用会产生大量子类。

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E5%90%88%E6%88%90%E5%A4%8D%E7%94%A8%E5%8E%9F%E5%88%99.png" alt="image-20191229173554296">

改进为 聚合复用。如果在Petrol和Electric后出现新的能源车辆，我们还可以对能源方式进行聚合。

<img src="https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/11721/%E5%90%88%E6%88%90%E5%A4%8D%E7%94%A8%E5%8E%9F%E5%88%991.png">





## 目录

### 构建模式

创建型模式的主要关注点是“怎样创建对象？”，它的主要特点是“将对象的创建与使用分离”。

这样可以降低系统的耦合度，使用者不需要关注对象的创建细节。

创建型模式分为：

* 单例模式 Singleton 
* 简单工厂 Simple Factory
* 工厂方法模式 Factory Method 
* 抽象工程模式 Abstract Factory
* 原型模式 Prototype 
* 建造者模式 Builder
