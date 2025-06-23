# Importeren
Al je code in één bestand plaatsen wordt al snel onbeheersbaar.
`import`-statements stellen je in staat om functies en globale variabelen uit een ander bestand te importeren.

`import bestandsnaam`

Dit is de eenvoudigste vorm van een import-statement. Het geeft je toegang tot alles wat is gedefinieerd in het bestand met de naam `bestandsnaam`. Elk venster in het spel is een bestand, en de bestandsnaam is de naam die bovenaan het venster wordt weergegeven.

Hier is een voorbeeld met twee bestanden:
Bestand genaamd helper:
`x = 0

def say_hello():
    print("hallo vanuit helper")`

Een ander bestand:
`import helper
helper.say_hello()
helper.x += 1`

Hier voert `import helper` het bestand met de naam `helper` uit en geeft je toegang tot al zijn globals.
Je kunt dan variabelen en functies binnen de geïmporteerde module benaderen met de `.`-operator.
In dit voorbeeld roept `helper.say_hello()` dus `say_hello()` aan binnen helper en de laatste regel verhoogt de globale variabele x.

Je kunt ook de globals van de geïmporteerde module verplaatsen naar de huidige scope waar de import-statement wordt uitgevoerd met de `from`-syntaxis.

`from helper import *`
Importeert alle globals uit helper.

of

`from helper import say_hello`
Importeert alleen de opgegeven globals uit helper.

Dit importeert ook het helper-bestand, maar in plaats van het te benaderen via een variabele genaamd `helper`, pakt het globals uit `helper` uit en wijst ze direct toe in de lokale scope.

`from helper import say_hello
say_hello()`

Deze vorm van importeren wordt meestal niet aanbevolen omdat het niet goed werkt wanneer twee bestanden elkaar importeren, en je kunt per ongeluk variabelen in het importerende bestand overschrijven door naamconflicten (name collisions).

# Hoe het echt werkt

## TL;DR
Imports kunnen behoorlijk onintuïtief zijn, maar de meeste problemen kunnen worden vermeden door je te houden aan de `import file`-syntaxis in plaats van `from file import`, en alles wat geen globale definitie is te omwikkelen met
`if __name__ == "__main__":`

## Import-neveneffecten
De eerste keer dat je een bestand importeert, wordt het hele bestand uitgevoerd en krijg je vervolgens toegang tot alle variabelen die tijdens de uitvoering zijn gedefinieerd.
Als je hetzelfde bestand opnieuw importeert, wordt gewoon de gecachte module van de eerste keer teruggegeven.

Dit betekent dat import-statements neveneffecten kunnen hebben. Als je een bestand importeert dat `harvest()` aanroept, zal het daadwerkelijk oogsten tijdens de import. Maar wanneer je het opnieuw importeert, zal het niet opnieuw oogsten omdat het bestand maar één keer wordt uitgevoerd.

Er is een manier om dergelijke neveneffecten te vermijden met de `__name__`-variabele. Dit is een variabele die automatisch wordt ingesteld op `"__main__"` wanneer een bestand direct wordt uitgevoerd, en op de naam van het bestand wanneer een bestand wordt uitgevoerd via `import`.
Het wordt beschouwd als goede praktijk om alle code die je niet wilt uitvoeren wanneer het bestand wordt geïmporteerd, binnen een `if __name__ == "__main__":`-blok te plaatsen.

Een gebruikelijke bestandsstructuur in Python is om de code die moet worden uitgevoerd wanneer het bestand wordt gestart in een `main()`-functie te plaatsen. Op deze manier heb je een duidelijk onderscheid tussen lokale variabelen (gedefinieerd binnen `main()`) en globale variabelen die kunnen worden geïmporteerd (gedefinieerd buiten `main()`).

`a_global_variable = "global"

def main():
    a_local_variable = "local"
    # doe dingen

if __name__ == "__main__":
    main()`

## Import-cycli
Wat gebeurt er als bestand `a` bestand `b` importeert en bestand `b` bestand `a` importeert?

bestand `a`:
`import b
x = 0`

bestand `b`:
`import a
def f():
    print(a.x)`

Dit zal prima werken. Laten we zeggen dat geen van beide bestanden al is geladen, en iemand anders `import a` uitvoert.

-`a` wordt uitgevoerd tot de `import b`-regel.
-`b` wordt uitgevoerd tot de `import a`-regel.
-De module `a` bestaat al, maar bevat nog geen `x` omdat het alleen de `import b`-regel heeft bereikt.
-`b` slaat een referentie naar de half geladen module `a` op in een variabele genaamd `a`.
-`b` voert de `def`-statement uit en slaat de functie `f()` op.
-`a` gaat verder met uitvoeren en initialiseert `x`.

Wanneer iemand `b.f()` aanroept, zal het correct `0` printen omdat de module `a` waarnaar `b` een referentie heeft, nu volledig is geladen.

Beschouw nu dezelfde code met de `from`-syntaxis.

bestand `a`:
`from b import *
x = 0`

bestand `b`:
`from a import *
def f():
    print(x)`

-`a` wordt uitgevoerd tot de `from b import *`-regel.
-`b` wordt uitgevoerd tot de `from a import *`-regel.
-De module `a` bestaat al, maar is nog niet volledig uitgevoerd.
-`b` pakt alles uit wat momenteel in `a` zit in zijn eigen globale scope. Op dit punt bevat `a` niets omdat het de `x = 0`-regel nog niet heeft bereikt, dus er wordt niets geïmporteerd.
-`b` voert de `def`-statement uit en slaat de functie `f()` op.
-`a` gaat verder met uitvoeren en initialiseert `x`.

Als iemand nu `b.f()` aanroept, krijgen ze een foutmelding dat `x` niet bestaat in de huidige scope. Dit komt omdat `b` dit keer geen referentie heeft naar het nog ladende `a` en geen definities ziet die na de import zijn toegevoegd.