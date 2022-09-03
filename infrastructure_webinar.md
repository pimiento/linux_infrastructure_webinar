- [Почему Linux?](#org52e9d4c)
- [Дистрибутивы Linux](#orgdb8387b)
- [Какой же ставить на сервер?!](#org3225c76)
  - [Debian-based](#org1410e5d)
  - [RedHat-based](#org9f6fcbe)
- [Debian-based](#org056ed41)
  - [Debian](#orgbf7d173)
  - [Ubuntu](#orgd64f452)
- [RedHat-based](#org2b2aad1)
  - [RedHat](#orgf530413)
  - [CentOS](#org1e74244)
  - [Fedora](#org015a5d5)
- [Другие](#orgcdf73a9)
  - [Gentoo](#org639aa79)
  - [Arch Linux](#org1488db1)
- [Полезные команды](#org274e9f1)
  - [Обновление системы](#orgb8253f8)
  - [Поиск пакета](#orge7736bf)
  - [Установка пакета](#org0889050)
- [initd, systemd](#orgc9e7dbd)
- [BSD](#org1201608)
  - [FreeBSD/OpenBSD/NetBSD](#org1471656)
- [Доп. информация по Linux](#orgb04b535)
- [Работа с «удалённым» сервером. SSH](#orgcd01408)
- [SSH Ключи](#org4895d65)
- [Добавление алиасов для SSH-хостов](#orgc95ffc7)
- [Python + SSH](#org256189c)
- [Ansible](#orga32322f)
- [Salt](#org8a7eaf0)
- [Rsync](#org2b93430)
- [screen / tmux](#org827d0ce)
- [Проверка состояния сервера](#orgfd58ef8)
- [Другие оболочки комнадной строки](#org82da93b)
- [PostgreSQL / MySQL / SQLite / NoSQL](#orge876aac)
- [Репликация](#org4e80186)
- [Шардирование](#org3e6861f)
- [Nginx](#org398a733)
- [Nginx](#orgf3e897f)
- [Cron](#orgf7d3b5a)
- [Бэкапы](#orgd7c4d09)
- [Logrotate](#org7d8a2c6)
- [Дополнительная литература](#orga000e30)
- [Безопасность](#orga1f06f7)
- [Вопросы-ответы](#org68d1a6d)



<a id="org52e9d4c"></a>

# Почему Linux?

[W3Techs](https://w3techs.com/technologies/overview/operating_system)  
![img](win_lin_statistics.png)  


<a id="orgdb8387b"></a>

# Дистрибутивы Linux

**[их очень много!](https://upload.wikimedia.org/wikipedia/commons/8/83/Linux_Distribution_Timeline_27_02_21.svg)**  

![img](linux_distros.png)  


<a id="org3225c76"></a>

# Какой же ставить на сервер?!


<a id="org1410e5d"></a>

## Debian-based

![img](debian_logo.png)  

-   deb-пакеты для установки программ
-   aptitude/apt — пакетный менеджер


<a id="org9f6fcbe"></a>

## RedHat-based

![img](red_hat_logo.png)  

-   rpm-пакеты для установки программ
-   yum — пакетный менеджер


<a id="org056ed41"></a>

# Debian-based


<a id="orgbf7d173"></a>

## Debian

Основная идея: он должен быть очень стабильный. В связи с этим версии пакетов будут довольно старые.  


<a id="orgd64f452"></a>

## Ubuntu

Задуман как user-friendly дистрибутив, но кто-то даже ставит его на продакшен-сервера. Не так заморочены за стабильность.  


<a id="org2b2aad1"></a>

# RedHat-based


<a id="orgf530413"></a>

## RedHat

Коммерческий дистрибутив. Много дополнительных плюшек для стабильности и безопасности за платную подписку.  


<a id="org1e74244"></a>

## CentOS

Бесплатная версия RedHat OS. Стремятся быть стабильными, в этом похожи на Debian.  


<a id="org015a5d5"></a>

## Fedora

User-friendly версия RedHat для рабочих станций.  


<a id="orgcdf73a9"></a>

# Другие


<a id="org639aa79"></a>

## Gentoo

Дистрибутив, где все (почти все) программы компилируются из исходных кодов с целью полной оптимизации под тот процессор, на котором программы будут работать.  


<a id="org1488db1"></a>

## Arch Linux

Дистрибутив для опытных пользователей. Стремятся устанавливать только самые последние версии программ и библиотек.  


<a id="org274e9f1"></a>

# Полезные команды


<a id="orgb8253f8"></a>

## Обновление системы

-   deb: apt-get update && apt-get upgrade
-   rpm: yum update


<a id="orge7736bf"></a>

## Поиск пакета

-   deb: apt-cache search <request>
-   rpm: yum search <request>


<a id="org0889050"></a>

## Установка пакета

-   deb: apt-get install <package>
-   rpm: yum install <package>


<a id="orgc9e7dbd"></a>

# initd, systemd

<span class="underline"><span class="underline">[статья про systemd](https://linux-notes.org/pishem-systemd-unit-fajl/?ysclid=l3zhnz2h2c)</span></span>  

![img](init.png)  


<a id="org1201608"></a>

# BSD


<a id="org1471656"></a>

## FreeBSD/OpenBSD/NetBSD

![img](freebsd-logo.png)  


<a id="orgb04b535"></a>

# Доп. информация по Linux

-   <span class="underline"><span class="underline">[Stepik: Введение в Linux](https://stepik.org/course/73/syllabus)</span></span>
-   Брайан У. Керниган, Роб Пайк «Unix. Программное окружение»


<a id="orgcd01408"></a>

# Работа с «удалённым» сервером. SSH

```shell
ssh -p 22 resu@host
```

```shell
scp -P 22 resu@host:/path/to/file ~/
```

```shell
scp -P 2220 \
    ~/file resu@host:/path/to/file
```


<a id="org4895d65"></a>

# SSH Ключи

-   Сгенерировать ключи *~/.ssh/id\_rsa* и *~/.ssh/id\_rsa.pub* для своего хоста (пользователя)  
    
    ```shell
    ssh-keygen
    ```
-   Отправить свой публичный ключ на удалённый сервер (добавит в *~/.ssh/authorized\_keys*)  
    
    ```shell
    ssh-copy-id user@host
    ```
    
    **Никогда не публикуйте свой приватный ключ!** *~/.ssh/id\_rsa*


<a id="orgc95ffc7"></a>

# Добавление алиасов для SSH-хостов

    Host foo
       Hostname 192.168.250.23
       User root
    Host bar
       Hostname 192.168.250.34
       User username
       Port 2221

В файл *~/.ssh/config* можно прописать алиасы для часто используемых хостов и сильно облегчить себе жизнь. Пароль прописать нельзя.  

```shell
ssh bar
```


<a id="org256189c"></a>

# Python + SSH

<span class="underline"><span class="underline">[Paramiko](https://www.paramiko.org/)</span></span>  

```python
from paramiko.client import SSHClient
client = SSHClient()
client.load_system_host_keys()
client.connect(
    "ssh.pvavilin.ru", username="root"
)
stdin, stdout, stderr = (
    client.exec_command("ls -l")
)
print(stdout.read().decode('utf-8'))
```


<a id="orga32322f"></a>

# Ansible

<span class="underline"><span class="underline">[Официальная страница](https://docs.ansible.com/ansible/latest/index.html)</span></span>  

    ---
    - name: My task
      hosts: all
      tasks:
         - name: Leaving a mark
           command: \
           "touch /tmp/ansible_was_here"

Запускаем список задач:  

```shell
ansible-playbook mytask.yaml
```


<a id="org8a7eaf0"></a>

# Salt

<span class="underline"><span class="underline">[Официальная страница](https://docs.saltproject.io/en/getstarted/)</span></span>  
В отличие от Ansible, все сервера-клиенты слушают мастер-сервер и ждут от него указаний. Это позволяет, например, ограничить на клиентах набор допустимых команд.  


<a id="org2b93430"></a>

# Rsync

Позволяет ускорить передачу данных с одного сервера на другой за счёт подсчёта контрольных сумм уже существующих данных. То есть, если на сервере есть данные за вчерашний день, то мы можем "докачать" блоки данных которые поменялись за сегодня.  

```shell
rsync -av source destination
```

Можно использовать и на локальной машине.  


<a id="org827d0ce"></a>

# screen / tmux

При работе с удалённым сервером часто нужно запустить несколько вкладок терминала. screen/tmux позволяют открыть несколько сессий командной строки в рамках одного подключения (можно и на локальной машине). Плюсом если у вас отвалится SSH-подключение, то при этом ваш сеанс работы с screen/tmux не будет потерян в отличие от работы в Bash напрямую. Благодаря последней возможности можно запускать фоновые сервисы без написания специальных скриптов.  

-   **<span class="underline"><span class="underline">[screen](https://www.gnu.org/software/screen/)</span></span>:** старый и вездесущий.
-   **<span class="underline"><span class="underline">[Tmux](https://www.ocf.berkeley.edu/~ckuehl/tmux/)</span></span>:** более user-friendly.


<a id="orgfd58ef8"></a>

# Проверка состояния сервера

-   **uptime:** покажет сколько времени сервер живёт с момента последней перезагрузки. Покажет загрузку процессоров задачами (Load Average)
-   **w:** покажет запущенные сеансы пользователей
-   **top:** покажет статистику по процессам
-   **htop:** user-friendly *top* (install)
-   **iotop:** покажет загрузку ввода/вывода (install)
-   **lsof:** показывает <span class="underline"><span class="underline">[информацию](https://habr.com/ru/company/ruvds/blog/337934/?ysclid=l3y0lg86um)</span></span> об открытых «файлах»
-   **df -h:** покажет состояние примонтированных файловых систем
-   **free -m:** покажет состояние оперативной памяти и файла подкачки
-   **date:** покажет текущее время на сервере


<a id="org82da93b"></a>

# Другие оболочки комнадной строки

*Bash* — это лишь одна из множества <span class="underline">оболочек командной строки</span>, но давно стал стандартом де-факто. Официальным стандартом является очень простая оболочка *sh*.\newline{}Кроме *Bash* пользуется популярностью оболочка *zsh* (в MacOS стандартная оболочка).\newline{} *Bash* и *zsh* совместимы с *sh* — это значит что базовый синтаксис у них соответствует синтаксису *sh*.  


<a id="orge876aac"></a>

# PostgreSQL / MySQL / SQLite / NoSQL

-   PostgreSQL и MySQL (MariaDB) обе профессиональные RDBMS. PostgreSQL может быть чуть сложнее в настройке из-за бóльшего набора возможностей.
-   SQLite — подходит только для очень маленьких задач или для изучения стандарта SQL.
-   NoSQL огромное множество. Выбор делается в соответствии с <span class="underline"><span class="underline">[теоремой CAP](https://ru.wikipedia.org/wiki/%25D0%25A2%25D0%25B5%25D0%25BE%25D1%2580%25D0%25B5%25D0%25BC%25D0%25B0_CAP)</span></span>


<a id="org4e80186"></a>

# Репликация

![img](db_replication.jpg)  


<a id="org3e6861f"></a>

# Шардирование

![img](db_sharding.png)  


<a id="org398a733"></a>

# Nginx

В интернете очень много статики!  

![img](cat.jpg)  


<a id="orgf3e897f"></a>

# Nginx

![img](nginx.jpeg)  


<a id="orgf7d3b5a"></a>

# Cron

    SHELL=/bin/sh
    PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin
    
    # Example of job definition:
    # .---------------- minute (0-59)
    # |  .------------- hour (0-23)
    # |  |  .---------- day of month (1-31)
    # |  |  |  .------- month (1-12) OR jan,feb,mar,apr
    # |  |  |  |  .---- day of week (0-6) (Sunday=0 or 7)
    # |  |  |  |  |       OR sun,mon,tue,wed,thu,fri,sat
    # |  |  |  |  |
    # m h dom mon dow user command
    17 * * * *  root  <command>
    25 6 * * *  root  <command>
    47 6 * * 7  root  <command>
    52 6 1 * *  root  <command>

```shell
man 5 crontab
```

```shell
crontab -e
```


<a id="orgd7c4d09"></a>

# Бэкапы

> Админы делятся на тех, кто делает бэкап и на тех, кто еще не делает.  

<span class="underline"><span class="underline">[Bacula](https://www.bacula.org/)</span></span>  

-   Полный бэкап (например, раз в месяц)
-   Инкрементальный бэкап (например, каждый день)


<a id="org7d8a2c6"></a>

# Logrotate

<span class="underline"><span class="underline">[Документация](https://www.redhat.com/sysadmin/setting-logrotate)</span></span>  
Подчищает старые лог-файлы.  


<a id="orga000e30"></a>

# Дополнительная литература

Если вам стал интересен какой-то из пунктов, то пишите запрос на доп. литературу в #XX\_offtopic или #XX\_library \Winkey[][green!60!white]  


<a id="orga1f06f7"></a>

# Безопасность

-   <span class="underline"><span class="underline">[Генерируйте пароли](https://www.cyberciti.biz/faq/generating-random-password/)</span></span> при помощи *pwgen* или *makepasswd*
-   Проверяйте пароли на стойкость с помощью *cracklib-check*
-   Никогда не работайте под **root**-ом, используйте *sudo*
-   Не пишите файлы в *shared* директории типа */tmp*
-   Лучше использовать нестандартный порт для SSH
-   Процессы лучше заворачивать в docker
-   Безопасность в Linux очень обширная тема. Специалисты по Linux-безопасности крайне востребованы.


<a id="org68d1a6d"></a>

# Вопросы-ответы

![img](questions.jpg)
