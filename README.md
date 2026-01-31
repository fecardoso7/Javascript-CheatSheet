# JavaScript - Resumo de Estudo

Este documento é um **guia completo para estudo da linguagem JavaScript**, pensado para iniciantes e intermediários. Ele reúne as principais informações e práticas da linguagem, incluindo:

- **Características principais**: JavaScript é dinâmica, interpretada, orientada a eventos e usada tanto no front-end quanto no back-end.
- **Tipos de dados**: primitivos (String, Number, Boolean, etc.) e objetos (Array, Function, Object, etc.).
- **Variáveis e escopo**: diferenças entre `var`, `let` e `const`.
- **Operadores**: aritméticos, lógicos, de comparação e ternário.
- **Estruturas de controle**: condicionais (`if`, `switch`) e loops (`for`, `while`, `for...of`).
- **Funções**: definição tradicional, anônima e arrow function, além de funções importantes para manipulação de arrays, strings e objetos.
- **Eventos (Front-End)**: exemplos de eventos de clique e teclado.
- **Atalhos úteis** para produtividade.
- **Boas práticas** de código e organização.
- **Recursos para estudo**: links para documentação oficial e sites de referência.

O objetivo deste documento é servir como um **manual de estudo e referência rápida**, permitindo que você revise conceitos, exemplos e boas práticas da linguagem JavaScript de forma organizada e direta.

---

## 📌 Principais Características

- **Interpretada**: Não precisa de compilação; os navegadores entendem o código diretamente.
- **Baseada em protótipos**: Usa herança via objetos.
- **Orientada a eventos**: Facilita manipular ações do usuário.
- **Versátil**: Funciona no front-end (navegadores) e back-end (Node.js).
- **Assíncrona**: Permite executar código sem bloquear a aplicação (promises, async/await).

---

## 📝 Tipos de Dados

- **Primitivos**: `String`, `Number`, `Boolean`, `Undefined`, `Null`, `Symbol`, `BigInt`
- **Objetos**: `Object`, `Array`, `Function`, `Date`, etc.

Exemplo:
```javascript
let nome = "Felipe"; // String
let idade = 26;      // Number
let ativo = true;    // Boolean
let usuario = { nome: "Felipe", idade: 26 }; // Object
let cores = ["azul", "verde", "vermelho"];  // Array
```

---

## ⚡ Variáveis e Escopo


- `var`: escopo global ou de função, não recomendado atualmente.
- `let`: escopo de bloco, recomendado para variáveis mutáveis.
- `const`: escopo de bloco, usado para constantes (imutáveis).


### Exemplo simples de `var`
```javascript
function exemploLet() {
  let gato = "Mingau";
  console.log(gato); // Mingau

  if (true) {
    let gato = "Tom"; // Esse é outro gato, só dentro do if
    console.log(gato); // Tom
  }

  console.log(gato); // Mingau (continua o original)
}

exemploLet();
```

### Exemplos de `let` e `const`
```javascript
let idade = 26; // variável mutável
const nome = "Felipe"; // constante imutável
```

---

## 🔧 Operadores

- **Aritméticos**: `+ - * / % **`
- **Atribuição**: `=, +=, -=, *=, /=`
- **Comparação**: `==, ===, !=, !==, >, <, >=, <=`
- **Lógicos**: `&&, ||, !`
- **Ternário**: `condição ? valorSeVerdadeiro : valorSeFalso`

```javascript
let resultado = (idade >= 18) ? "Maior de idade" : "Menor de idade";
```

---

## 🌀 Estruturas de Controle

### Condicionais
```javascript
if(idade >= 18){
  console.log("Adulto");
} else if(idade > 12){
  console.log("Adolescente");
} else {
  console.log("Criança");
}
```

### Switch
```javascript
let dia = "terça";
switch(dia){
  case "segunda":
    console.log("Início da semana");
    break;
  case "terça":
    console.log("Segundo dia da semana");
    break;
  default:
    console.log("Outro dia");
}
```

### Loops
```javascript
// for
for(let i=0; i<5; i++){
  console.log(i);
}

// while
let i = 0;
while(i < 5){
  console.log(i);
  i++;
}

// for...of (arrays)
let cores = ["azul","verde","vermelho"];
for(let cor of cores){
  console.log(cor);
}
```

---

## 🧩 Funções

Funções permitem agrupar código reutilizável.

```javascript
// Função tradicional
function soma(a, b){
  return a + b;
}

// Função anônima
const subtrai = function(a, b){
  return a - b;
}

// Arrow function
const multiplica = (a, b) => a * b;

console.log(soma(2,3));      // 5
console.log(subtrai(5,2));   // 3
console.log(multiplica(4,2));// 8
```

### Funções Importantes do JS

- **Manipulação de arrays**
```javascript
let numeros = [1,2,3,4,5];
numeros.push(6);   // Adiciona no final
numeros.pop();     // Remove do final
numeros.shift();   // Remove do início
numeros.unshift(0);// Adiciona no início
numeros.map(n => n*2);   // Retorna novo array multiplicado
numeros.filter(n => n>2);// Filtra valores
numeros.reduce((a,b)=>a+b,0); // Soma todos os valores
```

- **Strings**
```javascript
let texto = "Olá, mundo!";
texto.length;          // Comprimento da string
texto.toUpperCase();   // MAIÚSCULO
texto.toLowerCase();   // minúsculo
texto.includes("mundo"); // true/false
texto.replace("mundo","JS"); // Substitui texto
```

- **Objetos**
```javascript
let pessoa = {nome:"Felipe", idade:26};
Object.keys(pessoa);   // ["nome","idade"]
Object.values(pessoa); // ["Felipe",26]
Object.entries(pessoa);// [["nome","Felipe"],["idade",26]]
```

---

## 📌 Eventos Comuns (Front-End)

```javascript
const btn = document.querySelector("#meuBotao");
btn.addEventListener("click", () => {
  alert("Clicou!");
});

document.addEventListener("keydown", (e) => {
  console.log("Tecla pressionada:", e.key);
});
```

---

## ⚡ Atalhos Úteis

- `Ctrl + /` → Comentar/Descomentar linha
- `Ctrl + D` → Selecionar próxima ocorrência
- `Shift + Alt + F` → Formatar código
- `console.log()` → Debug rápido
- `typeof variavel` → Saber o tipo da variável

---

## 📦 Boas Práticas

- Sempre usar `let` ou `const`.
- Nomes de variáveis claros (`idade` em vez de `i` para valores que não são loop).
- Evitar funções longas; modularize.
- Usar `===` ao invés de `==` para comparações.
- Documentar código.
- Testar código com `console.log` ou ferramentas de depuração.

---

## 🔗 Recursos

- [Documentação Oficial MDN](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
- [ECMAScript 2026 Features](https://www.ecma-international.org/)
- [Node.js](https://nodejs.org/)
- [JavaScript Info](https://javascript.info/)
