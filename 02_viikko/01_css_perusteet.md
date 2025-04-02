# CSS:n perusteet

Cascading Style Sheets (CSS) tekee verkosta visuaalisesti houkuttelevan määrittelemällä, miten HTML-elementit tyylitellään ja asetellaan. Tässä on aloittelijaystävällinen yleiskatsaus CSS:ään.

## Mikä on CSS?

- CSS on lyhenne sanoista **Cascading Style Sheets** (vapaasti suomennettuna "vaikuttavat tyylisivut").
- Se hallitsee verkkosivun ulkoasua ja tuntumaa, mukaan lukien asettelu, värit, fontit ja paljon muuta.
- CSS erottaa **sisällön** (HTML) ja **esitystavan** (tyylittelyn).

## CSS-syntaksi ja valitsimet

### CSS-syntaksi

CSS-säännöt kirjoitetaan yksinkertaisessa muodossa:

```css
valitsin {
  ominaisuus: arvo;
}
```

- **Valitsin:** Kohdistaa tyylin HTML-elementtiin/-elementteihin.
- **Ominaisuus:** Määrittelee, mitä tyylitellään (esim. väri, fonttikoko).
- **Arvo:** Määrittelee halutun tyylin.

Esimerkki:

```css
h1 {
  color: blue;
  font-size: 24px;
}
```

### Valitsimet

Valitsimet määrittelevät, mihin HTML-elementteihin CSS-säännöt vaikuttavat:

- **Tyyppivalitsin:** Kohdistaa elementteihin niiden tunnisteen (tagin) perusteella.

  ```css
  p {
    color: red;
  }
  ```

- **Luokkavalitsin:** Kohdistaa elementteihin, joilla on tietty luokka.

  ```css
  .highlight {
    background-color: yellow;
  }
  ```

- **ID-valitsin:** Kohdistaa yksittäiseen elementtiin sen ID:n perusteella.

  ```css
  #main-title {
    text-align: center;
  }
  ```

- **Yleisvalitsin:** Kohdistaa kaikkiin elementteihin.
  ```css
  * {
    margin: 0;
  }
  ```

## CSS:n lisääminen HTML:ään

1. **Sisäinen CSS** (HTML-elementin sisällä):

   ```html
   <p style="color: green;">Tämä teksti on vihreä.</p>
   ```

2. **Sisäinen tyylisääntö** (HTML-tiedoston `<head>`-osassa `<style>`-tagin sisällä):

   ```html
   <style>
     body {
       font-family: Arial, sans-serif;
     }
   </style>
   ```

3. **Ulkoinen CSS** (erillisessä `.css`-tiedostossa):
   ```html
   <link rel="stylesheet" href="styles.css" />
   ```
   - Suositeltavaa suurissa projekteissa, koska se pitää HTML:n siistinä ja uudelleenkäytettävänä.

## Kommentit

CSS-kommentit auttavat dokumentoimaan koodiasi:

```css
/* Tämä on kommentti CSS:ssä */
h1 {
  color: blue;
} /* Otsikoiden tyyli */
```

- Selaimet ohittavat kommentit, ja niitä käytetään huomautusten tai selitysten jättämiseen.

## Perustason CSS aloittamiseen

### HTML-elementtien tyylitys

#### Otsikot ja kappaleet

```css
h1 {
  font-size: 32px;
  color: navy;
}
p {
  color: gray;
  line-height: 1.5;
}
```

#### Listat

```css
ul {
  list-style-type: square;
  padding-left: 20px;
}
ol {
  list-style-type: decimal;
  padding-left: 20px;
}
```

#### Linkit

```css
a {
  color: blue;
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
  color: darkblue;
}
```

#### Kuvat

```css
img {
  max-width: 100%;
  height: auto;
  border: 1px solid #ccc;
}
```

### Sivun asettelu ja tausta

```css
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f9f9f9;
}
```

## Käytännön esimerkki

Tämä esimerkki yhdistää semanttiset HTML-elementit ja perustason CSS-tyylityksen:

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Semanttinen HTML ja CSS</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        margin: 20px;
        background-color: #f9f9f9;
      }
      h1 {
        color: navy;
        font-size: 28px;
      }
      p {
        color: gray;
        line-height: 1.6;
      }
      a {
        color: blue;
        text-decoration: none;
      }
      a:hover {
        text-decoration: underline;
        color: darkblue;
      }
    </style>
  </head>
  <body>
    <h1>Tervetuloa semanttiseen HTML:ään ja CSS:ään</h1>
    <p>
      Tämä sivu havainnollistaa, miten semanttisia HTML-elementtejä tyylitellään
      CSS:n avulla.
    </p>
    <a href="#">Lue lisää</a>
  </body>
</html>
```
