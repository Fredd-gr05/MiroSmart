# Arquitetura - MiroSmart

## Fluxo Geral

```
User (Browser)
    ↓
Frontend (React 18 + Vite)
    ↓ WebSocket + REST API
Node.js API (Express + Socket.io)
    ↓ REST API + RLS Policies
Supabase (PostgreSQL + Realtime)
    ↓ Docker
VPS (Ubuntu 20.04)
```

## Componentes

### Frontend
- **Framework**: React 18 + TypeScript
- **Build**: Vite
- **UI**: TailwindCSS + Shadcn/UI
- **Canvas Drawing**: Konva.js ou Fabric.js
- **Realtime**: Socket.io Client
- **State**: Zustand
- **API Client**: Axios

### Backend
- **Runtime**: Node.js 18+
- **Framework**: Express.js
- **Realtime**: Socket.io (server)
- **Authentication**: JWT + Supabase Auth
- **Validation**: Zod

### Infrastructure
- **Database**: Supabase (PostgreSQL)
- **Auth**: Supabase Auth (Google OAuth)
- **Realtime**: Supabase Realtime + Socket.io
- **File Storage**: Supabase Storage
- **Hosting**: VPS Ubuntu + Docker
- **Reverse Proxy**: Nginx
- **SSL**: Let's Encrypt

## Database Schema

```sql
auth.users              -- Gerenciado por Supabase

public.projects {
  id: UUID PRIMARY KEY
  name: VARCHAR
  owner_id: UUID (FK)
  created_at: TIMESTAMP
}

public.collaborators {
  id: UUID PRIMARY KEY
  project_id: UUID (FK)
  user_id: UUID (FK)
  role: VARCHAR
}

public.canvas_drawings {
  id: UUID PRIMARY KEY
  project_id: UUID (FK)
  data: JSONB
  updated_at: TIMESTAMP
}
```

## Sincronizacao em Tempo Real

**Decisao**: Usar **Socket.io** para minima latencia em canvas

- Melhor latencia para desenho colaborativo
- Escalabilidade com Redis
- Fallback para HTTP polling
