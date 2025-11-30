# Protótipo de Blog e Rede Social Digital

![Tela leitura usuários e tags](https://github.com/user-attachments/assets/0deb3f84-c0d8-4436-8c4b-42b9e4665cc7)

Este projeto é uma aplicação que gerencia Usuários, Tags e Posts.

Nela pode-se realizar operações CRUD de Usuários, Tags e Posts.

A aplicação é dividida em dois componentes principais:
- Backend
- Frontend

Ambos seguindo boas práticas de desenvolvimento modernas para garantir robustez, escalabilidade e fácil manutenção.

## Tabela de Conteúdos
- [Arquitetura](#arquitetura)
- [Tecnologias](#tecnologias)
- [Instalação](#instalação)
- [Uso](#uso)
- [API Backend](#backend)
- [Frontend](#frontend)
- [Testes](#testes)

## Arquitetura

A aplicação segue uma arquitetura baseada em:
- padrão de repositórios (Repository Pattern).
- princípios SOLID.

Assim, garante a escalabilidade e manutenção eficiente.

O frontend também obedece princípios SOLID.

A comunicação entre frontend e backend é realizada por meio de API RESTful.

### Componentes Principais:
- **Backend**: Responsável pela lógica de negócios, acesso a dados e exposições da API.
- **Frontend**: Interface do usuário desenvolvida em React.js.
- **Banco de Dados**: Utiliza MySQL para persistência de dados.

## Tecnologias

- **Backend**: PHP, Laravel, PSR, Repository Pattern, SOLID Principles
- **Frontend**: React.js, SOLID Principles
- **Banco de Dados**: MySQL, SQLite
- **Testes**: PHPUnit, Mockery
- **Documentação da API**: Swagger
- **Docker**: Para containerização

## Instalação

### Pré-requisitos
- Docker e Docker Compose

### Passos

1. Clone o repositório:
   ```bash
   git clone git@github.com:JoabioVilela/blog-e-rede-social-digital.git

2. Navegue até a raiz do projeto:
	```bash
    cd blog-e-rede-social-digital
    
3. Suba os contêineres Docker:
	```bash
    docker compose up -d --build

A API estará disponível em: http://localhost:8000

 ![Tela app up](https://github.com/user-attachments/assets/9332d2fa-ee3e-4d1f-89b8-4a3b9fb8e1b7)

   
A documentação estará em: http://localhost:8000/api/documentation

![Documentação](https://github.com/user-attachments/assets/69eafd2e-43f0-45a1-b666-0e86c49575bd)


O frontend estará disponível em: http://localhost:3000

 ![Tela principal](https://github.com/user-attachments/assets/fdec3a3d-f1c6-41d3-b55b-d960181d9cc5)


É natural que leve alguns segundos para que os serviços estejam completamente prontos, mesmo depois de os contêineres terem sido iniciados.

## Uso

Tela inicial:

![Tela principal](https://github.com/user-attachments/assets/9bdabe80-80e9-444e-a14b-9f189390b9ee)

Tela cadastro de usuário:

![Tela cadastro usuário](https://github.com/user-attachments/assets/c9628b1e-c990-48f5-ae2d-e80b7d1ca05b)

Tela edição de usuário:

![Tela edição usuário](https://github.com/user-attachments/assets/38b82a3a-76cf-4c38-948d-24caa5f8bd72)

Tela cadastro de post:

![Tela cadastro post](https://github.com/user-attachments/assets/afea2c43-a4b3-43c2-aee6-c4b8a503ffc2)

Tela edição de post:

![Tela edição posts](https://github.com/user-attachments/assets/4a2e27ec-81f1-4d75-b1cc-4a5c1868001c)

Tela exibição de posts:

![Tela leitura posts](https://github.com/user-attachments/assets/77a45d00-d7cf-4c84-8122-99dc5ff914ea)


## Detalhes

### Backend

As requisições à API são feitas por meio de localhost:8000/api

Exemplo de requisição para criar um novo usuário:

POST /api/usuarios

Content-Type: application/json

![Tela POST Usuario](https://github.com/user-attachments/assets/2a348d6d-3030-4787-92fd-ba63a193da65)


### Estrutura

- `routes/api.php`: As rotas de UsuarioController, TagController e PostController.
- `app/Http/Controllers`: Os controllers UsuarioController, TagController e PostController.
- `app/Http/Requests`: Os form request de store e de update com as regras de validações e mensagens de feedback para requisições e de Usuario, Tag e Post.
- `app/Models`: Os models Usuario, Tag e Post.
- `app/Providers/AppServiceProvider.php`: Todos os bindings entre repositories interfaces e repositories eloquent.
- `app/Repositories`: As interfaces e eloquent.
- `app/Services`: Os services UsuarioService, TagService e PostService.
- `tests/Unit`: Os testes unitários dos services e dos repositories de Usuario, Tag e Post.
- `.env`: As variáveis de ambiente referente à conexão do banco de dados MySQL e a outros aspectos.
- `.env.testing`: As variáveis de ambiente referente à conexão de banco de dados com o SQLite para realização dos testes unitários.
- `Dockerfile`: PHP 8.3 e dependências e o driver do MySQL.
- `docker-compose.yml`:  Dockerfile do projeto e o MySQL 8.
- `phpunit.xml`: Configurações do PHPUnit.

Veja:

![Estrutura backend](https://github.com/user-attachments/assets/bd010654-3d2b-4bbb-b933-49b7b84d1b0c)

### Frontend

- O frontend foi desenvolvido usando React.js, useState, useEffect e Axios.

- Oferece operações de cadastro, exibição, edição e exclusão dos registros de usuários, tags e posts.

- Ele consome a API backend para fornecer dados dinâmicos.

### Estrutura

- `src/`: Contém todos os componentes React.
- `src/components`: Contém os componentes Modal, UsuarioManager, TagManager e PostManager.
- `src/services`: Contém os serviços UsuarioService, TagService e PostService.

Veja:

  ![Estrutura frontend](https://github.com/user-attachments/assets/edcb1573-def7-4ad5-b771-38e10725d687)


## Testes

A aplicação usa PHPUnit para testes unitários.

Para rodar os testes:

1. Navegue até o diretório da API:
	```bash
	cd api_rede_social
	
2. Execute os testes:
	```bash
	php artisan test

![Testes Unitários](https://github.com/user-attachments/assets/cb4ee26b-0257-4d86-9c20-e163937b9a97)
 

## Licença

Este projeto está licenciado sob a [MIT License](LICENSE).
