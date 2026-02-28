# 🎠 Carrossel Instagram — Versão Supabase + GitHub Pages

Gerador de carrossel 100% gratuito usando GitHub Pages (frontend) + Supabase Storage (imagens).

## 🛠️ Configuração Inicial

### 1. Supabase

1. Acesse [supabase.com](https://supabase.com) e crie uma conta gratuita
2. Crie um novo projeto
3. No painel do projeto, vá em **Storage** → **New Bucket**
   - Nome: `carrosseis`
   - Marque **Public bucket** ✅
4. Vá em **Project Settings → API** e copie:
   - **Project URL** (ex: `https://abcxyz.supabase.co`)
   - **anon / public key**

5. Abra o arquivo `config.js` e preencha:
```js
const SUPABASE_URL = 'https://SEU_PROJETO.supabase.co';
const SUPABASE_KEY = 'SUA_ANON_KEY_AQUI';
const BUCKET = 'carrosseis';
```

### 2. GitHub Pages

1. Crie um repositório público no GitHub (ex: `carrossel-instagram`)
2. Faça upload de todos os arquivos desta pasta para o repositório
3. Vá em **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` / pasta: `/ (root)`
4. Aguarde alguns minutos e acesse:
   `https://seu-usuario.github.io/carrossel-instagram`

## 📁 Estrutura dos Arquivos

```
carrossel-web/
├── index.html      → Gerador de carrossel
├── galeria.html    → Galeria e histórico de imagens
├── config.js       → Suas credenciais do Supabase ← PREENCHER
└── README.md       → Este arquivo
```

## 🗂️ Como os arquivos são organizados no Supabase

```
bucket: carrosseis/
├── posts/
│   ├── Slide_1.png   ← Posts mais recentes
│   └── Slide_2.png
└── historico/
    ├── 2026-02-27T20-30-00/
    │   └── Slide_1.png
    └── 2026-02-28T10-00-00/
        └── Slide_1.png
```

Toda vez que você salvar um novo carrossel, os posts atuais são automaticamente movidos para `historico/` antes de salvar os novos.

## ⚠️ Atenção com a Foto de Perfil

Diferente da versão VPS, aqui você precisa **selecionar a foto de perfil** manualmente na interface toda vez que for gerar um carrossel. A foto não é armazenada no servidor.
