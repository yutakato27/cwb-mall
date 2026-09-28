Gente, pra gente já começar o projeto de forma organizada, pensei em manter a divisão das telas que combinamos anteriormente.

A ideia do site é reunir os principais shoppings de Curitiba em um só lugar, mostrando os shoppings, lojas participantes, produtos/serviços, localização e outras informações relevantes.

O projeto vai ser feito somente com **HTML e CSS**.

A divisão vai ficar assim:

**João — Home + Explorar Shoppings**

* Página inicial do site
* Área de busca e filtros
* Cards dos shoppings
* Seção de shoppings em destaque
* Parte relacionada ao mapa/localização dos shoppings

Arquivos principais:

```text
index.html
```

**André — Detalhes do Shopping**

* Tela com as informações completas de um shopping
* Nome, descrição e informações gerais
* Lojas do shopping
* Navegação de retorno para as outras páginas

Arquivo principal:

```text
pages/festival.html
```

**Anna — Detalhes do Produto**

* Tela com os detalhes de um produto disponível no shopping
* Imagens
* Descrição
* Informações do produto
* Avaliação
* Reviews/comentários
* Botões e informações relacionadas

Arquivo principal:

```text
pages/pratos.html
```

**Sofia — Detalhes da Loja**

* Tela com as informações completas da loja
* Informações gerais
* Localização dentro do shopping
* Imagens
* Produtos/serviços disponíveis
* Comentários e informações adicionais

Arquivo principal:

```text
pages/restaurante.html
```

A estrutura inicial do projeto deve ficar mais ou menos assim:

```text
/
├── index.html
│
├── pages/
│   ├── festival.html     ← detalhes do shopping
│   ├── pratos.html       ← detalhes do produto
│   └── restaurante.html  ← detalhes da loja
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

Todos devem conseguir clonar o projeto, criar branches, fazer commit e push normalmente.

Pra não dar conflito, a ideia é cada um trabalhar em uma branch própria.

Evitem fazer alterações direto na `main`.

Quando uma parte estiver pronta, a pessoa abre um **Pull Request** e depois a gente junta tudo na `main`.

Também é importante sempre fazer:

```bash
git pull
```

antes de começar a trabalhar, principalmente depois que alguma alteração já tiver sido integrada.

Outra coisa importante: apesar de cada um ter sua própria tela, o site precisa parecer um projeto único. Então vamos manter o mesmo padrão de:

* cores
* fontes
* header
* botões
* espaçamentos
* estilo dos cards
* bordas
* tamanhos
* responsividade

Alguns componentes também vão aparecer em mais de uma tela, então é melhor reutilizar o mesmo estilo em vez de cada um criar uma versão diferente.

A divisão dos componentes que tínhamos pensado era:

**João**

* `search-bar`
* `select-filter`
* `shopping-card`
* `featured-list`
* `map-panel`

**André**

* `site-header`
* `back-link`
* `store-card`

**Anna**

* `media-gallery`
* `rating`
* `review-card`
* `btn`

**Sofia**

* `info-panel`
* `comment-card`
* reutiliza o `media-gallery`

O ideal é, quando alguém terminar um componente que outra pessoa também vai usar, avisar no grupo pra gente reaproveitar e manter tudo igual.

Assim cada um consegue desenvolver sua parte de forma relativamente independente, mas no final as telas continuam conectadas e visualmente consistentes.