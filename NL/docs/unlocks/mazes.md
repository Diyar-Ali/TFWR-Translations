# Doolhoven
`Items.Weird_Substance`, dat wordt verkregen door planten te [bemesten](docs/unlocks/fertilizer.md), heeft een vreemd effect op struiken. Als de drone boven een struik is en je roept `use_item(Items.Weird_Substance, amount)` aan, zal de struik uitgroeien tot een doolhof van heggen.
De grootte van de doolhof hangt af van de hoeveelheid `Items.Weird_Substance` die wordt gebruikt (het tweede argument van de `use_item()`-aanroep).
Zonder doolhof-upgrades resulteert het gebruik van `n` `Items.Weird_Substance` in een `n`x`n` doolhof. Voor elk doolhof-upgradeniveau moet je een extra `n` `Items.Weird_Substance` gebruiken om hetzelfde effect te krijgen.
Dus om een doolhof ter grootte van het volledige veld te maken:

`plant(Entities.Bush)
n_substance = get_world_size() * num_unlocked(Unlocks.Mazes)
use_item(Items.Weird_Substance, n_substance)`

Om de een of andere reden kan de drone niet over de heggen vliegen, ook al zien ze er niet zo hoog uit.

Er is een schat verborgen ergens in de heg. Gebruik `harvest()` op de schat om goud te ontvangen gelijk aan de oppervlakte van de doolhof. (Bijvoorbeeld, een 5x5 doolhof levert 25 goud op.) 

Als je `harvest()` ergens anders gebruikt, zal de doolhof simpelweg verdwijnen.

`get_entity_type()` is gelijk aan `Entities.Treasure` als de drone boven de schat is en `Entities.Hedge` overal elders in de doolhof.

Doolhoven bevatten geen lussen, tenzij je de doolhof hergebruikt (zie hieronder hoe je een doolhof hergebruikt). Er is dus geen manier voor de drone om weer op dezelfde positie te eindigen zonder terug te gaan.

Je kunt controleren of er een muur is door te proberen erdoorheen te bewegen.
`move()` geeft `True` terug als het is gelukt en anders `False`.

Als je geen idee hebt hoe je bij de schat moet komen, kijk dan naar Hint 1. Het laat zien hoe je een probleem als dit kunt benaderen.

Voor een extra uitdaging kun je de doolhof ook hergebruiken door dezelfde hoeveelheid `Items.Weird_Substance` opnieuw op de schat te gebruiken.
Dit verhoogt de hoeveelheid goud in de schat met een volledige doolhof en verplaatst het naar een willekeurige positie in de doolhof.

`measure()` gebruiken op een schat geeft de positie terug waar het naartoe zal bewegen, als een tuple.
`next_x, next_y = measure()`

Elke keer dat de schat wordt verplaatst, kan er een willekeurige muur uit de doolhof worden verwijderd. Hergebruikte doolhoven kunnen dus lussen bevatten.

Let op dat lussen in de doolhof het veel moeilijker maken omdat het betekent dat je weer op dezelfde locatie kunt komen zonder terug te bewegen.
Een doolhof hergebruiken levert niet meer goud op dan gewoon oogsten en een nieuwe doolhof spawnen.
Dit is 100% een extra uitdaging die je gewoon kunt overslaan.
Het is alleen de moeite waard als de extra informatie en de kortere wegen je helpen de doolhof sneller op te lossen.

Dezelfde doolhof kan maximaal 300 keer worden opgelost. Dit komt overeen met 299 verplaatsingen. Daarna zal het gebruik van rare substantie op de schat het goud erin niet meer verhogen en zal `measure()` `None` teruggeven.

<spoiler=show hint 1>Hier is een algemene aanpak om het probleem op te lossen:

Creëer een doolhof en stel je voor dat je de drone bent.

Denk na over hoe je de schat zou proberen te vinden als je in de doolhof was.

Schrijf je strategie stap voor stap op zodat iemand anders het zonder na te denken zou kunnen volgen.

Probeer nu je stappen in code te vertalen.
</spoiler>
<spoiler=show hint 2>Zolang er geen lussen zijn: Alle muren zijn eigenlijk één grote verbonden muur. Als je de muur volgt, leidt deze je door de hele doolhof.
Deze aanpak vereist heel weinig code en je hoeft niet bij te houden waar je al bent geweest. Ongeveer 10 regels code is alles wat je nodig hebt.</spoiler>
<spoiler=show hint 3>In plaats van de drone in absolute richtingen zoals oost of west te bewegen, kan het erg handig zijn om de drone in relatieve richtingen te bewegen zoals "draai rechts" of "draai links". Om dit te doen moet je bijhouden welke kant de drone op beweegt. De drone draait nooit echt, maar je kunt nog steeds een "virtuele" rotatie in code bijhouden.
De volgende index-truc is hier handig voor:

`directions = [North, East, South, West]
index = 0`

Gebruik `% 4` om het "in de rondte" te laten draaien, zodat het na `West` weer terugkeert naar `North`.
`# draai rechts
index = (index + 1) % 4`

`# draai links
index = (index - 1) % 4

move(directions[index])`</spoiler>
<spoiler=show hint 4>Als je het niet kunt oplossen, kun je het jezelf altijd gemakkelijk maken en het minder efficiënt doen.
Een `1`x`1` doolhof oplossen is triviaal.</spoiler>