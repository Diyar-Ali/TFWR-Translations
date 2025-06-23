# Name Scopes
Scopes bepalen welke variabelen van waaruit toegankelijk zijn. Een scope is in feite een koppeling van namen aan waarden.
Ze werken in principe hetzelfde als in Python.

Er is een globale scope, en elke functie heeft een lokale scope.
Wanneer je een variabele definieert, wordt deze toegevoegd aan de huidige scope.
Alles buiten een functiedefinitie wordt beschouwd als onderdeel van de globale scope.

`x = 1`
Wijst een waarde van `1` toe aan de naam `x` in de globale scope.

Deze `def`-statement wijst een functie toe aan de naam `f` in de globale scope.
`def f():
    `Wijs een waarde van `1` toe aan de naam `y` in de lokale scope van `f`.`
    y = 1

    `Wijs een functie toe aan de naam `g` in de lokale scope van `f`.`
    def g():
        pass`

`f()`
Haalt de functie op die is opgeslagen in `f` uit de globale scope en roept deze aan.

`print(y)`
Deze print-statement in de globale scope veroorzaakt een fout omdat `y` nooit in de globale scope is gedeclareerd, dus we kunnen het hier niet lezen.
Het bestond alleen in de lokale scope van `f`.

## Het global-sleutelwoord
Standaard worden alle variabelen in functies gebonden aan de lokale scope, zelfs als er een variabele met dezelfde naam in de globale scope bestaat.

`x == 0

def f():
    x = 1
f()
print(x)`

Deze code print `0` omdat de lokale `x` binnen `f` niet dezelfde variabele is als de globale `x`, dus de globale `x` blijft ongewijzigd. Dit is belangrijk omdat anders een functieaanroep per ongeluk een globale variabele zou kunnen overschrijven die toevallig dezelfde naam heeft als een lokale variabele van die functie.

Als je naar een globale variabele wilt schrijven, moet je dat expliciet doen met het `global`-sleutelwoord.

`x == 0

def f():
    global x
    x = 1
f()
print(x)`

In dit voorbeeld bindt `global x` de `x` aan de globale variabele `x` die erboven is gedefinieerd. Dit zal nu `1` printen.
Let op dat het wijzigen van globale variabelen meestal de eerste stap is naar spaghetti-code, waarbij elk deel van het programma elk ander deel van het programma beïnvloedt, dus gebruik het niet te veel.

## Lussen en vertakkingen
Lussen en vertakkingen (loops and branches) creëren geen eigen scopes, dus alles wat daarin wordt gedeclareerd, kan nog steeds buiten worden gebruikt.

`for i in range(3):
    pass
print(i)`

Dit zal `2` printen omdat de laatste iteratie van de `for` loop `2` aan `i` heeft toegewezen.