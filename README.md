# Django-ERP
Django-ERP是一款基于Django开发的ERP管理软件，包含常用的销售管理、采购管理、库存管理、组织管理等，支持按项目归集费用，支持工作流审批，支持采购单、报价单的批量导入。

Forked from <a href=https://github.com/zhuinfo</a> 感谢他的付出。

# 安装指南

> 现在为python3版本，如果你有什么疑问可以留言。


## 数据库配置

数据库配置项在mis/settings.py文件中
在88-96行为Mysql数据库配置

```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',#MYSQL类型数据库，Python会依赖MySQL的驱动器
        'HOST': 'localhost',#数据库主机地址
        'NAME': 'mis',#数据库名称
        'USER': 'root',#数据库用户名（建议不要加入root敢死队）
        'PASSWORD': 'root',#数据库密码
    }
}
```


## 克隆代码
> git clone https://github.com/bg4hkq/Django-ERP.git


## 导入数据库
> mysql -uroot -proot mis < Install/mis.sql

## 运行测试服务器
> python manage.py runserver

## 修改管理员账户密码
```
C:\Django-ERP>python manage.py changepassword admin

You have 3 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth.
Run 'python manage.py migrate' to apply them.
Changing password for user 'admin'
Password:
Password (again):
Password changed successfully for user 'admin'

C:\Django-ERP>
```

# 排错

## MYSQL驱动错误
```
django.core.exceptions.ImproperlyConfigured: Error loading MySQLdb module: No module named MySQLdb
```

出现No module named MySQLdb是django找不到MySQL驱动导致的问题，所以需要先安装一个数据库驱动。

