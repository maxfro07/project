Роль Telegraf
=========

Данная роль делает установку и настройку Telegraf, агента сбора метрик для InfluxDB. Эта роль не самостоятельная, а входит в состав других ролей.


Пример запуска роли monitoring в которую входит роль Telegraf
-----------------

```ansible-playbook role-monitoring.yml --extra-vars "target=monitoring" -u ubuntu --ask-become-pass```

В этой команде:

* role-monitoring.yml - запуск всех ролей по разворачиванию сервера мониторинга
* target=monitoring - в переменной target мы указываем в какой группе серверов добавить Telegraf, или на каком конкретном сервере
* -u ubuntu - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo


Теги
----------------

* telegraf - только установка Telegraf
* telegraf_config - только настройка Telegraf
