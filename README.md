# Personal-bank-account-management
# （个人银行账户管理程序）
C++入手项目（《C++语言程序设计》（第4版）课本项目）

### 2020/7/11 第四章类和对象

完成项目类的设计，初步实现基本功能（开户、存钱、取钱、结算利息）

### 2020/7/13 第五章数据的共享与保护改进  

1.为SavingsAccount类增加一个静态数据成员total,用来记录各个账户的总金额，并为其增加相应的静态成员函数getTotal用来对其进行访问。    
2.将SavingsAccount类的诸如getBalance,accumulate这些不需要改变对象状态的成员函数声明为常成员函数。     
3.对程序结构进行调整：将SavingsAccount类从主函数所在的源文件中分开，建立两个新的文件account.h和account.cpp,分别存放SavingsAccount类的定义和实现。    

### 第六章数组、指针与字符串改进
在第五章的基础上，将描述账号的数据类型由int改为了string，将描述日期的数据类型由int改为了新定义的Date类，并且为deposit,withdraw和settle三个函数都增加了一个用来存储该笔账目说明信息的string型的desc参数，并且增加了一个专用于输出错误信息的error函数。  

### 第七章继承与派生改进
增加信用账户，给出使用继承和派生的解决方案   
两个不足：   
①各个账户对象无法通过数组来访问，使得需要分别对每个对象执行某个操作时，只能分别写出针对各对象的代码，无法用循环来完成。   
②不同派生类的deposit,withdraw,settle等函数彼此独立，只有知道一个实例的具体类型后才能调用这些函数。   

### 第八章多态性改进
①针对第七章两个不足，引入虚函数和抽象类。   
②对账户所做的各种操作都可以通过基类的指针来调用，因此可以把各账户对象的指针都放在一个数组中。 
③主函数改为由用户输入账户编号、对账户的操作类型和操作的参数，以增强程序的灵活性。   
④重载Date类“-运算符，实现distance函数的功能。   

### 第九章群体类和群体数据的组织改进
使用动态数组类模板Array来代替C++预定义的数组类型完成同样的功能。由于Array数组允许动态改变大小，因此可以向Array数组中动态添加新的元素，从而使用户随时动态添加新的账户。   

### 第十章泛型程序设计与C++标准模板库改进
①STL本身提供的向量容器vector能够很好的满足数组的需求。   
②增加一个多重映射来存储每一笔账目，键—账目的日期，附加数据—账目的详细内容。   

### 第十一章流类库与输入输出改进
①将用户输入的存款、取款、结算等各种命令保存下来，下次启动程序时将这些命令读出并执行，这样各个账户就能恢复到上次退出程序时的状态了。
②建立Controller类，用于保存账户列表、当前日期和处理指定命令。   
③对Date类重载">>"、"<<"运算符 用于输入、输出日期。   

### 第十二章异常处理改进
①当用户的输入不符合要求时获取异常。   
②用户试图从一个账户中超额取款失败获取异常。  
