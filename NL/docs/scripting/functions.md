# Functies
Gebruik het `def`-sleutelwoord om een nieuwe functie te definiëren:
`def f(arg1, arg2 = False):
	#functiecode`

Je kunt de aanroepoperator `()` gebruiken om de functie aan te roepen:
`f(42)`

Zie ook [Scopes](docs/scripting/scopes.md) om meer te leren over lokale en globale variabelen in functies.

## Introductie
Je hebt al ingebouwde functies zoals `harvest()` gezien.
Je kunt ook je eigen functies definiëren, wat het mogelijk maakt om je code op een modulaire manier te structureren. Het stelt je in wezen in staat om een naam te geven aan een blok code, zodat je het overal vandaan kunt aanroepen.

## Functiedefinities
Je zou bijvoorbeeld een functie kunnen definiëren die de drone meerdere keren verplaatst.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

Het `def`-sleutelwoord geeft aan dat dit een functiedefinitie is.
`move_n_dir` is de naam waaraan de functie wordt gebonden. Dit kan elke geldige variabelenaam zijn en wordt gebruikt om de functie aan te roepen.
`n` en `dir` zijn parameters. Het zijn variabelen die de waarden bevatten die aan de functie worden doorgegeven (deze waarden worden ook argumenten genoemd). Je kunt zoveel parameters aan een functiedefinitie toevoegen als je wilt.
Na de `:` komt het codeblok dat wordt uitgevoerd wanneer de functie wordt aangeroepen.

Met de bovenstaande definitie verplaatst de volgende code de drone `10` tegels naar het `Noorden` en `2` tegels naar het `Westen`.

`move_n_dir(10, North)
move_n_dir(2, West)`

Wanneer je `def function():` ziet, moet je het echt zien als een variabeletoewijzing zoals deze:
`function = create_new_function_object()`
Zoals bij alle toewijzingen, kun je de variabele niet gebruiken voordat deze is toegewezen!
De `def`-statement moet worden uitgevoerd vóórdat functieaanroepen plaatsvinden.
Deze code zal een fout veroorzaken:

`func()
def func():
	pass`

## Return-waarden
Gebruik het `return`-sleutelwoord om een functie een waarde te laten teruggeven.
De volgende functie definieert bijvoorbeeld de exclusieve of-operatie. De exclusieve of geeft `True` terug als de ene waarde `True` is en de andere `False`:

`def xor(a, b):
	return a != b

if xor(True, False):
	do_a_flip()`

[Tuples](docs/scripting/tuples.md) maken het mogelijk om meerdere waarden terug te geven.

## Standaardargumenten
Je kunt ook standaardwaarden toewijzen die worden gebruikt als er geen argumenten worden doorgegeven.

`def f(a = False):
	if a:
		do_a_flip()

f()

f(True)`

Een argument met een standaardwaarde kan niet worden gevolgd door een argument dat geen standaardwaarde heeft.

## Geavanceerd Functiegebruik
Functies zijn waarden, net als elke andere waarde, en de `def`-statement fungeert gewoon als een toewijzingsstatement, waarbij de functie wordt toegewezen aan de naam die je eraan geeft.
Dit maakt het mogelijk om dingen als dit te doen:

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Hier roept `f()` de functie `f` aan, die een nieuwe functie `d` definieert en teruggeeft. De tweede `()` voert vervolgens de teruggegeven functie uit en voert een flip uit.
(Dit soort dingen doen is meestal geen goed idee omdat het moeilijk te zien is wat er gebeurt)

Functies die andere functies als argumenten nemen, laten je echt creatief worden:

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, North)
f(use_item, Items.Fertilizer)`

Deze code verplaatst de drone 10 keer naar het `Noorden` en gebruikt dan 10 keer kunstmest.