# Continue
`continue` maakt het mogelijk om de huidige iteratie van een lus te stoppen en naar de volgende iteratie van de binnenste lus te springen.

`for i in range(10):
	continue
    print("dit wordt nooit geprint")`

Dit voert alle `10` iteraties van de lus uit, maar de `print`-statement na de `continue` wordt altijd overgeslagen.

Het werkt ook bij `while loops`.

`while True:
	if not can_harvest():
		continue
    
    harvest()`

Deze code roept `harvest()` alleen aan wanneer `can_harvest()` `True` is. 
Het heeft hetzelfde effect als

`while True:
	if can_harvest():
		harvest()`

In geneste lussen heeft `continue` altijd invloed op de binnenste lus.

`for i in range(10):
	for j in range(10):
	    print("dit wordt 100 keer geprint")
		continue
		print("dit wordt nooit geprint")
	print("dit wordt 10 keer geprint")`