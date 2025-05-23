# 🐹 Lernplan: Go (Golang) Lernen in 8 Wochen


## 🎯 Ziel
Die Grundlagen von Go beherrschen, um produktiv Software, Tools, APIs und ggf. GUIs oder Microservices zu entwickeln.
Der Zeitaufwand bewegt sich zwischen 10-60 Minuten pro Tag.

---

## 📚 Woche 1: Einführung in Go

### Inhalte
- [🐣 Tag 0: Was ist Go? Und warum ist es ideal für Einsteiger?](DAY0.md)

- Go installieren ([golang.org/dl](https://golang.org/dl/))
- `go run`, `go build`, `go mod init`
- Syntax: Variablen, Konstanten, Datentypen

### Ressourcen
- [Tour of Go](https://tour.golang.org/)

### Übung
- Kleines CLI-Tool: Hello World, Variablenformatierer

---

## 📘 Woche 2: Funktionen & Kontrollstrukturen

### Inhalte
- Funktionen
- Kontrollstrukturen (if, switch, for, range)

### Ressourcen
- [Go by Example](https://gobyexample.com/)

### Übung
- CLI-Taschenrechner mit Benutzereingabe

### Inhalte
- Was ist Go? Warum Go?
- Go installieren ([golang.org/dl](https://golang.org/dl/))
- `go run`, `go build`, `go mod init`
- Syntax: Variablen, Konstanten, Datentypen
- Funktionen
- Kontrollstrukturen (if, switch, for, range)

### Ressourcen
- [Tour of Go](https://tour.golang.org/)
- [Go by Example](https://gobyexample.com/)

### Übung
- Kleines CLI-Tool: z. B. Taschenrechner oder Währungsrechner

---
---

## 🧠 Woche 3: Datenstrukturen & Fehlerbehandlung

### Inhalte
- Arrays, Slices, Maps
- Structs und Methoden
- Fehlerbehandlung (`error`, `errors.New`, `fmt.Errorf`, `panic`, `recover`)

### Übung
- Structs für eine einfache Buchhaltung oder To-Do-App
- Fehler sauber behandeln

---

## 🔄 Woche 4: Pakete, Module und Concurrency Basics

### Inhalte
- `go mod`, `go get`, Struktur eines Go-Projekts
- Standardbibliothek: `fmt`, `os`, `io`, `time`
- Goroutines und Channels (Einführung)

### Übung
- Schreibe ein CLI-Tool, das mehrere Websites gleichzeitig „pingt“ (mit Goroutines und Channels)

---

## 🌐 Woche 5: HTTP, JSON und REST-APIs

### Inhalte
- HTTP-Client/Server (`net/http`)
- JSON Marshalling/Unmarshalling (`encoding/json`)
- REST API entwickeln (z. B. einfache Notizen-API)

### Übung
- Eigene API schreiben, z. B. für To-Dos
- Client schreiben, der die API verwendet

---

## 💾 Woche 6: Dateien, Datenbanken und Testing

### Inhalte
- Dateien lesen/schreiben (`os`, `io/ioutil`)
- SQLite oder PostgreSQL mit Go (z. B. `database/sql` + `lib/pq` oder `sqlite`)
- Unit-Testing (`testing` Package)

### Übung
- Erweiterung der Notizen-API mit Datenbank
- Tests schreiben (Unit + evtl. Integration)

---

## 🔀 Woche 7: Fortgeschrittene Themen

### Inhalte
- Concurrency vertieft: `select`, `sync`, `context`
- Interfaces und Polymorphismus in Go
- Custom Packages

### Übung
- Ein Microservice, der Daten verarbeitet (z. B. Statistik über Anfragen)

---

## 🧩 Woche 8: Projekt und Deployment

### Inhalte
- Go-Projekt strukturieren
- Logging (`log`, `logrus`, `zerolog`)
- Deployment: Binary bauen, mit Docker verpacken
- Optional: GUI mit go-fltk oder Web-Frontend mit JS

### Abschlussprojekt-Ideen
- Task-Manager mit REST API + CLI
- Monitoring-Tool für Server
- Web-Scraper mit JSON-Export

---

## ✅ Tools und Ressourcen

- **Editor:** GoLand, VS Code mit Go-Plugin
- **Playground:** https://play.golang.org/
- **Dokumentation:** https://pkg.go.dev/
- **Go Patterns:** https://github.com/tmrts/go-patterns
