# Relatório de melhoria das páginas de matéria — Cosmos Week

Data: 2026-06-15

## Problema identificado

As páginas estáticas de matéria estavam tecnicamente funcionais, mas visualmente pareciam documentos isolados. Ao clicar em uma matéria, o leitor saía da experiência editorial principal do Cosmos Week e caía numa página com apenas um topo mínimo, sem cabeçalho completo, navegação principal, barra de editorias e rodapé institucional.

Isso criava a impressão de página genérica, mesmo com bom conteúdo, metadados e estrutura de artigo.

## Correções aplicadas

1. Todas as páginas em `/noticia/.../index.html` receberam um shell editorial completo.
2. Todas as páginas em `/en/news/.../index.html` receberam o mesmo tratamento em inglês.
3. Foi criado o arquivo `/assets/css/article-shell.css` para controlar o novo cabeçalho, barra de editorias, ferramentas e rodapé das matérias.
4. O gerador `/scripts/fetch_news.py` foi atualizado para aplicar automaticamente esse shell nas próximas matérias geradas.
5. A versão do template estático foi atualizada para `site-shell-v4-2026-06-15`.
6. O botão estranho “Abrir versão dinâmica” foi substituído por navegação editorial mais natural: “Explorar arquivo” / “Explore archive”.
7. O botão “Abrir homepage” foi substituído por “Mais notícias” / “More stories”.
8. As páginas em inglês passaram a apontar para `/en/`, evitando a rota menos elegante `?lang=en` dentro das matérias estáticas.
9. O breadcrumb de “Notícias” agora aponta para o arquivo em vez de simplesmente voltar para a home.

## Resultado prático

Agora, ao abrir uma matéria, o leitor continua vendo:

- identidade visual do Cosmos Week;
- navegação principal;
- busca;
- seletor de idioma;
- botão de metodologia;
- acesso comercial “Anuncie”;
- barra de editorias;
- rodapé com navegação, transparência, RSS, sitemap, privacidade, termos e contato.

A página deixa de parecer “solta” e passa a parecer uma matéria real dentro de um portal editorial.

## Validação feita

Foram verificadas 2.062 páginas de matéria:

- 1.031 páginas em português em `/noticia/`;
- 1.031 páginas em inglês em `/en/news/`.

Todas foram confirmadas com:

- cabeçalho novo presente;
- rodapé novo presente;
- CSS novo carregado;
- classe `cw-static-article` no `<body>`;
- ausência dos rótulos antigos “Abrir versão dinâmica” e “Open live edition”.
