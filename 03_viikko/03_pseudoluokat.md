# CSS:n pseudo-luokat ja pseudo-elementit

Pseudo-luokat ja pseudo-elementit ovat tehokkaita työkaluja CSS:ssä, joiden avulla voit tyylitellä elementtejä niiden tilan tai sisällön tiettyjen osien perusteella ilman ylimääräistä HTML:ää.

## Pseudo-luokat

**Pseudo-luokka** valitsee elementtejä niiden tilan, sijainnin tai vuorovaikutuksen perusteella. Se kirjoitetaan muodossa `valitsin:pseudo-luokka {}`.

### Yleisiä pseudo-luokkia

### Hover, Focus ja Active

Käytetään interaktiivisissa elementeissä, kuten painikkeissa ja linkeissä.

```css
a:hover {
  color: red; /* Muuttaa väriä kun viet hiiren päälle */
}

input:focus {
  border-color: blue; /* Korostaa syötekenttää kun siihen klikataan */
}

button:active {
  background-color: darkblue; /* Muuttaa taustaväriä painettaessa */
}
```

### First ja Last Child

Kohdistetaan ensimmäiseen tai viimeiseen elementtiin vanhemman sisällä.

```css
p:first-child {
  font-weight: bold;
}

p:last-child {
  font-style: italic;
}
```

### nth-Child ja nth-of-Type

Mahdollistavat elementtien kohdistamisen tietyn kaavan mukaan.

```css
li:nth-child(odd) {
  background-color: lightgray; /* Tyylittää joka toisen listan kohdan */
}

li:nth-child(3) {
  color: blue; /* Tyylittää kolmannen listan kohdan */
}

p:nth-of-type(2) {
  color: red; /* Tyylittää vain toisen kappaleen tietyssä osiossa */
}
```

### Empty, Not ja Checked

```css
div:empty {
  border: 1px solid red; /* Tyylittää tyhjät div-elementit */
}

input:not([type="text"]) {
  background: lightblue; /* Tyylittää kaikki syötteet paitsi tekstikentät */
}

input:checked {
  outline: 2px solid green; /* Korostaa valitut checkboxit tai radiopainikkeet */
}
```

## Pseudo-elementit

**Pseudo-elementti** valitsee ja tyylittää tiettyjä osia elementin sisällöstä. Se kirjoitetaan muodossa `valitsin::pseudo-elementti {}` (kaksoispisteellä `::`).

### First Letter ja First Line

Käytetään typografisten yksityiskohtien muotoiluun.

```css
p::first-letter {
  font-size: 2em;
  font-weight: bold;
  color: red;
}

p::first-line {
  font-style: italic;
}
```

### Valinnan tyylittäminen (Selection Styling)

Muuttaa tekstin ulkoasua, kun käyttäjä korostaa sitä.

```css
p::selection {
  background: yellow;
  color: black;
}
```

### Before ja After

Lisää sisältöä ennen tai jälkeen elementin ilman, että HTML:ää tarvitsee muokata.

```css
h1::before {
  content: "🔥 "; /* Lisää emojin ennen jokaista h1-elementtiä */
}

h1::after {
  content: " 🎉"; /* Lisää emojin jokaisen h1-elementin jälkeen */
}
```

## Käytännön käyttötapaukset

**Korosta pakolliset lomakekentät:**

```css
input:required {
  border: 2px solid red;
}
```

**Luo raidallinen taulukko nth-childin avulla:**

```css
tr:nth-child(even) {
  background-color: #f2f2f2;
}
```

**Erota paikkamerkkiteksti omalla tyylillä (placeholder):**

```css
input::placeholder {
  color: gray;
  font-style: italic;
}
```

## Yhteenveto

- **Pseudo-luokat** lisäävät tyylejä tilan perusteella (`:hover`, `:nth-child`, `:checked`).
- **Pseudo-elementit** tyylittävät osia elementistä (`::before`, `::after`, `::first-letter`).
- Käytä `::before` ja `::after` sisältöjen lisäämiseen.
- `:not()` auttaa sulkemaan tietyt elementit tyylien ulkopuolelle.
