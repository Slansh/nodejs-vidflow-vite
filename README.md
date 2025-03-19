# VidFlow - Exibição e Filtragem de Vídeos

Este projeto é uma aplicação web que exibe vídeos e permite filtrá-los por pesquisa e categoria. Ele utiliza Axios para buscar dados de vídeos de uma API e manipula o DOM para exibir e filtrar os vídeos na página.

## Funcionalidades

* **Exibição de Vídeos:** Carrega e exibe vídeos de uma API, mostrando o título, descrição, imagem do canal e o vídeo em si.
* **Filtragem por Pesquisa:** Permite pesquisar vídeos pelo título, filtrando os resultados em tempo real.
* **Filtragem por Categoria:** Permite filtrar vídeos por categorias predefinidas.
* **Tratamento de Erros:** Exibe uma mensagem de erro caso ocorra algum problema ao carregar os vídeos.
* **Ambiente de Desenvolvimento e Produção:** Utiliza diferentes URLs para buscar vídeos dependendo do ambiente (desenvolvimento ou produção).
* **Layout Responsivo:** Adapta-se a diferentes tamanhos de tela, utilizando flexbox e media queries.
* **Tema Claro/Escuro:** Permite alternar entre temas claro e escuro.

## Tecnologias Utilizadas

* **JavaScript:** Linguagem principal para a lógica da aplicação.
* **Axios:** Biblioteca para fazer requisições HTTP.
* **DOM:** Manipulação do Document Object Model para exibir e interagir com os elementos da página.
* **HTML:** Estrutura da página web.
* **CSS:** Estilos da página, incluindo reset, estilos gerais e layout flexbox.
* **Vite (presumido):** Utilização de `import.meta.env.PROD` sugere o uso do Vite para o build do projeto.

## Estrutura do Projeto

* **`index.html`:** Arquivo HTML principal, contendo a estrutura da página.
* **`script.js`:** Arquivo JavaScript com a lógica da aplicação.
* **`css/reset.css`:** Arquivo CSS para resetar estilos padrão do navegador.
* **`css/estilos.css`:** Arquivo CSS com estilos gerais da página.
* **`css/flexbox.css`:** Arquivo CSS com estilos para layout flexbox e responsividade.
* **`img/`:** Diretório contendo imagens utilizadas no projeto.

## Como Funciona

1.  **Estrutura HTML:**
    * O arquivo `index.html` define a estrutura da página, incluindo cabeçalho, menu lateral, seção de categorias e contêiner de vídeos.
    * O cabeçalho contém a logo, barra de pesquisa e ícones de usuário.
    * O menu lateral oferece navegação para diferentes seções e inscrições.
    * A seção de categorias permite filtrar os videos por categoria.
    * O container de videos exibe os videos.
2.  **Estilos CSS:**
    * `reset.css` remove estilos padrão do navegador para garantir consistência.
    * `estilos.css` aplica estilos gerais, como fontes, cores e espaçamento.
    * `flexbox.css` utiliza flexbox para criar um layout responsivo, adaptando-se a diferentes tamanhos de tela com media queries.
3.  **Lógica JavaScript:**
    * A função `buscarEMostrarVideos()` busca os dados dos vídeos de uma API e os exibe na página.
    * A função `filtrarPesquisa()` filtra os vídeos com base na entrada da barra de pesquisa.
    * A função `filtrarPorCategoria()` filtra os videos com base na categoria selecionada.
    * O projeto utiliza variáveis de ambiente do vite, para diferenciar o ambiente de produção e desenvolvimento.
4.  **Responsividade:**
    * O layout é responsivo, adaptando-se a diferentes tamanhos de tela usando media queries no arquivo `flexbox.css`.
    * O menu lateral se comporta de forma diferente em telas menores e maiores.
    * A barra de pesquisa aparece em telas maiores.
5.  **Tema Claro/Escuro:**
    * O projeto possui um switch para alternar entre temas claro e escuro, estilizado com CSS.

## Como Usar

1.  **Clone o repositório:**
    ```bash
    git clone <URL_DO_REPOSITORIO>
    ```
2.  **Instale as dependências (se necessário):**
    ```bash
    npm install # ou yarn install
    ```
3.  **Inicie o servidor de desenvolvimento (se necessário):**
    ```bash
    npm run dev # ou yarn dev
    ```
4.  Abra o arquivo `index.html` no seu navegador.

## Estrutura de Dados (JSON)

O arquivo JSON de vídeos deve ter a seguinte estrutura:

```json
[
  {
    "url": "URL_DO_VIDEO",
    "titulo": "TITULO_DO_VIDEO",
    "imagem": "URL_DA_IMAGEM_DO_CANAL",
    "descricao": "DESCRICAO_DO_VIDEO",
    "categoria": "NOME_DA_CATEGORIA"
  },
  // ... outros vídeos
]
