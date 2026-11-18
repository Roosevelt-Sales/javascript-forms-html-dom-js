# Cadastro de Aluno · Formulários + DOM

Projeto base da aula de **Formulários no HTML** e **primeiros passos no DOM**
UC4 · Desenvolvimento Front-end · Profa. Ma. Tamara Simões

## O que tem aqui

| Arquivo | O que é |
|---|---|
| `index.html` | Estrutura da página em divs. O formulário vai dentro da `div id="app"`. |
| `style.css` | CSS pronto, incluindo o estilo de form, fieldset, legend, inputs, botões e da lista de alunos. |
| `script.js` | Roteiro comentado da parte 2 (DOM). Você escreve o código em cada seção. |

## Parte 1: o formulário

Monte o `<form id="form-cadastro">` dentro da `div id="app"` com quatro fieldsets:
Dados pessoais, Acesso, Curso e Turno. Depois, o checkbox de regras, o
`<p id="mensagem" class="mensagem"></p>` e os botões.

Classes que o CSS já espera:

- `div.campo` em volta de cada label + input
- `div.opcoes` e `div.opcao` para os radios e o checkbox
- `div.botoes` em volta dos botões

Os ids que a parte 2 usa: `form-cadastro`, `nome`, `email`, `senha`, `curso`, `termos`, `mensagem`.

## Parte 2: o DOM

Siga as seções do `script.js`:

1. Capturar os elementos
2. Validar os campos
3. Criar novos elementos na lista
4. Prévia: `addEventListener` no botão

Na parte 2, o botão Cadastrar passa a ser
`<button type="button" id="btn-cadastrar" class="botao-principal">Cadastrar</button>`.
