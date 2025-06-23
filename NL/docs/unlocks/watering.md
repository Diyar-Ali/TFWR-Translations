# Water Geven
Planten groeien sneller als ze water krijgen. De grond heeft een waterniveau dat varieert van `0` tot `1`.
De functie `get_water()` geeft het waterniveau terug van de grond waar hij boven is.

De groeisnelheid van een plant schaalt lineair van 1x snelheid bij waterniveau 0 tot 5x snelheid bij waterniveau 1.

De grond droogt na verloop van tijd uit: Gemiddeld verliest het 1% van zijn huidige water per seconde, maar hier zit enige willekeurige variatie in. Het handhaven van een hoog waterniveau zal veel meer water verbruiken dan het handhaven van een laag waterniveau.

Je kunt water gebruiken voor je planten. Eén tank water wordt elke 10 seconden automatisch aan je inventaris toegevoegd.
Het upgraden van `Unlocks.Watering` geeft je elke 10 seconden een extra tank water.

Een tank bevat `0.25` water.

Roep `use_item(Items.Water)` aan boven elke grond om de grond water te geven.