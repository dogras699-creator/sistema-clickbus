# 🚀 Deploy Rápido no Netlify

## ⚡ Deploy em 3 Passos

### 1️⃣ Push para o GitHub

```bash
git add .
git commit -m "Preparar para deploy no Netlify"
git push origin main
```

### 2️⃣ Conectar ao Netlify

1. Acesse: https://app.netlify.com/
2. Clique em **"Add new site"** → **"Import an existing project"**
3. Selecione seu repositório GitHub
4. Clique em **"Deploy site"**

### 3️⃣ Pronto! 🎉

Seu site estará disponível em: `https://seu-site.netlify.app`

---

## 📋 Configurações Automáticas

O Netlify detectará automaticamente:

✅ **Build command:** `npm run build`  
✅ **Publish directory:** `dist`  
✅ **Node version:** `18`  
✅ **SPA redirects:** Configurado em `netlify.toml`  
✅ **Code splitting:** Otimizado para performance  

---

## 🔧 Arquivos de Configuração Incluídos

### netlify.toml
```toml
[build]
  command = "npm run build"
  publish = "dist"

[build.environment]
  NODE_VERSION = "18"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

### public/_redirects
```
/*    /index.html   200
```

### vite.config.js
- Code splitting configurado
- Otimizações de build
- Chunks separados para vendor e utils

---

## 📊 Resultado do Build

```
dist/index.html                            3.36 kB │ gzip: 1.44 kB
dist/assets/index-_Z9s2-tn.css            45.83 kB │ gzip: 8.14 kB
dist/assets/vendor-BhU_QYsM.js           161.42 kB │ gzip: 52.82 kB
dist/assets/utils-DZWkd0gh.js            416.99 kB │ gzip: 138.87 kB
dist/assets/index-DnRYx53z.js            224.66 kB │ gzip: 43.46 kB
```

**Total:** ~852KB (gzip: ~245KB)

---

## 🌐 Domínio Customizado (Opcional)

### Passo 1: Adicionar Domínio

1. No Netlify, vá em **"Domain settings"**
2. Clique em **"Add custom domain"**
3. Digite seu domínio: `seusite.com.br`

### Passo 2: Configurar DNS

No seu provedor de domínio, adicione:

```
Tipo: CNAME
Nome: www
Valor: seu-site.netlify.app

Tipo: A
Nome: @
Valor: 75.2.60.5 (IP do Netlify)
```

### Passo 3: HTTPS Automático

O Netlify ativa HTTPS automaticamente via Let's Encrypt!

---

## 🔐 Credenciais de Acesso

### Administrador
- **Email:** brladsagencia@gmail.com
- **Senha:** @Crypto123451

### Atendentes
- **Email:** maria@painel.com | **Senha:** 123456
- **Email:** joao@painel.com | **Senha:** 123456

---

## ✅ Checklist Final

- [ ] Código pushado para o GitHub
- [ ] Site conectado ao Netlify
- [ ] Deploy realizado com sucesso
- [ ] Site testado em produção
- [ ] Login funcionando
- [ ] Todas as funcionalidades testadas
- [ ] Domínio customizado configurado (opcional)

---

## 🆘 Problemas Comuns

### Build Falha
```bash
# Limpar e rebuild
rm -rf node_modules dist
npm install
npm run build
```

### Rotas Não Funcionam
- Verifique se `public/_redirects` existe
- Verifique se `netlify.toml` está configurado

### Assets Não Carregam
```bash
# Verificar build
ls -la dist/
ls -la dist/assets/
```

---

## 📚 Documentação Completa

Veja mais detalhes em: `/docs/DEPLOY_NETLIFY.md`

---

**Status:** ✅ **PRONTO PARA DEPLOY**

Seu painel está 100% pronto para deploy no Netlify! 🚀
