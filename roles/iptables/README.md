Роль iptables
=========

Данная роль позволяет централизованно управлять настройками Firewall на серверах


Пример добавление пользователя
-----------------

```ansible-playbook role-iptables.yml --extra-vars "target=web_servers" -u ubuntu --ask-become-pass```

В этой команде:

* role-iptables.yml - роль iptables которая сконфигурирует и применит настройки Firewall
* target=web_servers - в переменной target мы указываем в какой группе серверов добавить учётки, или на каком конкретном сервере
* -u test - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo


Переменные
--------------

Для работы роли iptables нам могут понадобится следующие переменные:

* accept_ports - в этих переменных указываем порт и протокол, который требуется открыть именно для этой группы серверов
* iptables_contour - список ip адресов своих серверов, между которыми будет полностью развешён любой трафик


Теги
----------------

* iptables - тег, устанавливающий firewall и его настройка
* iptables_config - тег делающий только настройку firewall
