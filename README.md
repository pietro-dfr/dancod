# dancod
show databases;

create database AULA;

use aula;                  

create table aluno(
 id int primary key auto_increment, 
 nome varchar (50) not null,
 cpf varchar (11) unique not null,
 telefone varchar(14),
 id_turma int not null,
 constraint fk_turma foreign key (id_turma) references turma(id)
);

create table turma(
 id int primary key auto_increment,
 nome  varchar (20)  unique not null
);

insert into turma (nome) values ('informática 2024.1'); 
insert into turma (nome) values ('mineraçao 2023.1'); 
insert into turma (nome) values ('ADM 2030.1'); 
insert into turma (nome) values ('agropecuaria 2024.1'); 


desc aluno;

desc turma;

drop database aula;

insert into aluno (nome, cpf, telefone, id_turma) values ('Danilo', '12345678901' ,'85855255452552',1);
insert into aluno (nome, cpf, telefone, id_turma) values ('Geugres', '01987654321' ,'858588852552',1);

select * from aluno order by id asc;

select * from turma order by id asc;

select * from aluno where id_turma = 1;

delete from aluno where id = 1;

update aluno set nome = 'clesio' where id = 3;

