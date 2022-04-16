Crie um sistema de ponto para registrar as horas dos colaboradores. Todas as telas e recursos só podem ser acessados por usuários autenticados

## Requisitos

* Login e senha
  * O login será pelo CPF e a senha deverá ser segura (números, letras maiusculas e minusculas com no mínimo 12 caracteres);
  * A senha e o CPF deverão ser salvos criptografados dentro do banco de dados, não utilizar MD5 para comparar os valores;
* Cadastro de funcionários
  * CPF (não precisa validar o CPF, só a quantidade de digitos do CPF)
  * Nome completo
  * Setor de trabalho
  * Endereço (Logradouro, CEP, cidade e estado)
  * Telefone para contato
  * Nome da mãe
  * Número do PIS
  * Cargo dentro da empresa
  * Salário base
  * Horário de trabalho (exemplo, das 08:00 as 19:00)
* Emissão da folha de ponto
  * Folha de ponto mensal
* Fila de aprovação de marcação de ponto 
* Registro de ponto

## Sistema de gerenciamento de usuários

Existem 3 tipos de usuários: **Administradores**, **Gestores** e **Colaboradores**:

* Administradores: Podem fazer qualquer operação no sistema;
* Gestores: Podem aprovar marcações de ponto, alterar o salário base e desativar o acesso de um funcionário, mas não podem emitir folhas de ponto a não ser as próprias folhas;
* Colaboradores: Podem alterar somente o telefone para contato, e registrar o ponto pelo sistema, além de emitir suas respectivas folhas de ponto;
* Um gestor pode desativar somente colaboradores, gestores não podem desativar outros gestores.
* Administradores podem desativar quaisquer tipo de usuários.
* Usuários não podem ser excluídos da base, seus acessos devem ser desativados, mas seus registros nunca excluídos.

## Sistema de registro de ponto

* Todos os usuários podem registrar ponto a qualquer momento, sendo permitido somente 4 marcações por dia;
  * Administradores não podem registrar mais de 4 marcações por dia; 
* Não é permitido registrar pontos aos sábados e domingos;
  * Administradores não podem registrar marcações aos sábados e domingos; 
* Usuários do tipo colaboradores que registrarem ponto fora do horário de trabalho devem ter seu ponto aprovado ou recusado por um gestor;
  * Qualquer gestor pode aprovar ou recusar uma marcação de qualquer funcionário; 
* Gestores podem marcar ponto fora do horário de trabalho sem aprovação;
* Administradores podem aprovar/recursar marcação de pontos dos colaboradores;
* Na tela de registro de ponto, o usuário deverá informar os 5 últimos dígitos do CPF e clicar um botão "Registrar ponto";
* Antes de registrar o ponto, uma tela deverá aparecer com o nome completo do funcionário, setor de trabalho e o botão "confirmar ponto". Confirmando o ponto, o mesmo deverá ser registrado no banco de dados;

Sistema de folha de ponto:

* Cada usuário pode emitir somente a sua própria folha de ponto;
* Usuários administradores podem emitir qualquer folha de ponto;
* A folha de ponto deve conter os dias, e as horas das 4 marcações realizadas. Caso não tenha marcação, apresentar somente o texto "FALTA" no relatório;
* A folha de ponto deverá conter todos os dias do mês, nos dias futuros, os campos devem estar em branco;
