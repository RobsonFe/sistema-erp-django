# Sistema ERP com Django Rest Framework e React

Este projeto é um Sistema de Planejamento de Recursos Empresariais (ERP) desenvolvido usando Django Rest Framework para o backend, React para o frontend e PostgreSQL como banco de dados. O sistema inclui autenticação de usuários para garantir a segurança e controle de acesso.

## Requisitos

Antes de começar, certifique-se de ter os seguintes requisitos instalados no seu sistema:

- Python 3.8+
- Node.js 14+
- PostgreSQL 16+
- Git

## Instalação

### Backend (Django)

1. Clone o repositório:
   ```bash
   git clone https://github.com/RobsonFe/sistema-erp-django
   cd erp/core
   ```

2. Crie um ambiente virtual e ative-o:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Para Linux/macOS
   venv\Scripts\activate  # Para Windows
   ```

3. Instale as dependências do backend:
   ```bash
   pip install -r requirements.txt
   ```

4. Configure o banco de dados PostgreSQL no arquivo `settings.py`:
   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.postgresql',
           'NAME': 'nome_do_banco',
           'USER': 'seu_usuario',
           'PASSWORD': 'sua_senha',
           'HOST': 'localhost',
           'PORT': '5432',
       }
   }
   ```

5. Aplique as migrações:
   ```bash
   python manage.py migrate
   ```

6. Crie um superusuário:
   ```bash
   python manage.py createsuperuser
   ```

7. Inicie o servidor de desenvolvimento:
   ```bash
   python manage.py runserver
   ```

### Frontend (React)

1. Navegue até o diretório do frontend:
   ```bash
   cd ../frontend
   ```

2. Instale as dependências do frontend:
   ```bash
   npm install
   ```

3. Inicie o servidor de desenvolvimento:
   ```bash
   npm start
   ```

## Autenticação de Usuário

O sistema inclui autenticação de usuário utilizando o Django Rest Framework com JWT (JSON Web Tokens). A autenticação é necessária para acessar as rotas protegidas da API.

### Registro

Para registrar um novo usuário, faça uma solicitação POST para:
```
POST /api/auth/register/
```
Com o seguinte payload:
```json
{
    "username": "seu_usuario",
    "password": "sua_senha"
}
```

### Login

Para autenticar um usuário, faça uma solicitação POST para:
```
POST /api/auth/login/
```
Com o seguinte payload:
```json
{
    "username": "seu_usuario",
    "password": "sua_senha"
}
```

A resposta incluirá um token JWT que deve ser usado para autenticação nas solicitações subsequentes.

## Estrutura do Projeto

```plaintext
seu-repositorio/
├── backend/
│   ├── manage.py
│   ├── core/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── app/
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── serializers.py
│   │   └── urls.py
│   └── requirements.txt
└── frontend/
    ├── public/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   ├── App.js
    │   └── index.js
    └── package.json
```

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Para quaisquer dúvidas ou sugestões, sinta-se à vontade para entrar em contato:

- Nome: [Robson Ferreira](https://github.com/RobsonFe)
- Email: [robson-ferreiradasilva@hotmail.com](robson-ferreiradasilva@hotmail.com)

---