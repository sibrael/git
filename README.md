Задание 1
Запустите два simple python сервера на своей виртуальной машине на разных портах
Установите и настройте HAProxy, воспользуйтесь материалами к лекции по ссылке
Настройте балансировку Round-robin на 4 уровне.
На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.

![Image alt](https://github.com/sibrael/git/blob/835d8660119b91407d991a70032a7c453b904396/HaproxyCFG.png)

![Image alt](https://github.com/sibrael/git/blob/bb7976b4560012ab877377584c8b98d5af3e27d8/Level%204.png)


---

Задание 2
Запустите три simple python сервера на своей виртуальной машине на разных портах
Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.

![Image alt](https://github.com/sibrael/git/blob/bb7976b4560012ab877377584c8b98d5af3e27d8/HaproxyCFG2.png)
![Image alt](https://github.com/sibrael/git/blob/bb7976b4560012ab877377584c8b98d5af3e27d8/Example.png)



---
