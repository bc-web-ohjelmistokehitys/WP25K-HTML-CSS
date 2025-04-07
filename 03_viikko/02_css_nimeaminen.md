# CSS-nimeämiskäytännöt

CSS-luokkien nimeäminen oikein on olennaista selkeän, ylläpidettävän ja laajennettavan koodin kirjoittamisessa.

## Miksi nimeäminen on tärkeää?

1. **Luettavuus**: Selkeät nimet tekevät koodista helposti ymmärrettävää sinulle ja muille.
2. **Laajennettavuus**: Johdonmukainen nimeäminen helpottaa uusien ominaisuuksien lisäämistä rikkomatta olemassa olevia.
3. **Yhteistyö**: Tiimityö sujuu paremmin, kun kaikki noudattavat samoja sääntöjä.

## Yleisiä CSS-nimeämisvinkkejä

1. **Käytä merkityksellisiä nimiä**:

   - Valitse nimiä, jotka kuvaavat elementin tarkoitusta tai roolia, ei sen ulkonäköä.
   - Huono: `.red-box` (kuvaa tyyliä)
   - Hyvä: `.error-message` (kuvaa tarkoitusta)

2. **Pidä nimet yksinkertaisina ja johdonmukaisina**:

   - Käytä pieniä kirjaimia ja yhdistä sanat yhdysmerkeillä.
   - Vältä välilyöntejä, erikoismerkkejä tai camelCase-muotoa luokkien nimissä.
   - Esimerkki: `.main-header`, `.nav-link`

3. **Vältä päällekkäisyyttä**:
   - Käytä yksilöllisiä nimiä estääksesi ristiriitoja muiden luokkien tai kirjastojen kanssa.

## Hyviä ja huonoja nimeämisesimerkkejä

### Huonoja nimeämisesimerkkejä

```html
<div class="red-box">This is a red box</div>
<div class="big-title">Main Heading</div>
```

```css
.red-box {
  background-color: red;
  padding: 10px;
}

.big-title {
  font-size: 32px;
  font-weight: bold;
}
```

Nimet kuten `.red-box` ja `.big-title` perustuvat visuaalisiin tyyleihin, mikä tekee niistä vaikeasti uudelleenkäytettäviä tai muokattavia, jos tyylit muuttuvat.

### Hyviä nimeämisesimerkkejä

```html
<div class="alert alert--error">This is an error message</div>
<div class="heading heading--large">Main Heading</div>
```

```css
.alert {
  padding: 10px;
  border: 1px solid #f00;
  background-color: #ffe5e5;
}

.error-message {
  color: red;
}

.heading {
  font-size: 16px;
  font-weight: normal;
}

.large-heading {
  font-size: 32px;
  font-weight: bold;
}
```

- Nimet kuten `.alert` ja `.heading` kuvaavat elementin tarkoitusta.
- Muuntimet kuten `--error` ja `--large` ilmaisevat variaatioita, mikä tekee luokista uudelleenkäytettäviä ja laajennettavia.

## BEM-menetelmä (Block-Element-Modifier)

**BEM** on yksi suosituimmista nimeämiskäytännöistä ja hyvä lähtökohta aloittelijoille.

### Mitä BEM tarkoittaa?

- **Block**: Itsenäinen komponentti tai osio (esim. kortti, lomake).
- **Element**: Osa blockia (esim. painike lomakkeessa).
- **Modifier**: Muunnelma tai tila blockista tai elementistä (esim. korostettu kortti).

### BEM-syntaksi:

```plaintext
.block__element--modifier
```

### Esimerkki:

1. **HTML**:

```html
<div class="card card--featured">
  <h2 class="card__title">Card Title</h2>
  <p class="card__description">This is a card description.</p>
</div>
```

2. **CSS**:

```css
/* Block */
.card {
  border: 1px solid #ddd;
  padding: 16px;
  background-color: #fff;
}

/* Modifier */
.card--featured {
  border-color: gold;
}

/* Element */
.card__title {
  font-size: 18px;
  margin-bottom: 8px;
}

.card__description {
  font-size: 14px;
  color: #666;
}
```

### Miksi käyttää BEM:ää?

- Tekee CSS:stäsi järjestelmällistä ja ennakoitavaa.
- Auttaa välttämään yleisluontoisia luokkien nimiä kuten `.button` tai `.box`.

## Muita nimeämismenetelmiä

### 1. **OOCSS (Object-Oriented CSS)**

- Keskittyy rakenteen (layout) ja ulkoasun (skin) erottamiseen.
- Kannustaa uudelleenkäytettäviin, modulaarisiin luokkiin.

#### Esimerkki:

```html
<div class="box box--large box--highlight">
  <p>This is a reusable component.</p>
</div>
```

```css
.box {
  padding: 20px;
  border: 1px solid #ddd;
}

.box--large {
  width: 300px;
}

.box--highlight {
  background-color: yellow;
}
```

### 2. **SMACSS (Scalable and Modular Architecture for CSS)**

- Jäsentää CSS:n kategorioihin, kuten base, layout ja module.
- Käyttää etuliitteitä tyylin tyypin osoittamiseen.

#### Esimerkki:

```html
<div class="l-header">
  <h1 class="m-title">Site Title</h1>
</div>
```

```css
/* Layout */
.l-header {
  display: flex;
  justify-content: space-between;
}

/* Module */
.m-title {
  font-size: 24px;
}
```

### 3. **Utility-luokat (Atomic CSS)**

- Käyttää pieniä, yksittäistarkoitukseen tehtyjä luokkia nopeaan tyylittelyyn.
- Yleisiä kehyksissä kuten Tailwind CSS.

#### Esimerkki:

```html
<div class="p-4 m-2 text-center bg-blue-500">
  <p>Quickly styled with utility classes!</p>
</div>
```

```css
/* Esimerkki mukautetuista utility-luokista */
.p-4 {
  padding: 16px;
}

.m-2 {
  margin: 8px;
}

.bg-blue-500 {
  background-color: #3b82f6;
}
```

## Yleisiä virheitä, joita kannattaa välttää

- Vältä nimiä kuten `.box`, `.section`, `.thing`. Ole tarkka ja selkeä.
- Vältä tarpeettoman pitkiä nimiä. Pidä nimet ytimekkäinä ja selkeinä.
- Älä sido luokkien nimiä tiettyihin tyyleihin (esim. `.blue-button`). Keskity toimintaan tai rooliin.
