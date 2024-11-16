# Django API com JWT Autenticação

Este projeto fornece uma API Django configurada com autenticação baseada em JWT (JSON Web Token) usando `djangorestframework_simplejwt`.

## Requisitos

- Python 3.8 ou superior
- Django 3.2 ou superior
- Django REST Framework
- djangorestframework_simplejwt

## Instalação e Início

1. **Clone o repositório:**

   ```bash
   git clone <url_do_repositorio>
   cd <nome_do_repositorio>
Crie e ative um ambiente virtual:

bash
Copiar código
python -m venv venv
source venv/bin/activate  # no Windows, use `venv\Scripts\activate`
Instale as dependências:

bash
Copiar código
pip install -r requirements.txt
Aplique as migrações do banco de dados:

bash
Copiar código
python manage.py migrate
Crie um superusuário (opcional, para acessar o admin):

bash
Copiar código
python manage.py createsuperuser
Inicie o servidor de desenvolvimento:

bash
Copiar código
python manage.py runserver
Agora a API estará acessível em http://127.0.0.1:8000.

Endpoints da API
1. Login (Geração de Token JWT)
URL: /api/accounts/token/

Método: POST

Corpo da Requisição (JSON):

json
Copiar código
{
    "email": "usuario@exemplo.com",
    "password": "senha"
}
Resposta (200 OK):

json
Copiar código
{
    "access": "token_de_acesso",
    "refresh": "token_de_refresh"
}
2. Refresh Token
URL: /api/accounts/token/refresh/

Método: POST

Corpo da Requisição (JSON):

json
Copiar código
{
    "refresh": "token_de_refresh"
}
Resposta (200 OK):

json
Copiar código
{
    "access": "novo_token_de_acesso"
}
3. Cadastro de Usuário (Registro)
URL: /api/accounts/register/

Método: POST

Corpo da Requisição (JSON):

json
Copiar código
{
    "email": "novo_usuario@exemplo.com",
    "password": "senha_forte",
    "confirm_password": "senha_forte"
}
Resposta (201 Created):

json
Copiar código
{
    "id": 1,
    "email": "novo_usuario@exemplo.com",
    "born_year": "1990-01-01",
    "is_active": true,
    "is_superuser": false,
    "is_staff": false
}
4. Listar Usuários (Protegido por Autenticação)
URL: /api/accounts/

Método: GET

Cabeçalho de Autorização:

http
Copiar código
Authorization: Bearer <seu_token_aqui>
Resposta (200 OK):

json
Copiar código
[
    {
        "id": 1,
        "email": "usuario@exemplo.com",
        "born_year": "1985-06-15",
        "is_active": true,
        "is_superuser": false,
        "is_staff": false
    },
    {
        "id": 2,
        "email": "usuario2@exemplo.com",
        "born_year": "1992-11-05",
        "is_active": true,
        "is_superuser": false,
        "is_staff": false
    }
]
