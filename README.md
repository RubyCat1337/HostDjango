# HostDjango
Краткое описание процесса деплоя (действия, команды в консоли etc.)
0. Регаемся в облачном сервисе PythonAnywhere 
1. Создаем виртуальное окружение
mkvirtualenv --python=python3.8 <virtualenv_name>

workon <virtualenv_name> - активация виртуального окружения deactivate - деактивация

2. Проверка инсталляции встроенного установщика пакетов и админской части  
which pip

which django-admin.py

3. Устанавливаем необходимые для работы вашего сайта или приложения пакеты
a) pip install <имя пакета>

или

b) pip freeze > requirements.txt - для выгрузки всех пакетов из среды разработки

Далее на PythonAnywhere, запускаем

pip install -r requirements.txt

4. Проверяем наличие пакетов
pip list

В моем случае это следующие основные пакеты:
5. Клонируем git-репо с вашим проектом или копируем все файлы вручную на сервис PythonAnywhere
#Cloning your Git Repository

а) git clone https://github.com/<git_user_name>/<repo_name>.git

б) для приватных репо

#To private

cd git_repo

git clone https://<git_user_name>:<git_pass> @github.com/<git_user_name>/<repo_name>.git

6. Команды для миграции моделей (сущностей) в БД и разворачивания вашего сайта-приложения в облачном сервисе PythonAnywhere
Following commands, ex:

(prdsite) 16:55 ~/prdsite/prdsite_proj $ python manage.py makemigrations <application_name>

(prdsite) 16:55 ~/prdsite/prdsite_proj $ python manage.py migrate

(prdsite) 16:56 ~/prdsite/prdsite_proj $ python populate_mblog.py

(prdsite) 16:57 ~/prdsite/prdsite_proj $ python manage.py createsuperuser

python manage.py collectstatic

7. Настраиваем Web-сервис | PythonAnywhere
a) WSGI - user_name_pythonanywhere_com_wsgi.py (см. данный git-репо)

b) необходимые рабочие директории (с кодом, со статикой, медиа) и др. в разделе Web в облачном сервисе PythonAnywhere

8. Настраиваем settings.py под ваши нужды
Зависит от функционала сайта.

9. Пример получившегося деплоя сайта-блога
nicholasid7.pythonanywhere.com

Всем, peace!

Congratulations!
