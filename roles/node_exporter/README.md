Роль node exporter
=========

Данная роль устанавливает на серверах агента Prometheus node exporter


Пример запуска роли
-----------------

```ansible-playbook role-node_exporter.yml --extra-vars "target=all_servers" -u ubuntu --ask-become-pass```

В этой команде:

* role-node_exporter.yml - роль node_exporter которая установит агента node exporter
* target=all_servers - в переменной target мы указываем что сделать установку агента надо на всех серверах
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo


Переменные
--------------

Для работы роли node_exporter нам потребуется всего одна переменная:

* version - версия агента node exporter


Теги
----------------

* node_explorer - тег устанавливающий node explorer
