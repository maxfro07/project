Роль managemysql
=========

Данная роль создаёт в БД MySQL базу для сайта, а так же пользователей. Пользователя для сайта и пользователя для мониторинга ProxySQL.


Пример запуска роли
-----------------

```ansible-playbook role-managemysql.yml --extra-vars "target=db01" -u ubuntu --ask-become-pass --ask-vault-pass```

В этой команде:

* role-managemysql.yml - роль создания заданных учёток и базы MySQL
* target=db01 - в переменной target мы указываем сервер db01, что бы на нём выполнить все операции MySQL.
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo
* --ask-vault-pass - пароль от vault, так как пароль root MySQL у нас храниться в зашифрованном виде
