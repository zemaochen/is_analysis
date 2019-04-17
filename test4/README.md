## 实验四：图书管理系统顺序图绘制
|学号|班级|姓名|照片|
|:-------:|:-------------: | :----------:|:---:|
|201610414102|软件(本)16-1|陈泽茂|![wo](../test1/wo.jpg)

### 1.登录用例
#### 1.1登录用例PlantUMl源码
```puml
@startuml
skinparam sequenceParticipant underline
actor ":系统用户" as A
participant ":验证身份" as B
participant ":验证密码" as C
participant ":登录成功" as D
activate A
A->B:输入id验证身份
activate B
deactivate
A->B:输入密码
activate B
B->C:验证密码正确性
deactivate
activate C
C->D:成功登录
deactivate
@enduml
```
#### 1.2登录用例顺序效果图
![登录用例顺序效果图](login.png)
#### 1.3登录用例顺序图说明
- 系统用户包括管理员和读者，用户登录时先输入ID验证身份与权限，系统判断用户是否存在，然后输入密码验证，最后登录成功
### 2.借书用例
#### 2.1借书用例PlantUMl源码
```puml
@startuml
skinparam sequenceParticipant underline
actor ":图书管理员" as A
participant ":读者" as B
participant ":资源项" as C
participant ":馆藏资源品种" as D
participant ":借书记录" as E
activate A
A->B:验证读者
activate B
deactivate B
A->B:读取读者限额
activate B
deactivate B
loop
A->C:获取资源项
activate C
C->D:查找资源品种
activate D
deactivate C
deactivate D
A->E:创建借书记录
activate E
deactivate E
A->C:借出资源
activate C
C->D:减少可借数量
activate D
deactivate C
deactivate D
A->B:减少可用限额
activate B
end
deactivate B
A->E:打印借书清单
activate E
deactivate E
@enduml
```
#### 2.2借书用例顺序效果图
![登录用例顺序效果图](lend.png)
#### 2.3借书用例顺序图说明
- 管理员验证读者是否符合借书条件，然后开始借书流程，借书流程正常完成后打印借书清单，记录借书信息。一次性可以借多本书，流程可以反复执行
### 3.还书用例
#### 3.1还书用例PlantUMl源码
```puml
@startuml
skinparam sequenceParticipant underline
actor ":图书管理员" as user
participant ":资源项" as bt
participant ":借书记录" as record
participant ":馆藏资源品种" as base
participant ":读者" as reader
participant ":逾期记录" as overrecord
activate user
user->bt:读取资源信息
activate bt
bt->record:取借记录
activate record
deactivate record
bt->base:取资源的品种
activate base
deactivate base
deactivate bt
user->reader:取借阅者信息
activate reader
deactivate reader
user->bt:归还资源
activate bt
bt->base:增加可借数量
activate base
deactivate bt
deactivate base
user->record:登记还书日期
opt 逾期
activate record
deactivate record
user->overrecord:登记逾期记录
activate overrecord
deactivate overrecord
end
@enduml
```
#### 3.2还书用例顺序效果图
![登录用例顺序效果图](return.png)
#### 3.3还书用例顺序图说明
- 管理员通过读者提供的信息查询借书记录，通过借书记录按资源项归还图书，增加此类图书库存，最后登记还书日期，若有逾期的情况，则执行逾期的顺序图流程
### 4.逾期罚款用例
#### 4.1逾期罚款PlantUMl源码
```puml
@startuml
skinparam sequenceParticipant underline
actor ":读者" as reader
participant ":资源项" as bt
participant ":管理员" as user
participant ":借书记录" as lendrecord
participant ":罚款记录" as finerecord
activate reader
reader->bt:输入资源项
activate bt
deactivate bt
reader->user:提交借书信息
activate user
user->lendrecord:查询借书记录
deactivate user
activate lendrecord
lendrecord->finerecord:计算罚款并记录
activate finerecord
deactivate finerecord
deactivate lendrecord
reader->finerecord:缴纳罚款
activate finerecord
deactivate finerecord
@enduml
```
#### 4.2逾期罚款用例顺序效果图
![登录用例顺序效果图](fine.png)
#### 4.3逾期罚款用例顺序图说明
- 读者提交还书资源信息，管理员根据读者提供的信息查询借书记录，发现有逾期现象，开始计算逾期时间，与罚款项，最后读者缴纳罚款，管理员记录逾期记录。
### 5.预定图书用例
#### 5.1预定图书PlantUMl源码
```puml
@startuml
skinparam sequenceParticipant underline
actor ":读者" as reader
participant ":资源项" as bt
participant ":图书管理员" as user
participant ":馆藏资源品种" as base
participant ":预定记录" as orderrecord
activate reader
reader->bt:输入资源项
activate bt
deactivate bt
reader->user:传递资源项
activate user
user->base:查找资源品种
activate base
deactivate base
user->orderrecord:登记预定记录
deactivate user
activate orderrecord
@enduml
```
#### 5.2预定图书用例顺序效果图
![登录用例顺序效果图](order.png)
#### 5.3预定图书用例顺序图说明
- 读者输入预定资源项传递给管理员，管理员获取资源项后查询资源库匹配资源，确认可以预定再登记预定信息
