# Debuggen
Soms werkt je code gewoon niet en moet je uitzoeken waarom. Er zijn een paar hulpmiddelen om je daarbij te helpen.

Het eerste is om het programma stap voor stap uit te voeren.
Je kunt naar de stap-voor-stap modus gaan met de knop naast de Uitvoeren-knop of door een breekpunt in te stellen.

Breekpunten kunnen worden toegevoegd door op het breekpuntpaneel links van de code te klikken.
![](Breakpoints227)
Wanneer de uitvoering de regel bereikt waar het breekpunt is, schakelt het automatisch over naar de stap-voor-stap modus.

Wanneer je je muis over een variabele beweegt, wordt de huidige waarde ervan weergegeven.

De `print()`-functie kan ook erg nuttig zijn. Het schrijft elke waarde die eraan wordt doorgegeven direct in de lucht.

Voorbeelden:

Print "0.24".
`print(0.24)`

Print "True" of "False".
`print(can_harvest())`

Print de huidige positie.
`print(get_pos_x(), get_pos_y())`

De print-functie print de waarde direct in de lucht en op de [Output](docs/output.md)-pagina.

In de lucht schrijven kan soms wat traag zijn als je veel waarden wilt printen.
In dat geval kun je de `quick_print()`-functie gebruiken die alleen naar het output-venster print.

Het output-venster logt ook waarschuwingen en fouten, dus als iets niet werkt zoals verwacht, kan het nuttig zijn om dat te controleren.

Wanneer de uitvoering stopt, wordt de output ook naar het output.txt-bestand in de spelmap geschreven. [output.txt](persistent_data_path/output.txt).