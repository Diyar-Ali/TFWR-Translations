# Snelheidsupgrade
De uitvoeringssnelheid is verdubbeld. Het probleem is dat de drone nu sneller oogst dan het gras kan groeien, wat resulteert in helemaal geen oogst. Om hiermee om te gaan zijn nu [if](docs/scripting/if.md) branches en de [can_harvest](functions/can_harvest) functie ontgrendeld.

## Controleren voor het Oogsten
Tot nu toe hadden we alleen `True` en `False` als voorwaarden, wat natuurlijk niet erg nuttig is met `if`.

De nieuwe functie can_harvest() biedt een betere voorwaarde. `can_harvest()` geeft `True` terug als de plant onder de drone geoogst kan worden en anders `False`.

`if can_harvest():
	#doe iets`

De reden dat je deze functie als voorwaarde kunt gebruiken, is omdat het een booleaanse waarde teruggeeft.

Een return-waarde betekent in wezen dat nadat de functionaliteit is uitgevoerd, de functieaanroep-expressie evalueert naar de teruggegeven waarde.

Wat gebeurt er wanneer de bovenstaande code wordt uitgevoerd:
	-de if wordt uitgevoerd 
	-`can_harvest()` wordt aangeroepen 
	-`can_harvest()` doet zijn ding 
	-`can_harvest()` geeft `True` of `False` terug 
	-de statement is nu `if True:` of `if False:` 
	-het codeblok wordt alleen uitgevoerd als er geoogst kan worden 

Nu kunnen we `if` gebruiken om te voorkomen dat de drone te vroeg oogst.