<p align="center">
  <img src="./public/cover.png" alt="Back-end Challenge">
</p>

<br />

<div align="center"><strong>Back-end Challenge</strong></div>
<div align="center">This is the last challenge for participants in the backend web development workshop.</div>

<br />

<div align="center">
  <sub>Created by <a href="https://www.instagram.com/igabrieldejesus">Gabriel de Jesus</a>.</sub>
</div>

<br />

# Desafio

Sua tarefa é construir uma API e banco de dados para uma aplicação chamada MegaRank. A aplicação é um rank onde será listado todos os participantes de uma competição com o link da sua foto, nome e sobrenome, XP (Experiência) e um link para uma rede social.

A aplicação pode ser construída utilizando qualquer linguagem, banco de dados, frameworks, libraries e ferramentas de sua preferência (Ex: Node + Express + Mongoose + MongoDB, PHP + Lumen + RedBean + PostgreSQL, etc). Apesar disso, a stack mais comum por aqui é **Node.js**. **Rust** é incomum, mas aparece em raros casos.

A API deverá ser documentada, informando todas as suas rotas e explicando como um desenvolvedor que nunca tenha visto essa API antes pode utilizá-la facilmente. Caso deseje, você pode utilizar ferramentas como: [API Blueprint](https://apiblueprint.org/) ou [Swagger](https://swagger.io/docs/specification/basic-structure/) para documentar ou até mesmo criar um arquivo `README.md` no projeto e criar a documentação ali.

## O que será avaliado

Quero avaliar sua capacidade de desenvolver e documentar um back-end para uma aplicação. Serão avaliados:

- Código bem escrito e limpo;
- Quais ferramentas foram usadas, como e por quê, além do seu conhecimento das mesmas;
- Seu conhecimento em banco de dados, requisições HTTP, APIs REST, etc;
- Sua capacidade de se comprometer com o que foi fornecido;
- Sua capacidade de documentação da sua parte da aplicação.

## O mínimo necessário

- Uma aplicação contendo uma API real simples, sem autenticação, que atenda os requisitos descritos a cima, fazendo requisições à um banco de dados para persistência de dados;
- README.md contendo informações básicas do projeto, documentação e como executá-lo;

## Bônus

Os seguintes itens não são obrigatórios, mas darão mais valor ao seu trabalho (os em negrito são mais significativos para mim)

- Uso de ferramentas externas que facilitem o seu trabalho;
- Cuidados especiais com otimização, padrões, entre outros;
- Migrations ou script para configuração do banco de dados utilizado;
- **Testes**;
- **Conteinerização da aplicação**;
- **Autenticação e autorização** (**OAuth, JWT**);
- Sugestões sobre o desafio embasadas em alguma argumentação.

---

# Requisitos

1.  A API deve responder na porta 3030

2.  Deve haver uma rota para listar todos os participantes cadastrados

**Exemplo:**

`GET /participants`

```json
[
  {
    "id": "36b8f84d-df4e-4d49-b662-bcde71a8764f",
    "name": "Gabriel de Jesus",
    "imageUrl": "https://github.com/gabrieldejesus.png",
    "xp": 220,
    "socialNetwork": "https://www.linkedin.com/in/igabrieldejesus"
  },
  {
    "id": "36b8f84d-df4e-4d49-4267-bcde71a8764f",
    "name": "Fernanda Caetano",
    "imageUrl": "https://github.com/FernandaMatt.png",
    "xp": 420,
    "socialNetwork": "https://www.linkedin.com/in/fernanda-cmbc/"
  },
  {
    "id": "ad238f84d-df4e-4d49-b662-bcde71a8764f",
    "name": "Gustavo F Sousa",
    "imageUrl": "https://github.com/gustavofsousa.png",
    "xp": 220,
    "socialNetwork": "https://www.linkedin.com/in/gustavofsousa/"
  },
  {
    "id": "36b8f84d-df4e-adf2-4267-bcde71a8764f",
    "name": "Izabele Cabral",
    "imageUrl": "https://github.com/izacabral.png",
    "xp": 410,
    "socialNetwork": "https://www.linkedin.com/in/izacabral"
  },
  {
    "id": "36b8f84d-df4e-4d49-b662-bcde71a87a20",
    "name": "Pedro Lopes",
    "imageUrl": "https://github.com/PedroArnaldo",
    "xp": 320,
    "socialNetwork": "https://www.linkedin.com/in/pedroarnaldoo"
  }
]
```

## 3: Deve haver uma rota para cadastrar um novo participante

O corpo da requisição deve conter as informações do participante a ser cadastrada, sem o ID (gerado automaticamente pelo servidor). A resposta, em caso de sucesso, deve ser o mesmo objeto, com seu novo ID gerado.

**Exemplo de uma requisição:**

`POST /participants`

`Content-Type: application/json`

```json
{
  "name": "Pedro Lopes",
  "imageUrl": "https://github.com/PedroArnaldo",
  "xp": 320,
  "socialNetwork": "https://www.linkedin.com/in/pedroarnaldoo"
}
```

**Exemplo de uma resposta:**

`Status: 201 Created`

`Content-Type: application/json`

```json
{
  "id": "36b8f84d-df4e-4d49-b662-bcde71a87a20",
  "name": "Pedro Lopes",
  "imageUrl": "https://github.com/PedroArnaldo",
  "xp": 320,
  "socialNetwork": "https://www.linkedin.com/in/pedroarnaldoo"
}
```

## 4: O usuário deve poder atualizar um participante por ID

**Exemplo de uma requisição:**

`PUT /participants/:id`

`Content-Type: application/json`

```json
{
  "name": "Pedro Lopes",
  "imageUrl": "https://github.com/PedroArnaldo",
  "xp": 320,
  "socialNetwork": "https://www.linkedin.com/in/pedroarnaldoo"
}
```

**Exemplo de uma resposta:**

`Status: 200 Ok`

`Content-Type: application/json`

```json
{
  "id": "36b8f84d-df4e-4d49-b662-bcde71a87a20",
  "name": "Pedro Lopes",
  "imageUrl": "https://github.com/PedroArnaldo",
  "xp": 320,
  "socialNetwork": "https://www.linkedin.com/in/pedroarnaldoo"
}
```

## 5: O usuário deve poder remover um participante por ID

**Exemplo de uma requisição:**

`DELETE /participants/:id`

**Exemplo de uma resposta:**

`Status: 200 OK`

```json
{}
```

## Critérios de Aceitação

- A API deve ser real e escrita por você. Ferramentas que criam APIs automaticamente (Loopback, json-server, etc) não são aceitas;
- Todos os requisitos acima devem ser cumpridos, seguindo o padrão de rotas estabelecido;
- Você deve criar uma documentação para descrever sua API;
- Se você julgar necessário, adequado ou quiser deixar a aplicação mais completa (bônus!) você pode adicionar outras rotas, métodos, meios de autenticação com usuários, etc.

Ao término do desafio, você deve enviar o repositório do seu desafio para mim através do Discord, em mensagem privada.
