# Operatoren
rekenkundige operatoren: `+, -, *, /, //, %, **`
vergelijkingsoperatoren: `==, !=, <=, >=, <, >`
booleaanse operatoren: `not, and, or`

Let op: Alle getallen in het spel zijn floating point-getallen. Dus alle rekenkundige operatoren zijn floating point-operatoren.
`//` is gedefinieerd om het getal na de deling gewoon naar beneden af te ronden.

Voor toewijzingsoperatoren moet je de "Variables"-ontgrendeling hebben.

## Introductie
Operatoren stellen je in staat om waarden te vergelijken, te wijzigen en te combineren.
De rekenkundige operatoren `+, -, *, /, //, %, **` worden gebruikt om veelvoorkomende wiskundige bewerkingen op getallen uit te voeren.
De vergelijkingsoperatoren `==, !=, <=, >=, <, >` worden gebruikt om waarden te vergelijken. Het resultaat is altijd ofwel `True` of `False`.
De logische operatoren (ook wel booleaanse operatoren genoemd) `not, and, or` worden gebruikt om waarheidswaarden te combineren.

## Rekenkundige Operatoren
`+` en `-` worden gebruikt voor optellen en aftrekken.

`2 + 3` evalueert naar `5`
`3 - 2` evalueert naar `1`

`*`, `/` en `//` worden gebruikt voor vermenigvuldigen en delen.

`2 * 3` evalueert naar `6`
`5 / 2` evalueert naar `2.5`

`//` doet hetzelfde als `/` maar het resultaat wordt naar beneden afgerond (afgerond naar het volgende gehele getal).

`5 // 2` evalueert naar `2`

`%` is de modulo-operator, ook bekend als de rest-operator. Het deelt in wezen de twee getallen en geeft dan de rest terug. Je kunt het ook zien als het herhaaldelijk aftrekken van het rechter getal van het linker getal totdat de rest kleiner is dan het rechter getal.

`4 % 2` evalueert naar `0`
`5 % 2` evalueert naar `1`
`6 % 2` evalueert naar `0`
`2 % 6` evalueert naar `2`
`1.5 % 1` evalueert naar `0.5`

`**` is de machtsoperator.

`2**2` evalueert naar `4`
`(-5)**3` evalueert naar `-125`

## Vergelijkingsoperatoren
`==` en `!=` worden gebruikt om te controleren of twee waarden "gelijk" (`==`) of "niet gelijk" (`!=`) zijn. Ze kunnen op alle soorten waarden worden gebruikt.

`2 == 2` evalueert naar `True`
`Entities.Bush != Entities.Bush` evalueert naar `False`
`3 != 3 + 1` evalueert naar `True`

`<=, >=, <, >` kunnen alleen op getallen worden gebruikt. Ze controleren of het linker getal "kleiner of gelijk" (`<=`), "groter of gelijk" (`>=`), "kleiner" (`<`) of "groter" (`>`) is dan het rechter getal.

`1 <= 1` evalueert naar `True`
`2 >= 3` evalueert naar `False`
`-2 < -1` evalueert naar `True`
`6 > 6` evalueert naar `False`

## Logische Operatoren
`not` keert simpelweg de waarde om:

`not False` evalueert naar `True`
`not True` evalueert naar `False`

`and` evalueert alleen naar `True` als beide waarden `True` zijn.

`True and True` evalueert naar `True`
`True and False` evalueert naar `False`
`False and False` evalueert naar `False`

`or` evalueert naar `True` als ten minste één van de waarden `True` is.

`True or True` evalueert naar `True`
`True or False` evalueert naar `True`
`False or False` evalueert naar `False`