
#### Instalando o ZesleCP

```
cd /home && sudo curl -o latest -L http://zeslecp.com/release/latest && sudo sh latest
sudo passwd root newpass
```

### Configurando o ZesleCP

```
Ir no Registro.br, acessar o host e EDITAR ZONA.
Criar um tipo A, com www e sem www, e colocar o IP do AWS Instance.
```

### Permitir Acesso Remoto MySQL

```
1. cd /etc/mysql/mysql.conf.d/mysqld.cnf
2. Alterar bind-address = 127.0.0.1 para bind-address = 0.0.0.0
3. Salvar (CTRL+X, Y + ENTER)
4. Restartar: systemctl restart mysql.service
```
