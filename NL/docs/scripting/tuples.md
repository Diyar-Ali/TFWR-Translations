# Tuples
Tuples zijn een geweldige manier om meerdere waarden in één enkele waarde te combineren.
Om een tuple te maken, scheid je de waarden gewoon met komma's:

`tuple = 1, 2`

Je kunt ze ook weer uitpakken in meerdere variabelen. In de onderstaande code wordt de tuple `(1,2)` uitgepakt in twee variabelen `a` en `b`.

`a, b = 1, 2`

Tuples kunnen worden geïndexeerd zoals lijsten, maar ze zijn 'immutable' (onveranderlijk) en kunnen niet worden gewijzigd na creatie.

`tuple = 1, 2`

`print(tuple[1])`
print `2`

`tuple[0] = 3`
geeft een fout
<unlock=dicts>
In tegenstelling tot lijsten kunnen tuples worden gebruikt als sleutels in dictionaries.

`d = {(1,2):(4,5)}

print(d[(1,2)])`
`print` (4,5)</unlock>

Ze kunnen ook nuttig zijn voor het teruggeven van meerdere waarden in een functie.

`def f():
    return 1, 2

a, b = f()`