# Aagrifam — Plataforma de Romaneios

Sistema web para emissão de **romaneios (guias de entrega)** da AAGRIFAM — Associação da Agricultura Familiar de Colorado, voltado para o intermediário comercial que negocia produtos entre produtores rurais e instituições compradoras (escolas, colégios, etc.) no âmbito do PNAE-PR.

> **Status atual:** Protótipo funcional v4 (HTML + JS, sem backend). Dados persistidos em `localStorage`. Pronto para validação operacional e evolução para full-stack.

---

## ✨ Funcionalidades implementadas (v4)

- 🔐 **Login** local (demo)
- 👥 **Cadastro de clientes/instituições** com campos do cabeçalho do romaneio (município, núcleo regional, endereço, telefone, classificação URBANA/RURAL, turno, horário)
- 🚜 **Cadastro de produtores/vendedores** com edição, exclusão e status ATIVO/INATIVO
- 🥬 **Cadastro de produtos** com grupo, unidade (KG/DÚZIA/UN), lote padrão e preços URBANA/RURAL
- 📝 **Criação de romaneio** vinculado a 1 produtor + 1 instituição, com cálculo automático de unidade, preço, lote e total
- 📋 **Lista de romaneios** com filtros por período, cliente, produtor, status de entrega e busca textual
- 🚚 **Status de entrega**: PENDENTE, EM SEPARAÇÃO, ENTREGUE, CANCELADO (alterável direto na tabela)
- 🖨️ **Impressão / Geração de PDF** do romaneio em layout fiel ao modelo oficial
- 📊 **Dashboard** com indicadores em tempo real
- 📈 **Relatórios semanal, mensal e personalizado** com:
  - Cards de resumo (valor total, quantidade, clientes, produtores)
  - Análises por produtor, cliente, grupo e status
  - Lista detalhada de romaneios e produtos consolidados
  - **Exportação CSV** (Excel/Google Sheets) e impressão em PDF

---

## 🚀 Como rodar localmente

### Opção 1 — Abrir direto no navegador (mais simples)

```bash
git clone https://github.com/renangl43-source/aagrifam-romaneios.git
cd aagrifam-romaneios
```

Abra o arquivo `src/index.html` no seu navegador (Chrome, Firefox ou Edge). Não precisa instalar nada.

### Opção 2 — Rodar com servidor local (recomendado)

Servir via HTTP local evita restrições de alguns navegadores e simula melhor um ambiente real.

**Com Python 3:**

```bash
cd src
python3 -m http.server 8000
```

Acesse: <http://localhost:8000>

**Com Node.js (npx):**

```bash
cd src
npx serve .
```

**Com VS Code:** instale a extensão *Live Server* e clique em "Go Live".

### 🔑 Credenciais de demonstração

| Campo | Valor |
|---|---|
| Usuário | `admin@aagrifam.local` |
| Senha | `123456` |

---

## 📁 Estrutura do projeto

```
aagrifam-romaneios/
├── src/
│   └── index.html              # Aplicação completa (HTML + CSS + JS)
├── docs/
│   ├── ARCHITECTURE.md         # Modelo de dados e arquitetura
│   ├── ROADMAP.md              # Plano de evolução para full-stack
│   └── BUSINESS-RULES.md       # Regras de negócio e fluxos
├── assets/                     # Imagens, logo, modelos de referência
├── scripts/                    # Scripts utilitários (importação, etc.)
├── .github/
│   └── workflows/
│       └── deploy-pages.yml    # Deploy automático no GitHub Pages
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🌐 Publicar como site no GitHub Pages (grátis)

Este repositório está configurado com deploy automático por **GitHub Actions**. A cada push na branch `main`, o conteúdo da pasta `src` é enviado para o GitHub Pages.

1. No GitHub, vá em **Settings → Pages**
2. Em **Build and deployment**, selecione **GitHub Actions** como fonte de publicação
3. Volte na aba **Actions** e aguarde o workflow **Publicar no GitHub Pages** concluir
4. Em alguns minutos o protótipo estará em: `https://renangl43-source.github.io/aagrifam-romaneios/`

> O workflow ativo está em `.github/workflows/deploy-pages.yml` e publica automaticamente o arquivo `src/index.html`.

---

## 🛣️ Roadmap — do protótipo ao sistema full-stack

### Fase 1 — Protótipo (✅ concluída)
- HTML + JS + localStorage
- Cadastros, romaneios, dashboard e relatórios
- Validação de fluxo e layout

### Fase 2 — MVP backend (próxima)
- **Stack sugerida:** Node.js + Express + PostgreSQL OU Supabase (PostgreSQL gerenciado + Auth + Storage)
- API REST para os 4 cadastros + romaneios + relatórios
- Autenticação real com JWT ou OAuth
- Upload do logo e configurações da associação
- Geração de PDF server-side (Puppeteer ou similar)

### Fase 3 — Plataforma completa
- Multi-usuário com permissões (admin, operador, leitura)
- Importação automática da planilha Excel atual
- **Assistente IA do WhatsApp**: cole a mensagem do cliente e o sistema preenche o romaneio automaticamente (OpenAI GPT ou Claude API)
- Painel mobile para o produtor confirmar entregas
- Histórico de preços e tabelas por mês de referência
- Backup automático e exportação periódica

### Fase 4 — Integrações
- Integração com WhatsApp Business API (envio automático de comprovantes)
- Integração com sistemas contábeis
- Assinatura digital do romaneio
- Relatórios de comissão/intermediação
- App PWA instalável no celular

---

## 💻 Stack recomendada para Fase 2

**Frontend:**
- React + Vite OU manter HTML/JS atual evoluindo gradualmente
- Tailwind CSS para estilização

**Backend (escolha uma):**
- **Opção A — Supabase** (mais rápida): PostgreSQL + Auth + Storage prontos, Row Level Security
- **Opção B — Node.js + Express + Prisma + PostgreSQL** (mais flexível)
- **Opção C — Next.js full-stack** (frontend e backend juntos)

**Hospedagem:**
- Frontend: Vercel, Netlify ou GitHub Pages (grátis)
- Backend: Railway, Render, Supabase ou Fly.io
- Banco: Supabase, Neon ou Railway PostgreSQL

---

## 📊 Modelo de dados (resumo)

```
produtores      (id, nome, documento, telefone, municipio, status, observacao)
clientes        (id, nome, classificacao, municipio, nucleo, endereco, ...)
grupos          (id, nome, limite_semanal)
produtos        (id, nome, grupo_id, unidade, lote, preco_urbana, preco_rural)
romaneios       (id, numero, data, produtor_id, cliente_id, status, valor_total, ...)
romaneio_itens  (id, romaneio_id, produto_id, quantidade, valor_unitario, valor_total)
usuarios        (id, email, senha_hash, perfil)
```

Detalhes completos em [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md).

---

## 🤝 Contribuindo

Este é um projeto privado da operação Aagrifam. Para contribuir:

1. Faça fork do repositório
2. Crie uma branch: `git checkout -b feature/nome-da-feature`
3. Commit: `git commit -m "feat: descrição"`
4. Push: `git push origin feature/nome-da-feature`
5. Abra um Pull Request

---

## 📄 Licença

Este projeto é de uso privado da AAGRIFAM. Veja [`LICENSE`](LICENSE).

---

## 📞 Contato

Operação comercial Aagrifam — Colorado/PR

---

## 🙏 Sobre

Sistema desenvolvido para facilitar a operação de intermediação comercial entre agricultura familiar e instituições compradoras no programa PNAE-PR, substituindo o controle manual em planilhas Excel por uma plataforma centralizada com geração automática de guias de entrega.
