# Server-Side Rendering (SSR) no Angular
## Guia Completo: SSR, SSG, SEO Técnico, Hidratação e AI SEO

---

# 1️⃣ Problema das SPAs Tradicionais

Aplicações SPA (Single Page Application) renderizam no navegador.

## HTML inicial típico

```html
<body>
  <app-root></app-root>
  <script src="main.js"></script>
</body>
```

Problemas:

- HTML praticamente vazio
- Conteúdo depende de JavaScript
- SEO prejudicado
- Indexação atrasada
- Performance inicial ruim
- Problemas para crawlers limitados

---

# 2️⃣ Como o Google Indexa Páginas

O processo possui 3 etapas:

## 1. Crawl (Rastreamento)

O bot acessa a URL e baixa o HTML inicial.

Se houver conteúdo no HTML → indexação imediata  
Se depender de JS → vai para renderização

---

## 2. Renderização

O Google executa JavaScript usando um motor baseado no Chrome.

Problemas:

- Pode demorar dias
- Pode falhar se houver erro JS
- Não é prioridade imediata
- Alto custo computacional

---

## 3. Indexação

Após renderizar, o Google extrai:

- Title
- Meta description
- Canonical
- H1-H6
- Texto
- Dados estruturados
- Links internos

---

# 3️⃣ Server-Side Rendering (SSR)

## Conceito

O servidor executa o Angular e envia HTML completo ao navegador.

## Fluxo

1. Requisição chega ao servidor
2. Angular roda no Node
3. HTML completo é gerado
4. Navegador recebe a página pronta
5. Angular hidrata a aplicação

---

## Benefícios

- Melhor SEO
- Conteúdo disponível imediatamente
- Melhor LCP
- Melhor preview social
- Melhor indexação

---

## Configuração no Angular

```bash
ng add @angular/ssr
npm run build
npm run serve:ssr
```

---

# 4️⃣ Static Site Generation (SSG)

## Conceito

As páginas são geradas no momento do build.

Ideal para:

- Blogs
- Landing pages
- Documentação
- Conteúdo institucional

---

## Vantagens

- Performance máxima
- HTML estático
- Pode usar CDN
- Indexação instantânea
- Custo muito baixo

---

# 5️⃣ SSR vs SSG

| Característica | SSR | SSG |
|---------------|-----|-----|
| Renderização | Por requisição | No build |
| Ideal para | Conteúdo dinâmico | Conteúdo estático |
| Escalabilidade | Média | Muito alta |
| Custo | Médio | Muito baixo |
| Performance | Alta | Muito alta |

---

# 6️⃣ Hidratação

## O que é?

Processo onde o Angular conecta eventos e estado ao HTML já renderizado.

Sem hidratação:
- DOM recriado
- Perda de performance

Com hidratação:
- DOM reaproveitado
- Melhor tempo de interação
- Menor custo de execução

---

# 7️⃣ Hidratação Parcial (Partial Hydration)

## Conceito

Apenas partes interativas são hidratadas.

Exemplo:

- Header estático → não hidrata
- Botões → hidratam
- Comentários → hidratação sob demanda

---

## Benefícios

- Menor bundle JS
- Melhor INP
- Melhor TTI
- Melhor performance mobile
- Menor uso de CPU

---

# 8️⃣ Tags SEO Essenciais

## Title (mais importante)

```html
<title>Curso Angular SSR Completo</title>
```

Impacta ranking e CTR.

---

## Meta Description

```html
<meta name="description" content="Aprenda Angular SSR com SEO avançado.">
```

Impacta taxa de clique.

---

## Canonical

```html
<link rel="canonical" href="https://site.com/curso-angular">
```

Evita conteúdo duplicado.

---

## Open Graph

```html
<meta property="og:title" content="Curso Angular SSR">
<meta property="og:description" content="Aprenda SSR moderno">
<meta property="og:image" content="https://site.com/img.png">
```

Controla preview social.

---

## Dados Estruturados

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Course",
  "name": "Curso Angular SSR"
}
</script>
```

Permite:

- Rich snippets
- FAQ expandida
- Estrelas
- Melhor visibilidade

---

# 9️⃣ Core Web Vitals

Métricas usadas como fator de ranking:

- LCP (Largest Contentful Paint)
- FCP (First Contentful Paint)
- CLS (Cumulative Layout Shift)
- INP (Interaction to Next Paint)

Impacto das estratégias:

- SSR melhora LCP e FCP
- SSG maximiza performance
- Hidratação parcial melhora INP

---

# 🔟 SEO para Agentes de IA (AI SEO)

Além do SEO tradicional, agora existe otimização para agentes de IA.

Esses agentes:

- Lêem páginas
- Extraem significado semântico
- Geram respostas
- Utilizam dados estruturados

---

## O que agentes de IA priorizam

- HTML já renderizado
- Estrutura semântica
- JSON-LD
- Schema.org
- Texto claro
- Hierarquia bem definida

---

## Controle via robots.txt

```txt
User-agent: GPTBot
Allow: /

User-agent: Google-Extended
Allow: /
```

Permite ou bloqueia crawlers de IA.

---

## Meta robots

```html
<meta name="robots" content="index, follow">
```

Controla indexação.

---

## HTML Semântico

Utilizar corretamente:

- <main>
- <article>
- <section>
- <header>
- <nav>
- <aside>

Melhora interpretação por IA.

---

# 1️⃣1️⃣ Estratégias Avançadas

## Lazy Hydration
Hidrata componente quando entra na viewport.

## Edge Rendering
SSR executado na borda da CDN.

## Incremental Static Regeneration (ISR)
Revalidação automática de páginas estáticas.

## Streaming SSR
HTML enviado em partes conforme fica pronto.

---

# 1️⃣2️⃣ Arquitetura Moderna Recomendada

Estratégia profissional:

1. SSG para conteúdo estático
2. SSR para conteúdo dinâmico
3. Hidratação parcial
4. CDN com cache
5. Sitemap.xml
6. Robots.txt
7. Dados estruturados
8. Canonical correto
9. HTML semântico
10. Controle de AI crawlers

---

# 🎯 Conclusão Técnica

SPA pura depende totalmente de JavaScript → SEO fraco.

Arquitetura moderna combina:

- SSR
- SSG
- Hidratação parcial
- Dados estruturados
- Performance otimizada
- Estratégia para agentes de IA

Resultado:

- Melhor indexação
- Melhor ranking
- Melhor performance
- Melhor experiência do usuário
- Melhor adaptação ao futuro da busca com IA
