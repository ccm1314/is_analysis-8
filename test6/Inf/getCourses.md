# 接口：getCourse  [返回](../README.md)
用例： [课程列表](../用例/课程列表.md)

- 权限：
    学生/访客
    老师

- 功能：
    返回所有课程列表。

- API请求地址：
   接口基本地址/v1/api/getOneCourse

- 请求方式 ：
    GET

- 请求参数说明:
    无

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 21,
            "data": [
                {
                "COURSE_ID": "03",
                "COURSE_NAME": "C语言",
                },
                {
                ...其他课程
                }
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回课程总数|
  |data|所有课程的数组|
  |COURSE_ID|课程ID|
  |COURSE_NAME|课程名|