# TORQUE — Gestão Financeira e Conciliação Bancária

Sistema financeiro completo (Fluxo de Caixa, DFC, Plano de Contas, Conciliação Bancária, Auditoria, **Controle de Saldos** com planilha interativa e **Modo Escuro / Claro**) conectado em nuvem com o **Supabase** (Projeto: *Agente de IA*).

- 🌐 **Aplicação no Ar (Produção)**: [https://projeto-torque.vercel.app](https://projeto-torque.vercel.app)
- 🐙 **Repositório GitHub**: [https://github.com/scorecontabilidade7-ctrl/projeto-torque](https://github.com/scorecontabilidade7-ctrl/projeto-torque)

---

## 🛠️ Principais Módulos do Sistema

1. **Fluxo de Caixa**: Lançamentos financeiros, conciliação bancária, importação de extratos (OFX, XLSX, CSV) e filtros avançados.
2. **Controle de Saldos (Planilha Digital Interativa)**:
   - Gestão gerencial independente e detalhada de Entradas, Saídas, Serviços e Peças.
   - Cálculo automático de Saldos de Serviços, Peças, Geral e Resultado Gerencial Consolidado.
   - Seletor nativo de Bancos (Banco do Brasil, Caixa, Itaú, Bradesco, Santander, Inter, Nubank, Sicoob, Sicredi, Dinheiro e opção OUTRO customizável).
   - Abas dedicadas: *Visão Geral*, *Serviços* e *Peças*.
   - Exportação instantânea para Excel (`.xlsx`) e configuração de saldos iniciais.
3. **DFC (Mês e Ano)**: Demonstração dos Fluxos de Caixa estruturada pelo plano de contas com totalizadores e fechamento.
4. **Comparativo**: Evolução gráfica mensal e diária com visualização de séries temporais e médias.
5. **Tema Escuro & Claro**: Alternância dinâmica no cabeçalho, com suporte a alto contraste e persistência local.


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

## 👥 Acessos e Autenticação Segura

O TORQUE opera com dupla camada de autenticação:
1. **Supabase Auth (Oficial em Nuvem)**: Contas gerenciadas no painel do Supabase (*Authentication › Users*).
2. **Autenticação Local / Offline**: Usuários cadastrados no painel do sistema (*Configurações › Usuários*), com derivação de chaves via **PBKDF2-HMAC-SHA256 (100.000 iterações)** e salt criptográfico individual.

| Usuário | E-mail | Perfil | Tipo de Acesso |
| :--- | :--- | :--- | :--- |
| **Arthur Frota** | `arthur@torque.com` | Administrador | Local + Nuvem |
| **Amanda Gabaglia** | `amanda@torque.com` | Usuário | Local + Nuvem |
| **Usuários Supabase Auth** | Contas cadastradas no Supabase | Definido no Supabase | Nuvem / Realtime |

> 🔒 **Recomendação de Segurança:** Nunca armazene senhas em texto puro neste documento ou no repositório. Altere suas senhas imediatamente no primeiro acesso pelo menu *Configurações › Usuários*.

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
