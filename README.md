# Projeto-Academico-Plano-de-Estudos

Projeto acadêmico desenvolvido em Flutter com o objetivo de praticar conceitos fundamentais de desenvolvimento mobile, gerenciamento de estado e navegação entre telas.

O aplicativo permite registrar sessões de estudo, ativar um modo de foco, informar o nome do estudante, visualizar um resumo e consultar uma orientação rápida.

> Projeto desenvolvido exclusivamente para fins acadêmicos e de estudo.

---

## Objetivo do projeto

Este projeto foi criado para aplicar, na prática, conceitos introdutórios de Flutter e Dart, incluindo:

- criação de interfaces com widgets;
- uso de `StatelessWidget` e `StatefulWidget`;
- gerenciamento de estado com `setState`;
- entrada de dados com `TextField`;
- uso de botões;
- uso de `SwitchListTile`;
- navegação entre telas;
- passagem de dados entre telas;
- uso de `showModalBottomSheet`;
- atualização dinâmica da interface.

---

## Tecnologias utilizadas

- Flutter
- Dart
- Material Design
- Git
- GitHub

---

## Funcionalidades

### Registro de sessões

O aplicativo possui um contador de sessões de estudo concluídas.

Ao tocar em:

```text
Concluir sessão
```

o contador é incrementado.

Também é possível desfazer uma sessão com o botão:

```text
Desfazer uma sessão
```

O contador não permite valores negativos.

### Modo foco

O aplicativo possui um controle para ativar ou desativar o modo foco.

Quando o modo foco está ativo:

- o estado da aplicação é atualizado;
- a informação aparece no resumo;
- o ícone principal da tela altera sua aparência.

### Nome do estudante

O usuário pode informar como deseja ser chamado através de um campo de texto.

A saudação da tela principal é atualizada dinamicamente.

Caso nenhum nome seja informado, o aplicativo utiliza uma identificação padrão de estudante.

### Resumo de estudos

O botão:

```text
Ver resumo
```

abre uma segunda tela com as informações atuais da sessão.

O resumo apresenta:

- nome do estudante;
- quantidade de sessões concluídas;
- estado do modo foco.

A navegação é realizada com:

```dart
Navigator.push(...)
```

e o retorno para a tela anterior é realizado com:

```dart
Navigator.pop(...)
```

### Orientação

O botão:

```text
Ver orientação
```

abre um `showModalBottomSheet`.

Nele são exibidas informações sobre:

- quantidade de sessões concluídas;
- importância de realizar pausas entre as sessões.

### Reiniciar informações

O aplicativo também possui a opção:

```text
Reiniciar sessões e foco
```

Essa ação:

- redefine o número de sessões para zero;
- desativa o modo foco.

---

## Estrutura principal

A lógica principal do projeto está concentrada em:

```text
lib/
└── main.dart
```

O arquivo contém:

- inicialização da aplicação;
- widget principal;
- tela de estudos;
- controle de estado;
- navegação;
- tela de resumo.

---

## Principais classes

### PlanoEstudosApp

Classe responsável por iniciar a aplicação Flutter e carregar a tela principal.

### TelaEstudos

Tela principal do aplicativo.

Ela utiliza `StatefulWidget`, pois possui informações que podem mudar durante a execução.

Os principais estados controlados são:

```dart
int sessoes = 0;
bool focoAtivo = false;
String nome = '';
```

Esses valores são atualizados com:

```dart
setState(() {
  // alteração do estado
});
```

### TelaResumo

Tela responsável por exibir o resumo das informações preenchidas na tela principal.

Ela recebe através do construtor:

```dart
nome
sessoes
focoAtivo
```

Isso demonstra a passagem de dados entre telas no Flutter.

---

## Conceitos praticados

### StatefulWidget

Foi utilizado porque a tela principal possui informações que mudam durante a execução do aplicativo.

Exemplos:

- quantidade de sessões;
- modo foco;
- nome informado pelo usuário.

### setState

O `setState` informa ao Flutter que o estado foi alterado e que a interface precisa ser reconstruída.

Exemplo:

```dart
setState(() {
  sessoes = sessoes + 1;
});
```

### TextField

Utilizado para receber o nome do estudante.

O valor digitado é capturado através de:

```dart
onChanged
```

e armazenado na variável `nome`.

### SwitchListTile

Utilizado para controlar o modo foco.

O componente trabalha com um valor booleano:

```dart
true
false
```

### Navigator

O `Navigator` é utilizado para controlar a navegação entre as telas.

Para abrir a tela de resumo:

```dart
Navigator.push(...)
```

Para voltar:

```dart
Navigator.pop(...)
```

### MaterialPageRoute

Utilizado junto com o `Navigator.push` para criar a rota até a tela de resumo.

### showModalBottomSheet

Utilizado para exibir a orientação na parte inferior da tela sem substituir completamente a tela principal.

### SingleChildScrollView

Utilizado para permitir rolagem caso o conteúdo seja maior do que o espaço disponível na tela.

### SafeArea

Utilizado para evitar que elementos da interface fiquem posicionados em áreas ocupadas por componentes do sistema operacional.

---

## Como executar o projeto

Certifique-se de possuir Flutter instalado e configurado.

Dentro da pasta do projeto, execute:

```bash
flutter pub get
```

Depois verifique o projeto com:

```bash
flutter analyze
```

Para iniciar a aplicação:

```bash
flutter run
```

---

## Verificação do código

Antes de executar ou enviar alterações para o repositório, é recomendado utilizar:

```bash
flutter analyze
```

Esse comando verifica possíveis problemas no código Dart e Flutter.

---

## Git e GitHub

Para verificar alterações:

```bash
git status
```

Para adicionar os arquivos:

```bash
git add .
```

Para criar um commit:

```bash
git commit -m "Descricao da alteracao"
```

Para enviar as alterações:

```bash
git push origin main
```

Para baixar alterações feitas em outra máquina:

```bash
git pull origin main
```

---

## Finalidade acadêmica

Este projeto foi desenvolvido como atividade acadêmica para prática dos fundamentos de Flutter e Dart.

O objetivo principal é demonstrar conceitos de:

- construção de interfaces;
- widgets;
- estado;
- interação com o usuário;
- navegação;
- passagem de informações entre telas;
- atualização dinâmica da interface.

---

## Observação final

O projeto possui finalidade exclusivamente acadêmica.

Os recursos implementados foram construídos com foco no aprendizado dos conceitos apresentados durante as aulas.
