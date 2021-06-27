Роль monitoring
=========

Данная роль monitoring является объединяющей в себе три роли, prometheus, grafana и alertmanager. То есть данная роль устанавливает и настроевает на сервере все компаненты мониторинга.


Пример запуска
-----------------

```ansible-playbook role-monitoring.yml --extra-vars "target=monitoring" -u ubuntu --ask-become-pass```

В этой команде:

* role-monitoring.yml - общая роль установки мониторинга на сервер
* target=monitoring - в переменной target мы передаём группу серверов, работающие для мониторинга
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo


Переменные
--------------

Для работы роли iptables нам могут понадобится следующие переменные:

* prometheus.node_exporter - список серверов которые будет опрашивать prometheus
* prometheus.alertmanager - список серверов на которые prometheus будет слать уведомления


Теги
----------------

* prometheus - тег устанавливающий prometheus и его настройка
* prometheus_config - тег делающий только настройку prometheus
* grafana - тег устанавливающий grafana
* alertmanager - тег устанавливающий alertmanager и его настройка
* alertmanager_config - тег делающий только настройку alertmanager
