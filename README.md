# PlayM0z — Pagamentos Digitais (Tron Legacy Style)

Plataforma de pagamentos **manuais** para Moçambique, inspirada no design de Tron Legacy e na estrutura do pagar.co.mz.

## Funcionalidades

- Criação de links de pagamento com referência única (`PMZ-YYYYMMDD-XXXX`)
- Página pública de pagamento com instruções M-Pesa / eMola
- Painel do vendedor para marcar transações como **PAGO** ou **CANCELADO**
- Design completo estilo Tron (grelha neon, glows, tipografia Orbitron)
- 100% estático + `localStorage` (sem backend necessário para começar)
- Documentação da API mock

## Como usar

### 1. Localmente
```bash
# Abra a pasta num servidor estático simples
npx serve .
# ou
python -m http.server 8000
```

### 2. GitHub Pages
1. Crie um repositório `PlayM0z` (ou qualquer nome)
2. Faça upload de todos os ficheiros desta pasta
3. Settings → Pages → Source: Deploy from branch `main` / root
4. O site fica disponível em `https://seu-usuario.github.io/PlayM0z/`

### 3. Netlify / Vercel / Cloudflare Pages
- Arraste a pasta ou ligue o repositório GitHub
- Deploy automático

## Fluxo de pagamento manual

1. Vendedor cria link em `create.html`
2. Partilha a URL `pay.html?ref=PMZ-...` ou a referência
3. Cliente transfere via M-Pesa / eMola usando a referência
4. Vendedor confirma no `dashboard.html` → **Marcar Pago**

Os dados ficam apenas no browser do vendedor (localStorage).

## Estrutura

```
playm0z/
├── index.html          # Landing page
├── create.html         # Criar link de pagamento
├── pay.html            # Página pública do cliente
├── dashboard.html      # Painel do vendedor
├── docs.html           # Documentação
├── css/style.css       # Tema Tron Legacy
├── js/main.js          # Lógica (localStorage)
└── README.md
```

## Domínio pretendido

`playm0z.co.mz` — registe num registrar autorizado em Moçambique e aponte para o hosting (GitHub Pages, Netlify, etc.).

## Próximos passos (produção real)

- Backend (Node/Python) + base de dados
- Integração oficial M-Pesa / eMola (requer autorização Banco de Moçambique)
- KYC, webhooks assinados, ambientes TEST/LIVE
- SSL + domínio próprio

## Licença

Use livremente. Feito para a comunidade de empreendedores moçambicanos.

---

**PlayM0z** — Receba do seu jeito.
