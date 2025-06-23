# Zintuigen
De drone kan nu zien!

De functies `get_pos_x()` en `get_pos_y()` geven de huidige x- en y-positie van de drone terug. Op de startpositie zijn ze beide `0`. De x-positie neemt met `1` toe voor elk vakje richting het `Oosten` en de y-positie neemt met `1` toe voor elk vakje richting het `Noorden`.

`num_items(item)` geeft terug hoeveel je van een item hebt.
Bijvoorbeeld, `num_items(Items.Hay)` geeft terug hoeveel hooi je hebt.

`get_entity_type()` en `get_ground_type()` geven het type entiteit of grond terug dat zich onder de drone bevindt.

Doe een flip als je boven een struik bent:
`if get_entity_type() == Entities.Bush:
	do_a_flip()`

Het `None`-sleutelwoord is nu ook ontgrendeld! `None` is een waarde die aangeeft dat er geen waarde is.
Bijvoorbeeld, een functie die geen `return`-statement heeft, zal feitelijk `None` teruggeven.

`get_entity_type()` geeft `None` terug als er geen entiteit onder de drone is.