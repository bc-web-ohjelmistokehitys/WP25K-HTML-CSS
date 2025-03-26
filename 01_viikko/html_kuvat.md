# HTML-kuvat

Kuvat ovat olennainen osa verkkosuunnittelua – ne lisäävät visuaalista vetovoimaa ja tukevat sisältöä. HTML tarjoaa tehokkaita työkaluja kuvien lisäämiseen ja hallintaan verkkosivuilla. Tässä kerrotaan, miten voit käyttää kuvia HTML:ssä.

## `<img>`-elementti

- `<img>`-elementtiä käytetään kuvien upottamiseen verkkosivulle.
- Se on yksittäinen (itse sulkeutuva) elementti, eli se ei tarvitse sulkevaa `</img>`-tagia.

```html
<img src="image.jpg" alt="Kuvauksen teksti" />
```

### `<img>`-elementin attribuutit

#### **`src` (Lähde)**

- Määrittää polun kuvatiedostoon.
- Voi olla:
  - **Absoluuttinen URL:** Täydellinen verkko-osoite.
    ```html
    <img src="https://example.com/image.jpg" alt="Esimerkkikuva" />
    ```
  - **Suhteellinen URL:** Polku suhteessa HTML-tiedostoon.
    ```html
    <img src="images/photo.jpg" alt="Kuva" />
    ```

#### **`alt` (Vaihtoehtoinen teksti)**

- Tarjoaa tekstikuvauksen kuvalle.
- Tärkeä saavutettavuuden kannalta ja näkyy, jos kuva ei lataudu.
  ```html
  <img src="image.jpg" alt="Maisemakuva vuoristosta" />
  ```

#### **`width` ja `height`**

- Asettaa kuvan mitat (pikseleinä tai prosentteina).
  ```html
  <img src="image.jpg" alt="Esimerkki" width="300" height="200" />
  ```

#### **`title`**

- Näyttää työkaluvihjeen, kun käyttäjä vie hiiren kuvan päälle.
  ```html
  <img src="image.jpg" alt="Esimerkki" title="Hover-teksti" />
  ```

## Responsiiviset kuvat

### CSS:n avulla

Tee kuvista responsiivisia asettamalla niiden enimmäisleveys 100 % ja korkeus automaattiseksi:

```css
img {
  max-width: 100%;
  height: auto;
}
```

### `<picture>`-elementin avulla

`<picture>`-elementti mahdollistaa useiden lähteiden käytön eri näyttökokoja varten:

```html
<picture>
  <source srcset="image-large.jpg" media="(min-width: 800px)" />
  <source srcset="image-small.jpg" media="(max-width: 799px)" />
  <img src="image-default.jpg" alt="Responsiivinen kuva" />
</picture>
```

## Kuvamuodot

### Yleiset muodot

- **JPEG:** Paras valokuville; tukee miljoonia värejä.
- **PNG:** Tukee läpinäkyvyyttä ja korkealaatuisia kuvia.
- **GIF:** Sopii yksinkertaisiin animaatioihin.
- **WebP:** Moderni muoto, joka tarjoaa paremman pakkaussuhteen ja laadun.
- **SVG:** Skaalautuva vektorigrafiikka, ihanteellinen kuvakkeille ja piirroksille.

### Oikean muodon valinta

- Käytä **JPEG**-muotoa valokuville tilan säästämiseksi.
- Käytä **PNG**-muotoa kuville, jotka vaativat läpinäkyvyyttä.
- Käytä **WebP**-muotoa, jos selain tukee sitä, suorituskyvyn parantamiseksi.

## Saavutettavuuden parhaat käytännöt

- Lisää aina `alt`-attribuutti, jossa on merkityksellinen kuvaus.
- Käytä `role="img"` koristekuville, tarvittaessa ARIA-määritteiden kanssa.
- Vältä tekstin esittämistä kuvina, ellei se ole ehdottoman välttämätöntä.

## Esimerkki: kattava kuvien käyttö

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>HTML-kuvat</title>
    <style>
      img {
        max-width: 100%;
        height: auto;
        border: 1px solid #ccc;
      }
    </style>
  </head>
  <body>
    <h1>Kuvien käyttö</h1>

    <h2>Peruskuva</h2>
    <img src="image.jpg" alt="Kaunis auringonlasku" />

    <h2>Responsiivinen kuva</h2>
    <picture>
      <source srcset="large.jpg" media="(min-width: 800px)" />
      <source srcset="small.jpg" media="(max-width: 799px)" />
      <img src="default.jpg" alt="Responsiivinen esimerkki" />
    </picture>

    <h2>Koristekuva</h2>
    <img src="decorative.jpg" alt="" role="img" />
  </body>
</html>
```
