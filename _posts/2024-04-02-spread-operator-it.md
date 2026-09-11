---
layout: post
title: "Operatore Spread"
date: 2024-04-02
category: blog
lang: it
ref: spread-operator
labels:
  - Tutorial
image: /images/spread.jpg
excerpt: "Alcuni giorni fa, stavo intervistando tre diversi sviluppatori per una posizione nella nostra azienda e mi sono imbattuto in qualcosa di veramente interessante. Nessuno conosceva l'operatore spread..."
---
Alcuni giorni fa, stavo intervistando tre diversi sviluppatori per una posizione nella nostra azienda e mi sono imbattuto in qualcosa di veramente interessante. Nessuno conosceva l'operatore spread.

Così ho deciso di scrivere un piccolo articolo che mostra i superpoteri dello **Spread Operator**, che possono farti risparmiare alcune righe di codice e logica nel tuo progetto.

La definizione dello **Spread Operator** sul W3C è:

# Operatore Spread

L'operatore spread di JavaScript (`...`) ci permette di copiare rapidamente tutto o parte di un array o oggetto esistente in un altro array o oggetto.

Quindi usiamo un semplice esempio per mostrare il suo primo superpotere:

**Copiare rapidamente tutto o parte di un array esistente**.

Mettiamo il caso di avere un Array di animali e un altro che elenca nuovi Animali e vogliamo unirli insieme in uno Zoo. Possiamo usare lo **Spread Operator** per ottenerlo:

```javascript
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const zoo = [...animals, ...newAnimals];

//zoo=["lion","eagle","fox","snake","whale","frog"]
```

Un altro esempio aggiunto dalla nostra Frontend Team Leader, Lidia Secchi, è che possiamo usare l'operatore spread anche per aggiornare una singola proprietà all'interno di un Oggetto, come nel seguente esempio:

```javascript
const animal = {leg:4, tail:1, fur:'short'};

const newAnimal = {...animal, fur:'long' };

console.log(newAnimal);
// {leg:4, tail:1, fur:'long'}
```

Il secondo superpotere che usiamo molto è la **destrutturazione** (destructuring).

Secondo i MDN Docs:

La sintassi di assegnazione tramite **destrutturazione** è un'espressione JavaScript che rende possibile estrarre valori da array o proprietà da oggetti in variabili distinte.

Quindi mettiamo il caso di avere questo Oggetto chiamato person e di usare solo 2 valori da esso, Name e Age. Abbiamo diversi modi per farlo, ma guarda com'è semplice e pulito usando la destrutturazione:

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

La stessa cosa funziona anche con gli array, ma invece di usare la chiave possiamo usare l'indice:

```javascript
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const [animal1, animal2] = newAnimals

console.log(animal1,animal2);

// "snake", "whale"
```

Questa è la **base** dello **Spread Operator**. Passiamo a qualcosa di un po' più **avanzato**, usando lo stesso esempio di prima, ma mettiamo il caso che per qualche motivo vogliamo rinominare le chiavi **Name** e **Age** in **personName** e **personAge**. Possiamo ottenerlo usando la destrutturazione e assegnando il nuovo nome:

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

Un altro uso più avanzato è selezionare l'indice specifico da un Array. Usando l'array degli animali, stampiamo in console solo il 3° animale. Usando virgole vuote possiamo saltare gli indici e prendere solo il terzo:

```javascript
const animals = ["lion","eagle","fox"];

const [,,thirdAnimal] = animals;

console.log(thirdAnimal)
// "fox"
```

Sembra strano ma è un uso comune in RXJS combineLatest quando devi usare solo un Observable come risposta.

L'ultimo ma non meno importante superpotere di cui parleremo è il **...rest**. Possiamo usarlo per recuperare il resto di un Array, segui l'esempio:

Qui prenderemo il primo libro e poi creiamo un array con il resto di essi:

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

Uff, ok… Ci sono molti modi per usare lo **Spread Operator**, ti farà risparmiare tempo e righe per avere un codice più pulito.

E tu, come lo usi?
