# CSS-syntaksi, valitsimet, spesifisyys, periytyminen ja kaskadoituminen

## CSS-syntaksi

CSS-säännöt noudattavat tätä perusrakennetta:

```css
valitsin {
  ominaisuus: arvo;
}
```

- **Valitsin**: Määrittää, mitä HTML-elementtiä tai -elementtejä tyylitellään.
- **Ominaisuus**: Määrittelee tyylin ominaisuuden (esim. väri, fonttikoko).
- **Arvo**: Määrittää halutun tyylin kyseiselle ominaisuudelle.

Esimerkki:

```css
p {
  color: blue;
  font-size: 16px;
}
```

## Valitsimet

CSS-valitsimilla kohdistetaan tyylit HTML-elementteihin. Tässä yleisimmät tyypit:

### Yleisvalitsin (`*`):

Kohdistuu kaikkiin elementteihin.

```css
* {
  margin: 0;
  padding: 0;
}
```

### Tyyppivalitsin:

Kohdistuu elementteihin niiden tagin perusteella.

```css
h1 {
  color: red;
}
```

### Luokkavalitsin (`.`):

Kohdistuu elementteihin, joilla on tietty luokka.

```css
.card {
  background-color: lightgray;
}
```

### ID-valitsin (`#`):

Kohdistuu yhteen elementtiin, jolla on tietty ID.

```css
#header {
  text-align: center;
}
```

### Yhdistelmävalitsimet

Määrittävät suhteita elementtien välillä:

#### Jälkeläisvalitsin (` `):

Kohdistuu elementteihin, jotka ovat toisen elementin sisällä.

```css
div p {
  color: gray;
}
```

#### Lapsivalitsin (`>`):

Kohdistuu suoriin lapsielementteihin.

```css
ul > li {
  list-style: square;
}
```

#### Viereinen sisarusvalitsin (`+`):

Kohdistuu elementin seuraavaan sisareen.

```css
h1 + p {
  font-size: 14px;
}
```

#### Yleinen sisarusvalitsin (`~`):

Kohdistuu kaikkiin saman tason sisaruksiin.

```css
h1 ~ p {
  color: blue;
}
```

## Spesifisyys

Spesifisyys määrittää, mikä CSS-sääntö sovelletaan, kun useat säännöt kohdistuvat samaan elementtiin. Suurempi spesifisyys ohittaa pienemmän.

### Spesifisyyden painoarvot:

1. **Inline-tyylit**: `1000`
2. **ID-valitsimet**: `100`
3. **Luokat, attribuutit, pseudo-luokat**: `10`
4. **Tyyppivalitsimet ja pseudo-elementit**: `1`

```css
/* Spesifisyys: 1 */
p {
  color: black;
}

/* Spesifisyys: 10 */
.text {
  color: blue;
}

/* Spesifisyys: 100 */
#highlight {
  color: green;
}

/* Inline-tyyli: 1000 */
<p style="color: red;">Red text</p>
```

## Periytyminen

Jotkin CSS-ominaisuudet, kuten `color` ja `font-family`, **periytyvät** lapsielementeille, kun taas toiset (esim. `margin` ja `padding`) eivät periydy.

### Periytymisen pakottaminen:

Käytä `inherit`-arvoa pakottaaksesi ominaisuuden periytymisen:

```css
p {
  color: inherit;
}
```

Esimerkki:

```html
<div style="color: red;">
  <p>This paragraph inherits red color.</p>
</div>
```

## Kaskadoituminen

Kaskadoituminen määrittää, miten CSS-säännöt sovelletaan ristiriitatilanteissa:

1. **Tärkeys**: `!important`-säännöt ohittavat kaikki muut.
2. **Spesifisyys**: Tarkemmat valitsimet menevät yleisten edelle.
3. **Lähdejärjestys**: Myöhemmin määritellyt säännöt ohittavat aiemmat.

```css
/* Alin prioriteetti */
p {
  color: black;
}

/* Korkeampi spesifisyys */
.text {
  color: blue;
}

/* Inline-tyyli: korkein spesifisyys */
<p style="color: red;">This is red text</p>

/* !important: ohittaa kaiken */
p {
  color: green !important;
}
```

## Käytännön esimerkki

Yhdistä oppimasi asiat tyylitelläksesi yksinkertaisen layoutin:

HTML:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS-perusteet</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header id="main-header" class="header">
      <h1>Tervetuloa CSS-perusteisiin</h1>
    </header>
    <nav class="nav">
      <a href="#">Etusivu</a>
      <a href="#">Tietoa</a>
      <a href="#">Yhteystiedot</a>
    </nav>
    <main class="content">
      <p>Tämä on varsinainen sisältöalue.</p>
    </main>
  </body>
</html>
```

CSS:

```css
/* Yleisvalitsin */
* {
  margin: 0;
  padding: 0;
}

/* ID-valitsin */
#main-header {
  background-color: lightblue;
  padding: 20px;
}

/* Luokkavalitsin */
.nav {
  text-align: center;
}

.nav a {
  margin: 0 10px;
  color: blue;
  text-decoration: none;
}

/* Tyyppivalitsin */
p {
  font-size: 16px;
  line-height: 1.5;
}
```
