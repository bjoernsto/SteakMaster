# 🤝 Contributing Guide

Danke, dass du zu **Steak Master** beitragen möchtest!

---

## 🐛 Bug melden

1. Prüfe die [Issues](../../issues) auf Duplikate
2. Öffne ein neues Issue mit Label `bug`
3. Beschreibe: erwartet vs. tatsächlich, Browser/OS, Screenshot

---

## 💡 Feature vorschlagen

Öffne ein Issue mit Label `enhancement` und beschreibe Funktion + Nutzen.
Bitte auf Feedback warten bevor du mit der Implementierung beginnst.

---

## 🔧 Code beitragen

```bash
# 1. Fork & klonen
git clone https://github.com/DEIN-USERNAME/steak-master.git
cd steak-master

# 2. Branch erstellen
git checkout -b feature/mein-feature

# 3. Lokaler Dev-Server
python3 -m http.server 8080
# → http://localhost:8080/steak-timer.html
```

### Commit-Konventionen

```
feat: neue Funktion
fix: Bug behoben
docs: Dokumentation
style: Formatierung
refactor: Umbau ohne Logikänderung
perf: Performance
```

### Pull Request

1. `git push origin feature/mein-feature`
2. PR auf GitHub öffnen
3. Zugehöriges Issue verlinken mit `Closes #123`

---

## 📋 Code-Style

- Reines HTML/CSS/JS — kein Framework
- Einrückung: 2 Spaces
- CSS-Variablen für alle Farben (`:root` in der HTML-Datei)
- Deutsche oder englische Kommentare sind okay

---

## 📄 Lizenz

Mit deinem Beitrag stimmst du der Veröffentlichung unter der [MIT Lizenz](LICENSE) zu.
