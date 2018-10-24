使用方法：
1.安装Python3环境（未在Python2上运行后，不知道有没有问题）
2.下载代码到本地并解压
3.cmd到根目录下安装相关依赖包
pip install -r requirements.txt<br>
pip install https://github.com/darklow/django-suit/tarball/v2
4.安装mysql数据库，配置数据库连接，进入api_automation_test/settings.py
DATABASES = {
    'default': {
        # 'ENGINE': 'django.db.backends.sqlite3',
        # 'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
        'ENGINE':'django.db.backends.mysql',     # 数据库类型，mysql
        'NAME':'api_test',            #  database名
        'USER':'root',               # 登录用户
        'PASSWORD':'123456',        #  登录用户名
        'HOST':'127.0.0.1',        # 数据库地址
        'PORT':'3306'              # 数据库端口
    }
}
5.cmd到根目录下，让 Django 知道我们在我们的模型有一些变更
python manage.py makemigrations
6.创造或修改表结构
python manage.py migrate 
7.创建超级用户，用于登录后台管理
python manage.py createsuperuser
8.安装VUE环境，下载node.js并配置环境，下载npm包管理器
9.cmd进入frontend目录下，运行npm install安装相关依赖包
10.打包
npm run build
11.运行启动django服务
python manage.py runserver 0.0.0.0:8000
12.现在就可以访问 http://127.0.0.1:8000/login 进行登录， http://127.0.0.1:8000/admin 为后台管理平台
微信打赏：
微信打赏


系统图解：
系统图

项目讲解：
1、登录页面，只提供了登录方法，并没有注册和忘记密码功能，账号由后台管理系统直接创建分配
登录页面

2、目前只开放了接口测试，所有只有项目列表页面，可完成项目的新增，删除，查询，修改，批量删除
首页

3、新增项目
新增项目

4、点击项目名称后，进入项目概况界面，总的展示一些项目的基本情况
项目概况

5、HOST配置页面，提供了，增删改查，批量修改HOST，作为执行自动化测试时的全局变量
HOST配置

6、新增Host
新增Host

7、API页面，可执行快速测试，类似于postman，新增修改删除接口分组，新增修改删除项目接口，后续计划根据输入的接口搭建mockserver和下载接口文档
API页面

8、快速测试界面，类似于postman的功能，后续怎么json格式显示的样式
快速测试界面

9、新增接口分组，用于按模块对接口进行分类，更好的管理接口
新增接口分组

10、新增API，用户可新增的API，目前只支持源数据格式和form-data格式
新增API

11、接口详情界面，查看接口基本内容，可对接口进行测试，修改，删除，查看接口历史动态
接口详情界面
12、下载的接口文档模板

接口文档

13、自动化测试页面，实现自动化用例的分组，增删改查用例，并添加自动化定时任务定时任务
自动化测试页面

14、新增测试用例
新增测试用例

15、用例下的接口列表，可添加用例接口，选择不同的环境测试接口，以及下载测试报告和设置定时任务
用例下的接口列表

16、用例下添加已有的接口，可添加在api模块中，已添加的接口，默认校验方式为不校验
用例下添加已有的接口

17、项目成员，只做一个展示项目组成员页面，成员添加删除由后台管理操作，后续引入权限系统，分配权限角色
项目成员

18、展示项目三天内的动态情况
项目动态

18、自动化测试生成的报告，保留最近10次测试结果
自动化测试报告

20、退出登录，跳转至登录页面
退出登录

21、后台管理页面，主要用作数据管理，及项目人员添加删除
后台管理

=====================================================
优化
frontend\index.html
------------------------------------------------------