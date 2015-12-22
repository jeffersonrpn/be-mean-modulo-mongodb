# MongoDB - Aula 04 - Exercício
Autor: Jefferson Neves

## 1. Adicionar 2 ataques ao mesmo tempo para os seguintes pokemons: Pikachu, Squirtle, Bulbasaur e Charmander

```
> var query = { $or: [ {name: /pikachu/i}, {name: /squirtle/i}, {name: /bulbasaur/i}, {name: /charmander/i} ]}
> var moves = ['Leer', 'Growl']
> var mod = {$pushAll: {moves: moves}}
> var options = {multi: true}
> db.pokemons.update(query, mod, options)
Updated 4 existing record(s) in 1ms
```

## 2. Adicionar 1 movimento em todos os pokemons: **Tackle**.

```
> var query = {}
> var mod = {$push: {moves: "Tackle"}}
> var options = {multi: true}
> db.pokemons.update(query, mod, options)
Updated 6 existing record(s) in 16ms
```

## 3. Adicionar o pokemon **Unknown** caso ele não exista com todos os dados com o valor null e a descrição: "No data"

```
> var query = {name: "Unknown"}
> var mod = { $setOnInsert: {name: "Unknown", attack: null, defense: null, height: null, type: null, moves: [], description: "No data"
}}
> var options = { upsert: true }
Updated 1 new record(s) in 1ms
```

## 4. Pesquisar todos o pokemons que possuam o ataque **Tackle** e mais um que você adicionou

```

```

## 5. Pesquisar todos os pokemons que **não são** do tipo **eletric**

```

```

## 6. Pesquisar todos os pokemons que tenham o ataque **Tackle** **E** tenham a defesa **não menor ou igual** a **49**

```

```

## 7. Remova todos os pokemons do tipo **water** e com ataque **menor que** 50

```

```
