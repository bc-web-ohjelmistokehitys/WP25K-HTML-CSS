# HTML-linkit

Linkit ovat yksi HTML:n tärkeimmistä ominaisuuksista, sillä ne mahdollistavat siirtymisen verkkosivujen ja resurssien välillä. Tämä opas kattaa kaiken oleellisen linkkien luomisesta ja hallinnasta HTML:ssä.

## Mikä on linkki?

- **HTML-linkki** luodaan `<a>` (anchor) -elementillä.
- Linkit yhdistävät verkkosivuja, ulkoisia resursseja, tiedostoja tai tiettyjä kohtia sivulla.

```html
<a href="https://example.com">Vieraile Example-sivustolla</a>
```

## `<a>`-elementin attribuutit

### **`href` (Hypertekstiviite)**

- Määrittää linkin kohteen.
- Voi olla:
  - **Absoluuttinen URL** (täydellinen verkko-osoite):
    ```html
    <a href="https://www.google.com">Google</a>
    ```
  - **Suhteellinen URL** (polku saman sivuston resurssiin):
    ```html
    <a href="about.html">Tietoa meistä</a>
    ```

### **`target`**

- Määrittää, mihin linkitetty asiakirja avataan.
- Yleisiä arvoja:
  - `_self` (oletus): Avaa samassa välilehdessä.
    ```html
    <a href="home.html" target="_self">Etusivu</a>
    ```
  - `_blank`: Avaa uudessa välilehdessä.
    ```html
    <a href="https://example.com" target="_blank"
      >Vieraile Example-sivustolla</a
    >
    ```

### **`title`**

- Näyttää työkaluvihjeen, kun hiiri viedään linkin päälle.
  ```html
  <a href="contact.html" title="Siirry yhteystietosivulle">Yhteystiedot</a>
  ```

### **`rel`**

- Määrittää nykyisen dokumentin ja linkitetyn resurssin välisen suhteen.
  - Yleisiä arvoja:
    - `nofollow`: Estää hakukoneita seuraamasta linkkiä.
    - `noopener noreferrer`: Parantaa turvallisuutta avattaessa linkkejä uusiin välilehtiin.
  ```html
  <a href="https://example.com" rel="noopener noreferrer">Turvallinen linkki</a>
  ```

## Linkkityypit

### **Ulkoiset linkit**

- Ohjaavat toiselle verkkosivustolle.
  ```html
  <a href="https://www.wikipedia.org">Wikipedia</a>
  ```

### **Sisäiset linkit**

- Siirtyvät saman sivuston sisällä.
  ```html
  <a href="about.html">Tietoa meistä</a>
  ```

### **Sähköpostilinkit**

- Avaa oletussähköpostiohjelman sähköpostin lähettämistä varten.
  ```html
  <a href="mailto:someone@example.com">Lähetä sähköpostia</a>
  ```

### **Puhelinlinkit**

- Avaa puhelinnumeron mobiililaitteen valitsimeen.
  ```html
  <a href="tel:+1234567890">Soita meille</a>
  ```

### **Ankkurilinkit**

- Siirtyvät tiettyyn kohtaan samalla sivulla tai toisella sivulla ID:n avulla.

  ```html
  <!-- Linkki -->
  <a href="#section1">Siirry osioon 1</a>

  <!-- Kohdeosio -->
  <h2 id="section1">Osio 1</h2>
  ```

## Linkkien tyylittely

### Perustason CSS-tyylitys

- Vaihda linkin väri:

  ```css
  a {
    color: blue;
  }
  ```

- Poista alleviivaus:
  ```css
  a {
    text-decoration: none;
  }
  ```

### Linkkien pseudoluokat

- Käytä CSS:n pseudoluokkia tyylittääksesi linkkejä niiden tilan mukaan:
  - `:link`: Oletustila, kun linkkiä ei ole vielä vierailtu.
  - `:visited`: Linkit, joissa on jo käyty.
  - `:hover`: Kun käyttäjä vie hiiren linkin päälle.
  - `:active`: Kun linkkiä klikataan.

```css
a:link {
  color: blue;
}
a:visited {
  color: purple;
}
a:hover {
  text-decoration: underline;
}
a:active {
  color: red;
}
```

## Esimerkki: kattava linkkien käyttö

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>HTML-linkit</title>
    <style>
      a {
        color: blue;
        text-decoration: none;
      }
      a:hover {
        text-decoration: underline;
      }
    </style>
  </head>
  <body>
    <h1>HTML-linkit</h1>
    <p>
      <a
        href="https://example.com"
        target="_blank"
        title="Siirry Example-sivulle"
        >Vieraile Example-sivulla</a
      >
    </p>
    <p><a href="about.html">Tietoa meistä</a></p>
    <p><a href="mailto:info@example.com">Lähetä sähköpostia</a></p>
    <p><a href="tel:+1234567890">Soita meille</a></p>
    <p><a href="#section1">Hyppää osioon 1</a></p>

    <h2 id="section1">Osio 1</h2>
    <p>Tämä on osio 1.</p>
  </body>
</html>
```
