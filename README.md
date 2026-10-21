# Atividade CRUD Notas Frontend

Front-end que consome as rotas CRUD da API Express para gerenciamento de notas da **Aula 05 — Criando APIs para o front-end**.

## Deploy

**Frontend:** [atividade-crud-frontend.vercel.app](https://atividade-crud-frontend.vercel.app) (Vercel)

> O front-end consome a API CRUD no Render por padrão (`https://atividade-crud-api.onrender.com`). Enquanto o deploy da API não estiver ativo, a tela carrega normalmente, mas não consegue listar, criar, atualizar ou deletar notas.

## Tecnologias

- HTML5
- CSS3
- JavaScript (Vanilla)
- Vite (build e dev server)
- Fetch API

## Funcionalidades

- Listar todas as notas (`GET /api/notas`)
- Criar nova nota (`POST /api/notas`)
- Atualizar nota (`PUT /api/notas/:id`)
- Deletar nota (`DELETE /api/notas/:id`)
- Estados: carregamento, sucesso e erro

## API de referência

[atividade-crud-api](https://github.com/jenifferCamar/atividade-crud-api) — API CRUD de notas (Express), publicada no Render.

## Configuração

A URL da API é definida em `index.html` a partir da variável de ambiente `VITE_API_URL`, com fallback para a URL de produção no Render:

```js
const API_URL = (import.meta && import.meta.env && import.meta.env.VITE_API_URL)
  || 'https://atividade-crud-api.onrender.com';
```

## Executar localmente

O projeto usa Vite, então utilize um servidor de desenvolvimento. **Não abra `index.html` diretamente no navegador**, pois `import.meta` só é resolvido pelo Vite:

```bash
npm install
npm run dev
```

Acesse http://localhost:5173.

Para apontar para uma API local (por exemplo, `http://localhost:3000`), execute com a variável de ambiente:

```bash
set VITE_API_URL=http://localhost:3000
npm run dev
```

## Build de produção

```bash
npm run build
npm run preview
```

A build gera a pasta `dist/`, que évirada pelo Vite e pronta para ser servida (Vercel, GitHub Pages, etc.).
