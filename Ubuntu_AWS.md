## Atualizando ambiente
```$ sudo apt-get update```

## Instalando o MySQL
```$ sudo apt-get install mysql-server```

#### Criando a senha root
```
$ sudo mysql_secure_installation utility

Digite: Y

Digite: 1 (MEDIUM)

=> Irá pedir a senha, digite-a, e depois selecione Y para todas as perguntas.
```


#### Iniciando o MySQL Server
```$ sudo systemctl start mysql```

#### Restartar o MySQL Server
```$ sudo systemctl restart mysql```

#### Colocar MySQL na Inicialização do servidor
```$ sudo systemctl enable mysql```

#### Configurando o MySQL
```
//Logar como root
$ sudo mysql -u root -p mysql (usar a senha criada um pouco acima)

//Mostrar todos os usuários
mysql> SELECT User,Host FROM mysql.user;

//Adicionar um usuário
mysql> CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypass';

//Permissões
mysql> GRANT ALL ON *.* TO 'myuser'@'%';

mysql> FLUSH PRIVILEGES;

//Remover um usuário
mysql> DROP USER 'remote'@'my-ip'

//Mostrar Conexões
mysql> show processlist;
```

#### Liberando o acesso remoto ao MySQL
```
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf

//Alterar
- bind-address = 127.0.0.1
//Para
- bind-address = 0.0.0.0

Crtl + X
Y
```

## Instalando o Node, NPM e Yarn

```
sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates && curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
```

```
sudo apt -y install nodejs
```

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

```
sudo apt update && sudo apt install yarn
```


## Instalando o gerenciador de versões do Node o "nvm"

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

```
source ~/.bashrc
```

```
nvm --version
```


## Instalando uma versão do Node com o NVM

```
nvm install v10.13.0
```

```
npm -v
```

```
node -v
```


## Instalando o PM2

```
npm i -g pm2
```

```
pm2 list
```

```
pm2 start index.js --name site1
```

