-- Criação do Banco de Dados

---Criação de tabelas

CREATE TABLE Alunos 
( 
 codigo_aluno VARCHAR(10) PRIMARY KEY,  
 curso VARCHAR(80) NOT NULL,  
 nome_aluno VARCHAR(80) NOT NULL,  
 email VARCHAR(50) NOT NULL,  
 telefone VARCHAR(11) NOT NULL,  
 codigosede INT 
); 

CREATE TABLE Sede 
( 
 endereco VARCHAR (80) NOT NULL,  
 nome_sede VARCHAR(80) NOT NULL,  
 codigosede INT PRIMARY KEY
); 

ALTER TABLE Alunos ADD FOREIGN KEY(codigosede) REFERENCES Sede (codigosede)
ALTER TABLE Sede ADD FOREIGN KEY(codigosede) REFERENCES Sede (codigosede)


----
Consultando tabelas
Select * From alunos;

Select * From sede;

---Inserir Dados
--- sede
INSERT INTO sede (codigosede,nome_sede,endereco) VALUES (1,'Dc Sul','Av,W...');
INSERT INTO sede (codigosede,nome_sede,endereco) VALUES (2,'Dc Aldeota','Av.Sd');



--- Inserir Dados
--- alunos

INSERT INTO alunos (codigo_aluno,nome_aluno,email,curso,telefone,codigosede) VALUES (1, 'aaaa','a@fj','DA Analytcs', '3333333',2),
                                                                                     (3, 'aaaa','a@fj','DA Analytcs', '3333333',1),
																					 (5, 'aaaa','a@fj','DA Analytcs', '3333333',2),
																					 (4, 'aaaa','a@fj','DA Analytcs', '3333333',2);

--- TESTE ERRO: Em virtude de ter uma chave
INSERT INTO alunos VALUES (7, 'aaaa','a@fj','DA Analytcs', '3333333',3);

--- TESTE INSERIR DADO ERRADO: Dados abaixo o e-mail não tem o sinal de @, logo, vai dar certo, mas será inerido o dado errado
INSERT INTO alunos VALUES (8, 'aaaa','adfj','DA Analytcs', '3333333',3);

--- TESTE 3 erro número 3 que não contém

INSERT INTO alunos (codigo_aluno,nome_aluno,email,curso,telefone,codigosede) VALUES (9, 'aaaa','a@fj','DA Analytcs', '3333333',3);

--- TESTE 4 inserir dados na ordem
INSERT INTO alunos (codigo_aluno,nome_aluno,email,curso,telefone,codigosede) VALUES (10, 'aaaa','a@fj','DA Analytcs', '3333333',2);

																					
--- TESTE DE NULO
INSERT INTO alunos (codigo_aluno,nome_aluno,email,curso,telefone) VALUES (11, 'aaaa','a@fj','DA Analytcs', '3333333');







