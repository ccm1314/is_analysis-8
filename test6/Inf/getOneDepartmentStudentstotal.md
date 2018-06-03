# 接口：getOneDepartmentStudentstotal  [返回](../README.md)
用例： [返回一个学院学生的总数。](../用例/返回一个学院学生的总数.md)

- 权限：
    学生/访客
    老师

- 功能：
    返回一个学院所有学生的总数。

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
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回学生人数|