# MiroSmart

Plataforma inteligente de desenho e design colaborativo em tempo real com IA.

## 🚀 Descrição
MiroSmart é uma solução inovadora que combina:
- **Desenho colaborativo** em tempo real com múltiplos usuários
- **IA integrada** para sugestões de design e automação
- **Sincronização WebSocket** para latência mínima
- **Supabase** como backend robusto
- **Escalabilidade** com Docker e VPS

## 🔗 Links Rápidos
| Recurso | Link |
|---------|------|
| **Supabase** | [miro-smart.supabase.co](https://miro-smart.supabase.co) |
| **GitHub** | [github.com/seu-user/mirosmart](https://github.com/seu-user/mirosmart) |
| **Documentação** | [/docs](/docs) |
| **Issues** | [GitHub Issues](https://github.com/Fredd-gr05/MiroSmart/issues) |
| **Roadmap** | [Milestones](https://github.com/Fredd-gr05/MiroSmart/milestones) |

## 📊 Status Atual
- 🚀 **Em Desenvolvimento**
- Última atualização: 2025-12-24
- Branch principal: `main`
- Clientes: Miro (primeiro cliente)

## 🏗️ Arquitetura Rápida
```
Frontend (React/Vue) 
    ↓
Node.js API (Express + Socket.io)
    ↓
Supabase (PostgreSQL + Realtime)
    ↓
VPS (Docker Compose)
```
*Veja [docs/ARCHITECTURE.md](/docs/ARCHITECTURE.md) para detalhes completos.*

## 🚀 Quick Start
```bash
# Clone
git clone https://github.com/seu-user/mirosmart.git
cd mirosmart

# Install
npm install

# Configure .env
cp .env.example .env
# Preencha SUPABASE_URL, SUPABASE_KEY, etc

# Run
npm run dev
```
*Veja [docs/SETUP.md](/docs/SETUP.md) para instruções completas.*

## 📚 Documentação
- [Arquitetura](/docs/ARCHITECTURE.md) - Fluxo técnico completo
- [Setup Local](/docs/SETUP.md) - Como rodar o projeto
- [API](/docs/API.md) - Endpoints e WebSocket
- [Database](/docs/DATABASE.md) - Schema Supabase
- [Deployment](/docs/DEPLOYMENT.md) - Docker e VPS
- [Roadmap](/docs/ROADMAP.md) - Sprints e TODOs

## 🎯 TODOs Atuais
- [ ] Setup autenticação Google
- [ ] Integrar Socket.io para colaboração
- [ ] Implementar drawing engine
- [ ] Conectar IA para sugestões
- [ ] Deploy Docker inicial
- [ ] Tests unitários

*Acompanhe no [Issues](https://github.com/Fredd-gr05/MiroSmart/issues) ou [Milestones](https://github.com/Fredd-gr05/MiroSmart/milestones)*

## ⚠️ Riscos / Blockers
| Blocker | Status | ETA |
|---------|--------|-----|
| Supabase Realtime quota | 🟡 Aguardando | Jan 15 |
| Socket.io scale | 🔴 Crítico | Jan 5 |
| IA latency | 🟡 Investigando | Jan 10 |
| Browser canvas performance | 🟡 Testing | Jan 8 |

*Veja [docs/ROADMAP.md](/docs/ROADMAP.md) para detalhes completos.*

## 💻 Stack Tecnológico
- **Frontend**: React 18 + Vite + TailwindCSS
- **Backend**: Node.js + Express + Socket.io
- **Database**: PostgreSQL (Supabase)
- **Auth**: Supabase Auth + Google OAuth
- **Realtime**: Supabase Realtime + Socket.io
- **Infra**: Docker + Docker Compose + Nginx
- **IA**: OpenAI API (integração planejada)

## 🤝 Como Contribuir
1. Faça um Fork
2. Crie uma branch (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📝 License
MIT

---

**Desenvolvido por**: Fredd-gr05  
**Última atualização**: 2025-12-24
