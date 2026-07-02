# event.preventDefault()

> Método do JavaScript utilizado para impedir que um elemento execute seu comportamento padrão, permitindo que o desenvolvedor assuma o controle da ação.

---

## Por que existe?

Muitos elementos do HTML possuem um comportamento padrão definido pelo navegador.

Alguns exemplos:

- um formulário é enviado quando o usuário clica em um botão do tipo `submit`;
- um link navega para outra página quando é clicado;
- uma caixa de seleção muda de estado quando recebe um clique.

Em alguns casos, queremos controlar essas ações manualmente usando JavaScript.

É exatamente para isso que existe o `event.preventDefault()`.

---

## O que é

`preventDefault()` é um método do objeto `event`.

Quando ele é executado, informa ao navegador que o comportamento padrão daquele evento não deve acontecer.

Isso permite que o JavaScript assuma o controle da ação e decida o que fazer.

---

## Como funciona

Quando um formulário é enviado normalmente, acontece o seguinte fluxo:

```text
Usuário preenche o formulário

        ↓

Clica no botão Enviar

        ↓

O navegador dispara o evento submit

        ↓

O navegador monta a requisição

        ↓

Envia os dados para o servidor

        ↓

Espera uma resposta

        ↓

Carrega a resposta recebida
```

Ao utilizar `event.preventDefault()`, esse fluxo é interrompido logo no início.

Depois disso, o JavaScript pode validar os dados, enviar uma requisição usando `fetch()` ou executar qualquer outra lógica antes de decidir o que fazer.

---

## Sintaxe

```javascript
form.addEventListener("submit", function (event) {
  event.preventDefault();

  // Código responsável por tratar o envio do formulário.
});
```

---

## Quando usar

Utilize `event.preventDefault()` quando quiser impedir o comportamento padrão de um elemento.

Alguns exemplos:

- validar um formulário antes do envio;
- enviar dados utilizando `fetch()`;
- impedir que um link navegue imediatamente;
- executar uma ação personalizada antes que o navegador faça a ação padrão.

---

## Contexto do aprendizado

Eu já utilizava `event.preventDefault()` em alguns projetos, inclusive no próprio Portfolio.

Sabia que ele impedia o comportamento padrão do formulário e evitava o recarregamento da página, mas nunca tinha entendido exatamente o que estava sendo interrompido.

Durante uma conversa com minha IA mentora, aprendi que o comportamento padrão do formulário é disparar o evento `submit`, montar a requisição e enviá-la automaticamente para o servidor.

Com isso, finalmente entendi o motivo de utilizar `event.preventDefault()` e por que ele normalmente é chamado logo no início da função que trata o envio do formulário.

---

## Observações

- `preventDefault()` não cancela o evento, apenas impede sua ação padrão.
- O restante da função continua sendo executado normalmente.
- Ele deve ser chamado antes que o comportamento padrão aconteça, por isso normalmente aparece nas primeiras linhas da função.

---

## Resumo

- ✔ É um método do objeto `event`.
- ✔ Impede o comportamento padrão de um evento.
- ✔ Em formulários, evita o envio automático realizado pelo navegador.
- ✔ Permite que o JavaScript controle o que acontece depois.
- ✔ É muito utilizado junto com validações e envio de dados usando `fetch()`.

---

## Palavras-chave

- JavaScript
- event
- preventDefault
- submit
- formulário
- comportamento padrão
- evento
- addEventListener
- fetch
- validação
- envio de formulário
- navegador