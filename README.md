# Passo a passo: Criaçao de um banco de dados 
Tutorial de como criar um banco de dados SQL que organiza as informações de 'livros', 'editora', 'autores' e 'assuntos'.
Este guia será dividido em etapas para demostrar desde a criação de tabelas, chaves e até manipulação/consulta de dados.

## Resumo de uma estrutura SQL 
* __CREATE__ para criar 'Banco de dados' ou 'Tabelas'
* __ALTER__ para adicionar ou modificar colunas 
* __DROP__ para remover 'Banco de dados' ou 'Tabelas'
* __INSERT__ para adicionar registros na tabela
* __UPDATE__ para atualizar os registros 
* __DELETE__ para remover os registros
* __SELECT__ para consultar e visualizar dados

## Passo 1: criação do Banco de Dados e das Tabelas
#### 1.1 Criando o DB

```
CREATE DATABASE biblioteca;
USE biblioteca;
```

#### 1.2 Criando a tabela 'editora'
```
CREATE TABLE editora(
    id_editora INT PRIMARY KEY AUTO_INCREMENT,
    nome_editora VARCHAR(100) NOT NULL,
    pais VARCHAR(50)
);
```

#### 1.3 Criando a tabela 'autor'
```
CREATE TABLE autor(
    id_autor INT PRIMARY KEY AUTO_INCREMENT,
    nome_autor VARCHAR(200),
    data_nascimento DATE
);
```

#### 1.4 Criando a tabela 'assunto'
```
CREATE TABLE assunto(
    id_assunto INT PRIMARY KEY AUTO_INCREMENT,
    descricao_assunto VARCHAR(300) NOT NULL
);
```
#### 1.5 Criando a tabela 'livro'
```
CREATE TABLE livro(
    id_livro INT PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR (150) NOT NULL,
    ano_publicado YEAR,
    FOREING KEY(id_editora) REFERENCES editora(id_editora)
    FOREING KEY (id_autor) REFERENCES autor (id_autor),
    FOREING KEY (id_assunto) REFERENCES assunto (id_assunto)
);
```
#### 1.6 Criando uam tabela EXTRA 
A tabela EXTRA vai servir para exemplificar a exclusão

```
CREATE TABLE extra(
    id INT PRIMARY KEY AUTO_INCREMENT,
    produtos VARCHAR(50) NOT NULL,
    quantidade INT (20) NOT NULL,
    preco DOUBLE NOT NULL
);
```
