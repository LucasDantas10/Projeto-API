<div align="center">

🔧 API de Manutenção

CRUD de chamados desenvolvido em PHP + PostgreSQL

</div>

📌 Sobre o projeto

Este projeto foi desenvolvido como uma atividade de Desenvolvimento de Sistemas, com o objetivo de criar uma API para controlar chamados de manutenção.

A API permite cadastrar, consultar, atualizar e excluir chamados utilizando os métodos HTTP GET, POST, PUT e DELETE.

🛠️ Tecnologias

Tecnologia

Utilização

🐘 PHP

Desenvolvimento da API

🐘 PostgreSQL

Banco de dados 

🔌 PDO

Conexão com o banco

📦 JSON

Envio e recebimento dos dados

🧪 Postman

Testes da API

📂 Estrutura do projeto

api-manutencao/
│
├── chamados.php
├── conexao.php
│
└── prints/
    ├── 01-post-dados.png
    ├── 02-get-chamado.png
    ├── 03-put-atualizacao.png
    ├── 04-get-atualizado.png
    ├── 05-delete.png
    └── 06-get-final.png

🗄️ Banco de dados

O projeto utiliza o banco manutencao.

CREATE DATABASE manutencao;

\c manutencao;

CREATE TABLE chamados (
    id SERIAL PRIMARY KEY,
    equipamento VARCHAR(150) NOT NULL,
    setor VARCHAR(100) NOT NULL,
    descricao TEXT NOT NULL,
    prioridade VARCHAR(20) NOT NULL,
    status VARCHAR(30) NOT NULL
);

📋 Campos da tabela

Campo

Descrição

id

Identificação do chamado

equipamento

Equipamento relacionado ao problema

setor

Setor onde está o equipamento

descricao

Descrição do problema

prioridade

Prioridade do chamado

status

Situação atual do chamado

🔗 Endpoints

Método

Função

🟢 GET

Listar chamados

🔵 POST

Cadastrar chamado

🟡 PUT

Atualizar chamado

🔴 DELETE

Excluir chamado

URL utilizada nos testes:

http://localhost:8000/chamados.php

🟢 POST — Cadastrar chamado

JSON enviado

{
    "equipamento": "Computador",
    "setor": "Informática",
    "descricao": "Computador não liga",
    "prioridade": "alta",
    "status": "aberto"
}

Resposta

{
    "Mensagem": "Chamado cadastrado com sucesso!"
}

📸 Teste no Postman



🔵 GET — Consultar chamados

O método GET retorna os chamados cadastrados no banco de dados.

Exemplo de resposta

[
    [
        {
            "id": 1,
            "equipamento": "Computador",
            "setor": "Informática",
            "descricao": "Computador não liga",
            "prioridade": "alta",
            "status": "aberto"
        }
    ]
]

📸 Teste no Postman



🟡 PUT — Atualizar chamado

JSON enviado

{
    "id": 1,
    "equipamento": "Computador",
    "setor": "Informática",
    "descricao": "Computador foi trocado",
    "prioridade": "media",
    "status": "concluido"
}

Resposta

{
    "Mensagem": "Chamado atualizado com sucesso!"
}

📸 Teste no Postman



🔎 Conferindo a atualização

Depois do PUT, foi realizado um novo GET para verificar os dados atualizados.



🔴 DELETE — Excluir chamado

JSON enviado

{
    "id": 1
}

Resposta

{
    "Mensagem": "Chamado excluído com sucesso!"
}

📸 Teste no Postman



🔎 Conferindo a exclusão

Após o DELETE, foi realizado um novo GET para verificar se o chamado havia sido removido.



✅ Validações

A API possui algumas validações antes de realizar as operações:

Campos obrigatórios devem ser preenchidos.

A prioridade deve ser:

baixa

media

alta

O status deve ser:

aberto

em andamento

concluido

🔄 Fluxo do CRUD

          ┌──────────────┐
          │   POST       │
          │   Cadastrar  │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │  PostgreSQL  │
          │   chamados   │
          └──────┬───────┘
                 │
       ┌─────────┼─────────┐
       ▼         ▼         ▼
     GET        PUT      DELETE
   Consultar  Atualizar   Excluir

🎯 Resultado

A API foi desenvolvida e testada utilizando os quatro principais métodos do CRUD:

CREATE → READ → UPDATE → DELETE

Os testes foram realizados no Postman, utilizando uma API local em PHP conectada ao PostgreSQL.

<div align="center">

Desenvolvido para a atividade de Desenvolvimento de Sistemas

PHP • PostgreSQL • PDO • JSON • Postman

</div>