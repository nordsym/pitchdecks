# Plan: Byt ut stockfoton mot riktiga Guldkant-bilder

## Nuläge
Presentationen använder 3 generiska Unsplash-bilder. 6 autentiska Guldkant-foton finns i `assets/`.

---

## Bildkatalog

| Fil | Motiv | Karaktär |
|-----|-------|----------|
| `guldkant2023-11.jpg` | Servitör lägger ved i brasan, dukat bord | Personal i action, värme |
| `guldkant2023-13.jpg` | Interiör med brasa, bord, monstera-växter | Översikt, kvällsstämning |
| `guldkant2023-30.jpg` | Bardisken, barstolar, rutigt golv | Klassisk bistro |
| `guldkant2023-33.jpg` | Vaxljus i vinflaskor, Louis Moreau | Stämningsdetalj |
| `guldkant2023-43.jpg` | Matsalen brett, gardiner, dukade bord | Helhetsbild av lokalen |
| `guldkant2023-56.jpg` | Kvällsdukning, lampor, utsikt mot stan | Elegant avslut |

---

## Ersättningsplan

| CSS-klass | Slide | Nuvarande | Ersätt med | Motivering |
|-----------|-------|-----------|------------|------------|
| `.hero-bg` | 1 (Hero) | Unsplash restaurang | **guldkant2023-13.jpg** | Visar Guldkants själ - brasa, värme, stämning |
| `.restaurant-bg` | 3 (Varumärke) | Unsplash mat | **guldkant2023-43.jpg** | Bred översikt visar konceptet |
| `.restaurant-bg` | 7 (Karriär) | Samma som ovan | **guldkant2023-11.jpg** | Personal i action = karriär |
| `.kitchen-bg` | 8 (Avslutning) | Unsplash kök | **guldkant2023-56.jpg** | Elegant kvällsbild som avslut |

---

## Teknisk implementation

### Steg 1: Lägg till ny CSS-klass för Karriär-sliden
Slide 3 och 7 använder samma `.restaurant-bg`. Behöver separata klasser:

```css
/* Slide 3 - Varumärke */
.restaurant-bg {
    background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.5)),
                url('assets/guldkant2023-43.jpg');
}

/* Slide 7 - Karriär (NY KLASS) */
.career-bg {
    background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.5)),
                url('assets/guldkant2023-11.jpg');
}
```

### Steg 2: Uppdatera alla URL:er

```
Rad 96:  unsplash...4c7edcad34c4 → assets/guldkant2023-13.jpg
Rad 103: unsplash...338989a2e8c0 → assets/guldkant2023-43.jpg
Rad 110: unsplash...1c02745aae4d → assets/guldkant2023-56.jpg
+ Ny:    career-bg               → assets/guldkant2023-11.jpg
```

### Steg 3: Ändra HTML för Slide 7
```html
<!-- Rad ~1046: Ändra restaurant-bg till career-bg -->
<div class="split-right career-bg lg:w-1/3 min-h-[50vh] lg:min-h-full">
```

---

## Oanvända bilder

| Fil | Potentiell användning |
|-----|----------------------|
| `guldkant2023-30.jpg` | Alternativ för bar-tema eller framtida slide |
| `guldkant2023-33.jpg` | Detalj-slide eller social media |

---

## Sammanfattning

```
Slide 1 (Hero)      → guldkant2023-13.jpg  (brasa + interiör)
Slide 3 (Varumärke) → guldkant2023-43.jpg  (matsalen)
Slide 7 (Karriär)   → guldkant2023-11.jpg  (personal)
Slide 8 (Avslut)    → guldkant2023-56.jpg  (kvällsstämning)
```

**Väntar på godkännande innan implementation.**
