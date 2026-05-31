# 💄 Glow Beauty — E-commerce de Cosméticos

> Projeto front-end estático de e-commerce de cosméticos veganos e cruelty-free, desenvolvido com HTML5, CSS3 puro e zero dependência de JavaScript (interatividade via `:checked` + `<label>`).

---

## 📋 Índice

- [Visão Geral](#visão-geral)
- [Páginas](#páginas)
- [Estrutura de Arquivos](#estrutura-de-arquivos)
- [Tecnologias](#tecnologias)
- [Funcionalidades](#funcionalidades)
- [Como Executar](#como-executar)
- [Boas Práticas Aplicadas](#boas-práticas-aplicadas)
- [Mensagens de Commit](#mensagens-de-commit)
- [Próximos Passos](#próximos-passos)

---

## Visão Geral

**Glow Beauty** é um template de loja virtual completo, com identidade visual refinada baseada em tons rosê, dourado e branco. O projeto demonstra como construir fluxos de UI multi-etapa (wizard de checkout, abas de produto, navegação de conta) usando **apenas CSS**, sem nenhuma linha de JavaScript.

| Paleta principal | Tipografia |
|---|---|
| `#D4AF37` Dourado | Playfair Display (títulos) |
| `#F9EFF1` Rosê claro | Poppins (corpo/UI) |
| `#2C1810` Marrom escuro | |
| `#FFFFFF` Branco | |

---

## Páginas

| Arquivo | Rota | Descrição |
|---|---|---|
| `index.html` | `/` | Home — hero, destaques, ofertas, newsletter |
| `shop.html` | `/shop.html` | Catálogo — filtros laterais, grade de produtos, paginação |
| `produto.html` | `/produto.html` | Detalhes do produto — galeria, abas (descrição/ingredientes/avaliações) |
| `checkout.html` | `/checkout.html` | Checkout multi-etapa — identificação → entrega → pagamento → sucesso |
| `conta.html` | `/conta.html` | Minha Conta — pedidos, endereços, dados pessoais, programa de fidelidade |

---

## Estrutura de Arquivos

```
glow-beauty/
├── index.html
├── shop.html
├── produto.html
├── checkout.html
├── conta.html
├── css/
│   ├── style.css        # Estilos globais: reset, variáveis, header, footer, home
│   ├── shop.css         # Estilos da página de catálogo (sidebar + grade)
│   ├── produto.css      # Estilos da página de produto (galeria + abas)
│   ├── checkout.css     # Estilos do wizard de checkout multi-etapa
│   └── conta.css        # Estilos do painel "Minha Conta"
├── imagens/
│   ├── icon.ico
│   ├── produtos/        # Fotos dos produtos (PNG com fundo transparente)
│   └── ofertas/         # Banners e imagens promocionais
└── README.md
```

---

## Tecnologias

- **HTML5** — semântico, com ARIA labels e atributos de acessibilidade
- **CSS3 puro** — variáveis CSS, Flexbox, Grid, `backdrop-filter`, animações
- **Google Fonts** — Playfair Display + Poppins
- **Padrão CSS Checkbox Hack** — interatividade multi-step e abas via `input[type=radio]` + `:checked` + `~` seletor

> ⚠️ Nenhum JavaScript foi utilizado neste projeto.

---

## Funcionalidades

### 🏠 Home (`index.html`)
- Hero com CTA e imagem de destaque
- Seção de categorias em grid
- Carrossel de produtos em destaque
- Banner de oferta com contador visual
- Seção de diferenciais (vegano, cruelty-free, frete grátis)
- Newsletter com campo de e-mail

### 🛍️ Shop (`shop.html`)
- Sidebar de filtros: categorias, faixa de preço (range slider), tipo de pele, ingredientes (tags)
- Grade responsiva de produtos com badges (Mais Vendido, Lançamento, Low Stock, Vegano)
- Quick-buy e favoritar por produto
- Ordenação e alternância de visualização (grade/lista)
- Paginação

### 💄 Produto (`produto.html`)
- Galeria de 4 imagens com miniaturas clicáveis (CSS puro via `input[type=radio]`)
- Seletor de cor e quantidade
- Preço com desconto e parcelamento
- 4 abas: Descrição, Ingredientes, Modo de Uso, Avaliações
- Resumo de avaliações com barras de porcentagem
- Seção de produtos relacionados (scroll horizontal)

### 💳 Checkout (`checkout.html`)
- Wizard de 3 etapas + tela de sucesso (CSS puro via `input[type=radio]`)
- Etapa 1: Identificação (nome, e-mail, CPF, telefone, senha)
- Etapa 2: Endereço de entrega + seleção de frete
- Etapa 3: Pagamento (cartão, Pix, boleto) + parcelamento
- Sidebar de resumo do pedido com produtos, cupom e cálculo de frete
- Indicador visual de progresso de etapas

### 👤 Minha Conta (`conta.html`)
- Hero com avatar, nome, e-mail e pontos de fidelidade
- Navegação lateral com 4 painéis (CSS puro via `input[type=radio]`)
- Painel Pedidos: histórico com status (entregue, em trânsito), thumbnails de produtos
- Painel Endereços: cards com endereço principal e secundário
- Painel Dados: edição de perfil e alteração de senha
- Painel Fidelidade: pontos, nível (Ouro → Diamante), barra de progresso, grid de prêmios

---

## Como Executar

Por ser um projeto 100% estático, basta abrir os arquivos no navegador:

```bash
# Opção 1 — abrir direto no browser
open index.html

# Opção 2 — servidor local com Python
python3 -m http.server 8000
# Acesse: http://localhost:8000

# Opção 3 — VS Code Live Server
# Instale a extensão "Live Server" e clique em "Go Live"
```

> 💡 Recomendado usar um servidor local (opção 2 ou 3) para evitar restrições de CORS ao carregar as imagens.

---

## Boas Práticas Aplicadas

| Prática | Detalhes |
|---|---|
| **Encoding** | UTF-8 em todos os arquivos |
| **Line endings** | LF (Unix) — CRLF removido |
| **Trailing whitespace** | Removido de todas as linhas |
| **EOF newline** | Todos os arquivos terminam com `\n` |
| **Indentação** | 2 espaços consistentes em HTML e CSS |
| **Variáveis CSS** | Paleta centralizada em `:root` no `style.css` |
| **Semântica HTML** | `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`, `<section>` |
| **Acessibilidade** | `aria-label` nos botões de ícone, `alt` descritivo em todas as imagens |
| **CSS modular** | Um arquivo CSS por página, `style.css` com estilos globais compartilhados |
| **Performance** | Sem JS, sem frameworks, sem dependências externas além de Google Fonts |

---

## Mensagens de Commit

Sugestões de commits descritivos para cada arquivo:

```bash
git add css/style.css
git commit -m "feat(styles): adiciona reset global, variáveis de tema e estilos compartilhados de header/footer"

git add css/shop.css
git commit -m "feat(shop): implementa layout de catálogo com sidebar de filtros e grade responsiva de produtos"

git add css/produto.css
git commit -m "feat(produto): estiliza galeria com troca de imagem via CSS, abas e seção de avaliações"

git add css/checkout.css
git commit -m "feat(checkout): cria wizard multi-etapa (identificação → entrega → pagamento → sucesso) usando CSS puro"

git add css/conta.css
git commit -m "feat(conta): desenvolve painel de conta com navegação lateral, pedidos, endereços e programa de fidelidade"

git add index.html
git commit -m "feat(home): estrutura página inicial com hero, categorias, produtos em destaque e newsletter"

git add shop.html
git commit -m "feat(shop): adiciona catálogo completo com filtros, 9 cards de produto e paginação"

git add produto.html
git commit -m "feat(produto): implementa página de detalhe com galeria, abas CSS-only e produtos relacionados"

git add checkout.html
git commit -m "feat(checkout): constrói fluxo de checkout 3 etapas e resumo do pedido sem JavaScript"

git add conta.html
git commit -m "feat(conta): cria área logada com painel de pedidos, endereços, dados pessoais e clube de fidelidade"

git add README.md
git commit -m "docs: adiciona README completo com estrutura, funcionalidades e instruções de execução"
```

---

## Próximos Passos

- [ ] Adicionar JavaScript para validação de formulários em tempo real
- [ ] Implementar carrinho de compras com `localStorage`
- [ ] Integrar API de CEP (ViaCEP) para autocompletar endereço
- [ ] Tornar o layout responsivo para mobile (media queries)
- [ ] Adicionar modo escuro (`prefers-color-scheme: dark`)
- [ ] Conectar a um back-end (Node.js/Next.js) ou headless CMS
- [ ] Configurar CI/CD com GitHub Actions para deploy automático no GitHub Pages

---

<div align="center">
  <p>Feito com 💄 e muito CSS por <strong>Glow Beauty</strong></p>
  <p><em>Vegano · Cruelty-free · Feito com amor</em></p>
</div>
