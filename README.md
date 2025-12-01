# **API Autobots atvi — Spring Boot**

##Tecnologias Utilizadas:

-Java 17
-Spring Boot 2.6.3
-Spring Web
-Spring Data JPA
-H2 Database
-Lombok
-Maven

---

##Como Executar o Projeto
  
###Pré-requisitos:

- JDK 17 instalado
- Maven instalado


###Rodando o projeto:

- mvn spring-boot:run


###A API estará disponível em:

- http://localhost:8080


###Configuração padrão:

JDBC URL: jdbc:h2:mem:testdb

User: sa

Password: (em branco)

---

##**Endpoints da API**

###A API contém 4 módulos principais:

/cliente
/documento
/endereco
/telefone

**Todos possuem endpoints CRUD padronizados.**

####1. CLIENTE
GET /cliente/cliente/{id}

Retorna um cliente pelo ID.

Exemplo de resposta:

{
  "id": 1,
  "nome": "Nome Completo",
  "nomeSocial": "Nome Social",
  "dataNascimento": "2000-01-01",
  "dataCadastro": "2023-01-01",
  "documentos": [],
  "endereco": null,
  "telefones": []
}


GET /cliente/clientes

Retorna todos os clientes cadastrados.


POST /cliente/cadastro

Cadastra um novo cliente.

Exemplo de requisição:

{
  "nome": "Nome Completo",
  "nomeSocial": "Nome Social",
  "dataNascimento": "2000-01-01",
  "dataCadastro": "2023-01-01",
  "documentos": [
    { "tipo": "RG", "numero": "123456789" }
  ],
  "endereco": {
    "estado": "SP",
    "cidade": "Cidade Exemplo",
    "bairro": "Centro",
    "rua": "Rua Exemplo",
    "numero": "100",
    "codigoPostal": "12345-000",
    "informacoesAdicionais": "Apartamento 1"
  },
  "telefones": [
    { "ddd": "12", "numero": "999999999" }
  ]
}


PUT /cliente/atualizar

Atualiza os dados de um cliente já existente.

Exemplo:

{
  "id": 1,
  "nome": "Nome Atualizado",
  "nomeSocial": "Nome Social Atualizado",
  "dataNascimento": "2000-01-01",
  "dataCadastro": "2023-01-01"
}


DELETE /cliente/excluir

Remove um cliente com base no ID informado.

Exemplo:

{
  "id": 1
}


###2. DOCUMENTO
GET /documento/documentos

Retorna todos os documentos cadastrados.


GET /documento/documento/{id}

Retorna um documento pelo ID.


POST /documento/cadastro

Exemplo:

{
  "tipo": "CPF",
  "numero": "00011122233"
}


PUT /documento/atualizar

Exemplo:

{
  "id": 1,
  "tipo": "RG",
  "numero": "999888777"
}


DELETE /documento/excluir

Exemplo:

{
  "id": 1
}


###3. ENDEREÇO
GET /endereco/enderecos

Retorna todos os endereços.


GET /endereco/endereco/{id}

Retorna um endereço pelo ID.


POST /endereco/cadastro

Exemplo:

{
  "estado": "SP",
  "cidade": "Cidade Exemplo",
  "bairro": "Centro",
  "rua": "Rua Exemplo",
  "numero": "200",
  "codigoPostal": "12000-000"
}


PUT /endereco/atualizar

Exemplo:

{
  "id": 1,
  "cidade": "Cidade Atualizada",
  "rua": "Nova Rua"
}


DELETE /endereco/excluir

Exemplo:

{
  "id": 1
}


###4. TELEFONE
GET /telefone/telefones

Retorna todos os telefones cadastrados.


GET /telefone/telefone/{id}

Retorna um telefone pelo ID.


POST /telefone/cadastro

Exemplo:

{
  "ddd": "12",
  "numero": "988887777"
}


PUT /telefone/atualizar

Exemplo:

{
  "id": 1,
  "ddd": "11",
  "numero": "977777777"
}


DELETE /telefone/excluir

Exemplo:

{
  "id": 1
}
