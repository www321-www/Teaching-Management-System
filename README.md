# teaching-management-system
# pycharm with python interpreter version 3.6 or higher
本周作业

角色:学校、学员、课程、讲师
要求:
1. 创建北京、上海 2 所学校
2. 创建linux , python , go 3个课程 ， linux\py 在北京开， go 在上海开
3. 课程包含，周期，价格，通过学校创建课程 
4. 创建讲师
5. 创建学员时，选择学校，关联班级
5. 创建讲师角色时要关联学校， 
6. 提供两个角色接口
6.1 学员视图， 可以注册，选择课程（等同于选择班级）
6.2 讲师视图， 讲师可管理自己的班级，上课时选择班级， 
    查看班级学员列表 ， 修改所管理的学员的成绩 
6.3 管理视图，创建讲师， 创建班级，创建课程

7. 上面的操作产生的数据都通过pickle序列化保存到文件里

##  1.需求分析（课程与班级合为一体）
    -管理员视图
        1.注册
        2.登录
        3.创建学校
        4.创建课程（先选择学校）
        5.创建班级
        
    -学员视图
        1.注册
        2.登录
        3.选择校区
        4.选择课程（先选择校区，再选择校区的某一门课程）
            学生选择课程，课程选择学生
        5.查看分数
        6.交学费
        
    -讲师视图
        1.登录
        2.查看教授课程
        3.选择教授班级
        4.查看课程下学生
        5.修改学生分数
        
        
## 2.程序的架构分析
    —三层架构（MVC,MVV）
        -用户视图层
            -用与与用户交互
            -小的逻辑判断，比如注册功能中两次密码能否一致的校验
            -core
                -src.py 主视图
                -admin.py 管理员视图层
                -student.py 学生视图层
                -teacher.py 教师视图层
                
        -逻辑接口层
            核心业务逻辑的处理
            
        -数据处理层
            -做数据的处理，比如数据的增删改查
            -db
                -models.py
                -db_handler.py
                    -ATM+购物车
                        存放json格式的数据
                        dic —-> json
                    -选课系统
                        存放pickle格式的数据
                        object --> pickle
            
## 3.分任务开发
