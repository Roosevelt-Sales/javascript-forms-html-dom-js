# Eventos em JavaScript

Eventos são ações ou ocorrências que acontecem no navegador ou na interface do usuário, como cliques, digitação em um campo de texto, carregamento de uma página, entre outros. O JavaScript permite que você manipule esses eventos para criar interatividade em uma aplicação web.

## O que são Eventos?

Eventos são gerados por interações do usuário (ou do sistema) e podem ser capturados e manipulados. Alguns exemplos de eventos comuns são:

- `click`: acionado quando um elemento é clicado.
- `keydown`: acionado quando uma tecla é pressionada.
- `mouseover`: acionado quando o mouse passa sobre um elemento.
- `submit`: acionado quando um formulário é enviado.

## Manipulação de Eventos com `addEventListener`

O método `addEventListener()` é a forma mais comum e recomendada para associar eventos a elementos no DOM. Ele permite que você adicione múltiplos manipuladores de eventos ao mesmo elemento, sem sobrescrever os eventos anteriores.

### Sintaxe

```javascript
element.addEventListener('evento', função, useCapture);
```

- `evento`: o tipo de evento que você deseja ouvir, como 'click', 'mouseover', 'keydown', etc.
- `função`: a função que será executada quando o evento for acionado.
- `useCapture` (opcional): um booleano que indica se o evento deve ser capturado durante a fase de captura ou propagação.

### Exemplo de uso do `addEventListener`

```javascript
// Selecionando um botão no DOM
const botao = document.querySelector('button');

// Adicionando um evento de clique ao botão
botao.addEventListener('click', function() {
    alert('O botão foi clicado!');
});
```

Nesse exemplo, um alerta será exibido sempre que o botão for clicado.

## Removendo um Event Listener

Você também pode remover um evento previamente adicionado usando o método `removeEventListener()`. Para isso, a função usada no `addEventListener` deve ser nomeada, e não anônima.

### Exemplo de uso do `removeEventListener`

```javascript
function alertaClicado() {
    alert('O botão foi clicado!');
}

botao.addEventListener('click', alertaClicado);

// Para remover o evento de clique
botao.removeEventListener('click', alertaClicado);
```

## Como Funciona `event.preventDefault()`

O método `event.preventDefault()` é uma função em JavaScript que impede o comportamento padrão de um evento. Ele é muito útil quando você deseja evitar que determinadas ações aconteçam, como o envio de um formulário ao pressionar um botão de "submit", ou evitar que um link leve o usuário a outra página.

Quando um evento é acionado em um elemento da página, ele normalmente executa seu comportamento padrão. Por exemplo:

- Em um formulário, ao clicar no botão de enviar, o navegador tenta enviar os dados para o servidor.
- Em um link (`<a>`), ao clicar, o navegador navega para o endereço especificado no atributo `href`.

O `event.preventDefault()` cancela esse comportamento padrão sem interromper o fluxo do código JavaScript ou do evento em si.

### Sintaxe

```javascript
element.addEventListener('evento', function(event) {
    event.preventDefault();
    // outras ações...
});
```

Aqui, a função `preventDefault()` é chamada dentro do manipulador de eventos, impedindo que o comportamento padrão do evento seja executado.

### Exemplo 1: Prevenir o envio de um formulário

Se você deseja validar um formulário antes de permitir que ele seja enviado, pode usar `event.preventDefault()` para evitar o envio até que todas as validações estejam corretas.

```javascript
const form = document.querySelector('form');

form.addEventListener('submit', function(event) {
    const input = document.querySelector('input').value;
    
    // Se o campo estiver vazio, prevenir o envio do formulário
    if (input === '') {
        event.preventDefault();
        alert('O campo não pode estar vazio.');
    }
});
```

Neste exemplo, se o campo de entrada estiver vazio, o envio do formulário será impedido.

### Exemplo 2: Prevenir o comportamento de um link

Quando um link é clicado, normalmente ele redireciona o usuário para outra página. Com `event.preventDefault()`, é possível impedir isso, permitindo, por exemplo, a execução de uma ação sem navegação.

```javascript
const link = document.querySelector('a');

link.addEventListener('click', function(event) {
    event.preventDefault();
    alert('O link foi clicado, mas a navegação foi impedida.');
});
```

Neste caso, ao clicar no link, a navegação é evitada e uma mensagem é exibida.

## Conclusão

O método `event.preventDefault()` é extremamente útil para controlar melhor o comportamento dos elementos na página, principalmente em situações onde você precisa de validações ou ações personalizadas antes que o comportamento padrão de um evento seja executado. Ele dá ao desenvolvedor mais controle sobre o fluxo da interação do usuário com a página.

## Outros Exemplos de Eventos

### Evento `keydown`

O evento `keydown` é acionado quando qualquer tecla é pressionada. Podemos usar isso para criar interatividade com o teclado.

```javascript
document.addEventListener('keydown', function(event) {
    console.log(`Tecla pressionada: ${event.key}`);
});
```

Neste exemplo, cada vez que uma tecla for pressionada, o nome da tecla será exibido no console.

### Evento `mouseover`

O evento `mouseover` é acionado quando o ponteiro do mouse passa sobre um elemento.

```javascript
const elemento = document.querySelector('div');

elemento.addEventListener('mouseover', function() {
    elemento.style.backgroundColor = 'yellow';
});
```

Aqui, a cor de fundo do `div` muda para amarelo sempre que o mouse passa sobre ele.

## Conclusão

Os eventos são uma parte fundamental da interatividade em páginas web. O método `addEventListener()` é uma ferramenta poderosa para escutar e responder a eventos sem sobrescrever outros manipuladores. Usando corretamente eventos como `click`, `keydown` e `mouseover`, você pode criar interfaces dinâmicas e interativas.

## Atividade - Desafio

Insira um botão no HTML que, ao ser clicado, ative um _Dark Mode_ na página. Para isso:
- altere o fundo da página para uma cor escura.
- altere o título, o texto do contador e os botões para uma cor clara. Atenção para alterar o texto do botão para a cor escura, para preservar o contraste.
- **Extra**: faça o processo inverso para habilitar, também, um _Light Mode_.
