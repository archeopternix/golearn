# 📦 Aufbau eines Go-Programms mit Paketen

Jedes Go-Programm besteht aus **Paketen** (engl. packages), die einzelne Funktionseinheiten gruppieren. Pakete ermöglichen die Strukturierung und Wiederverwendbarkeit von Code.

## ▶️ Startpunkt

Ein ausführbares Go-Programm beginnt immer im Paket main. Die Datei, die das Paket main deklariert und die Funktion main() enthält, ist der Einstiegspunkt (Startpunkt) des Programms. Ohne package main wird beim Kompilieren kein lauffähiges Programm erzeugt. 
```go
package main
```


## 📥 Importe

Go erlaubt es, mit der import-Anweisung andere Pakete einzubinden. Wenn nur ein Paket verwendet wird reicht folgende Form:

  	```go
  	import "fmt"
	```

In unserem Beispiel werden jedoch die Pakete `"fmt"` und `"math/rand"` verwendet.
Diese werden jeweils in einer eigenen Zeile nach dem `import`-Statement und innerhalb einer runden Klammer eingebunden:

  import (
      "fmt"
      "math/rand"
  )

In diesem Fall wird das Paket "fmt" (für Formatierungen wie Println) und das Paket "math/rand" (für Zufallszahlen) eingebunden.

## 📛 Namenskonvention

Nach Konvention ist der **Name eines Pakets identisch mit dem letzten Element seines Importpfads**:

- Der Import:

 	```go
  	import "math/rand"
	```

Die Quelldateien dieses Pakets beginnen daher mit:

	```go
	package rand
	```

Das bedeutet: Obwohl der vollständige Importpfad "math/rand" lautet, wird im Code nur der Kurzname rand verwendet:

	```go
	rand.Intn(100) // Zugriff auf eine Funktion des Pakets rand
	```
	
So bleibt der Code übersichtlich, und es ist sofort klar, zu welchem Paket ein Funktionsaufruf gehört.

## 📝 Aufgabe

✅ Ziel: Dein Programm soll bei jedem Start eine neue Zufallszahl ausgeben.

1. Gehe auf [replit.com](https://replit.com) und erstelle ein neues Go-Projekt.
2. Importiere das Paket `math/rand` 
3. Ändere die Ausgabe von:

   ```go
   fmt.Println("Hallo Welt")
	```
	
	zu

   ```go
   fmt.Println(rand.Intn(100))
	```
	
4. Klicke mehrmals auf „Run“, um dein Programm auszuführen. Beobachte wie sich die Zahl ändert
