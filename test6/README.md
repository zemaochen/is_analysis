## 实验六：基于GitHub的实验管理平台的分析与设计
|学号|班级|姓名|照片|
|:-------:|:-------------: | :----------:|:---:|
|201610414102|软件(本)16-1|陈泽茂|![wo](../test1/wo.jpg)
### 1.概述
<hr>

- 基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。学生和老师的实验内容均存放在GitHUB 页面上。
- 学生的功能主要有：一是设置自己的GitHub用户名，二是选择课程，三是查询自己的每一门课程的实验成绩。学生的GitHub用户名是公开的，但成绩不公开。
- 老师的功能主要有：一是选择课程，二是批改每个学生的成绩，三是查看每个学生每个课程的成绩。
- 老师和学生都能通过本系统的链接方便地跳转到学生的每个GitHUB实验目录，以便批改实验或者查看实验情况。
- 实验成绩按数字分数计算，每项实验的满分为100分，最低为0分。
- 系统自动计算每个学生的所有实验的平均分。
### 2.总体结构
<hr>

![实验管理平台](./images/实验管理平台.jpg)

- 界面设计参见: https://zemaochen.github.io/is_analysis_pages/test6/index

### 3.用例图设计|[源码](./uml/用例图设计.puml)
<hr>

![用例图设计](./images/用例图设计.png)

### 4.类图设计|[源码](./uml/类图设计.puml)
<hr>

![类图设计](./images/类图设计.png)

### 5.数据库设计
<hr>

[参见数据库设计](./md/数据库设计.md)
### 6.用例及界面详细设计
<hr>

- #### [“学生列表”用例](./用例/学生列表.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/index.html)
- #### [“评定成绩”用例](./用例/评定成绩.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/grade.html)
- #### [“登录”用例](./用例/登录.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/login.html)
- #### [“登出”用例](./用例/登出.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/bar.html)
- #### [“选择学期”用例](./用例/选择学期.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/course.html)
- #### [“选择课程”用例](./用例/选择课程.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/course.html)
- #### [“修改密码”用例](./用例/修改密码.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/modifypwd.html)
- #### [“修改用户信息”用例](./用例/修改用户信息.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/modify.html)
- #### [“查看用户信息”用例](./用例/查看用户信息.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/userinfo.html)
- #### [“查看成绩”用例](./用例/查看成绩.md),[界面](https://zemaochen.github.io/is_analysis_pages/test6/tests.html)



