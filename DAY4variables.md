# 📦 Variablen in Go

In Go brauchst du **Variablen**, um Werte zu speichern, die sich im Laufe des Programms ändern können.

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
Einige grundlegende Typen in Go:

- `int` → Ganzzahlen
- `float64` → Gleitkommazahlen
- `string` → Texte
- `bool` → Wahrheitswerte (true oder false)

---

### 🔄 Beispiel
```go
package main

import "fmt"

func main() {
    var zahl int = 10
    text := "Hallo, Go!"
    fmt.Println(zahl)
    fmt.Println(text)
}
```

---

## ✅ Best Practices
- Benutze `:=` für kurze, klare Initialisierungen.
- Verwende `var`, wenn du den Typ angeben musst oder außerhalb von Funktionen deklarierst.
- Achte auf sinnvolle Namen – sie machen deinen Code lesbar und verständlich.

---

## 🧠 Merke
- Variablen speichern veränderbare Werte.
- Go ist statisch typisiert → Der Typ wird beim Kompilieren überprüft.
- Die Kurzschreibweise `:=` funktioniert nur innerhalb von Funktionen.
