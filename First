# SQL练习1
## 实验目的
1. 掌握基本表的定义；
2. 掌握插入数据、修改数据和删除数据的常用形式。

## 实验内容 

### 1.新建一个数据库，命名为zyxt。


### 2. 根据以下要求，用建表语句定义所需的数据表

1. 该数据库记录某采油厂对油水井实施作业时所消耗的成本。（作业：为保证油水井正常生产所实施的工程项目）  
2. 成本的消耗（***成本表costTable***）分为预算、结算、入账三个状态。  
预算：采油队向管理部门提出作业申请，并经管理部门批准后，由管理部门负责录入。  
结算：某次作业施工结束后，由管理部门与施工单位共同核算各种成本，由管理部门负责录入。  
入账：结算后，财务部门将成本计入采油厂账目，由财务部门录入。  
（一）、 预算状态时需要录入的数据：（★：字符型   ◆数字型   ▲日期型）  
★单据号：某一作业项目的编号 invoice(varchar(16))  
★预算单位：指需要对油水井实施作业的采油队代码 departmentId(varchar(16))  
★井号：需要实施作业的油水井 oilWall(varchar(16))  
◆预算金额   budgetAmount(decimal(10,2))  
★预算人   budgetPerson(varchar(16))  
▲预算日期 budgetDate(datetime))  
（二）、 结算状态时需要录入的数据：（★：字符型   ◆数字型   ▲日期型）  
调出某条预算记录，录入以下数据：  
▲开工日期  startDate(datetime)  
▲完工日期   endDate(datetime)  
★施工单位   constructionUnit(varchar(16))  
★施工内容  constructionContent(varchar(16))  
◆材料费（要求另外用表单独记录材料消耗的明细） materialCost(decimal(10,2))  
***材料消耗表 materialCostDetail***（★单据号  invoice(varchar(16))  ★物码 materialId(decimal(10,2))  ◆消耗数量 consumeQuantity(decimal(10,2)) ）  
◆人工费 presonCost(decimal(10,2))  
◆设备费 equipmentCost(decimal(10,2))  
◆其它费用 otherCost(decimal(10,2))
◆结算金额（材料费+人工费+设备费+其它费用）allCost(decimal(10,2))  
★结算人  settlePreson(varchar(16))  
▲结算日期 settleDate(datetime)  
（三）、 入账状态时需要录入的数据：（★：字符型   ◆数字型   ▲日期型）  
调出某条结算记录，录入以下数据：  
◆入账金额 recordAmount(decimal(10,2))  
★入账人 recordPerson(varchar(16))  
▲入账日期 recordDate(datetime)  





3. 为了避免出现数据的不一致和方便数据录入，要求定义以下基础表：（★：字符型）  

***单位表 departTable***：  
★单位代码   departID(varchar(16))  
★单位名称   departName(varcahr(16))  


***油水井表 oilWallTable***：
★井号   oilWallId(varcahr(16))  
★井别：油井/水井   oilWallType(varcahr(16))  
★单位代码  （表示某口井由哪个单位负责管理） departID(varcharID(16))  



***材料表 materiaTable***：
★物码   materialId(varchar(16))  
★名称   materialName(varchar(16))  
★计量单位   measureUnit(varchar(16))  
◆单价   Price(decimal(10,2))  





### 3. 用数据插入语句录入以下数据

1. 向 ***单位表(departTable)*** 插入数据

|departID|departName|
|-|-|
|1122|productionPlant|
|112201|oilOne|
|112202|oilTwo|
|112201001|oilOneFirst|
|112201002|oilOneSecond|
|112201003|oilOneThird|
|112202001|oilTwoFirst|
|112202002|oilTwoSecond|



2. 向 ***油井表(oilWallTable)*** 插入数据

|oilWallId|oilWallType|departID|
|-|-|-|
|y001|oilWall|112201001|
|y002|oilWall|112201001|
|y003|oilWall|112201002|
|s001|waterWall|112201002|
|y004|oilWall|112201003|
|s002|waterWall|112202001|
|s003|waterWall|112202001|
|y005|oilWall|112202002|



3. 向 ***材料表(materiaTable)*** 插入数据

|materialId|materialName|measureUnit|Price|
|-|-|-|-|
|wm001|first|t|10|
|wm002|second|m|10|
|wm003|third|bucket|10|
|wm004|fourth|bag|10|



4. 向 ***成本表(costTable)*** 插入数据

|invoice|departmentId|oilWall|budgetAmount|budgetPerson|budgetDate|startDate|endDate|constructionUnit|constructionContent|materialCost|presonCost|equipmentCost|otherCost|allCost|settlePreson|settleDate|recordAmount|recordPerson|recordDate|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|zy2016001|112201001|y001|10000.00|A|2016-05-01 00:00:00|2016-05-04 00:00:00|2016-05-25 00:00:00|companyFirst|plugging|7000.00|2500.00|1000.00|1400.00|11900.00|B|2016-05-26 00:00:00|11900.00|C|2016-05-28 00:00:00|
|zy2016002|112201002|y003|11000.00|A|2016-05-01 00:00:00|2016-05-04 00:00:00|2016-05-23 00:00:00|companySecond|checkPump|6000.00|1500.00|1000.00|2400.00|10900.00|B|2016-05-26 00:00:00|10900.00|C|2016-05-28 00:00:00|
|zy2016003|112201002|s001|10500.00|A|2016-05-01 00:00:00|2016-05-06 00:00:00|2016-05-23 00:00:00|companySecond|profileControl|6500.00|2000.00|500.00|1400.00|10400.00|B|2016-05-26 00:00:00|10400.00|C|2016-05-28 00:00:00|
|zy2016004|112202001|s002|12000.00|A|2016-05-01 00:00:00|2016-05-04 00:00:00|2016-05-24 00:00:00|companyThird|unblock|6000.00|2000.00|1000.00|1600.00|10600.00|B|2016-05-26 00:00:00|10600.00|D|2016-05-28 00:00:00|
|zy2016005|112202002|y005|12000.00|A|2016-05-01 00:00:00|2016-05-04 00:00:00|2016-05-28 00:00:00|companyThird|sandControl|7000.00|1000.00|2000.00|1300.00|11300.00|B|2016-06-01 00:00:00|11300.00|B|2020-6-1 00:00:00|



5. 向 ***材料消耗表(materialCostDetail)*** 插入数据

|invoice|materialId|consumeQuantity|
|-|-|-|
|zy2016001|wm001|200|
|zy2016001|wm002|200|
|zy2016001|wm003|200|
|zy2016001|wm004|100|
|zy2016002|wm001|200|
|zy2016002|wm002|200|
|zy2016002|wm003|200|
|zy2016003|wm001|200|
|zy2016003|wm002|200|
|zy2016003|wm003|250|
|zy2016004|wm001|200|
|zy2016004|wm002|200|
|zy2016004|wm004|200|
|zy2016005|wm001|200|
|zy2016005|wm002|200|
|zy2016005|wm004|300|



### 4. 完成以下操作
1. 将编号为zy2016001的项目的presonCost、allCost和recordAmount增加200元。


