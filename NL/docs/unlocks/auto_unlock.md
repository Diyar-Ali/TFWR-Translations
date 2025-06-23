# Automatisch Ontgrendelen
Om het spel volledig te automatiseren, kun je de `unlock()`-functie gebruiken om functies automatisch te ontgrendelen.
Je kunt bijvoorbeeld `unlock(Unlocks.Speed)` en `unlock(Unlocks.Expand)` gebruiken om de snelheids- en uitbreidingsfuncties te ontgrendelen.

Om de kosten van een ontgrendeling te bepalen, gebruik je simpelweg de `get_cost()`-functie zoals je zou doen voor een plant of item.
Voorbeeld:
`get_cost(Unlocks.Loops)`
geeft `{Items.Hay:5}` terug 

Als je wilt weten hoeveel je van een bepaalde ontgrendeling hebt, gebruik dan de `num_unlocked(unlock)`-functie.

Bijvoorbeeld, `num_unlocked(Unlocks.Speed)` geeft het aantal snelheidsupgrades terug dat je hebt.

`num_unlocked(Unlocks.Senses)` geeft `1` terug als zintuigen zijn ontgrendeld en `0` als dat niet zo is.

Je kunt `num_unlocked()` ook gebruiken op Items, Entiteiten of Grondsoorten. Dit geeft `1` terug als het is ontgrendeld, anders `0`.

Wees voorzichtig, `num_unlocked(Unlocks.Carrots)` geeft het aantal keren terug dat het is ontgrendeld/geüpgraded.
`num_unlocked(Items.Carrot)` geeft alleen `0` of `1` terug. (Hetzelfde geldt voor andere planten)