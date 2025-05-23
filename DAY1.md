# 🧱 Aufbau eines einfachen Go-Programms

Ein Go-Programm besteht aus klar definierten Strukturen. Hier ist ein typisches Beispiel und die Erklärung der einzelnen Bestandteile:

---

## 📄 Beispiel: Einfaches Go-Programm

```go
package main

import "fmt"

func main() {
    fmt.Println("Hallo, Welt!")
}
```

# 🧩 Erklärung der Bestandteile eines Go-Programms

## 1. `package main`

- Jedes Go-Programm beginnt mit einer **package-Deklaration**.
- Das `main`-Paket ist besonders:
  - Es markiert den **Einstiegspunkt** eines ausführbaren Programms.
  - Ohne `main`-Paket kann kein ausführbares Programm erzeugt werden.

---

## 2. `import "fmt"`

- Mit dem **`import`-Statement** binden wir externe oder Standard-Bibliotheken ein.
- `"fmt"` ist Teil der **Go-Standardbibliothek**.
  - Es steht für **Formatierung**, z. B. zur Textausgabe auf der Konsole.

---

## 3. `func main()`

- Dies ist die **Hauptfunktion** eines Go-Programms.
- Das Programm **startet immer bei `main()`**.
- Sie muss im Paket `main` definiert sein.

---

## 4. `fmt.Println("Hallo, Welt!")`

- `fmt.Println()` gibt einen Text in die Konsole aus.
- Verwendet das Paket `fmt`, da im eigentlichen Sprachumfang von Go keine Ausgabefuntionen enthalten sind

---

# 📦 Struktur größerer Programme

Größere Programme bestehen typischerweise aus mehreren Dateien und Paketen:

```text
projekt/
├── main.go         → Einstiegspunkt (package main)
├── rechner/
│   └── plus.go     → Eigene Funktionen (package rechner)
└── util/
    └── helper.go   → Hilfsfunktionen (package util)

## 📌 Fazit

Der Aufbau eines Go-Programms ist:

- ✅ **Paketdefinition** mit `package`
- ✅ **Optionale Importe** mit `import`
- ✅ **Funktionen**, insbesondere `func main()`
- ✅ **Klare und einfache Syntax**

👉 Damit ist **Go perfekt geeignet für einen schnellen Einstieg** –  
und für **sauberen, wartbaren Code**.
