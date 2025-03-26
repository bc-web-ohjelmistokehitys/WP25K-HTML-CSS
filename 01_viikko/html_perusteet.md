# HTML-perusteet

HTML (HyperText Markup Language) on verkkokehityksen perusta. Se tarjoaa verkkosivun rakenteen määrittelemällä sisällön ja sen järjestyksen. Tutustutaan HTML:n olennaisiin käsitteisiin aloitusta varten.

## Miten se toimii?

HTML toimii verkkosivun selkärankana. Näin se toimii:

1. **HTML-dokumentit:**

   - HTML-tiedostot ovat pelkkiä tekstitiedostoja, joilla on `.html`-päätteet.
   - Selaimet tulkitsevat nämä tiedostot ja näyttävät sisällön.

2. **Rakenne:**

   - HTML järjestää sisällön elementeiksi, jotka määritellään tunnisteilla (tageilla).
   - Elementit voivat sisältää tekstiä, kuvia, linkkejä tai muita elementtejä.

3. **Renderöinti:**
   - Selaimet lukevat HTML-dokumentin, soveltavat tyylit (CSS) ja suorittavat skriptit (JavaScript) muodostaakseen lopullisen verkkosivun.

## HTML-DOM (Document Object Model)

DOM edustaa HTML-dokumentin rakennetta objektipuuna:

- **Juurielementti:**
  - `<html>` on dokumentin juuri.
- **Sisäkkäiset elementit:**
  - `<head>`: Sisältää metatiedot ja linkit resursseihin (esim. CSS, JavaScript).
  - `<body>`: Sisältää näkyvän sisällön.

Esimerkki DOM-rakenteesta:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Web Page</title>
  </head>
  <body>
    <h1>Welcome!</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

## HTML-attribuutit

Attribuutit tarjoavat lisätietoa elementeistä:

- **Syntaksi:**

  ```html
  <tag attribute="value">Content</tag>
  ```

- **Yleisiä attribuutteja:**
  - `id`: Yksilöi elementin.
    ```html
    <div id="main">Content</div>
    ```
  - `class`: Ryhmittelee elementtejä tyylittelyä varten.
    ```html
    <p class="highlight">Text</p>
    ```
  - `src`: Määrittelee median (esim. kuvat, videot) lähteen.
    ```html
    <img src="image.jpg" alt="Description" />
    ```
  - `alt`: Tarjoaa vaihtoehtoisen tekstin kuville.
    ```html
    <img src="logo.png" alt="Company Logo" />
    ```
  - `href`: Määrittelee linkin kohteen.
    ```html
    <a href="https://example.com">Visit</a>
    ```

## Kommentit

Kommentit ohitetaan selaimessa, mutta ne auttavat kehittäjiä dokumentoimaan koodia:

```html
<!-- Tämä on kommentti -->
<p>Tämä on näkyvää sisältöä.</p>
```

## CSS- ja JavaScript-tiedostojen lisääminen

1. **CSS (Cascading Style Sheets):**

   - Lisää tyylejä HTML-sisältöön.
   - Käytä `<link>`-tunnistetta ulkoisen CSS-tiedoston liittämiseen:
     ```html
     <link rel="stylesheet" href="styles.css" />
     ```

2. **JavaScript:**
   - Lisää vuorovaikutteisuutta verkkosivulle.
   - Käytä `<script>`-tunnistetta ulkoisen JavaScript-tiedoston liittämiseen:
     ```html
     <script src="script.js"></script>
     ```

## Käytännön esimerkki

Tässä on täydellinen esimerkki, jossa kaikki yhdistyvät:

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>HTML-perusteet</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Tervetuloa HTML-perusteisiin</h1>
    <p>Tämä sivu havainnollistaa HTML:n olennaiset asiat.</p>
    <img src="example.jpg" alt="Esimerkkikuva" />
    <a href="https://example.com">Lue lisää</a>
    <script src="script.js"></script>
  </body>
</html>
```
