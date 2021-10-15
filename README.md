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
 
### 1). 源文件一：
```
package banking;

public class Account {
    private double balance;

    public Account(double bal) {
        balance = Double.parseDouble(String.valueOf(bal));
    }

    public double getBalance() {
        return balance;
    }

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
        return result;
    }
}
```
### 2). 源文件二：
```
package banking;
public class Customer {
 private Account  account;
 private String   firstName;
 private String   lastName;
 public Customer(String f, String l, int cAge) {
   firstName = f;
lastName = l;
age = cAge;
 }
 public String getFirstName() {
   return firstName;
 }
 public String getLastName() {
   return lastName;
 }
 public Account getAccount() {
   return account;
 }
 public void setAccount(Account acct) {
   account = acct;
 }  
} 
``` 
### 3). 源文件三：
```
package banking;
import banking.*;
public class TestBanking {
 public static void main(String[] args) {
   Customer customer;
   Account  account;
   // Create an account that can has a 500.00 balance.
   System.out.println("Creating the customer Jane Smith.");
   customer = new Customer("Jane", "Smith");
   System.out.println("Creating her account with a 500.00 balance.");
   customer.setAccount(new Account(500.00));
   account = customer.getAccount();
   // Perform some account transactions
   System.out.println("Withdraw 150.00: " + account.withdraw(150.00));
   System.out.println("Deposit 22.50: " + account.deposit(22.50));
   System.out.println("Withdraw 47.62: " + account.withdraw(47.62));
   System.out.println("Withdraw 400.00: " + account.withdraw(400.00));
   // Print out the final account balance
   System.out.println("Customer [" + customer.getLastName()
​       + ", " + customer.getFirstName()
​       + "] has a balance of " + account.getBalance());
 }
}
```
#### 将上述文件编译后，尝试运行。
## 实验方法
在3个源代码的基础上,创建banking包,分别创建3个类customer,account,TestBanking.在源代码中发现已经创建了构造方法,只用在customer类里创建age属性,并在testbanking的输出里,用getage将age进行输出.
## 实验结果
---
* 在banking包下创建customer类,在类中创建账户名字和年龄的属性,之后用构造方法重构,在Customer方法中写入3个参数分别为String f, String l, int cAge.在下面在分别创建账户名字和年龄的普通方法,用于在Testbanking输出.
* 再创建Account类,创建balance bal的属性,创建获得余额,存款和提款3种方法.存款方法返回值为余额与存款额相加;取款为余额与提款额相减,若余额小于提款额,则不能进行,输出false.
* 最后创建TestBanking类,实例化一个账户,余额为500,然后进行提款、存款、提款、提款操作,最后输出账户人的姓名年龄和余额.
!
