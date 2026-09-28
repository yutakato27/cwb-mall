# Orientações iniciais para o desenvolvimento

Antes de cada um começar a desenvolver sua tela, precisamos organizar algumas coisas para evitar que cada página seja criada de uma forma completamente diferente.

Como o projeto será feito apenas com **HTML e CSS**, a ideia de "componentes" é um pouco diferente do que acontece em frameworks como React ou Angular.

Aqui, um componente significa principalmente um **bloco de HTML que segue sempre a mesma estrutura e utiliza as mesmas classes CSS**.

Por exemplo, se criarmos um botão padrão:

```html
<a class="btn btn-primary" href="#">Ver detalhes</a>
```

E no CSS tivermos:

```css
.btn {
    padding: 10px 16px;
    border-radius: 8px;
    text-decoration: none;
}

.btn-primary {
    background-color: #000;
    color: #fff;
}
```

Sempre que outra tela precisar do mesmo botão, a pessoa deve utilizar essas mesmas classes em vez de criar outro botão completamente diferente.

Ou seja, estamos reutilizando o **padrão visual e a estrutura**, mesmo que o HTML precise aparecer novamente em páginas diferentes.

O mesmo vale para coisas como:

```text
header
botões
cards
avaliações
galeria de imagens
informações de restaurante
link de voltar
comentários
```

O objetivo dessa organização é fazer com que, no final, todas as páginas pareçam fazer parte do **mesmo site**.

## Checklist — primeiros passos

* [ ] **1. Clonar o repositório**

Cada pessoa deve primeiro clonar o projeto para o computador.

```bash
git clone URL_DO_REPOSITORIO
```

Depois:

```bash
cd nome-do-projeto
```

---

* [ ] **2. Atualizar a `main` antes de começar**

Antes de criar a própria branch:

```bash
git checkout main
git pull
```

Isso garante que você está começando com a versão mais recente do projeto.

---

* [ ] **3. Criar sua própria branch**

Cada pessoa deve trabalhar na sua própria branch.

Exemplo:

```bash
git checkout -b andre/home
```

ou:

```bash
git checkout -b anna/prato
```

Evitem desenvolver diretamente na `main`.

---

* [ ] **4. Conferir a estrutura do projeto**

A estrutura inicial será parecida com:

```text
/
├── index.html
│
├── pages/
│   ├── festival.html
│   ├── prato.html
│   └── restaurante.html
│
├── css/
│   └── style.css
│
├── assets/
│   ├── images/
│   └── icons/
│
└── README.md
```

Não criem pastas novas sem necessidade.

Principalmente para imagens, usem:

```text
assets/images/
```

E para estilos:

```text
css/
```

---

* [ ] **5. Não começar pelo CSS individual de cada tela**

Antes de cada pessoa estilizar sua página do jeito que quiser, precisamos definir alguns padrões gerais.

Principalmente:

```text
fonte
cores
background
largura máxima do conteúdo
espaçamento
border-radius
estilo dos botões
estilo dos cards
tamanho dos títulos
header
```

Esses estilos globais devem ficar no começo do `style.css`.

Por exemplo:

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}
```

Assim ninguém precisa reinventar essas configurações em cada página.

---

* [ ] **6. Verificar se o componente já existe antes de criar um novo**

Esse é provavelmente o ponto mais importante.

Antes de criar algo, pense:

> Já existe alguma coisa parecida no projeto?

Por exemplo:

Se André já criou:

```html
<a class="back-link" href="../index.html">
    ← Voltar
</a>
```

Anna não precisa criar:

```html
<a class="return-button">
    Voltar
</a>
```

Ela pode reutilizar:

```html
<a class="back-link" href="festival.html">
    ← Voltar
</a>
```

Assim temos **um único padrão de botão de voltar no projeto**.

---

* [ ] **7. Componentes compartilhados devem manter o mesmo nome**

Se definirmos:

```css
.restaurant-card
```

esse será o nome usado em todas as páginas.

Não criar variações como:

```css
.card-restaurante
.restaurant-box
.restaurant-container
.restaurant-item
```

para representar exatamente a mesma coisa.

Isso deixa o CSS muito mais difícil de manter.

---

* [ ] **8. Cada componente pode ter variações**

Reutilizar um componente não significa que ele precisa ser sempre 100% igual.

Podemos ter uma classe principal:

```html
<div class="card">
```

e adicionar uma variação:

```html
<div class="card restaurant-card">
```

ou:

```html
<div class="card festival-card">
```

Assim compartilhamos os estilos básicos de `card`, mas cada tipo pode ter características próprias.

---

* [ ] **9. Não altere um componente compartilhado sem verificar o impacto**

Imagine que o `.btn` está sendo usado nas quatro telas.

Se alguém alterar:

```css
.btn {
    width: 100%;
}
```

isso pode quebrar botões das páginas dos outros integrantes.

Então, ao alterar uma classe reutilizada, é importante verificar onde ela já está sendo usada.

Quando a mudança for específica de uma tela, prefira criar uma variação.

Por exemplo:

```css
.btn {
    /* padrão */
}

