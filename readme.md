# 💳 Desafio Técnico - Sistema de Propostas de Crédito (Backend)

Bem-vindo(a)! Este é o desafio técnico para candidatos à vaga de **desenvolvedor(a) backend**. Aqui você encontrará todas as instruções para desenvolver uma aplicação RESTful baseada em Spring Boot, com foco em boas práticas, clareza e organização.

---

## 🎯 Objetivo

Criar uma aplicação backend em **Java com Spring Boot e Maven** que implemente um sistema de propostas de crédito, com persistência em banco de dados e manipulação de propostas e parcelas.

---

## 🛠️ Instruções

- Crie um **repositório público** no GitHub, com este desafio como base.
- Desenvolva a aplicação conforme os requisitos abaixo.
- Inclua neste `README.md`:
  - Instruções de como rodar a aplicação localmente.
  - Endpoints da API com exemplos de uso, se possível.

---

## 📦 Requisitos técnicos

- Java 17+ (ou versão mais recente estável)
- Spring Boot
- Maven
- PostgreSQL
- JPA/Hibernate (ou alternativa compatível)

---

## 🐳 Banco de Dados

Utilize **uma das opções abaixo**:

- ✅ PostgreSQL via Docker Compose (**preferencial**, arquivo incluso neste repositório)
- Supabase
- Fly.io
- MongoDB Atlas

> Caso escolha uma opção diferente do `docker-compose`, documente a decisão no README com instruções para uso.

---

## 📄 Funcionalidades da aplicação

### 📥 Criar Proposta

**Request:**

```json
{
  "cpf": "00011122233",
  "valorSolicitado": 1000.00,
  "quantidadeParcelas": 12,
  "dataSolicitacao": "2023-10-01"
}
```

**Regras:**

- Armazenar a proposta de crédito e gerar as parcelas relacionadas (1 proposta = N parcelas).
- As parcelas devem ser criadas com o status `"Em Aberto"`.
- Deve retornar o **ID da proposta criada**.
- Não deve permitir inserção de propostas com:
  - CPF inválido
  - Valor solicitado menor que R$ 100,00
  - Quantidade de parcelas menor que 1 ou maior que 24

---

### 🔍 Buscar Proposta por ID

**Regras:**

- Retornar os dados da proposta e suas parcelas.
- Retornar erro caso a proposta não exista.

---

### 📄 Listar Propostas (paginado)

**Regras:**

- Listar todas as propostas paginadas.
- Retornar as propostas e suas parcelas.
- Permitir parâmetros de paginação via query string.

---

### 💵 Pagamento de Parcela

**Regras:**

- Deve receber o ID da proposta e o número da parcela.
- Retornar erro caso a proposta ou parcela não exista.
- Realizar o pagamento da parcela e atualizar o status para `"Paga"`.

---

## 🔧 Diferenciais (opcionais)

- Documentação da API (Swagger/OpenAPI ou Postman)
- Testes unitários e/ou de integração
- Deploy da aplicação em algum provedor
- Alterar o `docker-compose.yml` para subir a aplicação junto ao banco de dados

---

## 📬 Entrega

- Repositório **público** com o código-fonte da aplicação.
- README com instruções de execução e explicações.
- Enviar o link para nossa equipe quando finalizado.

---

Boa sorte no desafio! 🚀