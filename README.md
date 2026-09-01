# Site Oliver Truck

Landing page comercial da Oliver Truck (reforma e fabricação de implementos rodoviários), construída em **HTML, CSS e JavaScript puro** — sem frameworks, sem etapa de build. É só um site estático.

```
oliver-truck-site/
├── index.html          → todo o site (HTML + CSS + JS em um único arquivo)
├── assets/
│   ├── logo.jpg
│   ├── estrutura.jpg
│   └── gallery/         → fotos de antes/durante/depois do portfólio
├── vercel.json          → configuração de deploy (cache das imagens, URLs limpas)
├── .gitignore
└── README.md
```

---

## 1. Colocar o código no GitHub

Se ainda não tem um repositório:

```bash
cd oliver-truck-site
git init
git add .
git commit -m "Primeira versão do site Oliver Truck"
```

1. Crie um repositório novo em https://github.com/new (pode ser público ou privado — não precisa marcar nenhuma opção extra, como README, .gitignore ou licença).
2. Copie a URL do repositório que o GitHub mostrar (algo como `https://github.com/SEU-USUARIO/oliver-truck-site.git`).
3. Conecte e envie o código:

```bash
git remote add origin https://github.com/SEU-USUARIO/oliver-truck-site.git
git branch -M main
git push -u origin main
```

Se já tiver um repositório existente, basta `git add . && git commit -m "update" && git push`.

---

## 2. Publicar no Vercel

**Pelo site (mais simples):**
1. Acesse https://vercel.com e entre com sua conta do GitHub.
2. Clique em **"Add New… → Project"**.
3. Selecione o repositório `oliver-truck-site` na lista.
4. O Vercel detecta automaticamente que é um site estático — não precisa mudar nenhuma configuração de build (Framework Preset: "Other", Build Command e Output Directory podem ficar em branco).
5. Clique em **Deploy**. Em cerca de 1 minuto o site estará no ar em um endereço `https://oliver-truck-site-xxxx.vercel.app`.

**Pelo terminal (alternativa):**
```bash
npm install -g vercel
cd oliver-truck-site
vercel        # primeiro deploy (ambiente de preview)
vercel --prod # publica em produção
```

### Domínio próprio (olivertruck.com.br)
No painel do projeto no Vercel: **Settings → Domains → Add**, digite `olivertruck.com.br` (e `www.olivertruck.com.br`) e siga as instruções para apontar o DNS do domínio para o Vercel.

### Atualizações futuras
Qualquer novo `git push` para a branch `main` gera automaticamente um novo deploy em produção — não precisa repetir os passos do Vercel.

---

## 3. O que atualizar depois do primeiro deploy

Abra `index.html` e ajuste, se necessário:

- **`og:image`** (linha ~17) e **`"image"`** do Schema Markup (linha ~48): trocar `SEU-DOMINIO-AQUI.vercel.app` pela URL real do site depois do deploy (ou pelo domínio próprio, quando configurado).
- **`canonical`**, **`og:url`** e **`"url"`** do Schema Markup: já apontam para `olivertruck.com.br` — ajuste se o domínio final for outro.
- **Endereço/Instagram**: procure por `COMPANY` dentro da tag `<script>` para alterar WhatsApp, e-mail, endereço e Instagram — tudo centralizado num único lugar.
- **Serviços, diferenciais, FAQ e galeria**: também estão em arrays no `<script>` (`SERVICES`, `DIFFERENTIALS`, `FAQ`, `GALLERY`), fáceis de editar sem mexer no HTML.

Depois de editar, é só `git add . && git commit -m "ajustes" && git push` — o Vercel atualiza sozinho.
