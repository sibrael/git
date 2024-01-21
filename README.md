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

![Image alt](https://github.com/sibrael/git/blob/92e802b249819e2998696e4c26df9220d7291846/gitlab%201.png)

---
Задание 2

Установите Zabbix Agent на два хоста.

# wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
# apt update

# apt install zabbix-agent

# systemctl restart zabbix-agent
# systemctl enable zabbix-agent

![Image alt](https://github.com/sibrael/git/blob/d00b3d5156d41b7f59a8bf5acce3a9b5cb29405f/2.png)

---
Задание 3
Установите Zabbix Agent на Windows (компьютер) и подключите его к серверу Zabbix.

![Image alt](https://github.com/sibrael/git/blob/6b6e250a208a390c98b4a0d11a85c78280e6f698/4.1.png)
![Image alt](https://github.com/sibrael/git/blob/6b6e250a208a390c98b4a0d11a85c78280e6f698/4.2.png)
![Image alt](https://github.com/sibrael/git/blob/6b6e250a208a390c98b4a0d11a85c78280e6f698/4.3.png)

---
