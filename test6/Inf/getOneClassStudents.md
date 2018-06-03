# 接口：getOneClassStudents  [返回](../README.md)
用例： [返回一个班级的学生列表](../用例/返回一个班级的学生列表.md)

- 权限：
    学生/访客
    老师

- 功能：
    返回一个班级所有学生的列表。

- API请求地址：
   接口基本地址/v1/api/getOneClassStudents

- 请求方式 ：
    GET

- 请求参数说明:
    无

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 121,
            "data": [
                {
                "STUDENT_ID": "201510315203",
                "NAME": "陈松华",
                },
                {
                ...其他学生
                }
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回学生人数|
  |data|所有学生的数组|
  |STUDENT_ID|学号|
  |NAME|真实姓名|