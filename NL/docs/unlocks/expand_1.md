# Uitbreiden 1
<unlock=for>Zie ook [Expand_2](docs/unlocks/expand_2.md)

</unlock>Je boerderij is gegroeid! Deze ruimte is niet erg nuttig als je de drone niet kunt bewegen, dus er is een nieuwe functie `move()` die de drone verplaatst. `move()` vereist dat je de richting opgeeft waarin je de drone wilt bewegen. Hiervoor zijn vier nieuwe constanten: `North, East, South, West`.

Bijvoorbeeld, `move(North)` zal de drone een vakje naar het noorden verplaatsen.

Als je over de rand van de boerderij beweegt, wordt de drone naar de andere kant van de boerderij verplaatst.
De volgende voorbeeldcode zal de drone naar het noorden blijven bewegen en terugkeren naar het begin wanneer hij de rand van de boerderij bereikt:

`while True:
	move(North)`