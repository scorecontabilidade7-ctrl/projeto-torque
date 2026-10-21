# TORQUE — Gestão Financeira e Conciliação Bancária

Sistema financeiro completo (Fluxo de Caixa, DFC, Plano de Contas, Conciliação Bancária, Auditoria) conectado em nuvem com o **Supabase** (Projeto: *Agente de IA*).

---

## ☁️ Conexão com a Nuvem (Supabase)

O projeto está 100% conectado ao Supabase no projeto **Agente de IA**:

- **Projeto Supabase**: `Agente de IA`
- **Project ID**: `jauchajqltpurlzyfgxd`
- **Project URL**: `https://jauchajqltpurlzyfgxd.supabase.co`
- **Tabela Principal**: `public.torque_docs` (estrutura chave-valor em PostgreSQL com JSONB)
- **Tempo Real**: `Supabase Realtime` habilitado (alterações feitas em um computador atualizam instantaneamente em todos os outros)
- **Segurança (RLS)**: Políticas ativas para usuários autenticados via Supabase Auth e acesso via chave Anon

---

## 👥 Acessos e Login

O TORQUE aceita tanto contas cadastradas diretamente no **Supabase Auth** quanto usuários administradores do sistema:

| Usuário | E-mail | Senha Padrão | Tipo |
| :--- | :--- | :--- | :--- |
| **Arthur Frota** | `arthur@score.com.br` | `123456` | Administrador |
| **Arthur Frota** | `arthur@torque.com` | `123456` | Administrador |
| **Usuários Supabase Auth** | Contas do projeto *Agente de IA* | Senha cadastrada no Supabase | Usuário / Cloud |

---

## 🚀 Como Rodar Localmente

Basta abrir o arquivo [index.html](file:///c:/Users/PC-CONTABILIDADE1/OneDrive/Documents/SCORE%20CONTABILIDADE/12%20-%20SCORE%20TECH/ARTHUR/TORQUE/index.html) em qualquer navegador moderno (Google Chrome, Microsoft Edge, Brave, Firefox).

---

## 🌐 Como Deixar em Nuvem (Deploy na Web)

O projeto já possui `vercel.json` e `index.html` prontos para deploy:

### Opção 1: Vercel (Recomendado)
1. Instale ou use o CLI da Vercel:
   ```bash
   npx vercel
   ```
2. Ou conecte a pasta/repositório Git diretamente no painel da [Vercel](https://vercel.com):
   - Import Project -> selecione o diretório -> Deploy automático.

### Opção 2: Netlify / Cloudflare Pages / GitHub Pages
- Basta arrastar ou apontar para a pasta do projeto contendo `index.html`. O sistema funciona 100% como Single Page Application estática conectada ao Supabase.
