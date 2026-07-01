# Como funciona o envio de um formulário HTML

> Aprendi como um formulário HTML envia informações e por que um projeto apenas com HTML, CSS e JavaScript não consegue enviar e-mails sozinho.

---

## Por que existe?

Durante muito tempo eu utilizava formulários sem pensar muito no que acontecia quando clicava no botão **Enviar**.

Enquanto fazia melhorias no formulário de contato do meu Portfolio, percebi que sabia usar o Formspree, mas não entendia exatamente qual era o seu papel.

Foi então que descobri como funciona o fluxo de envio de um formulário HTML e por que um servidor é necessário nesse processo.

---

## O que é

Um formulário HTML serve para coletar informações do usuário, como nome, e-mail e mensagem.

Quando o formulário é enviado, o navegador apenas reúne esses dados e faz uma requisição para um servidor.

É importante entender que o navegador **não envia e-mails sozinho**. Ele apenas envia os dados para algum lugar que seja capaz de processá-los.

Esse "algum lugar" normalmente é um back-end ou um serviço de terceiros, como o Formspree.

---

## Como funciona

Quando o usuário clica no botão de envio, acontece o seguinte fluxo:

```text
Usuário preenche o formulário

        ↓

Clica no botão Enviar

        ↓

O navegador reúne os dados do formulário

        ↓

Envia uma requisição para o servidor definido no atributo action

        ↓

O servidor processa os dados

        ↓

O servidor retorna uma resposta

        ↓

O navegador exibe essa resposta ou é redirecionado para outra página
```

Todo esse processo acontece automaticamente quando utilizamos um formulário HTML tradicional.

---

## Exemplo

```html
<form action="https://formspree.io/f/seu-endpoint" method="POST">
  <input type="text" name="nome" />
  <input type="email" name="email" />

  <button type="submit">
    Enviar
  </button>
</form>
```

Nesse exemplo, quando o usuário clicar em **Enviar**, o navegador enviará automaticamente os dados para a URL definida no atributo `action`.

---

## Quando usar

Esse comportamento é o padrão de qualquer formulário HTML.

Ele é útil quando:

- existe um servidor para receber os dados;
- utiliza-se um serviço de terceiros, como o Formspree;
- não há necessidade de controlar o envio com JavaScript.

Caso seja necessário validar dados, exibir mensagens personalizadas ou controlar o envio manualmente, o JavaScript pode interceptar esse comportamento.

---

## Contexto do aprendizado

Aprendi esse conceito enquanto fazia melhorias no formulário de contato do meu Portfolio.

Inicialmente, eu acreditava que utilizava o Formspree principalmente por causa da proteção contra spam.

Durante uma conversa com minha IA mentora, descobri que sua principal função é atuar como um servidor para receber os dados do formulário e enviá-los para o meu e-mail.

Também entendi que um projeto feito apenas com HTML, CSS e JavaScript não consegue enviar e-mails diretamente, pois o navegador não possui essa responsabilidade.

Essa conversa me ajudou a compreender melhor todo o fluxo de envio de um formulário antes mesmo de começar a implementar melhorias com JavaScript.

---

## Observações

- O navegador apenas envia os dados para um servidor.
- Quem processa esses dados é o servidor ou um serviço responsável por isso.
- O envio automático acontece por causa do comportamento padrão do elemento `<form>`.

---

## Resumo

- ✔ Um formulário HTML coleta dados do usuário.
- ✔ O navegador envia esses dados para um servidor.
- ✔ O navegador não envia e-mails diretamente.
- ✔ É necessário um back-end ou um serviço como o Formspree para processar o envio.
- ✔ Esse processo acontece automaticamente no envio padrão do formulário.

---

## Palavras-chave

- HTML
- formulário
- form
- envio de formulário
- submit
- navegador
- servidor
- requisição
- resposta
- action
- method
- Formspree
- front-end
- back-end
- fluxo de envio