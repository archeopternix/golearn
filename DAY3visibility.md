# 🔓 Sichtbarkeit und exportierte Namen in Go

In Go ist ein Name **exportiert**, wenn er mit einem **Großbuchstaben** beginnt. Das heisst, das
Du nur innerhalb des Paketes auf **nicht exportiert** Namen zugreifen kannst. Dies hilft Dir, bei großen Programmen
mit vielen Paketen, die komplexen internen Details der Pakete zu verstecken. So zeigt Dir z.B. die 
Autovervollständigung der Editoren Dir diese **nicht exportiert** Namen nicht an und Du kannst den gleichen 
Namen in verschiedenen Paketen verwenden.

## 📌 Beispiele:

- ✅ `Pizza` ist exportiert → sichtbar außerhalb des Pakets.
- ✅ `Pi` ist exportiert → z. B. `math.Pi` aus dem `math`-Paket.
- ❌ `pizza` ist **nicht exportiert** → nur innerhalb des eigenen Pakets sichtbar.
- ❌ `pi` ist **nicht exportiert** → nicht zugreifbar von außen.

---

## 📦 Zugriff bei Importen

Wenn du ein Paket importierst, kannst du **nur auf exportierte Namen** zugreifen.

Unexportierte Namen (die mit Kleinbuchstaben beginnen) sind **nicht zugänglich von außerhalb** des Pakets.

---

## ❗ Fehlerbeispiel

Wenn du versuchst, auf `math.pi` zuzugreifen, bekommst du einen Fehler:
```go
fmt.Println(math.pi) // Fehler: pi ist nicht exportiert
```

### ✅ Lösung: Verwende math.Pi (mit Großbuchstaben):
```go
fmt.Println(math.Pi)
```

## 🧠 Merke:
In Go entscheidet der **erste Buchstabe** eines Namens darüber, ob dieser **öffentlich** (exportiert) oder **privat** (nicht exportiert) ist.