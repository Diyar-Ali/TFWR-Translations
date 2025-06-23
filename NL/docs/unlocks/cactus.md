# Cactus
Net als andere planten kunnen [cactussen](objects/cactus) op aarde worden gekweekt en zoals gewoonlijk worden geoogst.

Ze komen echter in verschillende maten en hebben een vreemd gevoel voor orde.

Als je een volgroeide cactus oogst en alle naburige cactussen zijn in gesorteerde volgorde, zal het ook alle naburige cactussen recursief oogsten.

Een cactus wordt als in gesorteerde volgorde beschouwd als alle naburige cactussen in het `Noorden` en `Oosten` volgroeid zijn en groter of gelijk in grootte zijn en alle naburige cactussen in het `Zuiden` en `Westen` volgroeid zijn en kleiner of gelijk in grootte zijn.

De oogst zal zich alleen verspreiden als alle aangrenzende cactussen volgroeid zijn en in gesorteerde volgorde staan.
Dit betekent dat als een vierkant van gegroeide cactussen op grootte is gesorteerd en je oogst één cactus, het het hele vierkant zal oogsten.

Je ontvangt cactus gelijk aan het aantal geoogste cactussen in het kwadraat. Dus als je `n` cactussen tegelijk oogst, ontvang je `n**2` `Items.Cactus`.

De grootte van een cactus kan worden gemeten met `measure()`.
Het is altijd een van deze getallen: `0,1,2,3,4,5,6,7,8,9`.

Je kunt ook een richting doorgeven aan `measure(direction)` om de naburige tegel in die richting van de drone te meten.

Je kunt een cactus met zijn buur in elke richting verwisselen met het `swap()`-commando.
`swap(direction)` verwisselt het object onder de drone met het object één tegel in de `direction` van de drone.

## Voorbeelden
In elk van deze rasters zijn alle cactussen in gesorteerde volgorde en zal de oogst zich over het hele veld verspreiden:
`3 4 5 3 3 3 1 2 3 1 5 9
2 3 4 2 2 2 1 2 3 1 3 8
1 2 3 1 1 1 1 2 3 1 3 4`

In dit raster is alleen de cactus linksonder in gesorteerde volgorde, wat niet genoeg is om zich te verspreiden:
`1 5 3
4 9 7
3 3 2`

<spoiler=show hint 1>
Als elke kolom en elke rij van het veld gesorteerd is, dan is het hele veld gesorteerd.
</spoiler>
<spoiler=show hint 2>
Als je niet bekend bent met sorteeralgoritmen, wil je ze misschien online opzoeken en nadenken over welke kunnen worden aangepast aan dit probleem.
</spoiler>