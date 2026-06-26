# encodeURIComponent()

> Função nativa do JavaScript utilizada para codificar partes de uma URL, tornando caracteres especiais seguros para serem enviados em links.

---

## O que é

A função `encodeURIComponent()` converte caracteres especiais de uma string para um formato compatível com URLs.

Isso é útil quando um texto possui:

- Espaços
- Acentos
- Símbolos especiais
- Emojis
- Caracteres que podem quebrar uma URL

Em vez de enviar o texto original, a função retorna uma versão codificada.

---

## Sintaxe

```javascript
encodeURIComponent(texto);
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

Essa versão pode ser utilizada com segurança dentro de uma URL.

---

## Diferença entre encodeURIComponent() e encodeURI()

Embora os nomes sejam parecidos, possuem finalidades diferentes.

### encodeURIComponent()

Codifica praticamente todos os caracteres especiais.

Ideal para codificar:

- parâmetros de URL
- mensagens
- valores enviados na query string

Exemplo:

```javascript
encodeURIComponent("Olá, tudo bem?");
```

Resultado:

```text
Ol%C3%A1%2C%20tudo%20bem%3F
```

---

### encodeURI()

Codifica apenas os caracteres necessários para manter uma URL válida.

Não altera caracteres que fazem parte da estrutura da URL, como:

```text
:
/
?
&
=
#
```

Por isso, é indicado quando você deseja codificar uma URL inteira, e não apenas um trecho dela.

---

## Quando usar

Utilize `encodeURIComponent()` sempre que precisar inserir um texto dentro de uma URL.

Exemplos:

- mensagens do WhatsApp
- parâmetros de pesquisa
- nomes de usuários
- textos digitados pelo usuário
- filtros enviados pela URL

---

## Aprendizado prático

Aprendi essa função ao resolver um problema em um projeto onde uma mensagem contendo caracteres acentuados era inserida diretamente na URL.

Ao utilizar `encodeURIComponent()`, a mensagem passou a ser codificada corretamente, evitando problemas com caracteres especiais.

---

## Resumo

- ✔ É uma função nativa do JavaScript.
- ✔ Codifica partes de uma URL.
- ✔ Evita problemas com espaços, acentos e caracteres especiais.
- ✔ Para codificar uma URL inteira, normalmente utiliza-se `encodeURI()`.