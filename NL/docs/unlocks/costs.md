# Kosten
Elke kost kan worden weergegeven als een dictionary die items aan getallen koppelt.

De `get_cost()`-functie geeft zo'n dictionary terug. Het geeft de kosten van een plant of een ontgrendeling terug.

`get_cost(Entities.Pumpkin)`
geeft `{Items.Carrot:1}` terug 

Voor ontgrendelingen kan een optioneel tweede argument worden meegegeven voor het ontgrendelingsniveau waarvoor je de kosten wilt opvragen. Standaard is dit het huidige ontgrendelingsniveau.

`get_cost(Unlocks.Loops, 0)`
geeft `{Items.Hay:5}` terug 

Voor ontgrendelingen die al op het maximale niveau zijn, geeft `get_cost()` `None` terug.

Het kan als volgt worden gebruikt:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`