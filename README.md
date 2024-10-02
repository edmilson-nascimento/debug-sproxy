# External Debug / SPROXY Config

![N|Solid](img/sap-abap.jpeg)

![Static Badge](https://img.shields.io/badge/development-abap-blue)
![GitHub commit activity (branch)](https://img.shields.io/github/commit-activity/t/edmilson-nascimento/debug)
![Static Badge](https://img.shields.io/badge/murilo_borges-abap-lime)


~~eu sempre me esqueço das configurações para debug externo e também update task, enfim, vou salvar o que Murilo me mostrou para deixar de perguntar 2x vezes por mês a mesma coisa...~~

Existem configurações diferentes para itens diferentes. Um deles para `debug externo` e outro para `update task`. De bonus, também vou colocar as config da transação de `SPROXY` ~~que também eu sempre esqueço e fico perguntado para o Murilo~~. 

> Importante ter o arquivo de debug de janelas popup.

Para realizar o debug de um popup, é possível arrastar o arquivo para a janela e isso ja vai iniciar o debug como se tivesse usado o `/H`. É possível encontrar o arquivo [aqui](/files/debug.sap).

## Debug externo

Com o código fonte aberto (pela transação `SE38` por exemplo), acessar o menu **Utilitários > Configurações**.

![N|Solid](img/u-c.png)

A tela de configurações abaixo será exibida. Para o objetivo, é preciso acessar **Editor ABAP > Depuração**. Marcar a opção **Usuário** e informar no campo o usuário que chamará o que SAP externamente, neste caso, `S-PIDI1`, uu seja, o user que está configurado no outro sistema.

Após preencher essas informações, basta confirmar no botão **✓** (ok).  


![N|Solid](img/user-debug.png)

Depois de confirmar, basta colocar o `BREAK` externo (que é o que tem o bonequinho ☺).

![N|Solid](img/break-externo.png)

Obs.: Mas, para isso funcionar, depende da permissão desse usuário externo. Se ele for de `B - Sistema` acho que não faz o debug. Mas quando for colocar o `break`, o SAP te avisa informa com uma mensagem se há ou não permissão. Então tem que pedir pra mudar o *TP.Usuário* do usuário pra fazer a depuração.

![N|Solid](img/type-user.png)

É necessário uma sessão livre pois irá abrir em uma nova janela.

## Update task

A sintaxe abaixo é familiar em alguns cenários e existe uma maneira diferente de executar o debug dessa opção.

![N|Solid](img/update-task-0.png)

Com a necessidade de realizar o debug de funções que tem sintaxe `in update task`, algumas configurações devem ser atualizadas.

Inicie um debug de qualquer programa e deve ir ate o o menu **Configurações > Modificar configurações/Perfil depurador (shift+1)**.

![N|Solid](img/update-task-1.png)

Na proxima tela, deve ser marcada a opção **Depuração atualiz.**, conforme indicado na imagem abaixo.

![N|Solid](img/update-task-2.png)

Então, a configuração correta passa a ficar da maneira que está abaixo.

![N|Solid](img/update-task-2.1.png)

Durante o processamento do código, onde existe a chamada de função com o termo `update task`,  ao passar pela instrução, o cursor de debug não entra no processamento da função, somente passa (não sei se já percebeu isso).

Se ativar esse parâmetro (Depuração atualiz.), irá continuar passando e só quando der F8 (continue) e houver um `commit work`, passa um pouquinho e abre outra tela de DEBUG já nas funções de `UPDATE TASK`.

### Importante
> Tem alguma cena que coloca como premissa ter uma tela de debug aberta antes disso. "TO DO


## SPROXY config
Não menos importante, mas ~~como eu sempre esqueço e tenho que perguntar pro Murilo e nem sempre ele esta de bom humor~~ eu acho importante salvar essas opções para futuramente ter onde procurar essa info.

Acessar a transação `SPROXY` e ir ate o menu **Utilities > Settings**.
![N|Solid](img/sproxy-menu.png)

Nas opções abaixo, desmarcar todos os ~~piscos~~ flags e escolher as seguintes opções:
- Preferred Order in Proxy Tree: `WSDL order`
- Enterprise Service Browser: `R - ESR Browser`

Após preencher essa informações, basta confirmar no botão **✓ (ok)**.  

![N|Solid](img/sproxy-config.png)

Ainda faltam algumas coisas, mas o doc sera atualizado ~~quando eu descobrir o que pode ser~~ em breve.