.btn-full {
    width: 100%;
}
```

E utilizar:

```html
<button class="btn btn-full">
```

---

* [ ] **10. Header e outros elementos repetidos precisarão aparecer em mais de um HTML**

Como estamos usando apenas HTML e CSS, não temos uma forma automática de importar o mesmo header para todas as páginas.

Então é normal que exista algo como:

```html
<header class="site-header">
    ...
</header>
```

em:

```text
index.html
festival.html
prato.html
restaurante.html
```

O importante é que todos utilizem **a mesma estrutura e as mesmas classes**.

Se alguém atualizar bastante a estrutura do header, deve avisar o grupo para que as outras páginas também sejam atualizadas.

---

* [ ] **11. Cuidado com caminhos relativos**

Como algumas páginas estarão dentro da pasta `pages`, os caminhos mudam.

No `index.html`:

```html
<link rel="stylesheet" href="css/style.css">
```

Mas dentro de:

```text
pages/prato.html
```

será:

```html
<link rel="stylesheet" href="../css/style.css">
```

O mesmo vale para imagens.

Na Home:

```html
<img src="assets/images/prato.jpg">
```

Em uma página dentro de `pages`:

```html
<img src="../assets/images/prato.jpg">
```

Esse provavelmente será um dos erros mais comuns durante o projeto.

---

* [ ] **12. Fazer commits pequenos**

Não precisa terminar a tela inteira para fazer um commit.

É melhor algo como:

```bash
git add .
git commit -m "Create dish details structure"
```

Depois:

```bash
git commit -m "Add dish image gallery styles"
```

Depois:

```bash
git commit -m "Add rating component"
```

do que um único commit:

```text
"fiz tudo"
```

Isso facilita bastante caso alguma coisa precise ser revisada.

---

* [ ] **13. Antes de enviar alterações**

Sempre verificar:

```bash
git status
```

Depois:

```bash
git add .
git commit -m "Descrição da alteração"
git push
```

Na primeira vez que enviar a branch:

```bash
git push -u origin nome-da-branch
```

---

* [ ] **14. Quando terminar uma parte, abrir Pull Request**

Não juntar diretamente na `main`.

Fluxo esperado:

```text
branch da pessoa
        ↓
Pull Request
        ↓
revisão
        ↓
main
```

Assim conseguimos verificar se alguma mudança interfere nas páginas dos outros antes de integrar.

---

* [ ] **15. Depois que algo entrar na `main`, todos devem atualizar suas branches**

Quando uma alteração importante for integrada:

```bash
git checkout main
git pull
```

Depois volte para sua branch:

```bash
git checkout sua-branch
```

E traga as mudanças:

```bash
git merge main
```

Assim você continua trabalhando com os componentes mais recentes.

---

## Regra principal do projeto

Antes de criar algo novo:

> **Procure primeiro se já existe um componente que pode ser reutilizado.**

E antes de alterar algo compartilhado:

> **Verifique se essa mudança pode afetar a página de outra pessoa.**

Cada pessoa continua responsável pela sua própria tela, mas os componentes compartilhados pertencem ao **projeto inteiro**, não somente à pessoa que os criou.

Por isso, comunicação será importante principalmente quando alguém criar ou modificar componentes reutilizáveis.

## Ordem recomendada para começar

Antes de desenvolver as telas completas, o ideal é fazermos primeiro:

```text
1. Estrutura de pastas
        ↓
2. CSS global
        ↓
3. Header e navegação
        ↓
4. Componentes compartilhados principais
        ↓
5. Estrutura HTML de cada tela
        ↓
6. CSS específico de cada tela
        ↓
7. Integração entre as páginas
        ↓
8. Responsividade
        ↓
