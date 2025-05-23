# 🔧 Funktionen in Go (`func`)

In Go sind **Funktionen** zentrale Bausteine eines Programms. Sie bündeln wiederverwendbaren Code und machen Deinen Code besser lesbar.

---

## 🧩 Aufbau einer Funktion

```go
func funktionsname(parameter1 typ1, parameter2 typ2) rückgabewert_typ {
    // Funktionskörper
    return rückgabewert
}
```

### 🔁 Beispiel

Wir erstellen eine Funktion zum Addieren von Zahlen. Unsere Funktion nimmt 2 Eingabewerte 
**a** und **b** entgegen und gibt das Ergebnis der Berechnung zurück
```go
func addiere(a int, b int) int {
    return a + b
}
```

Wir verwenden diese Funktion gleich in unserem Programms
```go
fmt.Println("Addition: ", addiere(3,5)) // Ausgabe: Addition: 8
```

### 📝 Aufgabe
✅ Ziel: Passe Dein Programm auf Replit so an dass es 3 und 5 addiert und ausgibt.

1. Gehe auf [replit.com](https://replit.com) und erstelle ein neues Go-Projekt.
2. Einfügen der Funktion **addiere()** und Anpassen des fmt.Println Befehls

So ähnlich müsste Dein Code dann aussehen:
```go
package main

import (
    "fmt"
)

func addiere(a int, b int) int {
    return a + b
}

func main() {
    fmt.Println("Addition: ", addiere(3,5))
}
```

## ✅ Mehrere Rückgabewerte
Funktionen in Go können mehrere Werte zurückgeben:
```go
func teile(zahl int) (int, int) {
    return zahl / 2, zahl % 2
}
```

Aufruf:
```go
ganz, rest := teile(9)
fmt.Println(ganz, rest) // Ausgabe: 4 1
```

## 🔒 Rückgabewerte benennen (optional)
Dies wird eher selten verwendet und ist untypisch für Go Programme
```go
func mult(a, b int) (ergebnis int) {
    ergebnis = a * b
    return // explizites `return ergebnis` nicht nötig
}
```

## 🔁 Funktionen mit mehreren Rückgabewerten

Go erlaubt es dir, **mehrere Werte gleichzeitig** aus einer Funktion zurückzugeben. Das ist besonders nützlich, wenn du neben einem Ergebnis auch einen Fehler oder zusätzliche Informationen liefern möchtest. Die Rückgabewerte werden in Klammern angegeben und durch Kommas getrennt.

### Beispiel:
```go
func teile(a int) (int, int) {
    return a / 2, a % 2
}
```

Diese Funktion gibt sowohl den ganzzahligen Quotienten als auch den Rest einer Division zurück.

### Aufruf:
```go
ganz, rest := teile(9)
fmt.Println(ganz, rest) // Ausgabe: 4 1
```

Mehrere Rückgabewerte machen den Code in Go klarer und vermeiden den Einsatz komplexer Strukturen oder spezieller Objekttypen wie in anderen Sprachen.

Sehr häufig werden mehrere Rückgabeparameter verwendet um neben dem Ergebnis auch ein **error** Objket mitzugeben, dazu später aber mehr.

## 📌 Fazit

- Funktionen definierst du mit dem Schlüsselwort `func`.
- Du kannst **Parameter und Rückgabewerte** festlegen.
- Go erlaubt **mehrere Rückgabewerte**.
- Funktionen sind **erstklassige Objekte** (du kannst sie als Werte speichern und übergeben).
- Funktionen sind ein idealer Einstieg, um **Logik zu strukturieren** und **Code wiederverwendbar** zu machen!