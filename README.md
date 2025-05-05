# Criação de funções em JavaScript - Atividade
## 📌 Function Declaration
A declaração de função define uma função com parâmetros específicos utilizando a palavra-chave `function`. Uma função criada com uma declaração define a variável e faz com que ela referencie a função em questão, as declarações de função não fazem parte do fluxo normal de controle.

### Sintaxe
```Js
function functionName(parameter1, parameter2, ...) {
  return value; 
}
```

### Vantagens
- Apresenta uma sintaxe simples e direta, o que facilita a leitura e manutenção do código
- Pode ser chamada antes de ser definida, devido ao hoisting

### Desvantagens
- Não podem ser atribuídas a variáveis
- Menos flexível em alguns contextos 
  
### Exemplos usando _function declaration_
```Js
function soma(a, b){
  return a+b; 
}
```

```Js
function saudacao(nome){
  return 'Olá, {nome}!'; 
}
```

```Js
function dobro(n){
  return n*2; 
}
```

## 📌 Function Expression
Define uma função dentro de uma expressão, possui uma sintaxe semelhante a uma declaração. A principal diferença entre as duas está no nome da função, que na _function expression_ pode ser omitido para criar funções anônimas. Expressões de função não podem ser chamadas antes de serem definidas. 

### Sintaxe
```Js
function (parameter){
  statements
}
```

### Vantagens
- Permite criar funções anônimas
- Podem ser atribuídas a variáveis, o que as torna mais flexíveis em alguns casos

### Desvantagens
- Ela só é visível a partir do ponto em que é definida, ou seja, não sofre hoisting
- Pode ser menos legível do que a _function declaration_

### Exemplos usando _function expression_
```Js
const soma = function(a, b){
  return a+b;
}
```

```Js
const saudacao = function(nome){
  return 'Olá, {nome}!';
}
```

```Js
const dobro = function(n){
  return n*2;
}
```

## 📌 Function Arrow
No lugar de uma palavra-chave `function`, esse tipo usa uma seta (=>) para criar uma função. Não é necessário declarar o retorno pois a última expressão realizada será o retorno.

### Sintaxe
```Js
(param1, param2, …, paramN) => { statements }
// equivalente a: => { return expression; }

// Parênteses são opcionais quando só há um nome de parâmetro:
(singleParam) => { statements }
singleParam => { statements }

// A lista de parâmetros para uma função sem parâmetros deve ser escrita com um par de parênteses.
() => { statements }

// Envolva o corpo da função em parênteses para retornar uma expressão literal de objeto:
params => ({foo: bar})

// Parâmetros rest (rest parameters) e parâmetros padrões (default parameters) são suportados
(param1, param2, ...rest) => { statements }
(param1 = defaultValue1, param2, …, paramN = defaultValueN) => { statements }

// Desestruturação (destructuring) dentro da lista de parâmetros também é suportado
var f = ([a, b] = [1, 2], {x: c} = {x: a + b}) => a + b + c;
f(); // 6
```

### Vantagens
- Sintaxe mais curta e simples
- Herança automática do contexto de `this`, o que pode melhorar a legibilidade do código
- São mais simples e fáceis de ler em alguns contextos

### Desvantagens
- Não podem ser usadas para criar objetos, pois não possui [[construct]]
- Não tem acesso ao objeto `arguments`
- Não pode ser referenciada dentro de si mesma, o que limita a recursividade
- Não é possível ultilizá-la como construtora (constructor)

### Exemplos usando _function arrow_
```Js
const soma = (a, b) => a+b;
```

```Js
const saudacao = nome => 'Olá, {nome}!';
```

```Js
const dobro = (n) => n*2
```
