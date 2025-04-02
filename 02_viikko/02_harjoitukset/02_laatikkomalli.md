# Viikko 2, tehtävä 2

## Vaihe 1: Projektin alustus

1. Luo kansio nimeltä `profile_page_project`.
2. Luo kansion sisälle seuraavat tiedostot:
   - `index.html`
   - `styles.css`
3. Linkitä CSS-tiedosto HTML-tiedostoon `<link>`-elementillä `<head>`-osion sisällä.

## Vaihe 2: HTML-rakenteen luominen

1. Lisää **header** sivun yläosaan. Sisällytä siihen nimesi.
2. Luo **main-osio**, joka sisältää seuraavat:
   - Lyhyt esittelykappale.
   - Lista harrastuksista tai taidoista.
   - “Tietoa minusta” -osio, jossa on profiilikuva ja kuvaus.
3. Lisää **footer**, jossa on tekijänoikeusviesti ja linkkejä someen tai yhteystietoihin.

## Vaihe 3: Sivun tyylittely

### Yleisasetukset

1. Aseta kaikille elementeille `box-sizing` arvoksi `border-box`.

### Header

1. Käytä `padding`- ja `margin`-arvoja otsikon asetteluun.
2. Lisää yhtenäinen reunaviiva otsikon alapuolelle erottamaan se muusta sisällöstä.
3. Aseta otsikolle taustaväri, joka erottuu muun sivun värimaailmasta.

### Main-osio

1. **Esittelykappaleen tyyli**:

   - Lisää `margin` ja `padding` sopivan välimatkan luomiseksi.
   - Käytä eri taustaväriä.
   - Aseta leveys 25 %.

2. **Harrastus- tai taitolistan tyyli**:

   - Lisää `margin` ja `padding`.
   - Käytä eri taustaväriä.
   - Aseta leveys 500px.

3. **"Tietoa minusta" -osion tyyli**:
   - Aseta profiilikuva vasemmalle ja teksti oikealle.
   - Käytä `padding`- ja `margin`-arvoja siistin asettelun luomiseksi.
   - Lisää reunaviiva sekä taustaväri tai -kuva, jotta osio erottuu.

### Footer

1. Keskitä footerin sisältö käyttämällä `margin: auto` ja tekstin tasausta.
2. Lisää `padding` ja taustaväri, joka täydentää headerin väriä.

## Vaihe 4: Taustavärit ja -kuvat

1. Lisää koko sivulle hillitty taustaväri tai liukuväri.
2. Lisää taustakuva **"Tietoa minusta"** -osioon.
   - Käytä `background-size: cover;`, jotta kuva kattaa osion oikein.
