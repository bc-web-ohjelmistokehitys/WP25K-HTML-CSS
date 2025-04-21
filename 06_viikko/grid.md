# CSS Grid: Perusteet

CSS Grid on **tehokas** asettelujärjestelmä, jonka avulla on helppo luoda **responsiivisia**, **kaksiulotteisia** asetteluja. Toisin kuin Flexbox (joka toimii yhteen suuntaan kerrallaan), Grid mahdollistaa asettelun suunnittelun sekä **vaaka-** että **pystysuunnassa**.

## Mikä on CSS Grid?

CSS Grid on asettelumenetelmä, joka jakaa säiliön **riveihin** ja **sarakkeisiin**, ja elementit voidaan sijoittaa tämän rakenteen sisälle.

Aktivoidaksesi Gridin, lisää säiliöön `display: grid;`.

```css
.container {
  display: grid;
}
```

## Grid-säiliö ja Grid-elementit

CSS Grid koostuu **kahdesta pääosasta**:

- **Grid-säiliö** → Vanhempi elementti, joka sisältää grid-elementtejä (`display: grid;`).
- **Grid-elementit** → Suorat lapset grid-säiliön sisällä.

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: grid;
  background-color: lightgray;
}

.item {
  padding: 20px;
  background-color: steelblue;
  color: white;
  margin: 5px;
}
```

## Rivien ja sarakkeiden määrittely

Käytä `grid-template-columns` ja `grid-template-rows` määrittääksesi gridin **rakenteen**.

### **Esimerkki:**

```css
.container {
  display: grid;
  grid-template-columns: 100px 200px auto;
  grid-template-rows: 100px 150px;
}
```

- **Sarakkeet**: Ensimmäinen on 100px, toinen 200px, kolmas mukautuu automaattisesti.
- **Rivit**: Ensimmäinen on 100px, toinen 150px.

## Repeat ja murto-osayksiköt

Kiinteiden arvojen sijaan voit käyttää:

- `repeat()` → Luo toistuvia sarakkeita/rivejä.
- `fr` (fractional unit) → Jakaa tilan suhteellisesti.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

Tämä luo **kolme yhtä leveää saraketta**.

## Grid Gap (Välistys)

Käytä `gap`-ominaisuutta lisätäksesi tilaa **grid-elementtien väliin**.

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
```

- `gap: 10px;` → Lisää **10 pikselin** välin kaikkiin grid-elementtien väleihin.

## Elementtien sijoittaminen gridissä

Voit sijoittaa elementtejä `grid-column`- ja `grid-row`-ominaisuuksilla.

```css
.item {
  grid-column: 1 / 3; /* Ulottuu sarakkeista 1–3 */
  grid-row: 1 / 2; /* Ulottuu riville 1 */
}
```

## Justify & Align Items

| Ominaisuus      | Kuvaus                                  |
| --------------- | --------------------------------------- |
| `justify-items` | Kohdistaa elementit **vaakasuunnassa**. |
| `align-items`   | Kohdistaa elementit **pystysuunnassa**. |

```css
.container {
  display: grid;
  justify-items: center; /* Kohdistaa elementit vaakasuunnassa keskelle */
  align-items: center; /* Kohdistaa elementit pystysuunnassa keskelle */
}
```

## Justify & Align Content

Nämä ominaisuudet kohdistavat **koko gridin** säiliönsä sisällä.

| Ominaisuus        | Kuvaus                             |
| ----------------- | ---------------------------------- |
| `justify-content` | Siirtää gridiä **vaakasuunnassa**. |
| `align-content`   | Siirtää gridiä **pystysuunnassa**. |

```css
.container {
  display: grid;
  justify-content: center;
  align-content: center;
}
```

## Grid Auto-Placement (Automaattinen sijoittelu)

Oletuksena CSS Grid **sijoittaa** elementit automaattisesti vapaana oleviin kohtiin. Käytä `grid-auto-flow`-ominaisuutta sijoittelun hallintaan.

| Arvo     | Kuvaus                                  |
| -------- | --------------------------------------- |
| `row`    | Oletus. Sijoittaa elementit riveittäin. |
| `column` | Sijoittaa elementit sarakkeittain.      |
| `dense`  | Täyttää mahdolliset tyhjät välit.       |

```css
.container {
  display: grid;
  grid-auto-flow: column;
}
```

## Grid-alueet (Nimetyt asettelut)

Voit **antaa alueille nimiä** ja sijoittaa elementit käyttämällä `grid-area`-ominaisuutta.

```css
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
}

.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.main {
  grid-area: main;
}
.footer {
  grid-area: footer;
}
```

## Yhteenveto

`display: grid;` ottaa CSS Gridin käyttöön.  
`grid-template-columns` ja `grid-template-rows` määrittävät asettelun.  
`gap` hallitsee elementtien välistä tilaa.  
`justify-items` ja `align-items` kohdistavat elementit gridissä.  
`grid-area` mahdollistaa nimettyjen alueiden käytön.
