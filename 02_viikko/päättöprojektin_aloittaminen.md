# Staattisen HTML-projektin luominen

Staattisen HTML-projektin luominen on ensimmäinen askel verkkosivuston rakentamisessa. Tämä ohje opastaa sinut yksinkertaisen projektirakenteen luomisessa HTML-, CSS- ja JavaScript-tiedostoillesi.

## Vaihe 1: Luo projektikansio

1. **Luo uusi kansio:**

   - Nimeä se kuvaavasti, esimerkiksi `verkkosivuni` tai `html-projekti`.

2. **Luo kansion sisälle alikansiot:**
   - `css/`: Tyylitiedostoja varten.
   - `js/`: JavaScript-tiedostoja varten.
   - `images/`: Kuvien tai mediatiedostojen tallentamiseen.

Kansiorakenteen tulisi näyttää tältä:

```
verkkosivuni/
├── css/
├── js/
├── images/
└── index.html
```

---

## Vaihe 2: Luo HTML-tiedosto

1. **Luo `index.html`-niminen tiedosto** projektikansion juureen.
2. Lisää perus-HTML-rakenne:

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Oma staattinen verkkosivu</title>
    <link rel="stylesheet" href="css/styles.css" />
  </head>
  <body>
    <h1>Tervetuloa omalle staattiselle verkkosivulleni</h1>
    <p>Tämä on yksinkertainen staattisen HTML-projektin rakenne.</p>
    <script src="js/script.js"></script>
  </body>
</html>
```

## Vaihe 3: Lisää CSS-tiedosto

1. Luo `css/`-kansioon tiedosto nimeltä `styles.css`.
2. Lisää joitakin perustyylejä:

```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f9;
  color: #333;
}

h1 {
  color: #0056b3;
  text-align: center;
  margin-top: 20px;
}
```

## Vaihe 4: Lisää JavaScript-tiedosto

1. Luo `js/`-kansioon tiedosto nimeltä `script.js`.
2. Lisää yksinkertainen skripti:

```javascript
console.log("Hello, world! Welcome to my static website.");
```

## Vaihe 5: Testaa projektisi

1. Avaa `index.html`-tiedosto selaimessa kaksoisnapsauttamalla sitä.
2. Varmista, että:
   - Teksti näkyy sovelletuilla tyyleillä.
   - Selaimen konsolissa näkyy viesti `script.js`-tiedostosta.

## Vaihe 6: Valinnaisia lisäyksiä

### Lisää sivuja

- Luo lisää HTML-tiedostoja, kuten `about.html` tai `contact.html`.
- Linkitä ne käyttäen `<a>`-tageja:
  ```html
  <a href="about.html">About</a>
  ```

### Järjestä kuvat

- Sijoita kaikki kuvatiedostot `images/`-kansioon.
- Käytä suhteellisia polkuja lisätäksesi kuvat HTML-tiedostoon:
  ```html
  <img src="images/photo.jpg" alt="A sample image" />
  ```

### Lisää favicon

- Sijoita pieni kuva (esim. `favicon.ico`) juurikansioon.
- Linkitä se `<head>`-osiossa:
  ```html
  <link rel="icon" href="favicon.ico" type="image/x-icon" />
  ```

## Lopullinen projektikansiorakenne

```
verkkosivuni/
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── images/
│   └── photo.jpg
├── favicon.ico
└── index.html
```
