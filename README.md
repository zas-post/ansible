**Запуск ```ansible``` всех хостов**

```ansible -i hosts_inventory.txt all -m ping```

**Запуск ```ansible``` всех хостов Windows серверов**

```ansible -i hosts_inventory.txt windows_servers -m win_ping```
```ansible -i hosts_inventory.txt windows_servers -m win_ping --ask-pass```

**Какие группы и сервера прописаны**
```ansible-inventory --list```
```ansible-inventory --graph```