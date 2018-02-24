{% if page.proglang == "python" %}
![solution](https://media.githubusercontent.com/media/ahnlabb/schoolprog-external/master/math-exerciser.gif)
{% endif %}

## Denna övning innehåller:

- Strängar {% if page.proglang == "python" %}
- Listor [(exempel)](https://repl.it/@ahnlabb/RowdyOliveWeevil) {% endif %}
- Loopar
- Slump


## Motivering

Du har hört det sägas att "repetition är kunskapens moder" och vill därför sitta
och göra så många mattetal du kan. Matteboken är bra men den har vissa
begränsningar:
- du kan inte öva på vad du vill
- att bläddra sidor slösar på din dyrbara övningstid
- uppgifterna kan när som helst ta slut!

Du hade kanske kunnat använda dina nyvunna programmeringskunskaper för att
skriva ett matte-övningsprogram!

## Outline

1. Skriv en lista med frågor.
2. Använd `input` funktionen för att be användaren om svaret till frågan.
3. Jämför användarens svar med det sanna svaret och ge feedback t.ex. "Rätt svar!"

## Genomgång

Vi vill göra en lista med de frågor vi vill öva på och en lista med frågornas
svar så att vi kan kolla att användaren skrivit rätt.
I python kan vi skriva de två listorna så här:

``` {{ page.proglang }} {% case page.proglang %}
{% when "python" %}
questions = ["Vad är kunskapens moder?", "Vilken funktion används i python för att skriva ut text i kommandotolken?"]
answers = ["repetition", "print"]
{% when "scala" %}
var questions = List("Vad är kunskapens moder?", "Vilken funktion används i scala för att skriva ut text i kommandotolken?")
var answers = List("repetition", "println")
{% endcase %} ```

Första frågan i `questions` listan är "Vad är kunskapens moder?" och svaret på den
frågan hittar vi först i `answers` listan: "repetition".

Ditt program kan sen plocka en slumpmässig fråga ur listan och presentera den
till användaren.

Vi har fortfarande inte riktig löst problemet med att uppgifterna tar slut, det
kan bli väldigt jobbigt att skriva alla matteuppgifter du vill öva på. Vi kan
använda programmeringsknep för att göra det lättare! Om du vill öva på femmans
multiplikationstabell kan du lägga till alla frågor

``` {{ page.proglang }}
{% include_relative 1.{{ page.ext }} %}
```
