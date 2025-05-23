# 📦 Variablen in Go

In Go brauchst du **Variablen**, um Werte zu speichern, die sich im Laufe des Programms ändern können. Folgende Regeln gilt es zu beachten:
- Du kannst Variablen nicht gleich wie Go Standardfunktionen benennen (z.B. `switch`, `for`, `if`, `else`... ).
- Texte bei Variablen vom Typ `string` stehen in der Initialisierung immer zwischen 2 Doppelten-Anführungszeichen: `""`
- Zahlen vom Typ `float32` oder `float64` verwenden den `.` als Dezimalzeichen.
- Zahlen ohne `.` als Dezimalzeichen werden von Go immer als Ganzzahl `int` verstanden.
- Wahrheitswerte vom typ `bool` können die Werte `true` oder `false` annehmen


## 🛠️ Deklaration einer Variable

### 1. Mit `var`:

```go
var name string
name = "Gopher"
```

- Hier wird eine Variable `name` vom Typ `string` deklariert.
- Später wird ihr der Wert `"Gopher"` zugewiesen.

---

### 2. Mit Initialisierung:
Hier wird die Variable `age` direkt mit dem Wert `5` initialisiert.
```go
var age int = 5
```

---

### 3. Kurzschreibweise mit `:=` (nur innerhalb von Funktionen):
Hier wird die Variable `age` direkt mit dem Wert `5` initialisiert.
```go
message := "Hallo Welt"
```

Go erkennt den Typ automatisch → `message` ist vom Typ `string`.

---

### 🔤 Datentypen

# Go Variablentypen

Go stellt eine Vielzahl von grundlegenden Datentypen zur Verfügung:

## Boolesche Werte
- `bool`  
  Wahrheitswerte: `true` oder `false`

## Zeichenketten
- `string`  
  Textzeichenketten

## Ganzzahlen (Integer)
- `int`, `int8`, `int16`, `int32`, `int64`  
- `uint`, `uint8`, `uint16`, `uint32`, `uint64`  
- `uintptr`  

**Hinweis:**  
`int`, `uint` und `uintptr` sind in der Regel 32 Bit breit auf 32-Bit-Systemen und 64 Bit breit auf 64-Bit-Systemen.  
Wenn du eine ganze Zahl benötigst, solltest du normalerweise `int` verwenden, es sei denn, du hast einen speziellen Grund, einen genau definierten oder vorzeichenlosen Typ zu nutzen.

## Alias-Typen
- `byte` (alias für `uint8`)  
- `rune` (alias für `int32`)  
  Repräsentiert einen Unicode-Codepunkt

## Gleitkommazahlen (Floats)
- `float32`  
- `float64`

## Komplexe Zahlen
- `complex64`  
- `complex128`

---

### 🔄 Beispiel
```go
package main

import "fmt"

func main() {
    // 1. Definition ohne Initialisierung (Zero Value wird gesetzt)
    var zahl int
    fmt.Println("zahl:", zahl) // Ausgabe: zahl: 0

    // 2. Definition mit Initialisierung
    var text string = "Hallo Go"
    fmt.Println("text:", text) // Ausgabe: text: Hallo Go

    // 3. Kurzschreibweise mit Initialisierung (nur in Funktionen)
    message := "Willkommen!"
    fmt.Println("message:", message) // Ausgabe: message: Willkommen!

    // 4. Zuweisung: Wert ändern
    zahl = 42
    fmt.Println("zahl nach Zuweisung:", zahl) // Ausgabe: zahl nach Zuweisung: 42
}
```

---

## Nullwerte in Go

Variablen, die ohne expliziten Anfangswert deklariert werden, erhalten automatisch ihren **Zero Value** (Nullwert).

Die Nullwerte sind:

- `0` für numerische Typen  (`0.0` für Flieskommazahlen)
- `false` für den Booleschen Typ  
- `""` (der leere String) für Strings  
- `nil` für Pointer (Zeiger), Schnittstellen, Maps, Slices, Channels und Funktionen 

---

## Zusammenfassung
- Verwende `int` für allgemeine Ganzzahlen, außer du brauchst eine spezifische Größe oder Vorzeichenlosigkeit.
- `byte` und `rune` sind spezielle Alias-Typen für die Arbeit mit Bytes bzw. Unicode-Zeichen.
- Go bietet sowohl einfache Datentypen als auch komplexe für verschiedene Anforderungen.

---

## ✅ Best Practices
- Benutze `:=` für kurze, klare Initialisierungen.
- Verwende `var`, wenn du den Typ angeben musst oder außerhalb von Funktionen deklarierst.
- Achte auf sinnvolle Namen – sie machen deinen Code lesbar und verständlich.
- Verwende `err` für Fehlerwerte vom Type `Error`
- Verwende `i`, `j` für Schleifenvariablen

---

## 🧠 Merke
- Variablen speichern veränderbare Werte.
- Go ist statisch typisiert → Der Typ wird beim Kompilieren überprüft.
- Die Kurzschreibweise `:=` funktioniert nur innerhalb von Funktionen.
