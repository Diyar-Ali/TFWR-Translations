# Uitbreiden 2
Je boerderij is weer uitgebreid!  Nu liggen de tegels niet meer in een nette rij, dus je moet een manier vinden om een vierkant raster te doorkruisen.

Met de `while` loop is dit niet mogelijk totdat je zintuigen en operatoren ontgrendelt.
Het is tijd om de `for` loop te introduceren.

Je kunt alles over de `for` loop lezen op de [For Loop](docs/scripting/for.md) pagina, maar voor nu heb je het alleen nodig om code een vast aantal keren te herhalen.

`#doe n flips
for i in range(5):
	do_a_flip()`

`range(n)` creëert een reeks getallen van `0` tot `n-1`, die `n` elementen bevat. De `for` loop voert zijn lus-body eenmaal uit voor elk element in de reeks. In dit voorbeeld wordt `do_a_flip()` `5` keer aangeroepen.

De functie `get_world_size()` is nu ook beschikbaar. Het geeft de zijlengte van je boerderij terug. Op deze manier kun je code schrijven die niet breekt bij de volgende uitbreidingsupgrade.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Dit voorbeeld oogst één kolom van de boerderij voor elke boerderijgrootte.

Als je vastzit met het uitzoeken hoe je de drone over de boerderij moet bewegen, zie dan de hint hieronder.
<spoiler=show hint>Er zijn natuurlijk verschillende manieren om over de boerderij te bewegen.
Wat we zoeken is een manier om het op een systematische manier te doorkruisen die niet breekt wanneer de boerderij weer groeit.
Een systematische manier om elke plek op de boerderij te bereiken, zou zijn om de volgende 2 stappen voor altijd te herhalen:

1.Beweeg `Noord` totdat het terugkeert.
2.Beweeg `Oost`.

`for i in range(get_world_size()):` kan nuttig zijn om dit idee in code om te zetten.
</spoiler>
<spoiler=show possible solution> De basismanier van doorkruisen zou er zo uit kunnen zien:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#doe een flip op elke tegel
		do_a_flip()
		move(North)
	move(East)`
</spoiler>