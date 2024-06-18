# Nginx
Это более простая роль направлена на работу с MINIO. \
Установка и конфигурирование веб сервиса Nginx.

В рамках роли настраивается:
- Устанавливается и конфигурируется Nginx

## Переменные

Ниже, с примером, описаны переменные для установки ПО. 

```
# Версия
nginx__version: "1.18.0-0ubuntu1.4"
# Наименование блока хостов
nginx__upstream_name: "minio_servers"
# Порт 
nginx__upstream_port: 9001
# Исходящий порт 
nginx__listen_port: 80
# DNS имя
nginx__server_name: "minio.devdata.lan"
# Список хостов
nginx__host_names:
  - "devdata-minio-01"
  - "devdata-minio-02"
  - "devdata-minio-03"
  - "devdata-minio-04"

```
## Документация
https://nginx.org/ru/docs/
