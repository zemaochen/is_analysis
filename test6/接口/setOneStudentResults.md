# 接口：setOneStudentResults  [返回](../README.md)
用例： [评定成绩](../用例/评定成绩.md)

- 功能：
    老师根据得分项评分
- 权限：
    老师：可以查看所有学生的实验。
   
- API请求地址： 
    接口基本地址/v1/api/etOneStudentResults

- 请求方式 ：
    POST
 
- 请求实例：  
```json
{ 
     "student_id": "201610414102", 
     "status": true,
     "info": null,
     "data":
       {
         "grade_id":"01",
         "title":"实验一",
         "request":48,
         "format":18,
         "expansion":15,
         "comment":"本次实验做的不错"
        }
}
 ```
- 请求参数说明:       
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学号|
  |data|实验的各得分项得分|
  |grade_id|成绩单编号|
  |comment|本实验老师的评价，可以为空|   
- 返回实例：

```json
{         
            "status": true,
            "info": null
}
```

- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
