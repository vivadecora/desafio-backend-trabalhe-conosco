# Teste para candidatos à vaga de backend

> [![Logo Viva Decora](https://raw.githubusercontent.com/vivadecora/teste-backend/main/vivadecora-logo.svg)](https://www.vivadecora.com.br)
>
> Esse teste é público. Candidatos para vagas na Viva Decora devem responder este teste como parte do processo seletivo. A solução do teste deve estar disponível em um repositório online (Github, Bitbucket, etc) e o link deve ser encaminhado por **mensagem ou email**. Pode ser um repositório público ou privado com acesso para o avaliador. **Será desclassificado quem entregar a solução fazendo fork deste projeto ou criando uma issue no mesmo**.

## Objetivo do desafio
Implementar um programa que utilize *web scraping* para buscar informações de projetos públicos do Github e compile os dados obtidos em arquivos *.txt*. Esses arquivos devem incluir informações como quantidade de linhas (total e percentual) de cada extensão de arquivo e a estrutura de pastas do projeto.

### Entrada
O programa deve ler uma lista de repositórios de um arquivo `repositories.txt` onde cada linha contém o caminho relativo do projeto: `<dono-do-projeto>/<nome-do-projeto>`

Exemplo:
```txt
frontpressorg/frontpress
SambitAcharya/Mini-Projects
```

Essa lista contém um **número qualquer** de caminhos para projetos no Github. Por exemplo, a entrada `frontpressorg/frontpress` corresponde ao projeto [Frontpress](https://github.com/frontpressorg/frontpress).

### Saída
A saída do programa deve ser um arquivo *.txt* para cada um dos repositórios analisados. Esses arquivos devem ter um nome que indique o repositório ao qual eles correspondem. 

Cada um desses arquivos deve conter as seguintes informações:
- Caminho relativo do projeto. Exemplo: `frontpressorg/frontpress`
- Quantidade total de linhas.
- Quantidade total de Bytes.
- Para cada extensão de arquivo, informar qual a quantidade de linhas e Bytes (total e percentual). Arquivos sem extensão definida (como `.gitignore`, `Dockerfile`, `Makefile`, ...) podem ser agrupados como `<outros>`, a critério do candidato. Exemplo:
```
Extensão   |     Linhas    |    Bytes
js         |  17599 (96 %) | 31894 (79 %)
md         |    202 ( 1 %) |     5 ( 0 %)
html       |    130 ( 0 %) |  5703 (14 %)
json       |     95 ( 0 %) |   465 ( 1 %)
sh         |     75 ( 0 %) |   101 ( 0 %)
<outros>   |     74 ( 0 %) |  1322 ( 3 %)
sample     |     34 ( 0 %) |   787 ( 1 %)
enc        |      0 ( 0 %) |     3 ( 0 %)
``` 

- Estrutura de pastas do arquivo. Exemplo:
```
[Project frontpressorg/frontpress]
|__ [ci]
|   |__ compile.sh (5 linhas)
|   |__ travis_deploy.sh (70 linhas)
|__ [release]
|   |__ frontpress.js (7341 linhas)
|   |__ frontpress.min.js (3 linhas)
|   |__ frontpress.v1.js (7343 linhas)
|   |__ frontpress.v1.min.js (3 linhas)
|__ [src]
|   |__ [js]
|   |   |__ [apis]
|   |   |   |__ [configs-to-params]
|   |   |   |   |__ [models]
|   |   |   |   |   |__ configs-to-params.model.js (25 linhas)
|   |   |   |   |__ configs-to-params.module.js (4 linhas)
|   |   |   |__ [v1]
|   |   |   |   |__ [api-manager-map]
|   |   |   |   |   |__ [constants]
|   |   |   |   |   |   |__ api-manager-map.constant.js (13 linhas)
|   |   |   |   |   |__ api-manager-map.module.js (4 linhas)
...
... (apresentar a estrutura de arquivos completa na solução do teste)
...
```

As informações podem ser apresentadas da forma como o candidato achar mais conveniente, desde que atenda os requisitos solicitados. Os exemplos têm como objetivo apenas deixar mais claro quais são as informações solicitadas. 

### Requisitos

Os seguintes requisitos são obrigatórios:
- A aplicação deve ser implementada em Python e a descrição do projeto deve explicar todos os passos necessários para executá-lo.
- Caso haja testes unitários, também descrever como executá-los. 
- Todas as informações devem ser obtidas do Github através de *web scraping*. **Não utilize nenhuma API nem clone ou faça download do repositório**. 
- Processo de desenvolvimento versionado via Git em um repositório público ou em um repositório privado com acesso para o avaliador.

Os seguintes requisitos são opcionais:
- Relatório de cobertura dos testes unitários (com descrição sobre como gerá-lo).
- Badge que indique o status da build (como o do [Tracis CI](https://docs.travis-ci.com/user/status-images/) ou [Codacy](https://support.codacy.com/hc/en-us/articles/212799365-Badges)).


## Critérios de avaliação
- Apresentação das informações solicitadas de forma clara e objetiva.
- Organização do código.
- Performance.
- Flexibilidade do sistema para adição/remoção de funcionalidades.


### Como vamos avaliar
- Vamos executar a solução utilizando um arquivo `repositories.txt` com alguns repositórios selecionados pelo nosso time e analisar se a saída gerada atende aos requisitos solicitados.
- Mediremos o tempo médio de execução da solução proposta. Também tentaremos entender os gargalos da solução implementada e se qualquer otimização de performance comprometeu outros aspectos do código (como legibilidade ou desacoplamento).
- Analisaremos os testes unitários e o relatório de cobertura da aplicação, caso estejam disponíveis.
- Vamos analisar se o código segue as boas práticas de desenvolvimento, principalmente as boas práticas de desenvolvimento de código Python.

### O que nós gostamos
- Desacoplamento entre componentes do sistema.
- Hierarquia clara entre componentes.
- Tanto legibilidade quanto performance importam, muitas vezes um não precisa comprometer o outro.
- Testes unitário e ferramentas de integração que contribuam para a confiabilidade do projeto.
- Diante de dúvidas sobre qual caminho seguir, buscamos inspiração no Zen do Python.

### Dúvidas e sugestões
Caso haja alguma dúvida ou sugestão sobre o teste, pode criar uma issue neste projeto.
