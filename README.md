# Ansible Playbooks

## Структура репозитория

 - `files` - файлы плейбуков и задач, некатегоризируемых по ролям.
 - `inventories` - реестры ([inventory](http://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)) с целями и группами.
 - `roles` - структура ролей в соответствии с [документацией](http://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#content-organizationhttp://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#content-organization);

В корне проекта расположены все доступные плейбуки. Плейбуки на основе ролей начинаются с префикса `role-`.


## Главные роли

### Databases

Данная роль позволяет настроить наши MySQL сервера.

Пример запуска команды

```ansible-playbook role-databases.yml --ask-vault-pass```

В этой команде:

* role-databases.yml - список ролей который нужно выполнить на серверах группы "data_bases"
* --ask-vault-pass - пароль от vault, так как пароль root MySQL у нас храниться в зашифрованном виде


### Web servers

Данная роль позволяет настроить наши Web сервера.

Пример запуска команды

```ansible-playbook role-webservers.yml --ask-vault-pass```

В этой команде:

* role-webservers.yml - список ролей который нужно выполнить на серверах группы "web_servers"
* --ask-vault-pass - пароль от vault, так как пароли HTTP авторизации и прочее у нас храниться в зашифрованном виде


### Monitoring

Данная роль позволяет настроить наши Monitoring сервера.

Пример запуска команды

```ansible-playbook role-monitoring.yml --ask-vault-pass```

В этой команде:

* role-monitoring.yml - список ролей который нужно выполнить на серверах группы "monitoring"
* --ask-vault-pass - пароли от базы InfluxDB у нас храниться в зашифрованном виде


## Одиночные, самостоятельные роли

### Backup

Роль backup устанавливает скрипты резервного копирования файлов и базы данных сайта. А после добавляет задания backup в cron. Данная роль можем быть установлена на любом сервере из группы web_servers. Подробнее о запуске этой роли можно почитать в описание этой роли.

### Users

Данная роль добавляет/удаляет пользователей на любом из серверов, либо на группе серверов. Подробнее о запуске этой роли можно почитать в описание этой роли.

### ManageMySQL

Данная роль добавляет базу и пользователя для сайта wordpress. Обычно эта роль запускается на любом одном сервере из группы data_bases. Подробнее о запуске этой роли можно почитать в описание этой роли. 

### Certbot

Роль запускается на на том сервере, где требуется получить SSL сертификат. В составе группы Certbot не отрабатывает, так как должно быть подтвеждение домена с ip адресом. Подробнее о запуске этой роли можно почитать в описание этой роли.

### Grafana
Create dashboar -> import -> Import via panel json
Файл grafana.json - наш дасшборд для проекта
