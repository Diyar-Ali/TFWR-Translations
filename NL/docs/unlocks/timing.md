# Timing
Als je je methoden echt wilt optimaliseren, moet je begrijpen hoe tijd in dit spel wordt gemeten. Deze ontgrendeling draait daar volledig om.

## Nieuwe Functies
Er zijn twee nuttige functies om te meten hoe lang dingen duren:

`get_time()` geeft de tijd in seconden terug sinds het begin van het spel.

`get_tick_count()` geeft het aantal ticks terug dat is uitgevoerd sinds het begin van de uitvoering.

Deze twee functies, evenals `quick_print()`, zijn volledig gratis. Zelfs de aanroepoperatie is gratis voor hen.

## Runtime-details

### Let op
Dit is niet hoe prestaties in de echte wereld werken. Dit zijn slechts regels die voor dit spel zijn bedacht om een consistent en begrijpelijk timingmodel te hebben.
Je zult hier waarschijnlijk alleen om geven als je je code wilt hyper-optimaliseren.

De basiseenheid van tijd voor code-uitvoering wordt een "tick" genoemd. Zonder snelheidsupgrades en energie verloopt de uitvoering met een snelheid van `400` ticks per seconde.

Over het algemeen duren operaties die twee waarden combineren, zoals `+, -, *, /, //, %, and, or, ...`, één tick om uit te voeren.
Enkele-waarde `-` en `not` zijn gratis.
Een `if`-branch duurt ook één tick om uit te voeren (naast de tijd die nodig is om de voorwaarde-expressie te evalueren).
Functieaanroepen en het lezen en schrijven van variabelen zijn gratis, maar functiedefinities duren 1 tick.
`import`-statements zijn gratis.
Toegang krijgen tot een geïmporteerde module met de `.`-operator is gratis.
Als een functie of module is doorgegeven via argumenten of variabeletoewijzingen, zal het gebruik ervan 1 tick kosten in plaats van 0.
`for`- en `while`-loops duren één tick om te starten, maar de iteraties zijn gratis (de tijd om de voorwaarde/reeks-expressies te evalueren niet meegerekend).
`return`, `break` en `continue` zijn allemaal gratis.
`pass` duurt één tick, zodat het kan worden gebruikt om precieze vertragingen te creëren.
Indexeren in een datastructuur duurt één tick voor de indexoperator en, in het geval van een dictionary of set, extra ticks afhankelijk van de grootte van de sleutel.

Het aantal ticks dat ingebouwde functies nodig hebben om uit te voeren, wordt per functie gedocumenteerd in de documentatie van elke functie.