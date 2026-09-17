# StyleSync API

Projeto de estudo de uma API REST desenvolvida com **Flask** e **MongoDB**, simulando o backend de um sistema de controle de produtos, categorias e vendas para uma startup fictícia chamada **StyleSync**.

> Projeto desenvolvido para fins de aprendizado e prática de backend com Python.

## 🛠️ Tecnologias

- **Python 3**
- **Flask** — framework web
- **MongoDB** (via `pymongo`) — banco de dados NoSQL
- **Pydantic** — validação de dados
- **PyJWT** — autenticação via token
- **python-dotenv** — variáveis de ambiente

## 📁 Estrutura do projeto

```
Projeto_flask/
├── app/
│   ├── __init__.py          # Criação da app e conexão com o Mongo
│   ├── decorators.py        # Decorator de autenticação (token_required)
│   ├── models/              # Modelos Pydantic (Product, Category, Sale, User)
│   └── routes/              # Blueprints com as rotas da API
├── config.py                 # Configurações carregadas do .env
├── run.py                    # Ponto de entrada da aplicação
└── requirements.txt
```

## ✨ Funcionalidades

- Autenticação via **JWT** (`/login`)
- CRUD de **produtos** (`/products`, `/product/<id>`)
- Listagem e criação de **categorias** (`/categories`)
- **Importação de vendas** via upload de arquivo `.csv` (`/sales/upload`)
- Rotas protegidas por token para operações de escrita (criar, atualizar, deletar)

## ⚙️ Como rodar o projeto

1. Clone o repositório:
   ```bash
   git clone https://github.com/kauanalvs95-art/Projeto_flask.git
   cd Projeto_flask
   ```

2. Crie e ative um ambiente virtual:
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate     # Windows
   ```

3. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

4. Crie um arquivo `.env` na raiz do projeto com base no exemplo:
   ```env
   MONGO_URI=mongodb://localhost:27017/stylesync
   SECRET_KEY=sua_chave_secreta_aqui
   ```

5. Certifique-se de ter o **MongoDB** rodando localmente (ou aponte `MONGO_URI` para uma instância remota).

6. Execute a aplicação:
   ```bash
   python run.py
   ```

A API estará disponível em `http://localhost:5000`.

## 🔑 Autenticação

Para acessar as rotas protegidas, primeiro obtenha um token em `/login` e envie-o no header das requisições:

```
Authorization: Bearer <seu_token>
```

## 📌 Status

Projeto em desenvolvimento contínuo, criado com fins de estudo e prática de conceitos de API REST, autenticação e persistência em banco NoSQL.

## 📄 Licença

Este projeto é livre para fins educacionais.
