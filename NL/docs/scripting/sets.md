# Sets
Sets zijn zoals [dictionaries](docs/scripting/dicts.md), maar dan zonder waarden. Ze zijn gewoon een ongeordende verzameling van sleutels.

Ze worden aangemaakt zoals dictionaries, maar zonder waarden.
`set = {North, East, West}`

Gebruik `set()` om een lege set te maken. Let op: `{}` maakt een lege dictionary aan.

Gebruik `set.add(elem)` om een nieuw element aan de set toe te voegen.

Gebruik `set.remove(elem)` om een element uit een set te verwijderen.

Gebruik `if elem in set:` om te controleren of de set een element bevat.

Gebruik `for elem in set:` om over alle elementen in de set te itereren.
Voor grotere sets presteert de `in`-operator veel sneller dan bij een lijst.

Net als dictionaries zijn sets ongeordend, dus er zijn geen garanties over de volgorde waarin de elementen worden geïtereerd.

Ook zijn elementen in sets uniek, dus het toevoegen van een element dat al in de set zit, zal de set niet veranderen.