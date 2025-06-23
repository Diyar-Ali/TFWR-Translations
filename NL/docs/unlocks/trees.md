# Bomen
[Bomen](objects/tree) zijn een betere manier om aan hout te komen dan struiken. Ze geven elk 5 hout. Net als struiken kunnen ze op gras of aarde worden geplant.

Bomen houden van wat ruimte en als je ze direct naast elkaar plant, vertraagt hun groei. De groeitijd wordt verdubbeld voor elke boom die op een vakje direct ten noorden, oosten, westen of zuiden ervan staat. Dus als je bomen op elk vakje plant, duurt het `2*2*2*2 = 16` keer zo lang voordat ze groeien.

<spoiler=show> De `%` operator kan hier nuttig zijn. Onthoud dat de `%` operator de rest van de deling teruggeeft. Even getallen gedeeld door `2` hebben een rest van `0` en oneven getallen gedeeld door `2` hebben een rest van `1`.
Dus je kunt controleren of een getal even is zoals dit:

`def is_even(n):
	return n % 2 == 0`

Dit geeft `True` terug als n even is en `False` als dat niet zo is.
</spoiler>
