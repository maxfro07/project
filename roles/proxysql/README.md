Роль proxysql
=========

Данная роль устанавливает и настраевает ProxySQL. Данную роль я не сам писал, а взял уже готовую ([от суда](https://github.com/devops-works/ansible-proxysql)) .


Пример запуска
-----------------

```ansible-playbook role-proxysql.yml --extra-vars "target=web_servers" -u ubuntu --ask-become-pass --ask-vault-pass```

В этой команде:

* role-proxysql.yml - запускает установку и настройку ProxySQL
* target=web_servers - в переменной target мы указываем группу web серверов, на которых должен работать ProxySQL
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo
* --ask-vault-pass - пароль от vault, так как пароль root MySQL и другие пароли у нас храниться в зашифрованном виде


Переменные
--------------

Для работы роли proxysql нам могут понадобится следующие переменные:

* proxysql_admin_password - пароль от админки ProxySQL
* proxysql_version - версия ProxySQL. Очень важно указать новую версию 2.1, так как по умолчанию стоит старая версия.
* proxysql_mysql_servers - список адресом MySQL nod кластера которые будут добавлены в ProxySQL
* proxysql_mysql_users - список пользователей MySQL которые будут заведены в ProxySQL
* proxysql_mysql_query_rules - определяет правила запросов MySQL в ProxySQL. Хрен знает что это за переменные, но без них роль не работает.
