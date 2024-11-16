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
python -m venv venv
source venv/bin/activate  # no Windows, use `venv\Scripts\activate`
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
