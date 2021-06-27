Роль cluster
=========

Данная роль позволяет развернуть cluster Galera и настроить его. 


Пример добавление пользователя
-----------------

```ansible-playbook role-cluster.yml --extra-vars "target=data_bases" -u ubuntu --ask-become-pass --ask-vault-pass```

В этой команде:

* role-cluster.yml - роль cluster создаёт кластер
* target=data_bases - в переменной target мы указываем в какой группе серверов добавить учётки, или на каком конкретном сервере
* -u test - имя учётки, от которой будем делать установку
* --ask-become-pass - передать системе пароль sudo
* --ask-vault-pass - пароль от vault, так как пароль root MySQL у нас храниться в зашифрованном виде



Переменные
--------------

Для работы роли cluster нам понадобятся следующие переменные:

* name - имя текущего узла
* address - адреса всех узлов, которые будут работать в cluster-е
* root_password - пароль пользователя root в MySQL. Зашифрован ANSIBLE VAULT.
