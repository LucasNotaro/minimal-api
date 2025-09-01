#  Sistema de Gestão de Veículos - Minimal API

Este projeto foi desenvolvido como parte dos estudos no bootcamp **DIO – GFT Start 7 .NET**, com base nas videoaulas do programa.

Consiste em uma API REST em **.NET 9** para gerenciamento de veículos e administradores.

## Tecnologias utilizadas

- **.NET 9** - Framework principal
- **Entity Framework Core** - ORM para persistência
- **MySQL** - Banco de dados relacional  
- **JWT Bearer** - Autenticação e autorização
- **Swagger** - Documentação interativa

## Funcionalidades

### Autenticação
- Login de administradores com JWT
- Controle de acesso por perfil (Adm, Editor)

### Administradores
- CRUD completo
- Listagem paginada
- Busca por ID
- Validação de dados

### Veículos
- CRUD completo
- Listagem paginada
- Busca por ID
- Validação de ano (mínimo 1950)

## Pré-requisitos

- .NET 9 SDK
- MySQL Server
- Visual Studio ou VS Code

## Configuração
```bash
1. Clone o repositório
   git clone https://github.com/LucasNotaro/minimal-api
   cd minimal-api

2. Configure a conexão no arquivo Api/appsettings.json com os dados do MySQL

3. Execute as migrações
   cd Api
   dotnet ef database update

4. Rode a aplicação
   dotnet run
```
## Endpoints principais

### Autenticação
- POST /administradores/login - Login de administrador

### Administradores
- GET /administradores - Lista todos (perfil Adm)
- GET /administradores/{id} - Busca por ID (perfil Adm)
- POST /administradores - Criação (perfil Adm)

### Veículos
- GET /veiculos - Lista todos (requer login)
- GET /veiculos/{id} - Busca por ID (perfil Adm/Editor)
- POST /veiculos - Criação (perfil Adm/Editor)
- PUT /veiculos/{id} - Atualização (perfil Adm)
- DELETE /veiculos/{id} - Exclusão (perfil Adm)

## Autenticação

A API utiliza JWT Bearer.

1. Faça login em /administradores/login
2. Use o token no header Authorization: Bearer {token}

## Documentação

A documentação Swagger pode ser acessada em:
- **HTTP**: http://localhost:5299/swagger
