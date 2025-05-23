# 🔁 Schleifen in Go: `for`

In Go gibt es nur **eine Schleifenform**: die `for`-Schleife. Sie ist sehr flexibel und kann verschiedene Formen annehmen – ähnlich wie `while` oder `do...while` in anderen Sprachen.

---

## 1. Endlosschleife
Die einfachste Schleifenform ist die Endlosschleife. Das Programm läuft so lange in dieser Schleife, bis es durch `break` oder `return` abgebrochen wird, oder das Programm durch Schließen beendet wird.
```go
for {
    fmt.Println("unendlich")
}
```

---

## 2. `for` Schleife mit Abbruch Kriterium
Die Schleife wir so lange durchlaufen bis das Abbruch Kriterium ereicht wird
```go
i := 0
for i < 5 {
    fmt.Println(i)
    i++
}
```

Anmerkung: `i++` erhöht den Wert von `i` um `1`

---

## 3. Klassische `for`-Schleife (mit Zähler)
Die Schleifer erhält einen Startwert `i := 0`; ein Abbruchkriterium `i < 5`; und eine Zählerhochlauf (inkrement) `i++`
```go
for i := 0; i < 5; i++ {
    fmt.Println(i)
}
```

---

## 4. Schleifen mit range (über Arrays, Slices, Maps, Strings)
`range` gibt bei jedem Durchlauf den Index und den Einzelwert zurück. Du kannst den 
Index oder den Wert mit `_` ignorieren, wenn du ihn nicht brauchst.
```go
numbers := []int{10, 20, 30}
for index, value := range numbers {
    fmt.Println(index, value)
}
```

### 📝 Aufgabe 1
Erstelle ein Programm auf Replit bei dem Du 
- Alle 2'er Potenzen bis 16384 per `fmt.Println()` ausgibst

### ▶️ Lösung
```go
package main
import (
    "fmt"
)

func main() {
    // Print all powers of 2 up to 16384
    fmt.Println("Powers of 2 up to 16384:")
    
    // Start with 2^0 = 1, then keep multiplying by 2
    power := 1
    for power <= 16384 {
        fmt.Println(power)
        power = power * 2  // Multiply by 2 to get next power
    }
}
```

Jetzt schreibe das Programm so um dass Du eine klassische `for` Schleife verwendest.

### 📝 Aufgabe 2
Erstelle ein Programm auf Replit bei dem Du 
- alle `animals := []string{"Lion", "Zebra", "Snake"}` per `for..range` durchläufst und per `fmt.Println()` ausgibst

### ▶️ Lösung
```go
package main
import (
    "fmt"
)

func main() {
    // Create a slice (array) of animals
    animals := []string{"Lion", "Zebra", "Snake"}

    // Print each animal one by one
    fmt.Println("Animals:")
    for _, animal := range animals {
        fmt.Println(animal)
    }
}
```

## Zusammenfassung

- Go verwendet nur das `for`-Schlüsselwort für **alle Schleifenarten**.
- Mit `break` kannst du Schleifen **beenden**.
- Mit `continue` springst du direkt **zum nächsten Durchlauf**.