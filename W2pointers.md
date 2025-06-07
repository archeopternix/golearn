# Zeiger auf Variablen: *Pointers*

In Go sind Pointer ein wichtiges Konzept, um effizient mit Speicher und Datenstrukturen zu arbeiten. Bis jetzt haben wir *Variablen* (string, int, bool..) kennengelernt, die, wenn wir sie anlegen direkt den Wert speichern, den wir Ihnen geben.

## Was ist ein Pointer?

Ein Pointer ist auch eine Variable, die aber die Speicheradresse einer anderen Variable speichert – anstatt den Wert direkt zu halten, verweist der Pointer auf den Speicherort des Wertes. In Go wird ein Pointer durch das Präfix `*` deklariert.

+-----------+
|   alter   |
+-----------+
|    30     |  <-- Das ist der Wert
+-----------+

*Beispiel:*
```go
var a int = 42
var p *int = &a // p ist ein Pointer auf a

* &a gibt die Adresse von a zurück.
* p speichert diese Adresse.
* *p gibt den Wert zurück, auf den p zeigt (also 42).

## Warum Pointers verwenden?
* Sie ermöglichen es, Funktionen Referenzen auf Werte zu übergeben (statt Kopien).
* Sie sind notwendig, um veränderbare Datenstrukturen wie Slices, Maps oder eigene Structs effizient zu nutzen.
* Sie helfen, Speicher zu sparen und Performance zu verbessern.

## Beispiel: Pointer als Funktionsparameter

func increment(n *int) {
    *n = *n + 1
}

func main() {
    x := 5
    increment(&x)
    fmt.Println(x) // Ausgabe: 6
}

Hier wird nicht die Kopie von x erhöht, sondern der Wert an der Adresse, auf die n zeigt.

## Null-Pointer (nil)
Ein Pointer, der auf nichts zeigt, hat den Wert nil. Das sollte vor der Benutzung überprüft werden:

var p *int
if p == nil {
    fmt.Println("Pointer ist nil")
}

## Zusammenfassung:
Pointer sind in Go sicherer und einfacher als in vielen anderen Sprachen, da Go keine Pointer-Arithmetik wie C erlaubt. Sie sind jedoch essenziell, um Go effizient und idiomatisch zu nutzen.




v
