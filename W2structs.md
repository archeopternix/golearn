# Benutzerdefinierte Datentypen: Struct(s)

Structs (Strukturen) sind in Go benutzerdefinierte Datentypen, die es erlauben, mehrere Werte unterschiedlichen Typs unter einem Namen zusammenzufassen. Sie sind vergleichbar mit "Klassen ohne Methoden" aus anderen Programmiersprachen und ideal, um komplexe Datenmodelle zu erstellen.

## Deklaration eines Structs
Ein Struct wird mit dem Schlüsselwort type und struct deklariert:

```go
type Person struct {
    Name string
    Alter int
}
```

Hier wird ein Struct Person definiert, das zwei Felder hat: Name (Typ string) und Alter (Typ int).

## Verwendung eines Structs
Um ein Struct zu verwenden, erstellt man eine Variable dieses Typs und weist den Feldern Werte zu:

var p Person
p.Name = "Anna"
p.Alter = 28

Oder direkt bei der Initialisierung:

p := Person{Name: "Max", Alter: 32}

Zugriff auf Struct-Felder
Auf die Felder eines Structs greift man mit dem Punktoperator zu:

fmt.Println(p.Name)  // Gibt "Max" aus
fmt.Println(p.Alter) // Gibt 32 aus

## Structs als Funktionsparameter
Structs können wie andere Datentypen an Funktionen übergeben werden:

func begruessen(person Person) {
    fmt.Printf("Hallo, %s!\n", person.Name)
}

## Structs mit Zeigern
Oft wird ein Zeiger auf ein Struct verwendet, um Änderungen an den Struct-Daten innerhalb einer Funktion vorzunehmen:

func aelterWerden(person *Person) {
    person.Alter++
}

## Zusammenfassung:
Structs in Go sind ein zentrales Mittel, um Daten logisch zu gruppieren und übersichtlich zu organisieren. Sie sind einfach zu definieren und flexibel einsetzbar, z.B. um Personen, Adressen oder beliebige andere Objekte abzubilden.

