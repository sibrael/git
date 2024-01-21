Задание 1
Установите Zabbix Server с веб-интерфейсом.

# wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
# apt update
# apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix
# zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
# systemctl restart zabbix-server zabbix-agent apache2
# systemctl enable zabbix-server zabbix-agent apache2

![Image alt](https://github.com/sibrael/git/blob/3fe30ee389a18c0f39bdacfd01f88a36a69b365a/zabbix.png)

---
Задание 2

Установите Zabbix Agent на два хоста.

# wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
# apt update
# apt install zabbix-agent
# systemctl restart zabbix-agent
# systemctl enable zabbix-agent

![Image alt](https://github.com/sibrael/git/blob/3fe30ee389a18c0f39bdacfd01f88a36a69b365a/zabbix_2.png)
![Image alt](https://github.com/sibrael/git/blob/3fe30ee389a18c0f39bdacfd01f88a36a69b365a/zabbix_3.png)

---
Задание 3
Установите Zabbix Agent на Windows (компьютер) и подключите его к серверу Zabbix.


---
