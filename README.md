README - Sistema Básico de Usuários e Produtos em PHP + PostgreSQL
Descrição

Projeto simples em PHP com banco de dados PostgreSQL para gerenciar usuários e produtos, com páginas para exibir listas em formato de grid.

Estrutura do Projeto
/xampp/htdocs/nicolas/
│
├── conexao.php      # Arquivo de conexão com o banco PostgreSQL
├── menu.php         # Menu de navegação incluído nas páginas
├── produtos.php     # Página que lista os produtos
├── usuarios.php     # Página que lista os usuários (ex: admin)
├── pedidos.php      # (opcional) Página para gerenciar pedidos
├── index.php        # Página inicial
├── README.md        # Este arquivo
Requisitos
PHP instalado (recomendo usar XAMPP)
PostgreSQL instalado e rodando
Banco de dados configurado com as tabelas usuario e produto
Extensão pgsql do PHP habilitada
Como rodar
Coloque os arquivos na pasta do servidor web (htdocs/nicolas/ no XAMPP).
Configure o arquivo conexao.php com os dados corretos do seu banco PostgreSQL (host, usuário, senha, database).
Acesse via navegador: http://localhost/nicolas/index.php
Navegue entre as páginas usuarios.php e produtos.php pelo menu.
Estrutura básica das tabelas
Tabela usuario
CREATE TABLE usuario (
    idusuario INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    password VARCHAR(32) NOT NULL,
    status BOOLEAN DEFAULT true
);
Tabela produto
CREATE TABLE produto (
    idproduto INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    produtonome VARCHAR(50) NOT NULL,
    produtopreco NUMERIC(10,2) NOT NULL,
    produtostatus BOOLEAN DEFAULT true
);
Dicas importantes
Sempre inclua o menu.php no topo das suas páginas para manter a navegação.
Use include "menu.php"; e require "conexao.php"; para facilitar o reaproveitamento do código.
Ajuste os nomes das colunas no código PHP para refletir os nomes corretos do banco.
