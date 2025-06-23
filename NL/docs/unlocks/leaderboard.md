# Simulatie

Simulaties stellen je in staat om snel code te testen zonder de staat van de echte boerderij te veranderen.
De startstaat van de simulatie kan vrij worden gekozen, en wanneer de simulatie eindigt, zal de echte boerderij in exact dezelfde staat zijn als voor de simulatie begon.

De `simulate()` functie wordt gebruikt om een simulatie te starten.

het bestand waarin de uitvoering moet starten
`filename = "f1"`

begin met alles ontgrendeld en volledig geüpgraded
`sim_unlocks = Unlocks`

begin met 10000 wortels en 50 hooi
`sim_items = {Items.Carrot : 10000, Items.Hay : 50}`

begin met een globale variabele "a" met een waarde van 13
`sim_globals = {"a" : 13}`

gebruik een vaste random seed
`seed = 0`

versnel de simulatie met een factor 64
`speedup = 64`

voer de simulatie uit
`run_time = simulate(filename, sim_unlocks, sim_items, sim_globals, seed, speedup)`

De `simulate()` functie geeft de tijd, in seconden, terug die het kostte om het gegeven startbestand te simuleren.

### Bestandsnaam
Het eerste argument van de simulatiefunctie is de bestandsnaam. Dit is de naam die bovenaan het codevenster wordt weergegeven. De simulatie zal het opgegeven bestand uitvoeren alsof je op de Uitvoeren-knop ervan had geklikt.

### Startontgrendelingen
Alle programmeerfuncties zoals lussen, if-statements, lijsten, dicts,... blijven altijd ontgrendeld.

Het tweede argument stelt je in staat om te specificeren met welke ontgrendelingen/upgrades de simulatie moet beginnen naast de programmeerfuncties. Dit moet een reeks ontgrendelingen zijn. De simulatie zal beginnen met alle ontgrendelingen in de reeks geüpgraded naar hun maximale niveau.

Als je een ander upgrade-niveau wilt specificeren dan het maximum, kun je een dictionary doorgeven die de ontgrendelingen aan ontgrendelingsniveaus koppelt. In dat geval komen negatieve waarden overeen met het maximale ontgrendelingsniveau.

### Startitems
Het derde argument stelt je in staat om een dictionary door te geven die items aan getallen koppelt. Het specificeert de items waarmee de simulatie moet beginnen.

### Start-globals
Omdat de simulatie een volledig nieuwe programma-uitvoering start, kun je geen variabelen benaderen vanuit het programma dat de simulatie start.
Het is echter mogelijk om waarden aan de simulatie door te geven met het vierde argument. Dit is een dict die variabelenamen in de vorm van strings aan waarden koppelt. Deze variabelen worden dan toegevoegd aan de globale scope van de uitvoering binnen de simulatie.

Let op dat dit alle waarden kopieert, dus het muteren ervan binnen de simulatie heeft geen invloed op de originele waarden buiten de simulatie. Het is niet mogelijk om waarden uit de simulatie terug te geven, behalve de tijd die het kostte om te draaien.

### Random Seed
Het vijfde argument stelt je in staat om de random seed te specificeren die in de simulatie wordt gebruikt. Dit moet een positief geheel getal zijn. Negatieve waarden zorgen ervoor dat een willekeurige seed wordt gebruikt.

De random seed beïnvloedt alles, van plantengroeitijden tot doolhoflay-outs tot watervervaltijden. Als je dezelfde simulatie meerdere keren start met dezelfde random seed en dezelfde startomstandigheden, zou het resultaat altijd hetzelfde moeten zijn.

### Snelheid
Het zesde argument is de startsnelheid van de simulatie. Dit stelt je in staat om dingen snel te testen. Als het spel de ingestelde snelheid niet kan bijhouden, zal het automatisch vertragen.

De snelheid heeft op geen enkele manier invloed op het resultaat van de simulatie. Het bestaat alleen om de wachttijd te verminderen.