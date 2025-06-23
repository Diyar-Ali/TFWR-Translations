# Patch Notes

Deze patch brengt veel optimalisaties aan zowel de GPU- als de CPU-kant.
Vooral aan de GPU-kant zijn er enkele zeer significante optimalisaties doorgevoerd die het spel eindelijk minder GPU-intensief maken.
Helaas zijn de items in de inventaris niet langer 3D, omdat bleek dat dit veel GPU-bronnen gebruikte.

Enkele zaken die naast de optimalisaties zijn gewijzigd, zijn:
-De limiet van de call stack is nu 1000 functieaanroepen.
-Items in de inventaris hebben nu een vaste volgorde.
-Wanneer de camera naar de positie van een fout of een zoekterm beweegt, gaat deze nu naar de exacte locatie in plaats van het midden van het venster. Ook beweegt de camera niet langer naar fouten die al op het scherm te zien zijn.
-Diverse UI-bugs opgelost.

Brekende Wijzigingen uit oudere Patches die je mogelijk hebt gemist:
-Functies gedefinieerd in andere bestanden (vensters in het spel) worden niet langer impliciet geïmporteerd. Je moet nu expliciete import-statements ontgrendelen en gebruiken zoals in Python (zie de import-ontgrendeling).
-`Items.Bones` is hernoemd naar `Items.Bone` zodat alle items in het enkelvoud staan.
-`Entities.Carrots` is hernoemd naar `Entities.Carrot` zodat alle entiteiten in het enkelvoud staan.
-`Grounds.Turf` is hernoemd naar `Grounds.Grassland` om het begrijpelijker te maken.
-`Items.Water_Tank` is hernoemd naar `Items.Water` omdat de functie voor het bijvullen van de tank is verwijderd.
-`Unlocks.Benchmark` is vervangen door `Unlocks.Timing`.
-`get_op_count()` is hernoemd naar `get_tick_count()` om consistent te zijn met `get_world_size()`.
-`set_farm_size()` is hernoemd naar `set_world_size()` om consistent te zijn met `get_world_size()`.
-`get_companion()` geeft nu een tuple terug van de vorm (entity, (x, y)) in plaats van een lijst.
-`trade()` is uit het spel verwijderd.