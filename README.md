# Tarifa Social de Energia — landing page

Landing page estática (HTML/CSS/JS puro, sem build) que responde à busca de quem procura
**tarifa social**, **desconto na conta de luz** e **desconto de energia** no Brasil.
Traz um teste de elegibilidade de 4 perguntas, um fluxograma e, para quem não tem direito,
uma rota alternativa (energia por assinatura iGreen).

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | A página inteira: HTML, CSS, JS e JSON-LD num arquivo só |
| `robots.txt` | Libera explicitamente GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot, Google-Extended e cia. |
| `llms.txt` | Resumo em Markdown, na raiz, com os fatos prontos para citação por LLMs |
| `sitemap.xml` | Sitemap (atualize `lastmod` a cada revisão do conteúdo) |
| `og-image.png` | Imagem 1200×630 para WhatsApp, Facebook, X e LinkedIn |
| `favicon.svg` | Ícone |
| `404.html` | Página de erro do GitHub Pages |
| `.nojekyll` | Impede o Jekyll de processar/ignorar arquivos |

## Como publicar no GitHub Pages

```bash
# 1. crie o repositório em github.com/new  (sugestão de nome: tarifa-social)
git init
git add .
git commit -m "Landing page Tarifa Social + teste de elegibilidade"
git branch -M main
git remote add origin https://github.com/dutracaue/tarifa-social.git
git push -u origin main
```

Depois, no GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.

A URL fica: `https://dutracaue.github.io/tarifa-social/`

> **Se você usar outro nome de repositório ou um domínio próprio**, troque a URL em 5 lugares:
> `index.html` (canonical, og:url, og:image, twitter:image e o bloco JSON-LD), `sitemap.xml`,
> `robots.txt` (linha Sitemap), `llms.txt` e o link do `404.html`.

### Domínio próprio (recomendado para SEO)

Um domínio como `descontocontadeluz.com.br` rankeia melhor que um subdiretório do github.io.
Crie um arquivo `CNAME` na raiz com o domínio dentro, aponte o DNS para o GitHub Pages e
marque **Enforce HTTPS** nas configurações.

## Checklist de SEO / GEO já aplicado

- [x] Conteúdo todo em HTML estático — nada importante depende de JavaScript (crawlers de IA não executam JS)
- [x] Bloco "Resposta rápida" no topo, em formato extraível para AI Overviews e ChatGPT
- [x] Hierarquia H1 → H2 → H3, um tópico por seção, resposta antes do contexto
- [x] JSON-LD enxuto: Organization, WebSite, Article (com author + dateModified), BreadcrumbList, FAQPage
- [x] FAQ com 8 perguntas em linguagem natural (query fan-out)
- [x] `robots.txt` liberando os bots de IA + `llms.txt` na raiz
- [x] Canonical, Open Graph, Twitter Card, `lang="pt-BR"`
- [x] Zero dependência de framework, carrega rápido, responsivo, foco visível no teclado

## Manutenção (o que mais importa depois do lançamento)

1. **Frescor.** Motores de IA priorizam conteúdo recente. Sempre que o salário mínimo ou a
   regra mudar, atualize os valores, a data visível no rodapé, `dateModified` no JSON-LD e
   `lastmod` no `sitemap.xml`.
2. **Search Console + Bing Webmaster Tools.** Cadastre o site e envie o sitemap.
3. **Teste de citação.** Uma vez por mês, pergunte ao ChatGPT e ao Perplexity
   "quem tem direito à tarifa social de energia em 2026" e veja se o site aparece.
4. **Não duplique o FAQ** em outras páginas — conteúdo de FAQ repetido se anula.
