# rh-bootstrap

Начальная конфигурация хостов на RedHat 7.9

В рамках роли настраивается:
- ограничивается размер журнала логов
- если к машине подключен дополнительный диск - он монтируется в /data (работает при ```bootstrap__storage_enable: true```)
- обновление и установка пакетов
