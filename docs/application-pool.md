# Introdução
Tutorial exemplificado de criação de Application Pool em Servidores Windows.

# Sumário
<!-- TOC depthFrom:1 depthTo:2 withLinks:1 updateOnSave:1 orderedList:0 -->

- [1. Acesso ao Windows Server](#1-acesso-ao-windows-server)
- [2. Criação de Pastas](#2-criação-de-pastas)
     - [2.1. Pasta Front-end](#21-pasta-front-end)
     - [2.2. Pasta Back-end](#22-pasta-back-end)
- [3. Criação de Application Pools](#3-criação-de-application-pools)
     - [3.1 Títulos](#31-títulos)
       - [3.1.1 Pool Front-End](#311-pool-front-end)
       - [3.1.2 Pool Back-End](#312-pool-back-end)
         - [3.1.2.1 .NET CLR Version](#3121-net-clr-version)
- [4. Transferência de Arquivos](#4-transferência-de-arquivos)
- [5. Criação de Sites](#5-criação-de-sites)
     - [5.1 Conversão de Pastas para Application](#51-conversão-de-pastas-para-application)

<!-- /TOC -->
# 1. Acesso ao Windows Server
- Na barra de pesquisa do Windows, digitar: MSTSC;
- Aparecerá a janela de "Conexão de Área de Trabalho Remota";
- Inserir o endereço do servidor;
- Inserir usuário e senha;
- Aguarde a entrada no servidor.

_____________________________
# 2. Criação de Pastas
- Vá até o caminho "[Disco Local Padrão de Aplicações]\inetpub\wwwroot";
- Verifique no servidor qual é o disco local usado para as aplicações (normalmente o C: ou D:);
- Crie 2 pastas, uma representando o front-end e outra o back-end.

## 2.1. Pasta Front-end
- Deve ter o título "nome-da-aplicacao" (em kebab-case, sem aspas);
- Será uma rota visível ao usuário, é importante estar em kebab-case.

## 2.2. Pasta Back-end
- Deve ter o título "NomeAplicacao.WebAPI" (mescla de PascalCase com sufixo .WebAPI);
- Será uma rota não visível ao usuário, somente às requisições HTTP do front-end. 

_____________________________
## 3. Criação de Application Pools
Uma Application Pool é um container de aplicação e permite ao administrador **isolar** cada aplicação ou um conjunto de aplicações. Em uma manutenção ou uma parametrização de sistemas, uma configuração específica em um número X de sistemas, deverá ser criada uma Application Pool que será o container para essas aplicações específicas com as configurações específicas. Além disso, permite controlar a aplicação, parar, pausar por um tempo determinado, uma manutenção ou release.

- Pesquise na barra de pesquisa do Windows Server por "IIS Manager" e clique na opção;
- Ao abrir, expanda o SERVIDOR e então clique em Application Pools;
- Em qualquer local da tela da direita com os Application Pools clique com o botão direito do mouse e então em "Add Aplication Pool".
### 3.1 Títulos
Por padrão, coloque sempre o prefixo "APP_", com o padrão PascalCase.

#### 3.1.1 Pool Front-End
- Título: "APP_[NomeDaSuaAplicacaoEmPascalCase]" (sem colchetes).

#### 3.1.2 Pool Back-End
- Título: "APP_[NomeDaSuaAplicacaoEmPascalCase].WebAPI" (sem colchetes e com sufixo .WebAPI).
#### 3.1.2.1 .NET CLR Version
- No caso de **.NET Core** escolha "No Managed Code";
- No caso de **.NET Framework** escolha ".NET CLR Version 4.X".

_____________________________
## 4. Transferência de Arquivos
- Transfira os arquivos para as pastas criadas no tópico [2. Criação de Pastas](#1-criação-de-pastas).

_____________________________
## 5. Criação de Sites
Um Site representa a **união** entre uma **Application** a uma **Application Pool**.
Uma Application Pool pode ter N Sites.

### 5.1 Conversão de Pastas para Application
- Para acessar os Sites, vá até o IIS Manager novamente;
- Na lateral esquerda, expanda "Sites";
- Expanda então "Default Web Site";
- Você verá as pastas criadas no tópico [2. Criação de Pastas](#1-criação-de-pastas);
- Com o botão direito do mouse, clique sobre cada uma delas e então em "Convert to Application";
- Para realizar a conversão de pasta para Application é necessário associar uma Application Pool;
- Por padrão a Application virá com a Pool "DefaultAppPool";
- Troque para a Application Pool correspondente (back-end ou front-end), para isso, clique em "Select" e escolha a Application Pool correspondente e então em "OK";
- Faça o mesmo processo para front-end e back-end.

________________________
Criado por:
Gabriel Vicente
