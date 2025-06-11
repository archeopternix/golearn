# 🧱 Benutzerdefinierte Datentypen: Struct(s)

Structs (Strukturen) sind in Go benutzerdefinierte Datentypen, die es erlauben, mehrere Werte unterschiedlichen Typs unter einem Namen zusammenzufassen. Sie sind ideal, um komplexe Datenmodelle zu erstellen. Ein *struct* dient dabei als Bauplan, gleich wie die eingebauten Datentypen (int, string, bool...) für einen Variable und kann selber keine Werte halten und muss daher immer mit einer Variablen deklariert werden.

Ohne Structs müssten wir zusammengehörige Variablen mit eine Namenskonvention versehen:

```go
var PersonName string
var PersonAlter int
```

Dies würde den Sourcecode schwer lesbar machen und zu vielen Fehlern führen. So kann man inhaltlich zusammengehörige Werte / Variablen unter einem gemeinsamen 'Klassennamen' bündeln.

## Deklaration eines Structs
Ein Struct wird mit dem Schlüsselwort type und struct deklariert:

```go
type Person struct {
    Name string
    Alter int
}
```

Hier wird ein Struct Person definiert, das zwei Felder hat: Name (Typ string) und Alter (Typ int).

*type* weist uns darauf hin, dass wir einen neuen *Typ* definieren, der für Variablen und Funktinsparameter genutzt werden kann. In gewisser Art und Weise erweitern wir die in *Go* eingebauten Datentypen damit um selbst erstellte Typen.  

## Verwendung eines Structs
Um ein Struct zu verwenden, erstellt man eine Variable dieses Typs und weist den Feldern Werte zu:

```go
var p Person
p.Name = "Anna"
p.Alter = 28
```

Oder direkt bei der Initialisierung:

```go
p := Person{Name: "Max", Alter: 32}
```

Zugriff auf Struct-Felder
Auf die Felder eines Structs greift man mit dem Punktoperator zu:

```go
fmt.Println(p.Name)  // Gibt "Max" aus
fmt.Println(p.Alter) // Gibt 32 aus
```

## Structs als Funktionsparameter
Structs können wie andere Datentypen an Funktionen übergeben werden:

```go
func begruessen(person Person) {
    fmt.Printf("Hallo, %s!\n", person.Name)
}
```

## Structs mit Zeigern
Oft wird ein Zeiger auf ein Struct verwendet, um Änderungen an den Struct-Daten innerhalb einer Funktion vorzunehmen:

```go
func aelterWerden(person *Person) {
    person.Alter++
}
```

## Übung:

* Erstelle einen neue 'main.go' Datei
* Erstelle darin ein *struct* mit dem Namen *Adresse*, die Felder für Land, Stadt/Ort, Postleitzahl, Straße und Hausnummer enthält.
* Erstelle eine Variable mit diesem Typ und weise ihr die Werte für Deine Adresse zu.
* Zum Schluss gibst Du die Variable mit fmt.Println( *Variablenname*) aus

*Hinweis:* Variablen- und Feldnamen dürfen keine Umlaute und Sonderzeichen wie 'ß' enthalten. Denke daran dass Du die Feldnamen der Struct groß schreibst, sonst kannst Du (noch) nicht darauf zugreifen.


## Zusammenfassung:
Structs in Go sind ein zentrales Mittel, um Daten logisch zu gruppieren und übersichtlich zu organisieren. Sie sind einfach zu definieren und flexibel einsetzbar, z.B. um Personen, Adressen oder beliebige andere Objekte abzubilden.

