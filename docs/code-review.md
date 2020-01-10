# Introdução
Esse documento contém princípios de qualidade de desenvolvimento de software baseados na visão da empresa SoftWillians IT Solutions, tais princípios são avaliados nas rotinas de code-review.

# Sumário
<!-- TOC depthFrom:1 depthTo:2 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Princípios do Code-Review](#princípios-do-code-review)
- [Linguagens e Frameworks](#linguagens-e-frameworks)
- [Princípios de Arquitetura](#princípios-de-arquitetura)
- [Estrutura da Solução](#estrutura-das-soluções)
- [Utilização](#utilização)
- [Endpoints](#endpoints)
- [Observações de Código](#observações-de-código)
- [Implementações](#implementações)
- [Criação](#criação)
- [Licença](#licença)

<!-- /TOC -->

## Princípios do Code-Review
1. Code-Review é uma atividade de garantia de qualidade do desenvolvimento de software, onde o dev (committer) tem seu código avaliado por outro dev (reviewer).
2. Um code-review pode ter mais de 1 reviewer, dependendo do projeto e da disponibilidade do reviewer principal;
3. O código deve ser auto-explicativo para que esteja claro o que está sendo colocado no commit, tanto do ponto de vista técnico quanto de negócio.
4. A escrita do commit deve condizer com o que foi alterado no código baseado no tópico anterior.
5. É papel do reviewer questionar sobre o código, sugerir melhorias baseadas na visão da empresa e exigir detalhes sobre a regra de negócio.
6. É papel do committer saber explicar o código desenvolvido bem como a regra de negócio; 
7. É papel do committer escutar as sugestões do reviewer e aplicá-las SEMPRE que possível.
8. 

## Linguagens e Frameworks
O uso das seguintes linguagens e frameworks é mandatório para novos projetos.
1. Back-End
   * NET Core;
2. Bancos de Dados
   * .SQL Server.
3. Front-End
   * Angular 2+;
   * HTML5, SCSS, TypeScript e JavaScript.
4. Mobile
   * Ionic 4.
   
## Princípios de Arquitetura
A SoftWillians utiliza sua própria arquitetura, baseada em alguns tópicos dos seguintes conceitos:
* Domain-Driven Design (DDD);
* SOLID;
* Clean Code;
* Gang of Four.
* DRY, KISS, YAGNI

## Estrutura das soluções
* NomeDaSolucao.Api
* NomeDaSolucao.Application
* NomeDaSolucao.Domain
* NomeDaSolucao.Domain.Core
* NomeDaSolucao.Infra.Data
* NomeDaSolucao.Infra.CrossCutting

## Endpoints
* kebab-case;
