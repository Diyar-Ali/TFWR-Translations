# If
Je kunt if, elif en else gebruiken om code voorwaardelijk uit te voeren.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Syntaxis
`if`-statements stellen je in staat om code alleen uit te voeren als een bepaalde voorwaarde `True` is. Ze zijn als een `while loop` die niet herhaalt.
De `if` neemt een voorwaarde, net als de `while loop`, en voert het if-codeblok uit als de voorwaarde evalueert naar `True`:

`#doe een flip als de voorwaarde True is
if condition:
	do_a_flip()`

Je kunt ook een `else` toevoegen na de `if` die code definieert die wordt uitgevoerd als de voorwaarde evalueert naar `False`.

Doe een flip als `condition` Waar is, anders oogst.
`if condition:
	do_a_flip()
else:
	harvest()`

`elif` is een afkorting voor else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

kan worden verkort tot:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`