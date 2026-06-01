# Aluno: Daniel Batista 
# Turma: 2ADS - MAT

<br><br>

# XMLHttpRequest, fetch, Promises e async/await

## XMLHttpRequest (XHR)

Foi a maneira antiga criada para fazer requisições HTTP no JavaScript.

Ele permite buscar dados de uma API sem atualizar a página.

### Exemplo

```javascript
const xhr = new XMLHttpRequest();

xhr.open("GET", "https://api.site.com/dados");

xhr.onload = function () {
    console.log(xhr.responseText);
};

xhr.send();
```

### Características
- Mais antigo
- Código maior
- Mais difícil de ler
- Usa eventos e callbacks

---

# fetch()

`fetch` é a forma moderna de fazer requisições HTTP.

Ele foi criado para substituir o XMLHttpRequest.

### Exemplo

```javascript
fetch("https://api.site.com/dados")
    .then(resposta => resposta.json())
    .then(dados => {
        console.log(dados);
    });
```

### Características
- Mais simples
- Mais moderno
- Código mais limpo
- Usa Promises

---

# Promises

Promises são objetos que representam operações que ainda vão terminar.

Como uma requisição demora um tempo, o JavaScript usa Promises para esperar o resultado.

O `fetch()` já retorna uma Promise.

### Estados de uma Promise

| Estado | Significado |
|---|---|
| pending | esperando |
| fulfilled | sucesso |
| rejected | erro |

### Exemplo

```javascript
fetch("https://api.site.com/dados")
    .then(resposta => {
        console.log("Deu certo");
    })
    .catch(erro => {
        console.log("Deu erro");
    });
```

### Métodos principais
- `.then()` → executa quando dá certo
- `.catch()` → executa quando dá erro

---

# async/await

`async/await` é uma forma mais fácil de trabalhar com Promises.

Ele deixa o código mais parecido com código normal.

### Exemplo

```javascript
async function buscarDados() {
    const resposta = await fetch("https://api.site.com/dados");

    const dados = await resposta.json();

    console.log(dados);
}

buscarDados();
```

### Características
- Mais moderno
- Mais organizado
- Mais fácil de entender
- Usa Promises internamente

---

# Diferença principal

| Tecnologia | Função |
|---|---|
| XMLHttpRequest | Forma antiga de fazer requisições |
| fetch | Forma moderna de fazer requisições |
| Promises | Controlam operações assíncronas |
| async/await | Facilita o uso de Promises |

---

# Ordem de evolução

```text
XMLHttpRequest
      ↓
Promises
      ↓
fetch
      ↓
async/await
```

---

# Resumo simples

- XMLHttpRequest = antigo e complicado
- fetch = moderno e simples
- Promises = controlam operações demoradas
- async/await = deixa Promises mais fáceis de usar

---

<br><br><br>

---

# Comparação de desempenho e facilidade de uso

Todos os programas possuem o mesmo objetivo: buscar informações de um CEP usando a API ViaCEP.

A principal diferença entre eles está na forma como a requisição é feita e em como o código é organizado.

---

# XMLHttpRequest

## Facilidade de uso
- Mais difícil de entender
- Código maior e mais antigo
- Necessita configurar vários eventos manualmente
- Usa `readyState` e `status`

## Desempenho
- Bom desempenho
- Funciona corretamente
- Porém possui código mais complexo

## Vantagens
- Compatível com navegadores antigos
- Controle mais manual da requisição

## Desvantagens
- Código mais confuso
- Mais difícil de manter
- Menos organizado

### Conclusão
Funciona bem, mas atualmente é considerado ultrapassado comparado aos métodos modernos.

---

# fetch()

## Facilidade de uso
- Muito mais simples que XMLHttpRequest
- Código menor e mais limpo
- Fácil de aprender

## Desempenho
- Excelente desempenho
- Mais moderno
- Melhor organização do código

## Vantagens
- Sintaxe moderna
- Fácil leitura
- Menos linhas de código

## Desvantagens
- Requer Promises para tratar resultados

### Conclusão
É uma das formas mais utilizadas atualmente por ser simples e eficiente.

---

# Promises

## Facilidade de uso
- Organização melhor que callbacks antigos
- Permite controlar sucesso e erro da requisição

## Desempenho
- Bom desempenho
- Muito eficiente para operações assíncronas

## Vantagens
- Melhor controle do fluxo
- Facilita tratar erros com `.catch()`

## Desvantagens
- Muitos `.then()` podem deixar o código confuso

### Conclusão
Promises melhoraram bastante o JavaScript assíncrono e serviram de base para o async/await.

---

# async/await

## Facilidade de uso
- Método mais fácil de ler
- Código parece síncrono
- Melhor organização

## Desempenho
- Mesmo desempenho das Promises
- Mais confortável para desenvolvimento

## Vantagens
- Código limpo
- Fácil manutenção
- Melhor tratamento de erros usando `try/catch`

## Desvantagens
- Funciona sobre Promises, então depende delas internamente

### Conclusão
Atualmente é a forma mais moderna e recomendada para trabalhar com requisições assíncronas.

---

# Comparação geral

| Método | Facilidade | Organização | Modernidade |
|---|---|---|---|
| XMLHttpRequest | Difícil | Baixa | Antigo |
| fetch | Fácil | Boa | Moderno |
| Promises | Média | Boa | Moderno |
| async/await | Muito fácil | Excelente | Mais moderno |

---

# Resultado final

- XMLHttpRequest → mais antigo e mais complicado
- fetch → simples e moderno
- Promises → ajudam no controle assíncrono
- async/await → forma mais limpa e fácil atualmente

---

# Melhor opção atualmente

```text
async/await + fetch
```

Porque:
- deixa o código mais limpo
- facilita manutenção
- melhora leitura
- simplifica tratamento de erros
