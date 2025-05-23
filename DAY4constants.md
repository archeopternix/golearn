# 🔒 Konstanten in Go (Golang)

In Go kannst du mit dem **`const`**-Schlüsselwort **Konstanten** definieren. Konstanten sind **unveränderliche Werte**, die **beim Kompilieren feststehen** und sich **zur Laufzeit nicht ändern** lassen.

## 🧱 Warum Konstanten?

- Sie machen den Code **leichter verständlich**.
- Du vermeidest **versehentliches Überschreiben** wichtiger Werte.
- Sie verbessern die **Wartbarkeit** deines Programms.

---

## 🧪 Beispiel
```go
package main

import "fmt"

const pi = 3.14

func main() {
    fmt.Println("Der Wert von Pi ist:", pi)
}
```

pi ist hier eine Konstante. Du kannst sie lesen, aber nicht verändern.

## 🔤 Konstante Zeichenketten
Auch Zeichenketten (Strings) können konstant sein:
```go
const name = "Gopher"
fmt.Println("Hallo", name)
```

## 🔄 Unterschied zu Variablen

| Konstante (`const`)                   | Variable (`var`)                     |
|--------------------------------------|--------------------------------------|
| Wert ändert sich **nie**             | Wert **kann geändert** werden        |
| Muss beim Deklarieren **zugewiesen** werden | Kann **später zugewiesen** werden |
| Wird **zur Compile-Zeit** bestimmt   | Wird **zur Laufzeit** bestimmt       |

---

## 🧠 Merke

- Verwende `const`, wenn sich ein Wert **niemals ändern** soll.
- Konstanten geben deinem Code **Klarheit** und **Sicherheit**.
- Sie funktionieren mit **einfachen Datentypen** wie `int`, `float`, `string`, `bool`.