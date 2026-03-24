# Documentação - Passagem de Parâmetros
## Parâmetro Obrigatório (Tela de Perfil)
Foi implementada uma navegação para a tela de Perfil utilizando um parâmetro obrigatório (nome). 
Esse parâmetro deve ser obrigatoriamente informado. Esse parâmetro é definido na rota como {nome}

## Parâmetro Opcional (Tela de Pedidos)
Na tela de Pedidos, foi implementado um parâmetro opcional chamado cliente. 
Esse tipo de parâmetro permite que a navegação funcione mesmo quando nenhum valor é enviado.
O parâmetro é definido com um valor padrão, se nenhum valor é enviado, a aplicação utiliza o valor padrão,
caso um valor seja enviado, ele substitui o padrão

## Multiplos Parâmetros
Foi implementada a passagem de múltiplos parâmetros entre telas: nome e idade.
Os parâmetros são definidos na rota em sequência, onde ordem dos parâmetros deve ser respeitada
Cada valor é recuperado individualmente na tela de destino, que nesse caso é PerfilScreen
