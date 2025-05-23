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

🔁 Beispiel

Wir erstellen eine Funktion zum Addieren von Zahlen
```go
func addiere(a int, b int) int {
    return a + b
}
```

Wir verwenden diese Funktion gleich in unserem Programms
```go
fmt.Println(addiere(3, 5)) // Ausgabe: 8
```

## 📝 Aufgabe
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
