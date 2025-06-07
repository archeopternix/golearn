# Zeiger auf Variablen: *Pointers*

In Go sind Pointer ein wichtiges Konzept, um effizient mit Speicher und Datenstrukturen zu arbeiten. Bis jetzt haben wir *Variablen* (string, int, bool..) kennengelernt, die, wenn wir sie anlegen direkt den Wert speichern, den wir Ihnen geben.

## Was ist ein Pointer?

Ein Pointer ist auch eine Variable, die aber die Speicheradresse einer anderen Variable speichert – anstatt den Wert direkt zu halten, verweist der Pointer auf den Speicherort des Wertes. In Go wird ein Pointer durch das Präfix `*` deklariert. In *Go* hat jeder Pointer einen *Typ*, der klar festlegt auf welche Art Variabel der Pointer zeigen darf. So darf ein *string* Pointer nicht auf einen *int* zeigen. Das merkt der Compiler und er wird dich darauf hinweisen, dass Du hier einen Fehler gemacht hast. Dies ist in Sprachen wie z.B. C oder C++ anders und deswegen treten bei diesen Sprachen vermehrt Sicherheitslücken (Pufferüberlauf...) auf, die von Hackern ausgenutzt werden oder das Programm zum Absturz bringen können.

### Variable:

Jede Variable wird im Speicher angelegt und hat eine *Adresse* um sie wiederzufinden. An dieser *Adresse* im Speicher wird dann der *Wert* abgespeichert.

*Pointer*:

| var Alter *int        |
|-----------------------|
| Wert: 0xA1B2C3        |
| Adresse: 0xFB0023     |

Zeigt auf eine *Variable* im Speicher
      
| int                |        
|--------------------|          
| Wert:      42      |          
| Adresse: 0xA1B2C3  |                

Erklärung:
- *int* ist eine Variable vom Typ int und speichert direkt den Wert (z.B. 42).
- *Alter* ist ein Pointer auf einen Integer (int), der die Adresse von *int* speichert (z.B. 0xA1B2C3).

*Beispiel:*
```go
var a int = 42
var Alter *int = &a // p ist ein Pointer auf a
```

* &a gibt die Adresse von a zurück.
* p speichert diese Adresse.
* *p gibt den Wert zurück, auf den p zeigt (also 42).

## Warum Pointers verwenden?
* Sie ermöglichen es, Funktionen Referenzen auf Werte zu übergeben (statt Kopien), somit wirken sich Änderungen direkt auf die darunterliegenden Werte aus.
* Sie sind notwendig, um veränderbare komplexe Datenstrukturen wie Slices, Maps oder eigene Structs effizient zu nutzen.
* Sie helfen, Speicher zu sparen und Performance zu verbessern.

## Pointer als Funktionsparameter

```go
func increment(n *int) {
    *n = *n + 1
}

func main() {
    x := 5
    increment(&x)
    fmt.Println(x) // Ausgabe: 6
}
```

Hier wird nicht die Kopie von x erhöht, sondern der Wert an der Adresse, auf die n zeigt.

### Übung:
* Schreibe dieses Beispiel so um, dass kein Pointer übergeben wird und vergleiche das Ergebnis.
* Nun füge noch nach ans Ende der func increment... eine fmt.Println(n) ein und schaue Dir die Ausgabe nochmal an

## Null-Pointer (nil)
Ein Pointer, der auf nichts zeigt, hat den Wert nil. Das sollte vor der Benutzung überprüft werden:

```go
var p *int
if p == nil {
    fmt.Println("Pointer ist nil")
}
```

## Zusammenfassung:
Pointer sind in Go sicherer und einfacher als in vielen anderen Sprachen, da Go keine Pointer-Arithmetik wie C erlaubt. Sie sind jedoch essenziell, um Go effizient und idiomatisch zu nutzen.




v
