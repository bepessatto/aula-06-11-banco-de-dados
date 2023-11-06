## Comandos de banco de dados


### Criar database
* local para criar as tabelas do sistema

```
create database NOME_DATABASE
```

### Executar o comando 

```
CTRL + ENTER
```

### Selecionar database

```
use NOME_DATABASE
```

<hr>


## Projeto site ecommerce 
* Tabela de usuários 
* Tabela de produtos
* tabela de carrinho de compras

### Criar tbela de usuarios
```
create table usuário(
    id int not null auto_autoincrement,
    nome varchar(120) not null,
    email varchar(120) not null,
    senha varchar(120) not null,
    primary key(id)
);
```
* id: identificador de cada registro
* not null: campo obrigatório, não pode ser nulo
* auto_increment: soma +1 no último registro de id
* varchar (120): campo de texto com 120 caracteres 

### Criar tabela de produtos

```
 cretae table produtos (
    id int not null auto_increment,
    modelo varchar(120),
    noe varchar(120) not null,
    valor float not null,
    primary ey(id)
 );
```

### Criar tabela de carrinho

```
create table carrinho(
    id  int not null auto_increment,
    id_usuario int not null,
    id_produto int not null,
    primary kei(id),
    foreign key(id_usuario) references usuarios(id),
    foreign key(id_produtos) references produtos(id),
);
```
* foreign key: chave estrangeiro que recebe a referencia de outra tabela
* references: atributo para definir a tabela e o campo estrangeiro


EXEMPLO DE COMOO FUNCIONA: 

usuarios
3 andrei

produtos
5 tenis
6 meia
9 rgata

carrinho
id id_usuario id_produto
1      3           6
2      3           5


### inserir usuarios

```
insert into usuarios(nome, email, senha) values('Renato Gaucho', 'teste@teste.com', 'secret');
```

### Inserir produto

```
insert into produtos(modelo, nome, valor) values('nike sb', 'camiseta', '129.90');
```

### Inser carrinho


```
insert into carrinho(id_usuario, id_produtos) values(43, 234);
```

### Listar todas as colunas usuarios

```
select * from usuarios;
```

### Listar os nomes dos usuarios

```
select nome from usuarios;
```

### Listar nomes e email dos usuarios

```
select nome, email from usuarios;
```

### Listar usuarios pelo id

```
select * from ususarios where id = 43;
```

### Verificar produtos no carrinho pelo id do usuario

```
select p.nome from produtos p, carrinho p  where c.id_usuario = 43 AND p.id = c.id_produto;
```
