# External Debug


[![N|Solid](https://wiki.scn.sap.com/wiki/download/attachments/1710/ABAP%20Development.png?version=1&modificationDate=1446673897000&api=v2)](https://www.sap.com/brazil/developer.html)

Existem configurações diferentes para itens diferentes. Um deles para `debug externo` e outro para `update task`


## External

Agora não tem mistério... 

vc vai no código onde quer colocar o break.. 





Coloca o usuário que chamará o ]SAP externamente

Ou seja.. 

o usuário que está configurado no outro sistema... 

confirma.. 

e ai sim coloca o BREAK externo



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