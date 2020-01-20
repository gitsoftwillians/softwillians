# Criação de Application Pool no Windows Server.

- Na barra de pesquisa do Windows, digitar: MSTSC;
- Aparecerá a janela de "Conexão de Área de Trabalho Remota";
- Inserir o servidor;
- Inserir usuário e senha;
- Aguarde a entrada no servidor..

## Criação de Pastas
- Vá até o caminho "[Disco Local Padrão de Aplicações]\inetpub\wwwroot";
- Verifique no servidor qual é o disco local usado para as aplicações (normalmente o C: ou D:);
- Crie 2 pastas, uma representando o front-end e outra o back-end:

### Pasta Front-end
- Deve ter o título "nome-da-aplicacao" (em kebab-case, sem aspas).
- Será uma rota visível ao usuário, é importante estar em kebab-case.

### Pasta Back-end
- Deve ter o título "NomeAplicacao.WebAPI" (mescla de PascalCase com sufixo .WebAPI)
- Será uma rota não visível ao usuário, somente às requisições HTTP do front-end. 

## Criação de Application Pools
- Pesquise na barra de pesquisa do Windows Server por "IIS Manager" e clique na opção;
- Ao abrir, expanda o SERVIDOR e então clique em Application Pools.
- Em qualquer local da tela da direita com os Application Pools clique com o botão direito do mouse e então em "Add Aplication Pool";
### Títulos
Por padrão, coloque sempre o prefixo "APP_", com o padrão PascalCase.

#### Pool Front-End
- Título: "APP_[NomeDaSuaAplicacaoEmPascalCase]" (sem colchetes).
#### Pool Front-End
- Título: "APP_[NomeDaSuaAplicacaoEmPascalCase].WebAPI" (sem colchetes e com sufixo .WebAPI).

