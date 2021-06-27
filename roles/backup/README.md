Роль backup
=========

Данная роль позволяет делать резервные копии файлов и базы данных сайта. 


Пример запуска роли
-----------------

```ansible-playbook role-backup.yml --extra-vars "target=app01" -u ubuntu --ask-become-pass --ask-vault-pass```

В этой команде:

* role-backup.yml - запускает роль установки backup
* target=app01.gmr.su - в переменной target мы указываем сервер app01.gmr.su, так как на нём удобно запускать бэкапы. Но можно указать группу web_servers, что бы делался backup на всех app серверах.
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo
* --ask-vault-pass - пароль от vault, так как некоторые пароли у нас храниться в зашифрованном виде



Переменные
--------------

Для работы роли backup нам понадобятся следующие переменные:

* backup.path_scripts - адрес папки где будут храниться скрипты backup-ов
* backup.source_folder - папка с файлами сайта
* backup.source_base_name - название базы MySQL сайта
* backup.source_base_user - имя пользователя MySQL
* backup.source_base_password - пароль от базы MySQL
* backup.destination_folder - папка куда складывать backup-ы
