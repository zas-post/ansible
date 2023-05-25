**Запуск ```ansible``` всех хостов**

```ansible -i hosts_inventory.txt all -m ping```

**Запуск ```ansible``` всех хостов Windows серверов**

```ansible -i hosts_inventory.txt windows_servers -m win_ping```

```ansible -i hosts_inventory.txt windows_servers -m win_ping --ask-pass```

**Какие группы и сервера прописаны**

```ansible-inventory --list```

```ansible-inventory --graph```


```ansible all -m setup```  - информация по серверам

```ansible all -m shell -a "uptime"```  - запуск команд на серверах

```ansible all -m command -a "ls /var"```  - такой как shell, но не через shell :)


```ansible all -m copy -a "src=file.txt dest=/home mode=777" -b```  - копирование файла с sudo (-b)

```ansible all -m file -a "path=/home/file.txt state=absent" -b```  - удаление файла с sudo (-b)

```ansible all -m get_url -a "url=https://<url link> dest=/home" -b```  - скачивание с интернета с sudo (-b)

```ansible all -m yum -a "name=nano state=latest(or installed)" -b```  - установка прорамм с sudo (-b)

```ansible all -m yum -a "name=nano state=removed" -b```  - удаление прорамм с sudo (-b)

```ansible all -m uri -a "url=https://google.com" -b```  - проверка подсоединения к сайту

```ansible all -m uri -a "url=https://google.com return_content=yes" -b```  - проверка подсоединения к сайту, посмотреть контент с сайта

