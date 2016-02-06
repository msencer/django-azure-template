# Django project template for Azure Web Apps deployment

First of all, working with a non-Microsoft technology on a Microsoft platform is a total pain in the neck! I had spent full 2 days to figure out how to deploy a django project to Azure Web Apps. As you are in this repo, you' ll not share the same faith as me, for sure :)

Let's start! 

## Installing Django
```bash
$ pip install Django
``` 
## Starting a Django project
```bash
$ django-admin.py startproject <project_name> --template=https://github.com/msencer/django-azure-template/zipball/master
```

## Moving configuration files
```bash
$ mv ./config/* ./<project_name>
```
config folder contains following files :
* *web.2.7.config*           - web.config file for Python v2.7
* *web.3.4.config*           - web.config file for Python v3.4
* *requirements.txt*         - Azure server creates a virtual environment and installs the packages given in this file
* *.gitignore*               - Simple .gitignore file for a django project
* *ptvs_virtualenv_proxy.py* - Your django app will be running in an virtual environment so we need a proxy between IIS and Django

## Last touches
Edit *web.2.7.config* and *web.3.4.config* files and replace **{{ project_name }}** part with your project name.

Voila! Your django project is ready to be deployed on an azure web app.

## Commit & Deploy
I strongly suggest you to use git to push your code on Azure. You may initialize a git repo in the root folder of your project (where manage.py lies).
```bash
$ git init
$ git add --all
$ git commit -m "init"
$ git remote add azure <your_git_url>
$ git push azure master
```
Rest will be handled by Azure servers! You should see your Django project running in a few minutes.




