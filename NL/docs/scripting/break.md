# Break
`break` maakt het mogelijk om een lus vroegtijdig te stoppen. Wanneer de `break`-statement wordt bereikt, zal het onmiddellijk de binnenste lus verlaten en de code na de lus uitvoeren.

`for i in range(10):
	break
print(i)`
Dit print `0` omdat `i` `0` is in de eerste iteratie van de lus en dan beëindigt de break-statement de lus.

Het werkt ook bij `while loops`.

`while True:
	if can_harvest():
		break`

Deze code voert de `while loop` uit totdat `can_harvest()` `True` is. 
Het heeft hetzelfde effect als

`while not can_harvest():
	pass`

In geneste lussen verlaat `break` altijd de binnenste lus.

`for i in range(10):
	for j in range(10):
		break
		print("dit wordt nooit geprint")
	print("dit wordt 10 keer geprint")`