# Como funciona o envio de um formulário HTML

**Linguagem:** HTML  
**Contexto:** Projeto Portfolio  
**Categoria:** Fundamentos de formulários

---

## 📌 O que eu aprendi

Aprendi melhor como funciona o envio de um formulário HTML e o que acontece por trás quando o usuário clica no botão de enviar.

Eu já sabia que, ao enviar um formulário, a página podia recarregar e que o formulário precisava de um destino para enviar os dados, mas não entendia direito o que o navegador fazia nesse processo.

O fluxo básico que entendi foi:

```text
Usuário preenche o formulário
        ↓
Clica em enviar
        ↓
O formulário dispara o evento `submit`
        ↓
O navegador segue o comportamento padrão do formulário
        ↓
Monta e envia a requisição para o destino definido
        ↓
O servidor processa os dados
        ↓
O navegador recebe uma resposta
        ↓
O navegador pode navegar para essa resposta
```

No meu projeto, esse processo acontecia usando o **Formspree**, porque meu projeto é somente Front-End e eu não tinha um back-end próprio para receber e processar os dados do formulário.

---

## 🧩 O que acontece no meu projeto

Meu formulário funcionava originalmente desta forma:

```text
Usuário preenche os campos
        ↓
Clica em enviar
        ↓
O formulário dispara o `submit`
        ↓
O navegador segue o comportamento padrão
        ↓
Os dados são enviados para o Formspree
        ↓
Formspree processa o envio
        ↓
Formspree redireciona para a URL definida em `_next`
```

Ou seja, o navegador não estava usando JavaScript para controlar o envio.

Era o próprio comportamento padrão do formulário HTML que fazia esse processo.

---

## 🔍 O que eu entendi sobre o `submit`

O `submit` é o evento relacionado ao envio de um formulário.

Eu já sabia que existia um comportamento padrão quando clicava em enviar, mas não entendia exatamente o que esse comportamento fazia.

Agora entendo que, quando o formulário é enviado e o comportamento padrão não é impedido, o navegador segue o fluxo normal da submissão: prepara a requisição com os dados do formulário, envia para o destino definido e depois recebe uma resposta.

Por isso, quando o formulário é enviado dessa maneira, o navegador pode sair da página atual e navegar para a resposta recebida.

Esse entendimento foi importante para perceber que, se eu quiser controlar o envio pelo JavaScript e permanecer na mesma página, preciso impedir esse comportamento padrão e assumir o controle do processo.

---

## 💡 Por que isso foi importante no meu projeto

Esse entendimento apareceu quando eu estava tentando melhorar a experiência do formulário de contato.

Eu queria que, depois do envio, aparecesse um **overlay/card de sucesso ou erro na própria página**, em vez de simplesmente sair da página de contato e carregar uma página separada de agradecimento.

Para conseguir controlar esse comportamento pelo JavaScript, eu precisava primeiro entender o que o formulário fazia sozinho.

Foi a partir disso que entendi melhor a função do `preventDefault()` e por que ele é usado quando queremos impedir o comportamento padrão do `submit`.

---

## 🧠 O que mudou no meu entendimento

### Antes

Eu sabia que:

> "Quando envio o formulário, a página recarrega e os dados são enviados."

Mas não entendia claramente o que acontecia entre essas etapas.

### Depois

Passei a entender que existe um fluxo de envio do formulário:

```text
submit
  ↓
comportamento padrão do formulário
  ↓
navegador prepara a requisição
  ↓
envia para o destino
  ↓
recebe a resposta
  ↓
pode navegar conforme o fluxo do formulário
```

Isso também me ajudou a entender por que, quando quero assumir o controle desse processo com JavaScript, preciso interferir no comportamento padrão do formulário.

---

## 🎯 Aplicação no projeto

Esse conhecimento foi adquirido durante uma melhoria no formulário de contato do meu **Portfolio**.

O objetivo da melhoria era substituir o redirecionamento para uma página `obrigado.html` por um overlay dentro da própria página, permitindo mostrar uma mensagem amigável de sucesso ou erro sem tirar o usuário da página de contato.

A implementação ainda estava sendo planejada quando esse conceito foi estudado.

---

## 📈 Impacto

Esse aprendizado me deu uma visão melhor de como os formulários HTML funcionam antes mesmo de envolver JavaScript.

Isso é importante porque agora consigo entender melhor **o que o navegador já faz sozinho** e, a partir disso, decidir quando realmente preciso interferir nesse comportamento com JavaScript.

Também serviu como base para outros aprendizados que vieram durante a mesma melhoria:

- `preventDefault()`
- `event`
- `event.target`
- `FormData`
- `fetch`
- tratamento da resposta do servidor

---

## 🔑 Palavras-chave

`HTML` · `form` · `formulário` · `submit` · `form submission` · `action` · `method` · `requisição` · `resposta` · `servidor` · `Formspree` · `JavaScript` · `preventDefault` · `frontend`

---

## 📚 Relação com outros aprendizados

Este arquivo explica o **fluxo padrão do formulário**.

Outros arquivos relacionados aprofundam partes específicas desse processo:

- `preventdefault.md` → como impedir o comportamento padrão do formulário.
- `objeto-event.md` → entender o objeto de evento recebido pela função.
- `formdata.md` → coletar os dados do formulário.
- `fetch-e-tratamento-de-respostas.md` → enviar e tratar a resposta usando JavaScript.
- `formspree.md` → entender o serviço utilizado para processar o formulário no projeto.