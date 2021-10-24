# 实验一 程序组织及验证
 
## 实验目的
---
* 基本掌握本人所选择的集成开发工具的使用方法
* 掌握Java源程序命名、运行方法
* 理解、掌握创建包的方法
* 初步了解类的实例化方法
---
## 实验要求
* 定义包
* 组织类
* 定义类的属性、方法
## 实验步骤
* 步骤一：给出了程序的源文件（如下面的三个源文件），请阅读、理解其功能、含义，分析如下三个Java源程序文件的关系，理解以下三个源文件表达的实体业务逻辑关系（源文件分别描述了银行账户、存款人员、测试类）。
* 步骤二：在开发环境中组织代码并运行。
* 步骤三：请在Customer类新添加一个属性，描述其年龄，并补充操作年龄的方法。在测试类中调用这些方法。
* 步骤四：在理解上述程序的情况下，尝试从头分析并复写该程序。

#### 将上述文件编译后，尝试运行。
## 实验方法
在3个源代码的基础上,创建banking包,分别创建3个类customer,account,TestBanking.在源代码中发现已经创建了构造方法,只用在customer类里创建age属性,并在testbanking的输出里,用getage将age进行输出.

## 关键代码
```
public Customer(String f, String l, int cAge) {
        firstName = f;
        lastName = l;
        age = cAge;
    }
```
```
public boolean deposit(double amount) {
        balance = balance + amount;
        return true;
    }

public boolean withdraw(double amount) {
        boolean result = true;
        if (balance < amount) {
            result = false;
        } else {
            balance = balance - amount;
        }
```
```
Customer customer;
Account account;
customer = new Customer("Jane", "Smith",20);
customer.setAccount(new Account(500.00));
```

## 实验结果
![Image text](https://raw.githubusercontent.com/TakiSakura/Experiment1/master/截屏2021-10-24%20下午10.04.08.png)
---
* 在banking包下创建customer类,在类中创建账户名字和年龄的属性,之后用构造方法重构,在Customer方法中写入3个参数分别为String f, String l, int cAge.在下面在分别创建账户名字和年龄的普通方法,用于在Testbanking输出.
* 再创建Account类,创建balance bal的属性,创建获得余额,存款和提款3种方法.存款方法返回值为余额与存款额相加;取款为余额与提款额相减,若余额小于提款额,则不能进行,输出false.
* 最后创建TestBanking类,实例化一个账户,余额为500,然后依次进行提款、存款、提款、提款操作,最后输出账户人的姓名年龄和余额.
## 实验感想
---
在看到源代码后,对源代码观察和分析后.大致明白了其中的内容，和代码能发挥的作用.
并在过程中加深了对构造方法的理解,知道了构造方法在程序中起到的初始化的作用.
三个源代码我发现了其中有一定的关联性.
他们虽然不在一个程序中，但在同一个package下.
在customer和account类中定义的属性和方法，
在最后的testbanking中可以进行调用其中的属性，
并用创造的构造方法进行实例化.


