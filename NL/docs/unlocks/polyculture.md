# Polyculture
Je hebt misschien al gemerkt dat planten soms meer opbrengen als ze samen worden geplant.
Gras, struiken, bomen en wortels leveren meer op als ze de juiste plant als metgezel hebben. De voorkeur voor een metgezel is voor elke individuele plant anders en kan niet worden voorspeld. Gelukkig kan de voorkeur voor een metgezel van de plant onder de drone worden gemeten met `get_companion()`. Het geeft een tuple terug waarbij het eerste element het type plant is dat het als metgezel wil en het tweede element de positie is waar het zijn metgezel wil.

`plant, (x, y) = get_companion()`

Bijvoorbeeld, als je een struik plant en dan `get_companion()` aanroept, zal het iets teruggeven als `(Entities.Carrot, (3, 5))`. Dit betekent dat deze struik graag wortels op positie `(3,5)` zou hebben. Dus als je wortels plant op `(3,5)` en dan de struik oogst, zal deze meer hout opleveren. Het groeistadium van de wortel maakt niet uit.

De voorkeur voor een metgezel van een plant kan `Entities.Grass`, `Entities.Bush`, `Entities.Tree` of `Entities.Carrot` zijn. Elke plant kiest dit willekeurig, but it will always choose a different plant than itself. De positie kan ook elke positie zijn binnen 3 zetten van de plant, behalve de positie van de plant zelf.

Als er geen plant onder de drone is die een voorkeur voor een metgezel heeft, geeft `get_companion()` `None` terug.

De opbrengstvermenigvuldiger is `5` plus het aantal polycultuur-upgrades.