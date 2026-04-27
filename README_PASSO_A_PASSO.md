# Landing page — Os Bichinhos Cantam

Pacote pronto para publicar gratuitamente no GitHub Pages.

## Arquivos

- `index.html`: página principal com SEO básico, Open Graph e JSON-LD.
- `styles.css`: visual da landing page.
- `favicon.svg`: ícone simples.
- `robots.txt`: permite rastreamento e aponta para o sitemap.
- `sitemap.xml`: informa a URL principal ao Google.

## Antes de publicar

Troque todos os textos `SEU-USUARIO`, `SEU-CANAL` e `SEU-PERFIL` pelos links reais.

Exemplo:
- `SEU-USUARIO` → seu usuário do GitHub.
- `https://www.youtube.com/@SEU-CANAL` → link real do canal.
- `https://www.tiktok.com/@SEU-PERFIL` → link real do TikTok.
- `https://www.instagram.com/SEU-PERFIL` → link real do Instagram.
- `https://www.kwai.com/@SEU-PERFIL` → link real do Kwai.

## URL final esperada

Se você criar um repositório chamado `os-bichinhos-cantam`, a URL tende a ficar:

`https://SEU-USUARIO.github.io/os-bichinhos-cantam/`

Depois de descobrir a URL real, atualize:

- `index.html`: campos `canonical`, `og:url`, `og:image`, `twitter:image`, `url`, `image`.
- `robots.txt`: linha `Sitemap`.
- `sitemap.xml`: tag `<loc>`.

## Imagem de capa

Crie uma pasta `assets` e coloque uma imagem chamada:

`cover.jpg`

Caminho final:

`assets/cover.jpg`

Dimensão recomendada para preview social: 1200 x 630 px.
