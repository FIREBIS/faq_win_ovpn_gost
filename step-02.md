## Шаг "Выпуск сертификата"

Сформируйте запрос на создание нового сертификата:

> Часть для Linux систем:

    cd /opt/easy-gost && ./build-req ACCOUNT-ID
    
В каталоге /opt/easy-gost/keys будут созданы два файла -- ключ и запрос:

    /opt/easy-gost/keys/ACCOUNT-ID.key
    /opt/easy-gost/keys/ACCOUNT-ID.csr

Файл с ключом скопируйте в рабочий каталог OpenVPN-ГОСТ:

    sudo mv /opt/easy-gost/keys/ACCOUNT-ID.key /etc/openvpn-gost/client.key
    sudo chmod 0400 /etc/openvpn-gost/client.key

> При создании запроса рекомендуется указывать какое-то имя, которое будет идентифицировать сертификат. Здесь нужно подумать, нужна ли нам произвольная часть. Кажется, что нужна, поскольку без нее повторение вышеуказанных команд завершится с ошибкой.

> Часть для Windows систем:

Переместите папку "easy-gost" в `C:\cryptopack4\`.

С помощью ярылка "Командная строка МагПро КриптоПакет" на рабочем столе, созданного при установке, откройте командную строку и введите: 

cd easy-gost && start build-req ACCOUNT-ID

В каталоге `C:\cryptopack4\easy-gost\keys` будут созданы два файла -- ключ и запрос:

    C:\cryptopack4\easy-gost\keys\ACCOUNT-ID.key
    C:\cryptopack4\easy-gost\keys\ACCOUNT-ID.csr

Файл с ключом скопируйте в рабочий каталог OpenVPN-ГОСТ также через командную строку:

    move C:\cryptopack4\easy-gost\keys\ACCOUNT-ID.key C:\cryptopack4\client.key

---

Загрузите полученный на предыдущем шаге файл /opt/easy-gost/keys/ACCOUNT-ID.csr

> После успешного выпуска сертификатов должен происходить переход на третий шаг.