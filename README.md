# React Nest Face Auth

![GitHub repo size](https://img.shields.io/github/repo-size/lucasgfabris/react-nest-face-auth?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/lucasgfabris/react-nest-face-auth?style=for-the-badge)

> Sistema de autenticacao facial seguro e escalavel usando reconhecimento facial com face-api.js. Oferece registro e login via camera com deteccao em tempo real de posicionamento, iluminacao e qualidade da imagem.

<img src="imagem.png" alt="React Nest Face Auth">

## Pre-requisitos

Antes de comecar, verifique se voce atendeu aos seguintes requisitos:

- Node.js >= 18.0.0
- npm >= 9.0.0
- MySQL >= 8.0

## Instalando

Para instalar o React Nest Face Auth, siga estas etapas:

```bash
git clone https://github.com/lucasgfabris/react-nest-face-auth.git
cd react-nest-face-auth
npm run install:all
```

O comando `install:all` ira instalar todas as dependencias e baixar os modelos de IA automaticamente.

### Configurando o banco de dados

Execute o script SQL no MySQL:

```bash
mysql -u root -p < database/install-manual.sql
```

Configure as variaveis de ambiente:

```bash
cp backend/env.example backend/.env
```

Edite `backend/.env` com suas credenciais:

```env
DB_HOST=localhost
DB_PORT=3306
DB_USERNAME=root
DB_PASSWORD=sua_senha
DB_DATABASE=face_mask_auth
PORT=3001
```

## Usando

Para usar o React Nest Face Auth, siga estas etapas:

```bash
npm run dev
```

Isso iniciara:
- Frontend: http://localhost:5173
- Backend: http://localhost:3001

### Registro de Usuario

1. Digite nome e e-mail
2. Posicione-se na frente da camera
3. Siga as instrucoes em tempo real (distancia, centralizacao, iluminacao)
4. Captura automatica quando a posicao estiver correta

### Login Facial

1. Digite seu nome de usuario
2. Posicione-se na frente da camera
3. Sistema compara seu rosto com o cadastrado
4. Login automatico se houver match

## Tecnologias

| Camada | Tecnologias |
|--------|-------------|
| Frontend | React 18, TypeScript, Vite, TailwindCSS, face-api.js |
| Backend | NestJS, TypeORM, MySQL, bcrypt |

## Estrutura do Projeto

```
react-nest-face-auth/
├── frontend/               # Aplicacao React
│   ├── public/models/     # Modelos de IA do face-api.js
│   └── src/
│       ├── components/    # Componentes React
│       └── services/      # Servicos (API, deteccao facial)
├── backend/               # API NestJS
│   └── src/
│       ├── auth/         # Modulo de autenticacao
│       └── database/     # Configuracao e entidades
├── database/             # Scripts SQL
└── scripts/              # Scripts auxiliares
```

## Contribuindo

Para contribuir com React Nest Face Auth, siga estas etapas:

1. Bifurque este repositorio.
2. Crie um branch: `git checkout -b <nome_branch>`.
3. Faca suas alteracoes e confirme-as: `git commit -m '<mensagem_commit>'`
4. Envie para o branch original: `git push origin <nome_branch>`
5. Crie a solicitacao de pull.

Como alternativa, consulte a documentacao do GitHub em [como criar uma solicitacao pull](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).

## Licenca

Esse projeto esta sob licenca MIT.
