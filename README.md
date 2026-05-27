# Smutny Pan — Jekyll

Template strony Smutny Pan oparty na Jekyllu. Łatwa edycja filmów przez plik YAML.

---

## Szybki start

### 1. Zainstaluj Jekylla (jeśli nie masz)

```bash
gem install bundler jekyll
```

### 2. Zainstaluj zależności

```bash
cd smutny-pan-jekyll
bundle install
```

### 3. Uruchom lokalnie

```bash
bundle exec jekyll serve
```

Strona dostępna pod `http://localhost:4000`

### 4. Zbuduj wersję produkcyjną

```bash
bundle exec jekyll build
```

Wynik w folderze `_site/` — wgraj na hosting.

---

## Jak dodawać / zmieniać filmy

**Edytuj jeden plik:** `_data/videos.yml`

### Główny film (hero / embed)

```yaml
featured:
  id: "TWOJE_ID_YOUTUBE"
  title: "Tytuł filmu"
  caption: "\"Cytat lub opis nad wideo\""
  subcaption: "Podtytuł pod cytatem"
```

### Lista innych filmów

```yaml
others:
  - id: "ID_PIERWSZEGO"
    title: "Tytuł"
    views: "123 wyświetleń"
    date: "2 miesiące temu"

  - id: "ID_DRUGIEGO"
    title: "Kolejny tytuł"
    views: "456 wyświetleń"
    date: "3 miesiące temu"
```

### Gdzie znaleźć ID YouTube?

Adres: `https://www.youtube.com/watch?v=**7Jm0tuHQAoc**`

ID to część po `v=`: `7Jm0tuHQAoc`

---

## Jak zmienić dane strony

Edytuj `_config.yml`:

```yaml
title: "Smutny Pan — piosenki z rysunkami"
description: "Twój nowy opis..."
url: "https://twojadomena.pl"

author:
  youtube: "smutny_pan"      # nazwa kanału
  instagram: "smutnypan.art" # nazwa profilu
  spotify: "TWOJE_ID"        # ID artysty na Spotify
```

Po zmianie `_config.yml` **zrestartuj** Jekylla (Ctrl+C, potem `bundle exec jekyll serve`).

---

## Struktura plików

```
smutny-pan-jekyll/
├── _config.yml          # Ustawienia strony
├── _data/
│   └── videos.yml       # <-- TU EDYTUJESZ FILMY
├── _layouts/
│   └── default.html     # Szablon strony (nie ruszaj)
├── index.md             # Strona główna (nie ruszaj)
├── piotrek.jpg          # Zdjęcie w nagłówku
├── Gemfile              # Zależności Ruby
└── README.md            # Ten plik
```

---

## Wdrażanie na GitHub Pages

1. Wrzuć repo na GitHub
2. W Settings > Pages ustaw Source na branch `main`, folder `/(root)`
3. Strona zbuduje się automatycznie

Upewnij się, że w `_config.yml` masz poprawne `url` i `baseurl` (zostaw `baseurl: ""` dla custom domain).
