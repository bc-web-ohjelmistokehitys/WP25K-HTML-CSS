# Laatikkomalli, täyte, marginaali ja reunukset

CSS:n laatikkomalli on perustavanlaatuinen käsite, joka määrittelee, miten elementit rakennetaan ja sijoitetaan verkkosivulla. Se sisältää elementin sisällön, täytteen, reunuksen ja marginaalin.

## CSS:n laatikkomalli

Jokainen HTML-elementti nähdään laatikkona. Laatikkomalli koostuu seuraavista osista:

1. **Sisältö**:

   - Laatikon sisin osa, jossa teksti ja kuvat näkyvät.

2. **Täyte (Padding)**:

   - Sisällön ja reunuksen välinen tila.
   - Täyte kasvattaa elementin kokoa vaikuttamatta muihin elementteihin.

3. **Reunus (Border)**:

   - Täytteen ympärillä oleva reuna (tai sisällön, jos täytettä ei ole määritelty).

4. **Marginaali (Margin)**:
   - Reunuksen ulkopuolinen tila, joka erottaa elementin muista elementeistä.

## Block- ja inline-elementit

### Block-elementit

- Vie oletusarvoisesti koko säiliön leveyden.
- Ottavat huomioon marginaalit, täytteet ja reunukset kaikilla sivuilla.

Esimerkki:

```css
div {
  display: block;
  margin: 10px;
  padding: 10px;
  border: 2px solid black;
}
```

### Inline-elementit

- Vie vain sisältönsä tarvitseman tilan.
- Ottavat huomioon vaakasuuntaiset täytteet, marginaalit ja reunukset (ylä- ja alareunukset näkyvät, mutta eivät vaikuta asetteluun).

Esimerkki:

```css
span {
  display: inline;
  margin: 5px;
  padding: 5px;
  border: 1px solid gray;
}
```

### Inline-block-elementit

- Käyttäytyvät kuten inline-elementit, mutta ottavat huomioon täytteet, marginaalit ja reunukset kaikilla sivuilla.
- Hyödyllisiä, kun halutaan kohdistaa elementtejä vaakasuunnassa säilyttäen block-tyylinen välistys.

Esimerkki:

```css
.menu-item {
  display: inline-block;
  padding: 10px;
  margin: 5px;
  border: 1px solid black;
}
```

## Täyte (Padding)

- Määrittää sisällön ja reunuksen välisen tilan.
- Voi asettaa erikseen jokaiselle sivulle: `padding-top`, `padding-right`, `padding-bottom`, `padding-left`.

### Lyhennysmuoto

```css
padding: 10px 20px 15px 5px; /* Ylä, Oikea, Ala, Vasen */
```

### Esimerkit

```css
div {
  padding: 20px; /* Sama täyte kaikilla sivuilla */
}

div {
  padding: 20px 10px; /* 20px ylhäällä ja alhaalla, 10px vasemmalla ja oikealla */
}

div {
  padding: 20px 15px 10px 5px; /* Täyte: 20px ylhäällä, 15px oikealla, 10px alhaalla, 5px vasemmalla */
}

div {
  padding-top: 30px; /* Lisää 30px tilaa sisällön yläpuolelle */
  padding-left: 15px; /* Lisää 15px tilaa sisällön vasemmalle puolelle */
}
```

## Reunus (Border)

- Ympäröi täytteen (tai sisällön, jos täytettä ei ole).
- Ominaisuudet:
  - `border-width`: Reunuksen paksuus.
  - `border-style`: Tyyli, esim. solid, dotted, dashed jne.
  - `border-color`: Reunuksen väri.

### Lyhennysmuoto

```css
border: 2px solid black;
```

### Esimerkit

```css
div {
  border: 1px solid gray; /* Asettaa reunuksen leveyden, tyylin ja värin kaikille sivuille */
}

div {
  border-width: 2px;
  border-style: dashed;
  border-color: blue;
}

div {
  border-top: 3px dotted red; /* 3px pisteviiva yläreunassa, punainen väri */
  border-right: 2px solid green; /* 2px yhtenäinen viiva oikealla, vihreä väri */
}
```

## Marginaali (Margin)

- Luo tilaa reunuksen ulkopuolelle, erottaen elementit toisistaan.
- Voi asettaa erikseen jokaiselle sivulle: `margin-top`, `margin-right`, `margin-bottom`, `margin-left`.

### Lyhennysmuoto

```css
margin: 10px 20px 15px 5px; /* Ylä, Oikea, Ala, Vasen */
```

### Esimerkit

```css
div {
  margin: 20px; /* Sama marginaali kaikilla sivuilla */
}

div {
  margin: 20px 10px; /* 20px ylhäällä ja alhaalla, 10px vasemmalla ja oikealla */
}

div {
  margin-top: 30px;
  margin-right: 15px;
}
```

### Automaattinen marginaali keskitykseen

Marginaaleja voidaan käyttää lohkotason elementtien keskittämiseen vaakasuunnassa:

```css
div {
  margin: 0 auto;
  width: 50%;
}
```

## Laatikon koko (Box Sizing)

- Määrittää, miten elementin kokonaiskoko lasketaan.
  - `content-box`: Leveys ja korkeus sisältävät vain sisällön.
  - `border-box`: Leveys ja korkeus sisältävät myös täytteen ja reunuksen.

```css
div {
  box-sizing: border-box;
}
```

## Reunuksen pyöristys (Border Radius)

Pyöristää elementin kulmat.

### Esimerkit

```css
div {
  border: 2px solid black;
  border-radius: 10px;
}

div {
  border-radius: 50%;
}
```

## Reunuskuva (Border Image)

Käyttää kuvaa elementin reunuksena.

### Esimerkki

```css
div {
  border: 20px solid transparent;
  border-image: url("border-image.png") 30 round;
}
```

## Ääriviiva (Outline)

Piirretään elementin reunuksen ulkopuolelle, ei kuulu laatikkomalliin.

### Esimerkki

```css
div {
  outline: 2px dotted red;
}
```

## Käytännön esimerkki

CSS:

```css
.box {
  width: 200px;
  height: 100px;
  padding: 20px;
  border: 3px solid black;
  border-radius: 15px;
  margin: 20px auto;
  text-align: center;
}
```

HTML:

```html
<div class="box">Box Model Example</div>
```
