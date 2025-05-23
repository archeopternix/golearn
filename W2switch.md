# ❓ `switch` in Go – Einfache Fallunterscheidung

In Go ist `switch` eine elegante Möglichkeit, **mehrere Bedingungen** übersichtlich zu prüfen – als Alternative zu mehreren `if...else if`-Blöcken.

---

## 📌 Was ist ein `switch`?

Ein `switch`-Statement vergleicht **einen Ausdruck** mit mehreren möglichen **Fällen (cases)**. Der erste passende Fall wird ausgeführt.

- Du gibst einen Wert oder Ausdruck an, den du vergleichen willst.
- Danach folgen **mehrere `case`-Blöcke**, in denen du mögliche Werte prüfst.
- Wenn ein Fall zutrifft, wird **nur dieser Block ausgeführt** – danach wird das `switch` automatisch beendet (kein `break` nötig wie z. B. in C).
- Optional kannst du einen **`default`-Block** angeben – dieser wird ausgeführt, wenn **kein anderer Fall passt**.

---

## 📌 Einfaches `switch`

```go
package main

import "fmt"

func main() {
    tag := "Montag"

    switch tag {
    case "Montag":
        fmt.Println("Wochenstart!")
    case "Freitag":
        fmt.Println("Fast Wochenende!")
    default:
        fmt.Println("Ein ganz normaler Tag.")
    }
}
```

➡️ Der Ausdruck tag wird mit jedem case verglichen. Bei einem Treffer wird nur dieser Block ausgeführt.

---

## 🔹 switch ohne Ausdruck
Du kannst auch einen switch ohne Vergleichswert schreiben und stattdessen direkt Bedingungen prüfen:
```go
package main

import "fmt"

func main() {
    stunde := 10

    switch {
    case stunde < 12:
        fmt.Println("Guten Morgen!")
    case stunde < 18:
        fmt.Println("Guten Tag!")
    default:
        fmt.Println("Guten Abend!")
    }
}
```

➡️ Diese Form ist vergleichbar mit mehreren if...else if.

---

## 🔸 Mehrere Werte in einem Fall
Ein case kann auch mehrere Werte enthalten:
```go
package main

import "fmt"

func main() {
    zahl := 3

    switch zahl {
    case 1, 3, 5, 7:
        fmt.Println("Ungerade Zahl")
    case 2, 4, 6, 8:
        fmt.Println("Gerade Zahl")
    default:
        fmt.Println("Keine Zahl zwischen 1 und 8")
    }
}
```

---

### 📝 Aufgabe
Füge folgenden Code in Replit ein und lasse ihn laufen
```go
package main

import (
    "fmt"
    "runtime"
)

func main() {
    fmt.Print("Go runs on ")
    switch os := runtime.GOOS; os {
    case "darwin":
        fmt.Println("macOS.")
    case "linux":
        fmt.Println("Linux.")
    default:
        // freebsd, openbsd,
        // plan9, windows...
        fmt.Printf("%s.\n", os)
    }
}
```

Die Funktion `runtime.GOOS` ermittelt das Betriebssystem auf dem das Programm läuft und gibt den Namen auf der Console aus.

Schreibe den Code so um dass nur `if..else` benutzt werden

---

## ✅ Vorteile von `switch`

- **Klarer** als viele `if...else`-Blöcke
- **Einfacher zu lesen** und zu warten
- Automatisches Beenden nach dem ersten passenden `case`
- Unterstützt auch komplexere Vergleiche (z. B. Bedingungen, nicht nur Werte)

---

## 🧠 Merke

- `switch` eignet sich perfekt für **klare Fallunterscheidungen**.
- Kein `break` erforderlich – Go beendet den `switch` automatisch nach einem Treffer.
- Nutze `default`, um einen Standardfall anzugeben.

---

`switch` macht deinen Code **strukturierter und übersichtlicher**, besonders bei vielen Vergleichsfällen.
