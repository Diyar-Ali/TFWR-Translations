# Dictionaries
Dictionaries zijn een datastructuur waarmee je sleutels (keys) aan waarden (values) kunt koppelen, op dezelfde manier waarop een echt woordenboek woorden aan hun definities koppelt, en je kunt ze heel snel opzoeken.

Een dictionary kan als volgt worden aangemaakt:
`rotation = {North:East, East:South, South:West, West:North}`

De expressie vóór de dubbele punt is de sleutel en de expressie na de dubbele punt is de waarde waaraan de sleutel wordt gekoppeld.
De bovenstaande dictionary koppelt elke richting aan de richting rechts ervan.

Hier is er nog een die de positie van de drone koppelt aan de entiteit die eronder is.
`x, y = get_pos_x(), get_pos_y()
entity_dict = {(x,y):get_entity_type()}`

Toegang krijgen tot de waarde die aan een sleutel is gekoppeld, is vergelijkbaar met toegang krijgen tot een element in een lijst:
`value = dict[key]`

Voorbeeld:
`orientation = rotation[South]`
Dit stelt `orientation` in op `West`.

Je kunt een nieuw sleutel-waarde-paar als volgt aan een dictionary toevoegen:
`dict[key] = value`

Voorbeeld:
`entity_dict[(get_pos_x(), get_pos_y())] = get_entity_type()`
Dit werkt de entiteit bij die is opgeslagen voor de huidige positie.

Sleutels zijn uniek, dus het toevoegen van een sleutel die al in de dictionary bestaat, zal de vorige waarde overschrijven.

Gebruik `dict.pop(key)` om een sleutel-waarde-paar uit `dict` te verwijderen.

`key in dict` evalueert naar `True` als `key` een sleutel in de `dict` is en anders `False`.
Dus je kunt `if key in dict:` gebruiken om te controleren of `dict` de sleutel bevat.

Een dictionary in een for-lus plaatsen stelt je in staat om door alle sleutels te itereren:
`for key in dict:
	value = dict[key]`

Er zijn geen garanties over de volgorde waarin de sleutels worden geïtereerd.

Zie ook [Sets](docs/scripting/sets.md)