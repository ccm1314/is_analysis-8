# 数据库设计 [首页](./README.md)

<div id="ADMINISTRATOR"></div>

- ## ADMINISTRATOR表（管理员表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |ADMIN_ID|VARCHAR2(50 BYTE)|主键|否| | | 主键唯一约束|
    |USER_ID|NUMBER(8,0)|外键|是| | | 老师的工号ID，USERS表的外键|
    |POWER|VARCHAR2(20 BYTE)||否| | | 权限级别(区别是不是本班的老师)|

<div id="USERS"></div>

- ## USERS表（用户表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |USER_ID|NUMBER(8,0)|主键|否| | | 用户ID|
    |NAME|VARCHAR2(50 BYTE)| |否| | | 用户真实姓名|
    |GITHUB_USERNAME|VARCHAR2(50 BYTE)| |是|空| | GitHUB用户名|
    |UPDATE_DATE|DATE| |是|空| | GitHUB用户名修改日期|
    |PASSWORD|VARCHAR2(512 BYTE)| |是|空| | 加密存储密码，为空表示密码就是学号|
    |DISABLE|VARCHAR2(20 BYTE)| |否| | |是否禁用,值为是表示禁用,其他表示正常.|

<div id="TEACHERS"></div>

- ## TEACHERS表（老师表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEACHER_ID|VARCHAR2(50 BYTE)|主键|否| | | 老师的编号|
    |USER_ID|NUMBER(8,0)|外键|是| | | 老师的用户ID，USERS表的外键|
    |DEPARTMENT|VARCHAR2(400 BYTE)| |否| | | 老师属于的部门|

<div id="STUDENTS"></div>

- ## STUDENTS表（学生表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|主键|否| | | 学生的学号|
    |USER_ID|NUMBER(8,0)|外键|是| |空| 学生的用户ID，USERS表的外键，为空表示还没有建立用户|
    |CLASS_ID|VARCHAR2(20 BYTE)|外键|否| | | 班级编号|
    |GITHUB_USERNAME|VARCHAR2(50 BYTE)| |是|空| | GitHUB用户名|
    |UPDATE_DATE|DATE| |是|空| | GitHUB用户名修改日期|
    |WEB_SUM|VARCHAR2(400 BYTE)| |是|空| | GitHub网址是否正确|
	
<div id="COURSES"></div>

- ## COURSES表（课程表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |COURSES_ID|NUMBER(6,0)|主键|否| | | 课程编号|
	|NAME|VARCHAR2(60)||否| | | 课程名|
    |TEACHER|VARCHAR2(50 BYTE)||否| | | 课程的科任老师|

<div id="TERM"></div>

- ## TERM表（学期表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TERM_ID|VARCHAR2(50 BYTE)|主键|否| | | 学期编号|
    |YEAR|VARCHAR2(100 BYTE)| |否| | | 学年|

<div id="STUDENT_COURSES"></div>

- ## STUDENT_COURSES表（学生课程对应表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)||否| | | 学生的id，STUDENTS表外键|
    |COURSE_ID|VARCHAR2(50 BYTE)||否| | | 课程的编号，COURSES表外键|
    |TEACHER|VARCHAR2(50 BYTE)||否| | | 课程的科任老师，COURSES表外键|

<div id="CLASSE"></div>

- ## CLASSE表（班级表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |CLASS_ID|VARCHAR2(50 BYTE)|主键|否| | | 班级的编号|
    |NAME|VARCHAR2(100 BYTE)| |否| | | 班级的名称|
    |DEPARTMENT_ID|VARCHAR2(100 BYTE)| 外键|否| | | 所属院系，DEPARTMENT表的外键|
	|MAJOR|VARCHAR2(100 BYTE)| |否| | | 专业|
	
<div id="DEPARTMENT"></div>

- ## DEPARTMENT表（院系表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |DEPARTMENT_ID|VARCHAR2(50 BYTE)|主键|否| | | 院系的编号|
    |NAME|VARCHAR2(100 BYTE)| |否| | | 院系的名称|
    |DEAN|VARCHAR2(100 BYTE)| |否| | | 院长|
	
<div id="TESTS"></div>

- ## TESTS表（实验项目表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |TEST_ID|NUMBER(6,0)|主键|否| | | 实验编号|
	|TEACHER_ID|NUMBER(6,0)|外键|否| | | 发布实验的教师的id|
	|COURSE_ID|NUMBER(6,0)|外键|否| | | 所属课程的id|
    |TITLE|VARCHAR2(100 BYTE)| |否| | | 实验名称|
    |DESC|VARCHAR2(100 BYTE)| |否| | | 实验要求|
    |link|VARCHAR2(100 BYTE)| |否| | | 实验的github链接|

<div id="COURSES_TERMES"></div>

- ## COURSES_TERMES表（课程学年对应表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |COURSE_ID|VARCHAR2(50 BYTE)||否| | | 课程的id，COURSES表外键|
    |TERM_ID|VARCHAR2(50 BYTE)||否| | | 学期编号ID，TERMS表外键|
    |YEAR|VARCHAR2(50 BYTE)||否| | | 学年，TERMS表外键|
    
<div id="GRADES"></div>

- ## GRADES表（学生实验成绩表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |STUDENT_ID|VARCHAR2(50 BYTE)|联合主键1，外键|否| | | 学生的学号，STUDENTS表外键|
    |TEST_ID|NUMBER(6,0)|联合主键2，外键|否| | | 实验编号，TESTS表的外键|
    |RESULT_SPECIFIC|NUMBER| |是|空| | 具体成绩对象，对象由数个数组构成，数组第一个值为得分项题目，第二个值为单项得分|
    |MEMO|VARCHAR2(400 BYTE)| |是|空| | 老师对实验的评语|
    |UPDATE_DATE|DATE| |是|空| |老师批改实验的日期，为空表示未批改|
    |EACH_SCORE|VARCHAR2(400 BYTE)| |是|空| | 每个实验的每项考点分数|
