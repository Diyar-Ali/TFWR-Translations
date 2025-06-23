# While Loop
Je hebt de `while` loop en de waarden `True` en `False` ontgrendeld. De `while` loop blijft de lus-body uitvoeren zolang de voorwaarde `True` is.

`while condition:
	#loop body`

Maak je geen zorgen over het creëren van oneindige lussen. De vertragingen in de uitvoering voorkomen dat het programma vastloopt.

## Voor Beginners
Misschien heb je al geprobeerd om meerdere `harvest()`-aanroepen achter elkaar te plaatsen:

`harvest()
harvest()
harvest()`

Dit stelt je in staat om meerdere keren te oogsten in één programmarun.
Het zou echter fijn zijn om meer dan drie keer te oogsten, en het meerdere keren schrijven van dezelfde code is een slechte gewoonte.
De oplossing is een loop.
Een loop stelt je in staat om dezelfde code meerdere keren uit te voeren.

De while loop gebruikt een voorwaarde, wat een logische waarde is die zich slechts in een van de twee staten kan bevinden: `True` of `False`.
Een dergelijke waarde wordt een Booleaanse waarde genoemd.

De loop voert vervolgens de code binnenin de loop uit totdat de voorwaarde False is.
De while loop ziet er zo uit:

`while condition:
	#loop body
	#loop body
	#...`
	
Waarbij je "condition" moet vervangen door een booleaanse waarde en `#loop body` door wat je ook wilt doen in de loop.

Er zijn twee constante booleaanse waarden beschikbaar. Constanten zijn waarden die nooit veranderen tijdens het programma.

Om een constante booleaanse waarde te creëren die altijd `True` is, kun je simpelweg `True` schrijven. Schrijf `False` voor een constante booleaanse waarde die altijd `False` zal zijn.
Dus je zou ofwel kunnen schrijven

`while False:
	do_a_flip()`

of

`while True:
	do_a_flip()`

De eerste zal nooit een flip doen en de tweede zal voor altijd flips blijven doen (een oneindige lus).

Normaal gesproken is het creëren van een oneindige lus een slecht idee omdat het programma dan vastloopt, but in this game there are delays between each iteration of the loop, so it will cause the drone to keep doing a flip until you manually stop it by pressing the execute button again.

Merk op hoe de regel na de dubbele punt is ingesprongen. Inspringen zoals dit wordt gebruikt om blokken code te scheiden.
Druk gewoon op Tab om inspringing toe te voegen en Shift + Tab (of Backspace) om het te verwijderen.

De loop zal alle ingesprongen statements na de dubbele punt herhalen.
Statements na het ingesprongen blok zullen worden uitgevoerd nadat de loop is voltooid.