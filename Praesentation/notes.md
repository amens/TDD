TEST-DRIVEN-DEVELOPMENT
=======================

Philipp/Ben und ich wollen euch etwas über die testgetriebene
Entwickelung erzählen, vielleicht besser bekannt als test-driven
development, oder TDD.

* * *

DAS PROBLEM

In der Softwareentwickelung geschieht es doch recht häufig, dass
das Testen vernachlässigt, aufgeschoben oder gar übersprungen wird.
Dies führt unweigerlich zu einer schlechteren Qualität der
Software, und zu einer unabsehbaren Nachbesserungsaufwand. Das
Problem wird nur noch schlimmer je mehr Leute an dem Projekt
beteiligt sind. Das kann teuer werden.

* * *

DIE LÖSUNG

Die Lösung könnte sein, früh in der Entwicklung zu testen, ja sogar
Zeitgleich mit dem Kodieren der Produktivcode. Man könnte ein
Schritt weiter gehen, und fordern, dass die Tests vor der
Produktivcode fertig sind. Dieser Ansatz nennt man die
Testgetriebene Entwickelung.

* * *

TEST-DRIVEN DEVELOPMENT

Test-Driven Development ist nicht eine Gesamtentwickelungsstrategie
oder -philosophie, sondern nur ein Teil. Sie besteht aus:
test-first development und häufiges Refaktorisieren.

Hierbei ist das Refaktorisieren ein wesentlicher Teil der
Strategie. Erstens, der erste Code den man schreibt ist in der
Regel nicht der beste. Zweitens, erkennt man oft erst nach einiger
Zeit den besten Ansatz. Dann sollte man aber refaktorisieren.

Zusätzlich bringt TFD alleine nicht genug Vorteile und bringt
sogar manche Nachteile mit sich, wenn man das Refaktorisieren
weglässt. Wir werden später mehr dazu sagen.

* * *

KURZER ITERATIVER ZYKLUS

Wir wollen aber erstmal TDD ein bisschen genauer definieren.

Die testgetriebene Entwickelung besteht aus einem kurzen, iterativen
Zyklus:

...

* * *

THREE LAWS OF TDD

Eine andere Sicht auf die testgetriebene Entwickelung ist,
sie als eine Menge von Regeln oder Gesetzen aufzufassen.
Diese hier waren oft im Internet zitiert, und sind ziemlich
klar.

...

Der Entwickler reagiert nur auf fehlschlagende Tests.

- - -

Natürlich muss man ein Design haben und Code schreiben, dass
Unittestbar ist.

- - -

Hier könnt ihr mehr dazu lesen, inklusive einer ganzen Diskussion über die
Vorteile des TDDs.

Was fehlt aber hier?
— Das kritische Refaktorisieren.

* * *

BEMERKUNGEN

An dieser Stelle würde ich gern ein paar Bemerkungen zu TDD
loswerden.

1. Wenn man einen so kurzen Zyklus hat wie wir gesehen haben,
   dann entstehen als Folge ziemlich viele Kontextwechsel
   zwischen Produktivcode und Testcode schreiben. Das kann
   einen negativen Effekt auf die Produktivität haben, oder
   auch einen positiven. Es ist möglich z.B., dass die Tests
   den Programmierer helfen, den roten Faden nicht zu verlieren.

   Wie viele tests glaubt ihr werden durch TDD erzeugt?

2. In jedem Zyklus muss man mehrmals kompilieren und Tests
   ausführen. Wenn 20 Mann an einem Softwareprojekt arbeiten
   und jeder schreibt einen neuen Test jede Stunde, dann sind an
   einem Tag 20 * 6 = 120 Tests geschrieben. Man schätzt am Ende
   mit genausoviel Testcode wie Produktivcode. So viel Testen
   erfordert eine geeignete Testframework.

3. Die Entwickelungsumgebung muss das häufige Neu-kompilieren und
   das Ausführen solch einer Menge von Tests unterstützen können.
   Projekte die auch nur Minuten brauchen um zu kompilieren sind
   dann doch schon kritisch, geschweige denn die Projekte die
   Stunden brauchen!

   Zusätzlich spielt die Konfigurationsmanagement eine große Rolle.
   Es soll möglich sein, schnell den aktuellen Zustand zu „commiten“
   sowie einen früheren wiederherzustellen. Denn eine häufig genannter
   Vorteil von TDD ist, dass wenn etwas nicht funktioniert, es oft
   leichter und einfacher ist, den letzt besten Zustand zu „laden“,
   als rum zu Debuggen.

* * *
