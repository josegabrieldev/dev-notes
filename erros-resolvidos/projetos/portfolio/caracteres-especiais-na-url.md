# Caracteres especiais quebrando a URL

> Problema encontrado durante o desenvolvimento do Portfolio ao enviar uma mensagem contendo acentos e caracteres especiais diretamente pela URL.

---

## Problema

Durante o desenvolvimento do Portfolio, adicionei links para contato por WhatsApp e e-mail.

Esses links continham uma mensagem personalizada que possuía espaços e caracteres com acento.

Inicialmente, tentei utilizar o texto diretamente na URL, mas isso poderia gerar problemas por causa dos caracteres especiais presentes na mensagem.

---

## Causa

Uma URL possui caracteres reservados que fazem parte da sua estrutura.

Quando uma string contendo espaços, acentos ou símbolos especiais é adicionada diretamente à URL, esses caracteres podem alterar sua interpretação ou até mesmo quebrar o funcionamento do link.

---

## Solução

## Solução

Utilizei `encodeURIComponent()` apenas para codificar a mensagem.

```javascript
const mensagem = "Olá! Gostaria de conversar sobre um projeto.";

const mensagemCodificada = encodeURIComponent(mensagem);

console.log(mensagemCodificada);

Depois de obter o resultado, copiei o texto codificado e substituí a mensagem original nos links do WhatsApp e do e-mail presentes no HTML.

Como a mensagem era fixa, não houve necessidade de manter esse código no projeto.

---

## Resultado

Os links passaram a funcionar corretamente mesmo contendo uma mensagem com espaços e caracteres especiais.

Além de resolver o problema, aprendi quando utilizar `encodeURIComponent()` e em quais situações ela é mais indicada do que `encodeURI()`.

---

## Impacto no projeto

Os links de contato do Portfolio passaram a funcionar corretamente e ficaram preparados para lidar com mensagens contendo caracteres especiais.

---

## Lição aprendida

Sempre que um texto precisar ser enviado como parâmetro de uma URL, ele deve ser codificado antes de ser adicionado ao link.

Isso evita problemas com caracteres especiais e garante que a URL seja interpretada corretamente.

---

## Resumo

- ✔ O problema era causado por caracteres especiais enviados diretamente na URL.
- ✔ A solução foi utilizar `encodeURIComponent()`.
- ✔ A URL passou a funcionar corretamente após a codificação da mensagem.
- ✔ Também aprendi a diferença entre `encodeURIComponent()` e `encodeURI()`.

---

## Palavras-chave

- Portfolio
- JavaScript
- URL
- caracteres especiais
- acentos
- espaços
- query string
- parâmetros de URL
- mensagem
- link
- encodeURIComponent
- encodeURI
- bug
- correção
- resolução de erro