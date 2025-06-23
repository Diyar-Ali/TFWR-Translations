# Externe Editor
De in-game teksteditor is meestal voldoende om dit spel te spelen, maar kan natuurlijk niet concurreren met geavanceerdere teksteditors zoals Visual Studio Code.

Het spel slaat alle codebestanden op als .py-bestanden, zodat je ze met Python-editors kunt bewerken.
Let op: dit is alleen voor het gemak. De in-game taal is niet daadwerkelijk Python, maar het lijkt er genoeg op dat Python IntelliSense er redelijk op werkt.
Je kunt de bestanden vinden in de [opslagmap](persistent_data_path/Saves).

Elk opslagbestand bevat ook een `__builtins__.py`-bestand, dat ingebouwde Python-definities bevat die overeenkomen met de in-game builtins om IntelliSense mogelijk te maken.
VS Code kan `__builtins__.py` automatisch detecteren, maar sommige editors werken mogelijk alleen als je `from __builtins__ import *` gebruikt.

Om externe wijzigingen in het spel te zien zonder het opslagbestand opnieuw te hoeven laden, moet je de optie "File Watcher" inschakelen. Als je extern bestanden aanmaakt of verwijdert, moet je het opslagbestand nog steeds opnieuw laden om ze te zien.

## VS Code gebruiken
Visual Studio Code is de aanbevolen code-editor om te gebruiken met The Farmer Was Replaced.

Je kunt het [hier](https://code.visualstudio.com/download) installeren.

Na het downloaden, installeer je de Python-extensie in VS Code.

Zodra je dat hebt gedaan, open je de [map](persistent_data_path/Saves) die jouw `.py`-bestanden bevat in VS Code. Zorg ervoor dat je de hele map opent, niet alleen de afzonderlijke bestanden, anders werkt het `__builtins__.py`-bestand niet.

Zorg er in het spel voor dat je de "File Watcher"-optie hebt ingeschakeld. Nu zullen de wijzigingen automatisch in het spel verschijnen telkens wanneer je opslaat in VS Code.

Dat is alles! Nu kun je je code schrijven in een professionele code-editor!