# Setup - MiroSmart

## Requisitos

- Node.js 18+
- npm ou yarn
- PostgreSQL (Supabase)
- Docker (para deployment)

## Instalacao Local

### 1. Clone o repositorio

```bash
git clone https://github.com/seu-user/mirosmart.git
cd mirosmart
```

### 2. Instale as dependencias

```bash
npm install
```

### 3. Configure as variaveis de ambiente

```bash
cp .env.example .env.local
```

Edite `.env.local` com suas credenciais:

```env
# Supabase
VITE_SUPABASE_URL=https://seu-projeto.supabase.co
VITE_SUPABASE_ANON_KEY=sua-chave-publica
SUPABASE_SERVICE_ROLE_KEY=sua-chave-privada

# Google OAuth
VITE_GOOGLE_CLIENT_ID=seu-client-id.apps.googleusercontent.com

# API
VITE_API_URL=http://localhost:3000
API_PORT=3000

# Socket.io
SKOCKET_PORT=3001
```

### 4. Setup Supabase

```bash
# Instale Supabase CLI (opcional)
npm install -g supabase

# Ou use Supabase Cloud dashboard
# 1. Crie um novo projeto em supabase.com
# 2. Copie URL e keys para .env.local
# 3. Execute as migrations (SQL scripts em /database)
```

### 5. Inicie o servidor de desenvolvimento

```bash
npm run dev
```

Isso vai iniciar:
- Frontend: http://localhost:5173
- API: http://localhost:3000
- Socket.io: ws://localhost:3001

## Database Setup

Execute os scripts SQL em `database/migrations/`:

```sql
-- 01_create_tables.sql
-- 02_setup_auth.sql
-- 03_setup_realtime.sql
```

Ou use Supabase Dashboard > SQL Editor

## Build para Producao

```bash
# Build frontend
npm run build

# Build Docker
docker build -t mirosmart .

# Run container
docker run -p 3000:3000 mirosmart
```

## Troubleshooting

### Error: `Cannot find module`
- Limpe `node_modules` e execute `npm install` novamente

### Supabase conexao falha
- Verifique `.env.local` (URLs e chaves)
- Confirme firewall permite conexao ao Supabase

### Socket.io nao conecta
- Verifique `VITE_API_URL` (deve ser IP do servidor em producao)
- Confirme portas 3000, 3001 estao abertas

## Proximos passos

Veja [ARCHITECTURE.md](/docs/ARCHITECTURE.md) para entender fluxo geral
Veja [ROADMAP.md](/docs/ROADMAP.md) para ver o que vem por ai
