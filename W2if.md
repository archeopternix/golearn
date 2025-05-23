# ❓ Bedingungen in Go: `if` und `if...else`

In Go kannst du mit `if`-Anweisungen den Ablauf deines Programms steuern – je nachdem, ob eine Bedingung **wahr (true)** oder **falsch (false)** ist.

---

## 🔹 `if`

Mit `if` überprüfst du, ob eine bestimmte Bedingung erfüllt ist. Ist sie **wahr**, wird ein bestimmter Codeblock ausgeführt. Ist sie **falsch**, passiert nichts – außer du ergänzt `else`.
```go
x := 10

if x > 5 {
    fmt.Println("x ist größer als 5")
}
```

---

## 🔸 `if...else`

`else` ergänzt das `if` und gibt eine Alternative an. Wenn die Bedingung des `if` **nicht erfüllt** ist, wird der Code im `else`-Block ausgeführt.
```go
x := 3

if x > 5 {
    fmt.Println("x ist größer als 5")
} else {
    fmt.Println("x ist kleiner oder gleich 5")
}
```

---

## 🔹 `else if`

Mit `else if` kannst du **mehrere Bedingungen hintereinander** prüfen. Der erste Block, dessen Bedingung zutrifft, wird ausgeführt. Alle weiteren werden ignoriert.
```go
x := 5

if x > 10 {
    fmt.Println("x ist größer als 10")
} else if x > 5 {
    fmt.Println("x ist größer als 5")
} else {
    fmt.Println("x ist 5 oder kleiner")
}
```

---

## 🔸 Kurzdeklaration in `if`

In Go kannst du innerhalb eines `if`-Statements eine Variable deklarieren und sie **direkt in der Bedingung** verwenden. Diese Variable existiert **nur im `if`-Block**.
```go
if n := 7; n%2 == 1 {
    fmt.Println("Ungerade Zahl")
}
```

In diesem Fall ist `n` nicht ausserhalb der `if` Bedingung bekannt und kann nicht benutzt werden.

--

### 📝 Aufgabe 1
Erstelle ein Programm, das die Zahlen `1..100` durchläuft und jede Zahl die durch `5` ohne Rest teilbar ist per `fmt.Println()` ausdruckt.

Du kannst mit `n%5 == 0` überprüfen ob eine Zahl durch 7 teilbar ist

--

### ▶️ Lösung
Bedenke, wenn es gefordert ist bis inklusive `100` die Zahlen zu durchlaufen, dass die Abbruchbedingung in der `for` Schleife `<=` (kleiner gleich) sein muss. 
```go
package main
import (
    "fmt"
)

func main() {
    for i := 1; i<=100 ; i++ {
        if i%5==0 {
           fmt.Println(i)
        }
    }
}
```

Probiere aus was passiert wenn Du `<` (kleiner) in der Abbruchbedingung verwendest.

--

### 📝 Aufgabe 2 (schwer)
Erstelle ein Programm dass für jeden einzelnen Wert aus `numbers := []float64{2, 9, 16, 25, 50}` eine Funktion `func sqrt(x float64) float64` aufruft die
die Quadratwurzel einer Zahl mit der Newton's Formel `z -= (z*z - x) / (2*z)` berechnet.
Nimm als Startwert  `z := 1.0` und durchlaufe Newton's Formel 10mal bevor du den wert `z` zurückgibst `return z`

### ▶️ Lösung
Wenn Du das nicht selbst lösen konntest, frag den Agenten in Replit: 
```
implement a square root calculation for the values 2, 9, 16, 25, 50 using Newton's formula
```

```go
package main
import (
    "fmt"
)


// Newton's method square root function
func sqrt(x float64) float64 {
    z := 1.0  // Initial guess

    // Iterate 10 times using Newton's method
    for i := 0; i < 10; i++ {
        z -= (z*z - x) / (2*z)  // Your formula!
        fmt.Printf("Iteration %d: z = %g\n", i+1, z)
    }

    return z
}
func main() {
    // Test the square root function with different numbers
    numbers := []float64{2, 9, 16, 25, 50}

    for _, x := range numbers {
        fmt.Printf("\nCalculating square root of %.0f:\n", x)
        result := sqrt(x)
        fmt.Printf("Final result: %.10f\n", result)
        fmt.Printf("Verification: %.10f * %.10f = %.10f\n", result, result, result*result)
    }
}
```

## ✅ Best Practices

- Schreibe Bedingungen so klar und einfach wie möglich.
- Nutze `else` und `else if` nur, wenn nötig – zu viele verschachtelte Bedingungen machen den Code schwer lesbar.
- Vermeide Wiederholungen und schreibe Bedingungen leserlich (z. B. nicht zu lang).

---

## 🧠 Merke

- `if` prüft, ob etwas zutrifft (true).
- `else` legt fest, was passieren soll, wenn es **nicht zutrifft**.
- `else if` erlaubt dir **mehrere Möglichkeiten** zu prüfen.
- Go verlangt keine Klammern `()` um Bedingungen, aber **geschweifte Klammern `{}`** für Codeblöcke sind **Pflicht**.
