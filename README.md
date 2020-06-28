# 大创项目

数据挖掘实验平台











# 安装运行步骤

## 创建虚拟环境

conda开一个py3.6的虚拟环境

## 克隆

找好目录，GitHub克隆项目，cd进入项目目录

## 安装需要的包

```bash
pip install -r requirements.txt
```

## 修改项目mysql密码

文件是...\MxOnline\settings.py 在100行左右

```py
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'django_test',        #数据库名字
        'USER': 'root',          #账号
        'PASSWORD': 'root',      #密码 ！！这里改成自己的mysql密码！！
        'HOST': '127.0.0.1',    #IP
        'PORT': '3306',                   #端口
    }
}
```

## 建立本机同名数据库

打开MySQL

```sql
CREATE DATABASE django_test;
```

Query OK, 1 row affected (0.01 sec)

## 疑似失败的做迁移

控制台

```bash
python manage.py makemigrations
```

No changes detected

## 真·做迁移（？）

```bash
python manage.py migrate
```

  Applying captcha.0001_initial... OK
  Applying organization.0001_initial... OK
  Applying courses.0001_initial... OK
  Applying operation.0001_initial... OK
  Applying operation.0002_auto_20181128_0630... OK
  Applying sessions.0001_initial... OK
  Applying xadmin.0001_initial... OK
  Applying xadmin.0002_log... OK
  Applying xadmin.0003_auto_20160715_0100... OK

## 建立管理员用户

```bash
python manage.py createsuperuser
```

用户名: (自己起一个)
电子邮件地址: （随意，目测不会真的发邮件）
Password:（要求8个字符以上，自己记一下）
Password (again):（就是重复密码）
Superuser created successfully.

之后就可以用这个账户登录了