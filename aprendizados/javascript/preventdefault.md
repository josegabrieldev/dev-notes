# `preventDefault()` e o comportamento padrão dos eventos

**Linguagem:** JavaScript  
**Contexto:** Projeto Portfolio  
**Categoria:** Eventos e formulários

---

## 📌 O que eu aprendi

Eu já conhecia o `preventDefault()` e sabia que ele era usado para evitar o comportamento padrão de um elemento ou evento.

O que eu não entendia era **qual comportamento padrão estava sendo evitado no caso de um formulário** e o que realmente acontecia quando eu não utilizava esse método.

Durante uma melhoria no formulário de contato do meu Portfolio, fui entender isso melhor porque queria interceptar o envio do formulário usando JavaScript para mostrar um overlay de sucesso ou erro na própria página.

---

## 🔍 O que é o comportamento padrão

Quando um evento acontece no navegador, determinados elementos possuem um comportamento padrão associado a esse evento.

No caso de um formulário, quando o usuário envia os dados, acontece o evento `submit`.

Se esse comportamento padrão não for impedido, o navegador segue o fluxo normal de envio do formulário:

```text
Usuário preenche o formulário
        ↓
Clica em enviar
        ↓
O formulário dispara o evento `submit`
        ↓
O navegador segue o comportamento padrão
        ↓
Monta e envia a requisição
        ↓
Recebe uma resposta
        ↓
Pode navegar para essa resposta
```

No meu projeto, esse comportamento fazia parte do fluxo tradicional em que o HTML enviava os dados para o Formspree.

---

## 🛑 O que o `preventDefault()` faz

O `preventDefault()` é um método do JavaScript usado para **impedir o comportamento padrão associado a um evento**.

No caso do formulário, ele permite impedir que o navegador siga automaticamente o fluxo padrão do `submit`.

A ideia pode ser representada assim:

```text
Evento acontece
     ↓
JavaScript recebe o evento
     ↓
`event.preventDefault()`
     ↓
Comportamento padrão é impedido
     ↓
JavaScript pode assumir o controle do fluxo
```

Isso não significa que o evento `submit` deixa de existir.

O evento continua acontecendo. O que muda é que o comportamento padrão associado a ele é impedido.

---

## 🧠 Por que ele precisa aparecer no início da função

Durante a explicação, entendi que o `preventDefault()` deve ser chamado **antes de deixar o restante da lógica continuar**, principalmente quando a intenção é assumir o controle do comportamento do formulário.

Um exemplo simplificado:

```js
form.addEventListener('submit', (event) => {
    event.preventDefault();

    // restante da lógica
});
```

Primeiro o comportamento padrão é impedido.

Depois disso, posso executar minha própria lógica JavaScript sem deixar o navegador continuar automaticamente com a submissão tradicional do formulário.

---

## 💡 O que eu sabia antes

Eu já sabia que:

> "`preventDefault()` evita o comportamento padrão."

Também sabia que, em um formulário, ele podia impedir o recarregamento da página.

O que eu ainda não entendia era **o que estava por trás desse comportamento**.

Eu não sabia que o envio do formulário dispara o evento `submit` e que, seguindo o comportamento padrão, o navegador realiza a submissão do formulário, prepara a requisição e segue o fluxo de resposta.

---

## 🚀 O que eu entendi depois

Agora entendo melhor a relação entre as três coisas:

```text
`submit`
   ↓
evento de envio do formulário
   ↓
comportamento padrão
   ↓
navegador realiza a submissão
   ↓
requisição / resposta
```

E, quando uso:

```js
event.preventDefault();
```

o fluxo passa a ser:

```text
`submit`
   ↓
JavaScript recebe o evento
   ↓
`event.preventDefault()`
   ↓
comportamento padrão é impedido
   ↓
JavaScript pode controlar o que acontece depois
```

Esse foi o ponto principal do aprendizado.

---

## 🎯 Aplicação no projeto

Esse aprendizado surgiu enquanto eu estava planejando uma melhoria no formulário de contato do meu **Portfolio**.

O formulário originalmente funcionava sem JavaScript controlando o envio:

```text
Usuário preenche os campos
        ↓
Clica em enviar
        ↓
HTML envia para o Formspree
        ↓
Formspree processa
        ↓
O navegador segue o redirecionamento definido
```

Eu escolhi mudar esse comportamento porque queria uma experiência melhor para o usuário.

A ideia era interceptar o envio do formulário e, depois de controlar a resposta pelo JavaScript, mostrar um **overlay/card de sucesso ou erro** na própria página.

Para isso, primeiro precisei entender o comportamento padrão que deveria ser impedido.

---

## 📈 Impacto

Esse aprendizado mudou minha compreensão sobre eventos no JavaScript.

Antes, eu conhecia o `preventDefault()` principalmente como uma forma de "impedir o comportamento padrão".

Agora consigo entender **qual comportamento estou impedindo e por que preciso fazer isso**.

Isso também me ajuda a entender melhor situações em que o JavaScript precisa assumir o controle de uma ação que o navegador normalmente executaria sozinho.

No caso do formulário, esse conhecimento se tornou uma base importante para os próximos passos da implementação:

- receber o evento `submit`;
- impedir o comportamento padrão;
- obter os dados do formulário;
- enviar os dados usando JavaScript;
- tratar a resposta;
- mostrar uma mensagem de sucesso ou erro.

---

## 🔑 Palavras-chave

`JavaScript` · `preventDefault()` · `event` · `evento` · `submit` · `form` · `formulário` · `comportamento padrão` · `DOM` · `event listener` · `addEventListener` · `requisição` · `Formspree`

---

## 📚 Relação com outros aprendizados

Este arquivo explica **como e por que impedir o comportamento padrão de um evento**, com foco no envio de formulários.

Outros aprendizados relacionados aprofundam partes diferentes desse processo:

- `como-funciona-o-envio-de-um-formulario.md` → explica o fluxo padrão de envio de um formulário HTML.
- `objeto-event.md` → explica o objeto `event` recebido pela função e as informações disponíveis nele.
- `formdata.md` → explica como obter os dados do formulário de uma só vez.
- `fetch-e-tratamento-de-respostas.md` → explica o envio controlado pelo JavaScript e o tratamento da resposta.