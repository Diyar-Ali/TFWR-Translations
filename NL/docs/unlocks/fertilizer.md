# Kunstmest
Op een gegeven moment is wachten tot de planten groeien gewoon niet meer efficiënt genoeg.
Net als water, ontvang je automatisch elke 10 seconden 1 kunstmest, plus een extra voor elke upgrade.

Kunstmest kan planten direct laten groeien. `use_item(Items.Fertilizer)` vermindert de resterende groeitijd van de plant onder de drone met 2 seconden.

Dit heeft enkele neveneffecten.
Planten die met kunstmest zijn gekweekt, raken geïnfecteerd.

Wanneer een plant geïnfecteerd is, wordt de helft van de opbrengst omgezet in `Items.Weird_Substance` wanneer deze wordt geoogst.
Weird Substance kan ook op planten worden gebruikt, wat het effect heeft dat de geïnfecteerde status van de plant en alle aangrenzende planten wordt omgeschakeld.

Dus als je `use_item(Items.Weird_Substance)` aanroept op een geïnfecteerde plant, zal het deze genezen, maar als je het op een gezonde plant gebruikt, zal het deze infecteren.

Als je het gebruikt op een geïnfecteerde plant met gezonde buren, zal het de plant genezen maar de buren infecteren en vice versa.