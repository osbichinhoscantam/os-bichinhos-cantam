# Os Bichinhos Cantam — Site oficial

Landing estática do projeto brasileiro de música infantil **Os Bichinhos Cantam**, com Edgar, João, Duda e Raquel. Estado atual: pré-lançamento do Vol. 1 em 12/05/2026.

- **URL oficial:** https://osbichinhoscantam.github.io/os-bichinhos-cantam/
- **Hospedagem:** GitHub Pages (estático, sem backend)
- **Stack:** HTML + CSS, sem frameworks, sem JS pesado.

## Links oficiais

| Plataforma | URL |
|---|---|
| Spotify Artist | https://open.spotify.com/artist/374HOBk3QG7FJRoDCOQnXE |
| Apple Music Artist | https://music.apple.com/us/artist/os-bichinhos-cantam/1895318699 |
| YouTube | https://youtube.com/@osbichinhoscantam |
| Instagram | https://www.instagram.com/osbichinhoscantam |
| TikTok | https://www.tiktok.com/@os.bichinhos.cantam |
| Kwai | https://kwai.com/@osbichinhoscantam |

## Estrutura do repositório

```
os-bichinhos-cantam/
├── index.html
├── styles.css
├── sitemap.xml
├── robots.txt
├── favicon.svg
├── googlec72d03a0d08176a6.html   # verificação Google Search Console
├── README.md
└── assets/
    ├── hero.jpg              # 1600×900 — banner principal
    ├── og-image.jpg          # 1200×630 — preview social/Google
    ├── cover.jpg             # 1200×1200 — capa quadrada
    ├── banner-wide.jpg       # 1600×436 — panorâmico
    ├── poster-vertical.jpg   #  900×1600 — pôster vertical
    ├── edgar.jpg             #  720×720 — card personagem
    ├── joao.jpg              #  720×720 — card personagem
    ├── duda.jpg              #  720×720 — card personagem
    └── raquel.jpg            #  720×720 — card personagem
```

## Como atualizar

### Trocar/adicionar links de streaming

Edite `index.html` em dois lugares:

1. CTAs do hero (`section.hero` → `.cta-row`).
2. Lista de links oficiais (`section#links` → `.link-list`).

Mantenha sempre `target="_blank" rel="noopener noreferrer"` em links externos.

### Trocar imagens

Sobrescreva o arquivo correspondente em `/assets/` mantendo o **mesmo nome** e **mesmas proporções**:

- Hero: 16:9 (recomendado 1600×900).
- Capa: 1:1 (1200×1200).
- OG image: 1200×630.
- Banner panorâmico: ~1600×436 (preservar proporção).
- Pôster vertical: 9:16.
- Personagens: 1:1 (mínimo 720×720, recomendado 900×900).

**Não distorcer personagens.** Use `object-fit: cover` (cortar bordas) ou `object-fit: contain` (mostrar tudo). Para preencher área lateral/superior faltante, expandir fundo com IA — nunca redesenhar nem esticar.

### Validar sitemap e robots

- Abrir `https://osbichinhoscantam.github.io/os-bichinhos-cantam/sitemap.xml`
- Abrir `https://osbichinhoscantam.github.io/os-bichinhos-cantam/robots.txt`
- Atualizar `<lastmod>` em `sitemap.xml` ao publicar mudanças relevantes.

### Deploy via GitHub Pages

1. Branch publicada: `main`.
2. Pasta: raiz `/`.
3. Settings → Pages → Source: `Deploy from a branch` → `main` → `/ (root)`.
4. URL final: `https://osbichinhoscantam.github.io/os-bichinhos-cantam/`.

Cada `git push` para `main` republica o site automaticamente em ~1 minuto.

## Checklist pré-commit

- [ ] `index.html` aponta para os assets corretos.
- [ ] `sitemap.xml` tem URL canônica e `lastmod` atualizado.
- [ ] `robots.txt` aponta para o sitemap correto.
- [ ] **Sem** senhas, tokens, chaves, `.env` ou dados privados.
- [ ] Imagens sem distorção e com `alt` descritivo em PT-BR.
- [ ] Links externos com `target="_blank" rel="noopener noreferrer"`.
- [ ] Site abre corretamente no celular (testar 360px e 390px).
- [ ] Em pré-lançamento, não usar “já no ar”, “ouvir agora” ou links de faixa como se o EP já estivesse disponível.
- [ ] Link principal de pré-lançamento leva para o HyperFollow/pré-save correto.
- [ ] Links Spotify/Apple em pré-lançamento levam para páginas de artista, não para botões “ouvir agora”.

## Segurança — repositório público

O repositório é público porque o site é 100% estático.

**Nunca commitar:**

- Senhas, tokens, chaves de API.
- Arquivos `.env` reais.
- Dados pessoais (CPF, endereço, telefone).
- Prints de painéis internos (DistroKid, Spotify for Artists, Search Console).

**Regra de ouro:** se a informação não deveria aparecer para qualquer pessoa no Google, ela não pode estar neste repositório.

## SEO / Search Console

- Propriedade Search Console: `https://osbichinhoscantam.github.io/os-bichinhos-cantam/`
- Sitemap enviado: `/sitemap.xml`
- Verificação por arquivo HTML: `googlec72d03a0d08176a6.html`

Solicitar nova indexação apenas após mudança relevante (novo link principal, nova OG image, alteração grande de copy).

## Licença / direitos

© Os Bichinhos Cantam. Todos os direitos reservados sobre conteúdo musical, personagens e identidade visual. Código do site disponível para consulta no contexto deste repositório.
