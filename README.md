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
package banking;
public class Account {
 private double   balance;
 public Account(String bal) {
   balance = bal;
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
   if ( balance < amount ) {
     result = false;
   } else {
     balance = balance - amount;
   }
   return result;
 }
}
### 2). 源文件二：
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
 
### 3). 源文件三：
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
#### 将上述文件编译后，尝试运行。
