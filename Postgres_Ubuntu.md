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

### Subsitituir as linhas:

