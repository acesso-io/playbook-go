# Guia de padrões e boas práticas em Go

Este guia foi inspirado por: [playbook-go](https://github.com/betrybe/playbook-go).

Este documento define os padrões e boas práticas que adotamos ao escrever código Go na unico. Este guia está separado por temas, e priorizado pela necessidade e impacto na qualidade do nosso código.

> **Observação:** Este é um documento vivo e reflete as necessidades da unico, que podem mudar com o tempo, assim como as decisões que tomamos para melhor resolver nossos problemas.

## Como esse guia está organizado

- [Qualidade de Codigo](#qualidade-de-codigo)
- [Arquitetura](#arquitetura)
- [Variáveis de configuração](#variáveis-de-configuração)
- [Estrutura do repositório](#estrutura-do-repositório)
- [Pacotes externos](#pacotes-externos)

## Qualidade de código

### Code Review

A base para um bom code review pode ser encontarda no [Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments), que é uma lista do que deve ser levado em conta quando estamos revisando codigos Go.

### Linter

Estamos adotando o [golangci-lint](https://golangci-lint.run/) no Github Actions para garantir que nossos códigos sejam revisados e corretamente formatados.

### Nome de pacotes

Devemos seguir as recomendações do [Go Blog](https://go.dev/blog/package-names).

## Arquitetura

### Clean Architecture

Recomendamos o uso de Clean Architecture e incentivamos o uso do [go-cleanarch](https://github.com/roblaszczak/go-cleanarch) com Github Actions.

## Variáveis de configuração

De acordo com as [recomendações](https://12factor.net/config) documentadas no projeto [12 factor](https://12factor.net) armazenamos as configurações que mudam de acordo com o ambiente (`staging`, `dev`, `production`) em variáveis de ambiente.

## Estrutura do repositório

Usamos o conceito tanto de monorepo quanto de multirepos, dependendo do squad/tribe, nos baseamos em grandes projetos open source como [kubernetes](https://github.com/kubernetes/kubernetes) e o repositorio [golang-standards](https://github.com/golang-standards/project-layout) que nos ajuda a organizar nossos projetos.

## Pacotes externos

### Router HTTP

A ser definido, mas deixo o exemplo abaixo:

Usamos o [Chi](https://github.com/go-chi/chi). Fatores usados na escolha:

- features (middlewares, inline middlewares, route groups and sub-router mounting; Context control);
- atividade do projeto (estrelas e atividade de atualizações do projeto no Github);
- usado por cases grandes, de acordo com o [site](https://github.com/go-chi/chi/issues/91) e pesquisas que realizamos;
- [performance](https://github.com/go-chi/chi#benchmarks)
- não possui dependências externas, *"plain ol' Go stdlib + net/http"*.

### Testes

Usamos o [testify](https://github.com/stretchr/testify) para deixar os códigos dos testes mais legíveis. E incentivamois o uso de [Table Driven Tests](https://github.com/golang/go/wiki/TableDrivenTests).


### Mocks

A ser definido.

### ORM X SQL

A ser definido.

### Injeção de dependência

A ser definido, mas deixo o exemplo abaixo:

Usamos o [Uber FX](https://github.com/uber-go/fx) como framework de injeção de dependência. Fatores usados na escolha:

- Legibilidade do código;
- Lida muito bem como monorepos;
- Mantido pela Uber.

