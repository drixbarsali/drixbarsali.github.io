---
layout: post
title: "Operador Spread"
date: 2024-04-02
category: blog
lang: pt-br
ref: spread-operator
labels:
  - Tutorial
image: /images/spread.jpg
excerpt: "Alguns dias atrás, eu estava entrevistando três desenvolvedores para uma vaga em nossa empresa e me deparei com algo realmente interessante. Ninguém conhecia o operador spread..."
---
Alguns dias atrás, eu estava entrevistando três desenvolvedores diferentes para uma posição em nossa empresa e me deparei com algo realmente interessante. Ninguém conhecia o operador spread.

Por isso decidi escrever um pequeno artigo mostrando os superpoderes do **Spread Operator**, que podem economizar algumas linhas de código e lógica no seu projeto.

A definição do **Spread Operator** no W3C é:

# Operador Spread

O operador spread do JavaScript (`...`) nos permite copiar rapidamente todo ou parte de um array ou objeto existente para outro array ou objeto.

Então vamos usar um exemplo simples para mostrar o seu primeiro superpoder:

**Copiar rapidamente todo ou parte de um array existente**.

Digamos que temos um Array de animais e outro listando novos Animais e queremos juntá-los em um Zoo. Podemos usar o **Spread Operator** para alcançar isso:

```javascript
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const zoo = [...animals, ...newAnimals];

//zoo=["lion","eagle","fox","snake","whale","frog"]
```

Outro exemplo que foi adicionado pela nossa Líder de Equipe Frontend, Lidia Secchi, é que também podemos usar o operador spread para atualizar uma única propriedade dentro de um Objeto, conforme o seguinte exemplo:

```javascript
const animal = {leg:4, tail:1, fur:'short'};

const newAnimal = {...animal, fur:'long' };

console.log(newAnimal);
// {leg:4, tail:1, fur:'long'}
```

O segundo superpoder que usamos muito é a **desestruturação** (destructuring).

Segundo a documentação do MDN:

A sintaxe de atribuição via **desestruturação** é uma expressão JavaScript que possibilita desembalar valores de arrays, ou propriedades de objetos, em variáveis distintas.

Então digamos que temos este Objeto chamado person e usaremos apenas 2 valores dele, Name e Age. Temos diferentes formas de fazer isso, mas veja como fica simples e limpo usando a desestruturação:

```javascript
const person = {
  name: "Jon Doe",
  age: 30,
  height: 180,
  weight: 80
};

const {name, age} = person;

console.log(name,age);

// "Jon Doe", 30
```

A mesma coisa funciona também com arrays, mas em vez de usar a chave podemos usar o índice:

```javascript
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const [animal1, animal2] = newAnimals

console.log(animal1,animal2);

// "snake", "whale"
```

Esta é a **base** do **Spread Operator**. Vamos avançar para algo um pouco mais **avançado**, usando o mesmo exemplo anterior, mas digamos que por algum motivo queremos renomear as chaves **Name** e **Age** para **personName** e **personAge**. Podemos alcançar isso usando desestruturação e atribuindo seu novo nome:

```javascript
const person = {
  name: "Jon Doe",
  age: 30,
  height: 180,
  weight: 80
};

const {name:personName, age:personAge} = person;

console.log(personName,personAge);

// "Jon Doe", 30
```

Outro uso mais avançado é selecionar um índice específico de um Array. Usando o array de animais, vamos exibir apenas o 3º animal. Usando vírgulas vazias, podemos pular os índices e capturar apenas o terceiro:

```javascript
const animals = ["lion","eagle","fox"];

const [,,thirdAnimal] = animals;

console.log(thirdAnimal)
// "fox"
```

Parece estranho, mas é um uso comum no combineLatest do RXJS quando você precisa usar apenas um Observable como resposta.

O último superpoder, mas não menos importante, do qual falaremos é o **...rest**. Podemos usá-lo para recuperar o restante de um Array, siga o exemplo:

Aqui vamos pegar o primeiro livro e depois criar um array com o restante deles:

```javascript
const books = [
  "To Kill a Mockingbird",
  "1984",
  "Pride and Prejudice",
  "The Great Gatsby" ];

const [book1,...rest] = books

console.log(book1,rest);

//"To Kill a Mockingbird", ["1984", "Pride and Prejudice", "The Great Gatsby"]
```

Ufa, ok… Existem muitas maneiras de usar o **Spread Operator**. Ele economizará tempo e linhas para ter um código mais limpo.

E você, como o utiliza?
