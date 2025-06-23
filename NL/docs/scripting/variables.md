# Variabelen
Variabelen kunnen worden gezien als benoemde containers die een waarde kunnen bevatten.
De `=` operator wordt gebruikt om een variabele te declareren en er een waarde in op te slaan.

`variable_name = value`

De linkerkant van de operator is de naam van de variabele. Je kunt het elke naam geven die je wilt.
De rechterkant is een expressie waarvan de resulterende waarde in de variabele wordt opgeslagen.

Declareer een variabele genaamd `a` en sla de waarde `5` erin op:
`a = 5`
Declareer een variabele genaamd `b` en sla de return-waarde van `can_harvest()` erin op:
`b = can_harvest()`

Verwar de `=` operator niet met de `==` operator.
De `==` operator controleert of twee waarden gelijk zijn en geeft `True` of `False` terug.
De `=` operator wijst de waarde aan de rechterkant toe aan de naam aan de linkerkant.

Nadat een variabele is toegewezen, kun je deze in de code gebruiken om de waarde die het bevat op te halen.

`a = 5
for i in range(a):
	do_a_flip()`

De bovenstaande loop wordt 5 keer uitgevoerd omdat `a` is ingesteld op `5`.
De `i` in de `for` loop is ook een variabele die automatisch de huidige waarde van de reeks toegewezen krijgt bij elke iteratie van de loop. (Het hoeft niet `i` te heten, je kunt het elke geldige variabelenaam geven.)

Variabelen laten je ook hetzelfde doen met een while loop:

`a = 5
i = 0
while i < a:
	do_a_flip()
	i = i + 1`

Dit doet hetzelfde als de for loop hierboven. We moeten i alleen handmatig verhogen.
Let op: om i te verhogen, stellen we het in op zijn eigen waarde plus `1`. Het veranderen van de waarde van een variabele op basis van zijn vorige waarde komt zeer vaak voor.
Het kan worden afgekort met deze operatoren: `+=, -=, *=, /=, %=`

`i = i + 1` is hetzelfde als `i += 1`
`a = a / 3` is hetzelfde als `a /= 3`