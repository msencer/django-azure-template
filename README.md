# django-azure-template

```bash
$ virtualenv env 
```
```bash
$ source ./env/bin/activate
```
```bash
$ pip install Django
```
```bash
$ django-admin.py startproject <project_name> --template=https://github.com/msencer/django-azure-template/zipball/master
```
```bash
$ mv ./config/* ./<project_name>
```

Edit web.2.7.config and web.3.4.config files and replace {{ project_name }} part with your project name.


