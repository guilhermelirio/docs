## Entrar no user root
```$ sudo su -```

## Atualizando ambiente
```$ sudo apt-get update```

## Instalando o Postgres
```$ sudo apt-get install postgresql postgresql-contrib```

## Alterando o usuário
```su - postgres```

## Entrando no Postgres
```postgres@$ psql```

## Saindo do Postgres
```postgres=# \q```

## Criando USUÁRIO e SENHA de acesso ao BD
```postgres@$ createuser --interactive --pwprompt ```

## Digitar os dados
```
Enter name of role to add: <name of user>
Enter password for new role: <password of user>
Enter it again: <password of user>
Shall the new role be a superuser? (y/n) y
```

## Criando o BD associado ao USUÁRIO
```postgres@$ createdb -O <usuario> <banco de dados>```

## Liberar o Acesso remoto (alterar o número de acordo com a versão do Postgres)
``` nano /etc/postgresql/13/main/postgresql.conf```

### Alterar a linha:
```#listen_addresses = 'localhost'```
por
```listen_addresses = '*'```

CRTL + X -> Y

## Liberar Acesso à todos IP's
```nano /etc/postgresql/10/main/pg_hba.conf```

### Alterar a linha:
```
# IPv4 local connections:
host    all             all             127.0.0.1/32            md5
```
por
```
# IPv4 local connections:
host    all             all             0.0.0.0/0            md5
```
CRTL + X -> Y

## Reiniciar o Postgres
```$ sudo systemctl restart postgresql```
