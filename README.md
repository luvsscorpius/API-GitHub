# Exibição de Repositório do GitHub

Este projeto envolve a busca de informações de repositórios do GitHub usando a API do GitHub e a exibição dessas informações em uma página da web. O código JavaScript fornecido utiliza a função `Fetch` para obter os dados dos repositórios de um usuário específico do GitHub e, em seguida cria elementos HTML dinamicamente para apresentar os detalhes dos repositórios na página.

## Como funciona 

1. O script começa selecionando um elemento HTML com o nome de classe `content-main` usando o método `document.querySelector`. Esse elemento é onde as informações dos repositórios obtidos serão exibidas.
2. A função `getApiGitHub` é definida. Dentro dessa função:
    - Uma solicitação `fetch` é feita para a API do GitHub usando a URL `'https://api.github.com/users/luvsscorpius/repos'`. Essa URL busca os dados dos repositórios do usuário do GitHub com o nome de usuário `luvsscorpius`.
    - A resposta da API é processada usando o método `.then`. Se a respota não for bem-sucedida (código de status diferente de 200 OK), um erro é gerado. 
    - Os dados da resposta são convertidos para o formato JSON usando `await res.json()`.
    - O método `data.map` é usado para percorrer cada item de repositório nos dados obtidos.
    - Para cada item de repositório:
        - Um novo elemento `div` com a classe `project` é criado.
        - Dentro dessa `div`, os detalhes do repositório são adicionados, incluindo o nome do repositório, data de criação (formatada usando `Intl.DateTimeFormat`), URL do repositório e linguagem de programação. 
        - O novo elemento `div` é anexado ao elemento `content-main`, adicionando assim os detalhes do repositório à página.
3. Por fim, a função `getApiGitHub` é invocada, iniciando o processo de busca dos dados dos repositórios do GitHub e preenchando o conteúdo HTML com as informações obtidas.

## Uso

Para utilizar este projeto, siga estes passos:

1. Adicione o código JavaScript fornecido ao seu documento HTML, idealmente dentro de uma tag `<script>`.
2. Certifique-se de ter um elemento HTML com o nome da classe `content-main` onde deseja exibir as informações dos repositórios.
3. Quando a página carregar, o script automaticamente buscará os dados dos repositórios e preencherá o elemento `content-main` com os detalhes dos repositórios.

Lembre-se de garantir um tratamento adequado de erros e considere o uso de async/await para melhorar a legibilidade do código, se desejar.