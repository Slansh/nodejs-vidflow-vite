# VidFlow - Exibição e Filtragem de Vídeos

Este projeto é uma aplicação web que exibe vídeos e permite filtrá-los por pesquisa e categoria. Ele utiliza Axios para buscar dados de vídeos de uma API e manipula o DOM para exibir e filtrar os vídeos na página.

## Funcionalidades

* **Exibição de Vídeos:** Carrega e exibe vídeos de uma API, mostrando o título, descrição, imagem do canal e o vídeo em si.
* **Filtragem por Pesquisa:** Permite pesquisar vídeos pelo título, filtrando os resultados em tempo real.
* **Filtragem por Categoria:** Permite filtrar vídeos por categorias predefinidas.
* **Tratamento de Erros:** Exibe uma mensagem de erro caso ocorra algum problema ao carregar os vídeos.
* **Ambiente de Desenvolvimento e Produção:** Utiliza diferentes URLs para buscar vídeos dependendo do ambiente (desenvolvimento ou produção).

## Tecnologias Utilizadas

* **JavaScript:** Linguagem principal para a lógica da aplicação.
* **Axios:** Biblioteca para fazer requisições HTTP.
* **DOM:** Manipulação do Document Object Model para exibir e interagir com os elementos da página.
* **HTML/CSS:** Para a estrutura e estilo da página (presumido, pois o código JS interage com elementos HTML).
* **Vite (presumido):** Utilização de `import.meta.env.PROD` sugere o uso do Vite para o build do projeto.

## Como Funciona

1.  **Busca de Vídeos:**
    * A função `buscarEMostrarVideos()` é chamada ao carregar a página.
    * Ela utiliza Axios para fazer uma requisição GET para a URL dos vídeos.
    * A URL varia dependendo do ambiente:
        * Em produção, busca de um arquivo JSON hospedado no GitHub Gist.
        * Em desenvolvimento, busca de um servidor local (localhost:3000/videos).
    * Os dados dos vídeos são recebidos e processados.
    * Caso algum video não possua categoria, um erro é lançado.
2.  **Exibição dos Vídeos:**
    * Para cada vídeo, um elemento `<li>` é criado e adicionado ao contêiner de vídeos (`.videos__container`).
    * O elemento `<li>` contém um `<iframe>` para o vídeo, uma imagem do canal, o título do vídeo, a descrição e a categoria (oculta).
3.  **Filtragem por Pesquisa:**
    * Um evento `input` é adicionado à barra de pesquisa (`.pesquisar__input`).
    * A função `filtrarPesquisa()` é chamada a cada alteração na barra de pesquisa.
    * Ela obtém o valor da barra de pesquisa e filtra os vídeos exibidos, mostrando apenas aqueles cujo título contém o valor da pesquisa.
4.  **Filtragem por Categoria:**
    * Um evento `click` é adicionado a cada botão de categoria (`.superior__item`).
    * A função `filtrarPorCategoria()` é chamada ao clicar em um botão.
    * Ela obtém a categoria do botão e filtra os vídeos exibidos, mostrando apenas aqueles que pertencem à categoria selecionada.
    * A categoria "tudo" mostra todos os videos.
5.  **Tratamento de Erros:**
    * A função `buscarEMostrarVideos()` utiliza um bloco `try...catch` para tratar erros durante a busca de vídeos.
    * Se ocorrer um erro, uma mensagem de erro é exibida no contêiner de vídeos.

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
