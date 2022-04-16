# GraphQL

Funciona através do protocolo HTTP, cuja responsabilidade é requisitar exatamente os dados que precisa no frontend.

Caso não esteja utilizando o GraphQL, toda responsabilidade de retornar os dados para o frontend fica a cargo do backend.

## Quais problemas resolve?

- Overfetching: Buscar informações demais, realizar o fetch a mais do que eu preciso do meu backend. Na prática pode ter uma aplicação web e mobile que consomem a mesma API, pode ser que em uma das aplicações, eu não tenha necessidade de buscar dados aninhados, relacionados, ou seja, processamento desnecessário.
  - http://localhost:3000/users
    - DB (usuarios, endereços)
- Underfetching: É quando estamos querendo buscar informações que eu preciso, porém a rota não retorna todas elas. Aí entramos num dilema. Será que fazemos a rota retornar o endereço também?
  - http://localhost:3000/users
    - DB (usuarios)
  - - http://localhost:3000/addresses
    - DB (endereços)

## Desvantagens

- Traz mais complexidade

## Dificuldades

- Cache:
  - Google Chrome já faz um Cache-control: 5 segundos automáticamente. O GraphQL só utiliza uma rota, e ai? 🤔
- Erros:
  - REST: Retornamos códigos HTTP 404, 401, 500
  - GraphQL: Todas as chamadas HTTP sempre retorna 200, ou seja, a tratativa de erro tem que ser feita além do que o browser entende por ser erro ou sucesso.

Quando vamos criar uma estrutura GraphQL podemos usar Schema First ou Code First. Neste projeto estamos utilizando Code First.

- Query: buscar dados
- Mutation: criar, alterar ou deletar
