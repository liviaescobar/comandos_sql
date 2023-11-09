## Comandos de bancos de dados 


### EXECUTAR O COMANDO
```
CTRL + Enter
```

### Criar database
* Local para criar as tabelas do sistema
```
create database NOME_DATABASE;
```

### Selecionar databse
```
use NOME_DATABASE;
```
<hr>

## Projeto Site E-commerce
* Tabela de usuários
* Tabela de produtos
* Tabela de carrinho de compras

## Criar tabela de usuários
```
create table usuarios(
    id int not null auto_increment, 
    nome varchar(120) not null, 
    email varchar(120) not null, 
    senha varchar(120) not null,
    primary key(id)
);
```
* id: identificador de cada registro
* not null: campo obrigatório
* auto_autoincrement: soma + 1 no último registro de id
* varchar(120): camp de texto com 120 caracteres

### Criar tabela de produtos
```
create table produtos(
    id int not null auto_increment, 
    modelo varchar(120), 
    nome varchar(120) not null,
    valor float not null,
    primary key (id)
);
```

### Criar tabela de carrinho
```
create table carrinho(
    id int not null auto_increment, 
    id_usuario int not null, 
    id_produto int not null,
    primary key(id),
    foreign key(id_usuario) references usuarios(id),
    foreign key(id_produto) references produtos(id)
);
```

* foreign key: chave estrangeira que recebe a referencia de outra tabela
* references: atributo para definir a tabela e o campo estrangeiro

### Inserir usuarios
```
insert into usuarios(nome, email, senha) values('João', 'teste@gmail.com', 'secret');
```

### Inserir produtos
```
insert into produtos(modelo, nome, valor) values('nike', 'camiseta', 129.90);
```

### Inserir carrinho
```
insert into carrinho(id_usuario, id_produto) values(43, 234);
insert into carrinho(id_usuario, id_produto) values(43, 12);
```

### Listar todas as colunas de usuarios
```
select * from usuarios;
```

### Listar os nomes e email dos usuarios
```
select nome, email from usuarios;
```

### Listar usuarios pelo id
```
select * from usuarios where id = 23;
```

### Verificar produtos no carrinho pelo id do usuario
```
select p.none
form pordutos p, carrinho c
where c.id_usuario = 23 AND p.id = c.id_produto;
```