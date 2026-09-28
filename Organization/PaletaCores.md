# Brand Guide — CWB Malls · Shoppings de Curitiba

Este documento define o padrão visual do projeto e deve ser seguido em todas as páginas para que o site mantenha a mesma identidade, mesmo sendo desenvolvido por pessoas diferentes.

O objetivo visual é transmitir uma sensação de **modernidade urbana, confiança, praticidade e sofisticação**, sem parecer formal demais.

---

# 1. Identidade visual

A identidade do site será baseada em:

* azul profundo como cor institucional principal — transmite confiança e profissionalismo;
* dourado como cor de destaque e ações — transmite premium e sofisticação;
* fundo cinza-azulado leve — moderno e limpo, sem parecer genérico;
* cards brancos com sombras azuladas sutis;
* títulos com fonte elegante;
* textos com fonte moderna e de alta legibilidade.

A interface deve parecer:

**moderna + urbana + confiável + sofisticada.**

Evitar:

* muitas cores diferentes;
* sombras muito fortes ou quentes;
* bordas muito arredondadas;
* excesso de gradientes;
* textos completamente pretos (`#000000`);
* muitos elementos chamativos competindo entre si.

---

# 2. Paleta de cores

## Azul profundo — cor principal

**HEX:** `#1B3A6B`

Principal cor da identidade. Referência ao céu azul de Curitiba e ao profissionalismo.

Usar em:

* header;
* footer;
* títulos importantes;
* elementos de navegação;
* botões secundários;
* bordas ativas e focus.

```css
--color-primary: #1B3A6B;
```

---

## Azul escuro

**HEX:** `#122851`

Variação mais escura do azul principal.

Usar em:

* hover de elementos azuis;
* footer ainda mais escuro se necessário;
* estados ativos.

```css
--color-primary-dark: #122851;
```

---

# 3. Dourado — cor de destaque

**HEX:** `#C9971A`

Cor de ação e destaque do site. Transmite luxo, qualidade e sofisticação.

Usar em:

* botões principais;
* links importantes;
* tags;
* destaques;
* elementos interativos;
* ícones que precisam chamar atenção.

Exemplo:

**Ver detalhes**

```css
--color-secondary: #C9971A;
--color-terracotta: #C9971A; /* alias para compatibilidade */
```

---

## Dourado escuro

**HEX:** `#A87C14`

Usar principalmente em hover.

```css
--color-secondary-dark: #A87C14;
--color-terracotta-dark: #A87C14; /* alias para compatibilidade */
```

Exemplo:

```css
.btn-primary:hover {
    background-color: var(--color-secondary-dark);
}
```

---

# 4. Dourado claro — cor de acento

**HEX:** `#F0C040`

Cor de apoio. Não deve aparecer em grandes áreas.

Usar principalmente em:

* estrelas de avaliação (★★★★★);
* badges especiais;
* shopping em destaque;
* pequenos ícones de destaque.

```css
--color-accent: #F0C040;
```

---

# 5. Background principal

**HEX:** `#F4F6F9`

Fundo das páginas. Tom levemente azulado — moderno e neutro.

```css
--color-background: #F4F6F9;
```

Evitar usar `#FFFFFF` como fundo principal das páginas.

O cinza-azulado faz as páginas parecerem mais modernas e faz os cards brancos se destacarem.

---

# 6. Background de cards

**HEX:** `#FFFFFF`

Branco puro. Usar em:

* cards;
* painéis;
* caixas de informações;
* filtros;
* reviews;
* áreas destacadas.

```css
--color-surface: #FFFFFF;
```

---

# 7. Texto principal

**HEX:** `#1A1A2E`

Quase preto com leve tom azul. Usar em:

* títulos;
* textos principais;
* informações importantes.

```css
--color-text: #1A1A2E;
```

Evitar preto puro `#000000`.

---

# 8. Texto secundário

**HEX:** `#5A6380`

Cinza-azulado médio. Usar em:

* descrições;
* horários;
* endereços;
* informações secundárias;
* textos auxiliares;
* placeholders.

```css
--color-text-secondary: #5A6380;
```

---

# 9. Bordas

**HEX:** `#D8DDE8`

Cinza frio leve. Usar em:

* inputs;
* cards;
* divisórias;
* dropdowns;
* filtros.

```css
--color-border: #D8DDE8;
```

---

# 10. Tipografia

Utilizaremos duas fontes.

## Fonte de destaque

### Playfair Display

Utilizada nos títulos principais para dar identidade ao projeto.

Usar em:

* `h1`;
* nome dos shoppings;
* nome das lojas;
* nome dos produtos;
* títulos principais de cada página.

```css
font-family: "Playfair Display", serif;
```

---

## Fonte principal da interface

### Inter

Utilizada em todo o restante do site.

Usar em:

* parágrafos;
* menus;
* botões;
* filtros;
* cards;
* avaliações;
* tags;
* informações;
* formulários.

```css
font-family: "Inter", sans-serif;
```

---

# 11. Importação das fontes

Adicionar no `<head>` de todas as páginas:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link
    href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Playfair+Display:wght@600;700&display=swap"
    rel="stylesheet"
>
```

---

# 12. Hierarquia de textos

## H1 — título principal da página

**Playfair Display** · `48px` · peso `700` · cor `#1A1A2E`

```css
h1 {
    font-family: "Playfair Display", serif;
    font-size: 48px;
    font-weight: 700;
    color: var(--color-text);
    line-height: 1.15;
}
```

## H2 — título de seção

**Playfair Display** · `32px` · peso `600` · cor `#1A1A2E`

## H3 — título de card

**Inter** · `20px` · peso `600` · cor `#1A1A2E`

---

# 13. Botão principal

Background: `#C9971A` · Texto: `#FFFFFF` · `Inter` · peso `600` · `15px` · border-radius `8px`

```css
.btn-primary {
    background-color: var(--color-secondary);
    color: #FFFFFF;
    padding: 12px 20px;
    border: none;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: 0.2s ease;
}

.btn-primary:hover {
    background-color: var(--color-secondary-dark);
}
```

---

# 14. Botão secundário

```css
.btn-secondary {
    background: transparent;
    color: var(--color-primary);
    border: 1px solid var(--color-primary);
    border-radius: 8px;
    padding: 11px 20px;
}

.btn-secondary:hover {
    background-color: var(--color-primary);
    color: white;
}
```

---

# 15. Cards

```css
.card {
    background-color: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 16px rgba(27, 58, 107, 0.10);
}
```

Cards clicáveis:

```css
.card-clickable {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.card-clickable:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(27, 58, 107, 0.16);
}
```

---

# 16. Espaçamento

Múltiplos de `4px`: `4 · 8 · 12 · 16 · 20 · 24 · 32 · 40 · 48 · 64px`

---

# 17. Resumo da paleta

| Variável | HEX | Uso |
|---|---|---|
| `--color-primary` | `#1B3A6B` | Header, footer, nav, links |
| `--color-primary-dark` | `#122851` | Hover azul |
| `--color-secondary` | `#C9971A` | Botões, CTAs, destaques |
| `--color-secondary-dark` | `#A87C14` | Hover dourado |
| `--color-accent` | `#F0C040` | Estrelas, badges |
| `--color-background` | `#F4F6F9` | Fundo das páginas |
| `--color-surface` | `#FFFFFF` | Cards e painéis |
| `--color-text` | `#1A1A2E` | Textos principais |
| `--color-text-secondary` | `#5A6380` | Textos secundários |
| `--color-border` | `#D8DDE8` | Bordas e divisórias |
