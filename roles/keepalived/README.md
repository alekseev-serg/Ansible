# Keepalived

Установка и конфигурирование балансировщика нагрузки keepalived.

В рамках роли настраивается:
- Включается маршрутизация пакетов ipv4
- Устанавливается и конфигурируется keepalived

## Переменные

Ниже, с примером, описаны переменные для установки ПО. 

```
# Название инстанса
keepalived__instance_name: "MINIO"
# Версия
keepalived__version: "1:2.0.19-2ubuntu0.2"
# Тип авторизации между хостами
keepalived__auth_type: "PASS"
# Виртуальный ip адрес 
keepalived__virtual_ipaddress: 10.200.225.155
# Виртуальный интерфейс ipv4
keepalived__interface: "ens160"
# Количество хостов 
keepalived__count_hosts: 4
# Список хостов с входящими данными 
keepalived__instances:
  - ip: 1.1.1.1
    state: master
    priority: 100
  - ip: 1.1.1.2
    state: backup
    priority: 99
  - ip: 1.1.1.3
    state: backup
    priority: 98
  - ip: 1.1.1.4
    state: backup
    priority: 97

```
## Документация
https://keepalived.readthedocs.io/en/latest/
