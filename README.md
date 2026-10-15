# Studio Matemática

Aplicação web de acompanhamento, aprendizagem e simulados de matemática.

## Estrutura do projeto

```text
.
├── index.html                 # Aplicação (HTML, CSS e JavaScript embutidos)
├── manifest.webmanifest       # Metadados para instalação como aplicativo (PWA)
├── sw.js                      # Service worker e cache básico do app shell
├── icons/
│   ├── favicon-32.png
│   ├── icon-192.png
│   ├── icon-512.png
│   └── icon-512-maskable.png
├── .gitignore
└── README.md
```

## Testar localmente

Para testar recursos de PWA/service worker, abra a pasta por um servidor local (não diretamente com `file://`). Por exemplo, com Python instalado:

```bash
python -m http.server 8000
```

Depois acesse `http://localhost:8000`.

## Publicar no GitHub Pages

1. Crie um repositório no GitHub e envie todos os arquivos e a pasta `icons/` para a raiz do repositório.
2. No repositório, vá a **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, selecione a branch principal e a pasta **/(root)**.
4. Salve e aguarde o GitHub Pages publicar o endereço do site.

O arquivo principal se chama `index.html`, então o GitHub Pages consegue abrir o site pela página inicial do repositório.

## Observações

- O CSS e o JavaScript estão embutidos no `index.html`; por isso, não há pastas `css/` e `js/` separadas nesta versão.
- O cache do service worker ajuda a abrir a estrutura do site offline após a primeira visita, mas funções que dependem de internet, CDN ou Supabase continuam precisando de conexão.
- Se configurar Supabase ou outros serviços, não publique chaves secretas de servidor neste repositório. Use apenas as credenciais públicas apropriadas para aplicações web e as políticas de segurança do serviço.
