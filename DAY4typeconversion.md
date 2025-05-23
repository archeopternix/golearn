# 🔄 Typkonvertierung in Go

In Go musst du Datentypen explizit konvertieren, wenn du z. B. eine Variable von einem Typ in einen anderen umwandeln möchtest.

## Syntax

```go
neuerWert := Typ(variable)
```
Dabei ist Typ der gewünschte Zieltyp.

Beispiel:
```go
package main

import (
    "fmt"
)

func main() {
    var i int = 42
    var f float64 = float64(i)       // int → float64
    var u uint = uint(f)             // float64 → uint

    fmt.Println(i)  // Ausgabe: 42
    fmt.Println(f)  // Ausgabe: 42
    fmt.Println(u)  // Ausgabe: 42
}
```

### 📝 Aufgabe
✅ Erstelle ein Programm auf Replit bei dem Du 
- Eine Variable mit `55.67` initialisierst
- Diese Variable mit `fmt.Println()` ausgibst
- Eine neue Variable vom Typ `int` anlegst und den Wert der ersten Variable konvertierst (float64 → int)
- Diese neue Variable mit `fmt.Println()` ausgibst

Das Programm wird so aussehen:
```go
package main
import (
    "fmt"
)

func main() {
    f:= 55.67
    fmt.Println(f)
    i := int(f)
    fmt.Println(i)
}
```

### ▶️ Ergebnis
Das Ergebnis wird folgendermaßen aussehen:
```go
55.67
55
```
Der Grund hierfür ist, dass `int` nur Ganzzahlen speichern kann und bei der Konvertierung werden natürlich die Nachkommstellen abgeschnitten. 
Deswegen führt Go auch keine automatischen Konvertierungen durch, da hierbei sonst sehr schwer zu entdeckende Fehler entstehen könnten (Go ist immer nachvollziehbar und transparent). 


## 🧠 Merke

- Automatische Typumwandlung gibt es nicht! Du musst immer explizit konvertieren.  
- Bei der Konvertierung kann es zu Datenverlust kommen, z. B. bei `float` → `int`.  
- Typkonvertierung funktioniert nur zwischen kompatiblen Typen.

## Zusammenfassung

- Typkonvertierung erfolgt mit `Typ(variable)`.  
- Immer explizit in Go, keine implizite Konvertierung.  
- Achte auf mögliche Verluste bei der Konvertierung.