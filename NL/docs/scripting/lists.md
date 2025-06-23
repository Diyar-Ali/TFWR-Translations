# Lists
Lists zijn een makkelijke manier om meerdere waarden in één variabele op te slaan.
Je kunt nieuwe Lists als volgt aanmaken:

`list = [2, True, Items.Hay]`

De lijst bevat nu de waarden `2`, `True` en `Items.Hay`.
Een lijst kan ook leeg zijn:

`empty_list = []`

Je kunt een element van een lijst benaderen via zijn index. De index is `0` voor het eerste element, `1` voor het tweede, `2` voor het derde...

plant wortels
`list = [Entities.Tree, Entities.Carrot, Entities.Pumpkin]
plant(list[1])`

Je kunt over een lijst itereren met een for-lus. Het volgende voorbeeld telt alle elementen in de lijst op.

`list = [4, 7, 2, 5]
sum = 0
for number in list:
	sum += number`
`sum` is nu `18`

De volgende lijstmethoden stellen je in staat om elementen toe te voegen en te verwijderen:

`list.append(elem)` voegt een element toe aan het einde van de lijst:

`list = [2, 6, 12]
list.append(7)`
`list` is nu `[2, 6, 12, 7]`

`list.remove(elem)` verwijdert het eerste voorkomen van een element uit een lijst:

`list = [1, 2, 4, 2]
list.remove(2)`
`list` is nu `[1, 4, 2]`

`list.insert(index, elem)` voegt een element in op de gegeven index:

`list = [Entities.Tree, Items.Hay]
list.insert(1, Items.Wood)`
`list` is nu `[Entities.Tree, Items.Wood, Items.Hay]`

`list.pop(index)` verwijdert het element op de opgegeven index.
Als er geen index is opgegeven, wordt het laatste item verwijderd.

`list = [3, 5, 8, 25]
list.pop()`
`list` is nu `[3, 5, 8]`
`list.pop(1)`
`list` is nu `[3, 8]`

De `len()`-functie geeft de lengte van de lijst terug.
`list = [3, 2, 1]
x = len(list)`
`x` is nu `3`

Lists hebben 'reference semantics'. Dit betekent dat het toewijzen van een lijst aan een variabele hetzelfde lijstobject aan die variabele toewijst, in plaats van een kopie van de lijst te maken.
Als twee variabelen naar dezelfde lijst verwijzen, zullen wijzigingen in de lijst door beide worden gezien.

`a = [1,2]
b = a
b.pop()`
`a` en `b` zijn nu beide `[1]`