9. Revisão final
```

Não precisamos deixar todos os componentes perfeitos antes de começar as páginas.

A ideia é apenas definir uma **base comum primeiro**. Depois cada integrante desenvolve sua parte e, conforme surgirem componentes que possam ser compartilhados, eles são incorporados ao padrão do projeto.

Isso deve evitar dois problemas comuns em trabalhos em grupo: cada tela parecer um site diferente e várias pessoas criarem soluções diferentes para exatamente a mesma coisa.

# Checklist individual — o que cada um já pode começar

A prioridade inicial de cada pessoa deve ser:

**modelar a própria tela → criar seus componentes → montar o HTML → começar o CSS específico.**

Não precisa esperar componentes compartilhados de outra pessoa. Quando eles forem integrados, ajustamos/reutilizamos.

---

## André — Home / Explorar Festivais

* [ ] Fazer a **modelagem da Home** antes de codar

  * definir as seções da página
  * ordem dos elementos
  * onde ficam filtros, cards, destaques e mapa
* [ ] Criar o esqueleto do `index.html`
* [ ] Desenvolver os componentes:

  * `search-bar`
  * `select-filter`
  * `festival-card`
  * `featured-list`
  * `map-panel`
* [ ] Criar alguns festivais fictícios/reais como exemplo para testar os cards
* [ ] Montar a grid/listagem dos festivais
* [ ] Fazer o CSS específico da Home
* [ ] Deixar os links dos cards preparados para abrir a página de detalhes do festival
* [ ] Separar e organizar imagens necessárias em `assets/images`

**Não depende de ninguém:** pode usar um header temporário enquanto o definitivo ainda não estiver integrado.

---

## João — Detalhes do Festival

* [ ] Fazer a **modelagem da página do festival**

  * banner/imagem
  * nome
  * período
  * descrição
  * informações principais
  * restaurantes participantes
* [ ] Criar `pages/festival.html`
* [ ] Desenvolver os componentes:

  * `site-header`
  * `back-link`
  * `restaurant-card`
* [ ] Criar dados de exemplo de um festival para montar a página
* [ ] Criar pelo menos 2 ou 3 `restaurant-card` para testar o layout
* [ ] Fazer o CSS da página
* [ ] Preparar os links dos restaurantes para `restaurante.html`
* [ ] Conferir como o layout se comporta com descrições pequenas e grandes

**Importante:** o `site-header` será usado pelos outros depois, então deve ser feito de forma genérica e não pensando somente na página de festival.

---

## Anna — Detalhes do Prato

* [ ] Fazer a **modelagem da página do prato**

  * galeria/foto principal
  * nome do prato
  * restaurante
  * descrição
  * preço/informações
  * avaliação
  * comentários/reviews
* [ ] Criar `pages/prato.html`
* [ ] Desenvolver os componentes:

  * `media-gallery`
  * `rating`
  * `review-card`
  * `btn`
* [ ] Criar informações de um prato de exemplo para preencher a tela
* [ ] Fazer diferentes exemplos de avaliação/review para testar
* [ ] Criar o CSS da página
* [ ] Preparar link para voltar ao restaurante/festival
* [ ] Testar a galeria com diferentes quantidades e tamanhos de imagem

**Importante:** `btn` e `media-gallery` podem ser usados em outras telas, então evitar colocar estilos muito específicos da página do prato diretamente neles.

---

## Sofia — Detalhes do Restaurante

* [ ] Fazer a **modelagem da página do restaurante**

  * imagem
  * nome
  * descrição
  * tipo de culinária
  * localização
  * informações principais
  * pratos participantes
  * comentários
* [ ] Criar `pages/restaurante.html`
* [ ] Desenvolver os componentes:

  * `info-panel`
  * `comment-card`
* [ ] Criar dados de um restaurante de exemplo
* [ ] Criar a área/listagem dos pratos disponíveis
* [ ] Fazer o CSS específico da página
* [ ] Preparar links dos pratos para `prato.html`
* [ ] Reservar a área onde será utilizado o `media-gallery`

**Não precisa esperar o `media-gallery` da Anna:** pode criar inicialmente apenas um bloco placeholder, por exemplo:

```html
<section class="media-gallery-placeholder">
    <!-- media-gallery será inserido aqui -->
</section>
```

Depois substituímos pelo componente definitivo.

---

# O que todos devem fazer primeiro

Antes de focar em detalhes visuais:

* [ ] Desenhar/modelar rapidamente a própria tela
* [ ] Identificar quais partes são componentes
* [ ] Montar o HTML sem se preocupar em deixar bonito
* [ ] Testar a hierarquia e organização das informações
* [ ] Depois começar o CSS
* [ ] Usar conteúdo de exemplo para conseguir visualizar a tela completa
* [ ] Não depender de outra página estar pronta para criar links

Por exemplo:

```html
<a href="restaurante.html">Ver restaurante</a>
```

O link pode existir mesmo que `restaurante.html` ainda não esteja terminado.

---

# Sobre a modelagem

Antes de escrever muito CSS, cada pessoa deveria ter pelo menos um esboço simples da tela, mesmo que seja feito no papel, Figma, Excalidraw ou semelhante.

O objetivo não é fazer um protótipo perfeito.

É simplesmente responder:

```text
O que aparece primeiro?
↓
Quais informações vêm depois?
↓
Quais elementos se repetem?
↓
Quais desses elementos viram componentes?
↓
Como o usuário chega à próxima página?
```

Por exemplo, na página de um festival:

```text
Header

↓
Voltar

↓
Imagem + nome do festival

↓
Data / localização / descrição

↓
Restaurantes participantes

↓
[restaurant-card] [restaurant-card] [restaurant-card]
```

A partir disso fica muito mais fácil transformar a estrutura em HTML.

---

# Regra para essa primeira etapa

Ninguém precisa ficar esperando outra pessoa terminar.

Se um componente compartilhado ainda não existir, **deixe o espaço preparado e continue sua tela**.

Depois fazemos a integração:

```text
Cada um desenvolve sua base
        ↓
Componentes compartilhados ficam prontos
        ↓
Integramos nas outras páginas
        ↓
Padronizamos CSS
        ↓
Revisamos o site completo
```

O mais importante agora é todo mundo conseguir terminar a **estrutura e a modelagem da própria tela**, porque isso já permite identificar cedo o que realmente precisa ser compartilhado entre as páginas.
