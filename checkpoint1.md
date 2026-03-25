# Documentação - Passagem de Parâmetros
## Parâmetro Obrigatório (Tela de Perfil)
Foi implementada uma navegação para a tela de Perfil utilizando parâmetros obrigatórios (nome)(idade). 
Esse parâmetro deve ser obrigatoriamente informado. Esse parâmetro é definido na rota como {nome}

- Esses parâmetros são definidos na rota dentro da MainActivity:
perfil/{nome}/{idade}
Na configuração dos argumentos:
navArgument("nome"){ type = NavType.StringType }
navArgument("idade"){ type = NavType.IntType }

- No MenuScreen, os valores são enviados:
navController.navigate("perfil/Leticia/21")

- E para afirma que os valores não sejam nulos, foi utilizado:
  nome!!
  idade!!

## Parâmetro Opcional (Tela de Pedidos)
Na tela de Pedidos, foi implementado um parâmetro opcional chamado cliente. (pedidos?cliente={cliente}) 
Esse tipo de parâmetro permite que a navegação funcione mesmo quando nenhum valor é enviado.
O parâmetro é definido com um valor padrão, se nenhum valor é enviado, a aplicação utiliza o valor padrão,
caso um valor seja enviado, ele substitui o padrão

- Na MainActivity confirma que se nenhum valor for enviado, assume que name = "Cliente Genérico"
  navArgument("cliente") {
  defaultValue = "Cliente Genérico"
  }

- Para recuperar os argumentos, é usado na MainActivity:
  it.arguments?.getString("cliente")

- E passado para PedidosScreen:
- "PEDIDOS - $cliente"

## Multiplos Parâmetros
Foi implementada a passagem de múltiplos parâmetros entre telas: nome e idade.
Os parâmetros são definidos na rota em sequência, onde ordem dos parâmetros deve ser respeitada
Cada valor é recuperado individualmente na tela de destino, que nesse caso é PerfilScreen

- No menu é passado os parâmetros:
  navController.navigate("perfil/Leticia/21")

- E recuperados com os valores enviados na MainActivity:
  getString("nome")
  getInt("idade")

- Na MainActivity para recuperação de dados onde caso não informado o usuário e idade, é assumido um
  valor genérico:
  val nome: String? = it.arguments?.getString("nome", "Usuário Genérico")
  val idade: Int? = it.arguments?.getInt("idade", 0)

- Para que o argumento opcional não seja null, é usado:
defaultValue = "Cliente Genérico"
