# Dinosaurussen
Dinosaurussen zijn oude, majestueuze wezens die gekweekt kunnen worden voor oude botten.

Helaas zijn dinosaurussen al lang geleden uitgestorven, dus het beste wat we nu kunnen doen, is ons als een dinosaurus verkleden.
Voor dit doel heb je de nieuwe dinosaurushoed ontvangen.

De hoed kan worden uitgerust met
`change_hat(Hats.Dinosaur_Hat)`

Helaas ziet het er niet helemaal uit zoals op de advertentie... 

Als je de dinosaurushoed uitrust en genoeg pompoenen hebt, wordt er automatisch een [appel](objects/apple) gekocht en onder de drone geplaatst.
Wanneer de drone boven een appel is en opnieuw beweegt, zal hij de appel eten en zijn staart met één laten groeien. Als je het je kunt veroorloven, wordt er een nieuwe appel gekocht en op een willekeurige locatie geplaatst.
De appel kan niet spawnen als er iets anders is geplant waar hij wil zijn.

De staart van de dinosaurus wordt achter de drone aan gesleept en vult de vorige tegels waar de drone overheen bewoog. Als een drone bovenop de staart probeert te bewegen, zal `move()` mislukken en `False` teruggeven.
Het laatste segment van de staart zal tijdens de beweging uit de weg gaan, zodat je erop kunt bewegen. Echter, als de slang de hele boerderij vult, kun je niet meer bewegen. Je kunt dus controleren of de slang volgroeid is door te controleren of je niet meer kunt bewegen.

Het gebruik van `measure()` op een appel geeft de positie van de volgende appel terug als een tuple.

`next_x, next_y = measure()`

Wanneer de hoed weer wordt afgezet door een andere hoed uit te rusten, wordt de staart geoogst.
Je ontvangt botten gelijk aan de staartlengte in het kwadraat. Dus voor een staart van lengte `n` ontvang je `n**2` `Items.Bone`.
Bijvoorbeeld:
lengte 1 => 1 bot 
lengte 2 => 4 botten 
lengte 3 => 9 botten 
lengte 4 => 16 botten 
lengte 16 => 256 botten 
lengte 100 => 10000 botten 

De Dinosaurushoed is erg zwaar, dus als je hem uitrust, duurt `move()` 800 ticks in plaats van 200. Echter, elke keer dat je een appel oppakt, wordt het aantal ticks dat `move()` gebruikt met 3% verminderd (naar beneden afgerond), omdat een langere staart je kan helpen bewegen.

De volgende loop print het aantal ticks dat `move()` gebruikt na een willekeurig aantal appels:

`ticks = 800
for i in range(100):
    print("ticks after ", i, " apples: ", ticks)
    ticks -= ticks * 0.03 // 1`

<spoiler=show hint 1>Als je langs hetzelfde pad blijft bewegen dat het hele veld beslaat, kun je gemakkelijk een slang krijgen die elke keer het hele veld bedekt, omdat je elke vrije plek bedekt voordat je terugkomt waar je staart is. Het is niet erg efficiënt, maar het werkt.
Velden met een oneven grootte kunnen moeilijker zijn. Als je `Unlocks.Debug2` hebt ontgrendeld, kun je de grootte van het veld veranderen in iets handigers.</spoiler>