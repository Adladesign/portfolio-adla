# Guia de Deployment - Website de Portfólio

## 🚀 Opções de Deployment

### 1. Netlify (Recomendado)
```bash
# Build do projeto
pnpm run build

# Fazer upload da pasta 'dist' para Netlify
# Ou conectar repositório Git para deployment automático
```

### 2. Vercel
```bash
# Instalar Vercel CLI
npm i -g vercel

# Deploy
vercel

# Seguir instruções no terminal
```

### 3. GitHub Pages
```bash
# Instalar gh-pages
npm install --save-dev gh-pages

# Adicionar ao package.json:
"homepage": "https://seuusername.github.io/portfolio-website",
"scripts": {
  "predeploy": "pnpm run build",
  "deploy": "gh-pages -d dist"
}

# Deploy
pnpm run deploy
```

### 4. Hosting Tradicional
```bash
# Build do projeto
pnpm run build

# Fazer upload da pasta 'dist' para o servidor
# Configurar servidor para servir ficheiros estáticos
```

## ⚙️ Configurações Importantes

### Vite Config (vite.config.js)
```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'
import path from 'path'

export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
  base: './', // Para hosting relativo
})
```

### Build de Produção
```bash
# Criar build otimizado
pnpm run build

# Testar build localmente
pnpm run preview
```

## 🔧 Personalizações Futuras

### Adicionar Novas Secções
1. Criar componente na pasta `src/components`
2. Importar e adicionar ao `App.jsx`
3. Atualizar navegação se necessário

### Modificar Cores
Editar variáveis CSS em `src/App.css`:
```css
:root {
  --primary: [nova cor];
  --secondary: [nova cor];
}
```

### Adicionar Novos Projetos
Atualizar array `projects` em `App.jsx`:
```javascript
const projects = [
  {
    title: "Novo Projeto",
    category: "Categoria",
    description: "Descrição do projeto",
    image: "/src/assets/novo-projeto.jpg",
    tags: ["Tag1", "Tag2"]
  }
]
```

## 📊 Analytics e SEO

### Google Analytics
Adicionar ao `index.html`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_TRACKING_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_TRACKING_ID');
</script>
```

### Meta Tags SEO
Atualizar `index.html`:
```html
<meta name="description" content="Sofia - Designer & Estrategista Criativa">
<meta name="keywords" content="web design, estratégia criativa, branding">
<meta property="og:title" content="Sofia - Designer & Estrategista Criativa">
<meta property="og:description" content="Transformo ideias em experiências digitais memoráveis">
```

## 🔒 Segurança

### Formulário de Contacto
Para funcionalidade completa do formulário:
1. Configurar backend (Node.js, PHP, etc.)
2. Ou usar serviços como Formspree, Netlify Forms
3. Implementar validação e proteção SPAM

### HTTPS
- Sempre usar HTTPS em produção
- Certificados SSL gratuitos via Let's Encrypt
- Plataformas como Netlify/Vercel incluem HTTPS automático

## 📱 Testes

### Responsividade
- Testar em diferentes dispositivos
- Usar DevTools para simular tamanhos
- Verificar breakpoints: 320px, 768px, 1024px, 1280px

### Performance
```bash
# Lighthouse audit
npm install -g lighthouse
lighthouse https://seusite.com

# Ou usar Chrome DevTools > Lighthouse
```

### Cross-browser
- Chrome/Chromium
- Firefox
- Safari
- Edge

## 🎯 Checklist de Deployment

- [ ] Build de produção criado
- [ ] Imagens otimizadas
- [ ] Meta tags configuradas
- [ ] Analytics implementado
- [ ] Formulário de contacto funcional
- [ ] HTTPS configurado
- [ ] Teste em múltiplos dispositivos
- [ ] Teste em múltiplos browsers
- [ ] Performance verificada
- [ ] SEO otimizado

---

**Website pronto para deployment! 🚀**

