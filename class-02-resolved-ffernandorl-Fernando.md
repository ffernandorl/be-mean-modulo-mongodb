# MongoDB - Aula 02 - Exercício
autor: Francisco Fernando

## Crie uma database chamada be-mean-pokemons

use be-mean-pokemons
switched to db be-mean-pokemons

## Liste quais databases você possui nesse servidor

pokemons → 0.078GB
test     → 0.078GB
local    → 0.078GB
be-mean  → 0.078GB
admin    → (empty)

## Insira pelo menos 5 pokemons A SUA ESCOLHA utilizando o mesmo padrão de campos utilizado: name, description, attack, defense e height

var pokemon =  [
{'name': 'Charizard', 'description': 'FODA pra kralho', 'type': 'fire', 'attack': 109, 'height': 17 },
{'name': 'Blastoise', 'description': 'bombeiro', 'type': 'water', 'attack': 85, height: 16 },
{'name': 'Arbok', 'description': 'Ai q delicia de pokemon ', 'type': 'Poison', attack: 65 , height: 3.5 },
{'name': 'Mr. Mime', 'description': 'Um palhaco muito do estranho','type': 'Psychic/Fairy', attack: 45, height: 1.3 },
{name: 'Alakazam', 'description': 'mais q genio' , 'type': 'Psychic', 'attack': 50,  'height': 15 }
]

db.be-mean-pokemons.insert(pokemon)


## Liste os pokemons existentes na sua coleção

db.pokemons.find()

{
  "_id": ObjectId("56453624f31bdbb25aa0e0d9"),
  "name": "Charizard",
  "description": "FODA pra kralho",
  "type": "fire",
  "attack": 109,
  "height": 17
}
{
  "_id": ObjectId("56453624f31bdbb25aa0e0da"),
  "name": "Blastoise",
  "description": "bombeiro",
  "type": "water",
  "attack": 85,
  "height": 16
}
{
  "_id": ObjectId("56453624f31bdbb25aa0e0db"),
  "name": "Arbok",
  "description": "Ai q delicia de pokemon ",
  "type": "Poison",
  "attack": 65,
  "height": 3.5
}
{
  "_id": ObjectId("56453624f31bdbb25aa0e0dc"),
  "name": "Mr. Mime",
  "description": "Um palhaco muito do estranho",
  "type": "Psychic/Fairy",
  "attack": 45,
  "height": 1.3
}
{
  "_id": ObjectId("56453624f31bdbb25aa0e0dd"),
  "name": "Alakazam",
  "description": "mais q genio",
  "type": "Psychic",
  "attack": 50,
  "height": 15
}
Fetched 5 record(s) in 5ms


## Busque o pokemons a sua escolha, pelo nome, e armazene-o em uma variável chamada `poke`

var query = { name: 'Alakazam' }
var poke = db.pokemons.findOne( query )
poke
{
  "_id": ObjectId("56453624f31bdbb25aa0e0dd"),
  "name": "Alakazam",
  "description": "mais q genio",
  "type": "Psychic",
  "attack": 50,
  "height": 15
}



## Modifique sua `description` e salvê-o

poke.description = "Muito mais q genio"
db.pokemons.save(poke)
Updated 1 existing record(s) in 67ms
WriteResult({
  "nMatched": 1,
  "nUpserted": 0,
  "nModified": 1
})