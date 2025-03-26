# HTML-listat

Listat ovat keskeinen tapa jäsentää ja esittää sisältöä selkeässä ja luettavassa muodossa. HTML tarjoaa useita erilaisia listatyyppejä eri käyttötarkoituksiin.

## HTML-listojen tyypit

### 1. **Järjestämätön lista (`<ul>`)**

- Näyttää kohteet oletuksena luotipisteillä.
- Soveltuu luetteloihin, joissa järjestyksellä ei ole merkitystä.

```html
<ul>
  <li>Kohta 1</li>
  <li>Kohta 2</li>
  <li>Kohta 3</li>
</ul>
```

### 2. **Järjestetty lista (`<ol>`)**

- Näyttää kohteet numeroilla tai kirjaimilla.
- Soveltuu luetteloihin, joissa järjestyksellä on merkitystä.

```html
<ol>
  <li>Vaihe 1</li>
  <li>Vaihe 2</li>
  <li>Vaihe 3</li>
</ol>
```

### 3. **Määritelmälista (`<dl>`)**

- Käytetään termien ja niiden selitysten määrittelyyn.
- Koostuu elementeistä `<dt>` (termi) ja `<dd>` (määritelmä).

Esimerkki:

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

## Sisäkkäiset listat

Listoja voidaan sisällyttää toisiinsa monitasoisen rakenteen luomiseksi.

```html
<ul>
  <li>
    Hedelmät
    <ul>
      <li>Omena</li>
      <li>Banaani</li>
    </ul>
  </li>
  <li>
    Vihannekset
    <ul>
      <li>Porkkana</li>
      <li>Parsakaali</li>
    </ul>
  </li>
</ul>
```

---

## Listojen attribuutit

### **`type` (järjestetyt listat)**

- Muuttaa numeroinnin tyyliä.
- Arvot: `1`, `A`, `a`, `I`, `i`.

```html
<ol type="A">
  <li>Vaihtoehto A</li>
  <li>Vaihtoehto B</li>
</ol>
```

### **`start` (järjestetyt listat)**

- Määrittää aloitusnumeron.

```html
<ol start="5">
  <li>Kohta 5</li>
  <li>Kohta 6</li>
</ol>
```

### **`reversed` (järjestetyt listat)**

- Näyttää listan käänteisessä järjestyksessä.

```html
<ol reversed>
  <li>Kolmas sija</li>
  <li>Toinen sija</li>
  <li>Ensimmäinen sija</li>
</ol>
```

## Listojen tyylittäminen CSS:llä

### Luotipisteiden poistaminen

```css
ul {
  list-style-type: none;
  padding: 0;
}
```

### Luotipisteiden mukauttaminen

```css
ul {
  list-style-type: square;
}
```

### Merkin sijainnin muuttaminen

```css
ul {
  list-style-position: inside;
}
```

### Järjestettyjen listojen numeroiden tyylittäminen

```css
ol {
  list-style-type: upper-roman;
}
```

## Esimerkki: kattava listojen käyttö

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>HTML-listat</title>
    <style>
      ul {
        list-style-type: square;
        padding-left: 20px;
      }
      ol {
        list-style-type: upper-roman;
        padding-left: 20px;
      }
    </style>
  </head>
  <body>
    <h1>HTML-listat</h1>

    <h2>Järjestämätön lista</h2>
    <ul>
      <li>Omena</li>
      <li>Banaani</li>
      <li>Kirsikka</li>
    </ul>

    <h2>Järjestetty lista</h2>
    <ol type="I">
      <li>Johdanto</li>
      <li>Runko</li>
      <li>Päätelmä</li>
    </ol>

    <h2>Määritelmälista</h2>
    <dl>
      <dt>HTML</dt>
      <dd>HyperText Markup Language</dd>
      <dt>CSS</dt>
      <dd>Cascading Style Sheets</dd>
    </dl>
  </body>
</html>
```
