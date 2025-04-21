# Edistynyt CSS: Nykyaikaiset ominaisuudet ja temput

CSS on kehittynyt merkittävästi, tuoden mukanaan tehokkaita ominaisuuksia, jotka parantavat tyylittelyä, ylläpidettävyyttä ja suorituskykyä.

## CSS-muuttujat (Custom Properties)

CSS-muuttujien avulla voit **tallentaa ja käyttää arvoja uudelleen** tyylitiedostoissasi.

```css
:root {
  --primary-color: #3498db;
  --font-size-large: 20px;
}

body {
  color: var(--primary-color);
  font-size: var(--font-size-large);
}
```

Helppo **teeman muokattavuus**, parempi **koodin ylläpidettävyys** ja mahdollisuus **dynaamisiin muutoksiin JavaScriptin avulla**.

## `clamp()`, `min()` ja `max()` responsiiviseen suunnitteluun

Nämä funktiot **säätelevät arvoja dynaamisesti** näytön koon mukaan.

```css
h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);
}
```

- **Pienin koko**: `1.5rem` (ei mene liian pieneksi)
- **Suositeltu koko**: `5vw` (suhteessa näytön leveyteen)
- **Suurin koko**: `3rem` (ei kasva liian suureksi)

```css
div {
  width: min(50vw, 400px); /* Valitsee pienemmän arvon */
  height: max(300px, 10vh); /* Valitsee suuremman arvon */
}
```

Täydellinen responsiiviseen typografiaan ja layout-muutoksiin.

## Container-kyselyt

Toisin kuin media queryt, **container queryt** kohdistavat tyylejä vanhemman säiliön kokoon sen sijaan, että käyttäyisivät näkymää eli viewportia.

### **Esimerkki**

```css
@container (min-width: 600px) {
  .card {
    font-size: 20px;
  }
}
```

Sopii erinomaisesti aidosti uudelleenkäytettäville komponenteille.

## `has()`-valitsin (Parent Selector)

Mahdollistaa **vanhemman elementin tyylittämisen sen lapsien perusteella**.

```css
div:has(img) {
  border: 2px solid red;
}
```

Ei tarvitse lisätä ylimääräisiä luokkia tai käyttää JavaScriptiä vanhempi–lapsi-logiikkaan.

## Sisäkkäinen ruudukko eli Subgrid (Edistyneet asettelut)

Mahdollistaa sisäkkäisten ruudukkojen perivän ja kohdistuvan vanhemman ruudukkoon.

```css
.grid-container {
  display: grid;
  grid-template-columns: 1fr 2fr;
}

.grid-item {
  display: grid;
  grid-template-columns: subgrid;
}
```

Säilyttää kohdistuksen sisäkkäisten elementtien välillä.

## `scroll-snap` sulavaan vieritykseen

Mahdollistaa tarkan hallinnan vierityskäyttäytymisestä.

### **Esimerkki**

```css
.container {
  scroll-snap-type: x mandatory;
}

.item {
  scroll-snap-align: center;
}
```

Erinomainen kuvakaruselleihin, liukusäätimiin ja koko sivun vieritysefekteihin.

## `accent-color` lomake-elementeille

Muuttaa oletusväriä valintaruuduissa, radiopainikkeissa ja liukusäätimissä.

```css
input[type="checkbox"] {
  accent-color: #ff5733;
}
```

Helpottaa mukauttamista ilman lisätyylejä.

## `backdrop-filter` huurrelasiefekteihin

Soveltaa efektejä, kuten sumennus, kirkkaus tai kontrasti, elementteihin, jotka ovat toisen elementin taustalla.

```css
.modal {
  background: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(10px);
}
```

Luo moderneja käyttöliittymäefektejä, kuten Applen lasimorfismi.

## Loogiset ominaisuudet parempaan kansainväliseen tukeen

Käytä määritelmien `left` ja `right` sijaan loogisia ominaisuuksia, jotka tukevat paremmin **oikealta vasemmalle (RTL)** -kieliä.

```css
div {
  margin-inline-start: 20px; /* Toimii sekä LTR- että RTL-asetteluissa */
}
```

Parantaa saavutettavuutta ja joustavuutta globaaleissa projekteissa.

## `:is()` ja `:where()` yksinkertaistettuihin valitsimiin

Vähentää toistoa CSS-valitsimissa.

### **Esimerkki**

```css
:is(h1, h2, h3) {
  color: blue;
}
```

Tekee useiden elementtien tyylittämisestä tehokkaampaa.
