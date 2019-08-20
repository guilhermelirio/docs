
## Instalando o ZesleCP

```
cd /home && sudo curl -o latest -L http://zeslecp.com/release/latest && sudo sh latest
sudo passwd root
sudo passwd ubuntu 
```

### Configurando o ZesleCP

```
Ir no Registro.br, acessar o host e EDITAR ZONA.
Criar um tipo A, com www e sem www, e colocar o IP do AWS Instance.
```

### Permitir Acesso Remoto MySQL

```
1. Capturar a senha do usuario debian-sys: sudo cat /etc/mysql/debian.cnf
2. mysql> SELECT User FROM mysql.user;
3. mysql> GRANT ALL PRIVILEGES ON *.* TO 'remote'@'%' IDENTIFIED BY 'newpassword';
4. sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
5. Alterar bind-address = 127.0.0.1 para bind-address = 0.0.0.0
6. Salvar (CTRL+X, Y + ENTER)
7. Restartar: systemctl restart mysql.service
```

### Alterar Senha do root

```
UPDATE mysql.user SET authentication_string = PASSWORD('MyNewPass'), password_expired = 'N' WHERE User = 'root' AND Host = 'localhost';
```

### Configurar RoundCube (ZesleCP)

```
1. Acessar /usr/local/zesle/webmail/roundcube/SQL e copiar o arquivo mysql.initial.sql
2. Conectar via phpmyadmin/heidisql e criar um banco chamado: zen_roundcube
3. Executar o mysql.inital.sql dentro do bd zen_roundcube
4. Via SSH, digitar: sudo cat /usr/local/zesle/webmail/roundcube/config/config.inc.php e pegar o valor de $pass.
5. Acessar o mysql como root: mysql -u root -p
6. Criar um nome usuário: GRANT ALL PRIVILEGES ON *.* TO 'zes_roundcube'@'localhost' IDENTIFIED BY 'senha_do_config.inc.php';
```
