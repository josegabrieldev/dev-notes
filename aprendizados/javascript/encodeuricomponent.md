# encodeURIComponent()

> Função nativa do JavaScript utilizada para codificar uma string para que ela possa ser utilizada com segurança como parte de uma URL.

---

## O que é

`encodeURIComponent()` é uma função nativa do JavaScript que converte caracteres especiais de uma string para um formato compatível com URLs.

Ela é muito útil quando um texto contém:

- espaços;
- acentos;
- símbolos especiais;
- emojis;
- ou qualquer caractere que possa alterar ou quebrar uma URL.

Em vez de utilizar o texto original, a função retorna uma versão codificada que pode ser enviada com segurança como parte da URL.

---

## Sintaxe

```javascript
encodeURIComponent(valor);
```

---

## Exemplo

```javascript
const mensagem = "Olá, tudo bem?";

const mensagemCodificada = encodeURIComponent(mensagem);

console.log(mensagemCodificada);
```

Saída:

```text
Ol%C3%A1%2C%20tudo%20bem%3F
```

No meu caso, utilizei a função apenas para gerar o texto codificado.

```javascript
const mensagem = "Olá! Gostaria de conversar sobre um projeto.";

const mensagemCodificada = encodeURIComponent(mensagem);

console.log(mensagemCodificada);
```

Depois de obter o resultado, copiei o texto codificado e o utilizei diretamente nos links do WhatsApp e do e-mail do meu Portfolio.

---

## Diferença entre encodeURIComponent() e encodeURI()

As duas funções possuem objetivos parecidos, mas são utilizadas em situações diferentes.

### encodeURIComponent()

Utilize quando precisar codificar apenas uma parte da URL, como um parâmetro ou uma mensagem.

Exemplo:

```javascript
const mensagem = "Olá, tudo bem?";

encodeURIComponent(mensagem);
```

Resultado:

```text
Ol%C3%A1%2C%20tudo%20bem%3F
```

---

### encodeURI()

Utilize quando quiser codificar uma URL inteira.

Ela preserva caracteres que fazem parte da estrutura da URL, como:

```text
:
/
?
&
=
#
```

Por isso, normalmente ela é utilizada quando a URL completa já está montada.

---

## Quando usar

Utilize `encodeURIComponent()` quando precisar adicionar um texto dentro de uma URL.

Alguns exemplos:

- mensagens do WhatsApp;
- links de e-mail (`mailto`);
- parâmetros de pesquisa;
- filtros enviados pela URL;
- textos digitados pelo usuário;
- parâmetros enviados em requisições GET.

---

## Contexto do aprendizado

Aprendi `encodeURIComponent()` enquanto desenvolvia meu Portfolio.

Eu estava adicionando links para contato por WhatsApp e e-mail com uma mensagem personalizada.

Como essa mensagem possuía espaços e caracteres com acento, descobri que não era uma boa prática colocá-la diretamente na URL.

Pesquisando sobre o problema, encontrei a função `encodeURIComponent()`, que codificou o texto corretamente. Depois disso, bastou copiar o resultado gerado e utilizá-lo diretamente nos links do HTML.

Durante esse processo também aprendi a diferença entre `encodeURIComponent()` e `encodeURI()`.

---

## Observações

- `encodeURIComponent()` não cria uma URL.
- Ela apenas codifica uma string para que ela possa fazer parte de uma URL.
- O resultado pode ser utilizado em links, parâmetros de URL e outros locais onde seja necessário enviar texto pela URL.

---

## Resumo

- ✔ É uma função nativa do JavaScript.
- ✔ Codifica uma string para ser utilizada com segurança em uma URL.
- ✔ Evita problemas com espaços, acentos e caracteres especiais.
- ✔ É indicada para parâmetros e valores enviados pela URL.
- ✔ Para codificar uma URL inteira, normalmente utiliza-se `encodeURI()`.

---

## Palavras-chave

- JavaScript
- encodeURIComponent
- encodeURI
- URL
- codificação de URL
- caracteres especiais
- acentos
- espaços
- query string
- parâmetros de URL
- requisição GET
- API
- WhatsApp