# External Debug / SPROXY Config

![N|Solid](https://wiki.scn.sap.com/wiki/download/attachments/1710/ABAP%20Development.png)
~~eu sempre me esqueço das configurações para debug externo e tambem update task, enfim, vou salvar o que Murilo me mostrou para deixar de perguntar 2x vezes por mês a mesma coisa.~~

Existem configurações diferentes para itens diferentes. Um deles para `debug externo` e outro para `update task`. De bonus, tambem vou colocar as config da transação de `SPROXY` ~~que tambem eu sempre esqueço e fico perguntado para o Murilo~~.


## Debug External

Com o código fonte aberto (pela transação `SE38` por exemplo), acessar o menu **Utilitarios > Configurações**.

![N|Solid](img/u-c.png)

A tela de configurações abaixo será exibida. Para a o objetivo, é preciso acessar **Editor ABAP > Depuração**. Marcar a opção **Usuário** e informar no campo o usuário que chamará o que SAP externamente, neste caso, `S-PIDI1`, uu seja, o usuário que está configurado no outro sistema.

Após preencher essa informações, basta confirmar no botão **✓ (ok)**.  


![N|Solid](img/user-debug.png)

Depois de confirmar, basta colocar o `BREAK externo`.

![N|Solid](img/u-c.png)


que é o que tem o bonequinho.. 

Massssssss

para isso funcionar 

depende da permissão desse usuário externo.. 

se ele for de SISTEMA... 

acho que não debuga.. 

Mas quando for colocar o break ele te avisa.. 

daí tem que pedir pra mudar o TIPO do usuário pra fazer a depuração.. 

## Update Task

só marcar ese FLAG que já está ativo kkk 

depurar atualização 

Mas isso só funciona para funções em UPDATE TASK

um caso bom pra testar isso é fazer um pedido de compra.. 

vc faz ele debugando normal.. 

e epoius que dá F8.. passa um pouquinho e abre outra tela de DEBUG já nas funções de UPDATE TASK

]kkkk