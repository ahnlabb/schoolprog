---
layout: page
title: GCD
permalink: /exercises/gcd/
type: exercise
state: draft
tags: 
 - funktioner
toc: true
---

## Denna övning innehåller:

## Motivering

När du gjort ett mattetal och lösningen innehåller ett bråk så ska du alltid skriva talet i sin enklaste form,
d.v.s. förkorta bråket så långt som möjligt innan du svarar.
Hur vet man vilket tal man ska förkorta med för att få talet på sin enklaste form?

## A: Testa dig fram

Ett tal **delar** ett annat tal om det inte blir någon rest över när du delar.
Fyra personer kan dela på 12 kronor, de får tre kronor var och det blir inget över.
Fyra delar tolv så när du delar tolv med fyra får du tre, ett heltal.
Fyra delar inte tretton så försöker fyra personer dela på tretton kronor kan de få tre var men sen blir det en krona över.
Resten är ett.

I python kan vi räkna ut resten med `%`

testa följande kod:
``` python3
print(13 % 4) # skriver ut: 1
print(12 % 4) # skriver ut: 0
```

Med detta kan vi t.ex. skriva ett program som kollar om ett tal är jämnt eller udda:
``` python3
n = int(input("Skriv ett tal: "))
if n % 2 == 0: # Om talet är jämnt så är resten vid division med 2 noll
    print("Talet är jämnt!")
else:
    print("Talet är udda!")
```


Hur kan vi använda detta för att förkorta bråk?

För att förkorta ett bråk så långt som möjligt så ska du förkorta bråket med det största tal som delar både täljaren och nämnaren.
Detta tal kallas täljaren och nämnarens **största gemensamma delare**.
Om du har bråket

$$
\frac{12}{30}
$$

så delar talen 1, 2, 3, 4, 6 och 12 täljaren och talen 1, 2, 3, 6, 10, 15 och 30 nämnaren. Det största talet som delar både täljaren och nämnaren är alltså 6.
Vi använder detta för att förkorta bråket:

$$
\frac{12}{30} = \frac{2 \cdot 6}{5 \cdot 6} = \frac{2}{5} 
$$

Genom att använda `%` kan vi testa om ett tal är gemensam delare till två andra tal genom att som innnan testa att det är delare till ena talet och är delare till det andra talet,
i python skriver vi `and` mellan de två påståendena för att testa att båda är sanna.

``` python3
number = int(input())

if 12 % number == 0 and 30 % number == 0:
    print('talet är gemensam delare till 12 och 30')
else:
    print('talet delar inte både 12 och 30')
```

Testa koden ovan. Talen 2, 3 och 6 är de enda gemensamma delarna till 12 och 30.


Genom att kombinera detta med en for loop som testar alla tal upp till det minsta av de två talen kan du räkna ut alla gemensamma delare!
Använd följande skal och testa om 

``` python3
a = input('F')
b = input()

for number in range min(a,b):
    # testa
```
