# For Loop
De `for` loop werkt zoals in Python. (In sommige talen een foreach loop genoemd, niet te verwarren met de C-stijl for loop, wat iets anders is).

`for i in sequence:
	#doe iets met i`

Net als de `while` loop, roept de `for` loop ook herhaaldelijk een blok code aan. In plaats van te lussen op basis van een voorwaarde, voert het de lus-body eenmaal uit voor elk element in een reeks.

## Syntaxis
Een for loop ziet er zo uit:

`for variable_name in sequence:
	#codeblok`

`variable_name` kan elke naam zijn die je kiest. Het is een variabele die het huidige element in de reeks opslaat. `sequence` moet een waarde zijn die kan worden geïtereerd, zoals een reeks getallen. Het codeblok wordt voor elk element uitgevoerd met de lusvariabele toegewezen aan dat element.

## Reeksen
[Ranges](functions/range)      <unlock=lists>[Lijsten](docs/scripting/lists.md)      </unlock><unlock=functions>[Tuples](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Dictionaries](docs/scripting/dicts.md)      </unlock><unlock=sets>[Sets](docs/scripting/sets.md)</unlock>

## Voorbeeld
`for i in range(5):
    harvest()`

Deze lus voert de body een vast aantal keren uit. Het is in wezen hetzelfde als schrijven

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Het roept dus `harvest()` 5 keer aan.

Zie ook [Break](docs/scripting/break.md) en [Continue](docs/scripting/continue.md)