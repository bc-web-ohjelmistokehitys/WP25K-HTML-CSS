# CSS-fontit, värit ja taustat

## Fontit CSS:ssä

### Fonttiperheen määrittäminen

CSS:n avulla voit määrittää tekstin fonttityylin käyttämällä `font-family`-ominaisuutta.

```css
body {
  font-family: Arial, sans-serif;
}
```

- Käytä **varafontteja** (fallback fonts), jotta teksti pysyy luettavana, jos ensisijainen fontti ei ole saatavilla.
- Esimerkki: `font-family: 'Roboto', Arial, sans-serif;`

Tässä on **helppo tapa** lisätä Google-fontteja verkkosivullesi kahdella tavalla: **tuomalla CSS:ssä** ja **linkittämällä `<head>`-osiossa**.

### **1. Google-fontin linkittäminen `<head>`-osioon (Suositeltu tapa)**

Tämä on helpoin tapa! Lisää `<link>` HTML-tiedostosi `<head>`-osioon.

#### **Vaiheet:**

1. Mene osoitteeseen [Google Fonts](https://fonts.google.com/).
2. Valitse haluamasi fontti.
3. Kopioi annettu `<link>`-tagi.
4. Liitä se HTML-tiedoston `<head>`-osioon.

```html
<head>
  <link
    href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap"
    rel="stylesheet"
  />
</head>
```

5. Käytä nyt fonttia CSS:ssä:

```css
body {
  font-family: "Open Sans", sans-serif;
}
```

✔️ **Paras aloittelijoille** – nopea ja toimii heti!

### **2. Google-fontin tuominen CSS-tiedostossa**

Tässä menetelmässä Google-fontti tuodaan CSS-tiedoston sisällä `@import`-säännön avulla.

#### **Vaiheet:**

1. Mene osoitteeseen [Google Fonts](https://fonts.google.com/) ja valitse fontti.
2. Kopioi `@import`-linkki.
3. Liitä se **CSS-tiedoston alkuun**.

```css
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap");

body {
  font-family: "Roboto", sans-serif;
}
```

✔️ **Hyvä moduulirakenteisessa CSS:ssä** – mutta fonttien lataus on hieman hitaampaa kuin `<link>`-menetelmällä.

### **Kumpaa kannattaa käyttää?**

- **Käytä `<link>`-menetelmää**, jos haluat nopeamman sivulatauksen ja paremman suorituskyvyn.
- **Käytä `@import`-menetelmää**, jos haluat liittää fontit tietyn CSS-tiedoston sisään.

### Fonttien muotoiluominaisuudet

- `font-size`: Säätää tekstin kokoa.
- `font-weight`: Määrittää tekstin paksuuden (`normal`, `bold`, `lighter` tai numeeriset arvot kuten `400`, `700`).
- `font-style`: `normal`, `italic` tai `oblique`.
- `text-transform`: `uppercase`, `lowercase` tai `capitalize`.

Esimerkki:

```css
h1 {
  font-size: 2rem;
  font-weight: bold;
  text-transform: uppercase;
}
```

## Värit CSS:ssä

### Värien määrittäminen

CSS tukee useita väriformaatteja:

- **Nimetyt värit**: `red`, `blue`, `green`
- **HEX-koodit**: `#ff5733`
- **RGB-arvot**: `rgb(255, 87, 51)`
- **RGBA (läpinäkyvyys)**: `rgba(255, 87, 51, 0.5)`
- **HSL/HSLA**: `hsl(0, 100%, 50%)`

Esimerkki:

```css
p {
  color: #333;
}
```

### Läpinäkyvyyden käyttäminen

RGBA mahdollistaa läpinäkyvyyden säätämisen.

```css
h2 {
  color: rgba(255, 0, 0, 0.5);
}
```

### CSS-muuttujien käyttäminen väreille

CSS-muuttujat helpottavat yhtenäisen värimaailman hallintaa.

```css
:root {
  --primary-color: #3498db;
  --secondary-color: #2ecc71;
}

button {
  background-color: var(--primary-color);
  color: white;
}
```

## Taustat CSS:ssä

### Taustavärin asettaminen

```css
body {
  background-color: #f4f4f4;
}
```

### Taustakuvien lisääminen

```css
.hero {
  background-image: url("background.jpg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
```

- **`background-size`**: `cover` (skaalaa koko alueelle), `contain` (mahtuu sisälle), tai tarkat arvot (`100% 100%`).
- **`background-position`**: `center`, `top left`, `50% 50%`.
- **`background-repeat`**: `no-repeat`, `repeat`, `repeat-x`, `repeat-y`.

### Liukuväritaustat

```css
section {
  background: linear-gradient(to right, #ff7e5f, #feb47b);
}
```

### Peiteväritehoste (Overlay Effect)

Lisätäksesi värillisen peitteen taustakuvan päälle:

```css
.overlay {
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("image.jpg");
  background-size: cover;
}
```

## Parhaat käytännöt

- Käytä luettavia fonttikokoja ja rivivälejä saavutettavuuden takaamiseksi.
- Pysy **rajatussa väripaletissa** yhtenäisen ulkoasun saavuttamiseksi.
- Optimoi taustakuvat, jotta sivun latausaika ei hidastu.
