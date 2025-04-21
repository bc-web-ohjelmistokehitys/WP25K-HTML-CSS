# CSS Flexbox: Perusteet

Flexbox (Flexible Box Layout) on tehokas CSS-asettelujärjestelmä, joka helpottaa **responsiivisten**, **dynaamisten** ja **tasattujen** asettelujen suunnittelua. Se auttaa jakamaan tilaa tehokkaasti elementtien välillä, vaikka niiden koko ei olisi ennalta tiedossa.

## Mikä on Flexbox?

Flexboxin avulla voit tasata elementtejä vaakasuunnassa ja pystysuunnassa vain vähällä CSS-koodilla. Se on erityisen hyödyllinen esimerkiksi:

- Elementtien keskittämisessä
- Dynaamisten asettelujen luomisessa
- Responsiivisten navigaatiopalkkien rakentamisessa
- Yhtäkorkuisten sarakkeiden hallinnassa

Flexboxia käytetään määrittämällä `display: flex;` vanhemmalle säiliöelementille.

```css
.container {
  display: flex;
}
```

## Flex-säiliö ja flex-elementit

Flexbox koostuu **kahdesta pääosasta**:

- **Flex-säiliö** → Vanhempielementti, joka sisältää flex-elementtejä (`display: flex;`).
- **Flex-elementit** → Suorat lapset flex-säiliön sisällä.

```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```

```css
.container {
  display: flex;
  background-color: lightgray;
}

.item {
  padding: 20px;
  background-color: steelblue;
  color: white;
  margin: 5px;
}
```

## Pääakseli ja poikkiakseli

Flexboxissa on tärkeää ymmärtää kaksi akselia:

- **Pääakseli** → Määrittyy `flex-direction`-ominaisuudella (`row` tai `column`).
- **Poikkiakseli** → Kulkee kohtisuorassa pääakseliin nähden.

### **Esimerkki:**

```css
.container {
  display: flex;
  flex-direction: row; /* Pääakseli: vasemmalta oikealle */
}
```

## Flex Direction

Määrittää, miten flex-elementit järjestetään.

| Arvo             | Kuvaus                                 |
| ---------------- | -------------------------------------- |
| `row`            | Oletus. Elementit vasemmalta oikealle. |
| `row-reverse`    | Elementit oikealta vasemmalle.         |
| `column`         | Elementit ylhäältä alas.               |
| `column-reverse` | Elementit alhaalta ylös.               |

```css
.container {
  display: flex;
  flex-direction: column;
}
```

## Justify Content (Tasaus pääakselilla)

Määrittää elementtien kohdistuksen **pääakselilla**.

| Arvo            | Kuvaus                                |
| --------------- | ------------------------------------- |
| `flex-start`    | Kohdistetaan alkuun (oletus).         |
| `flex-end`      | Kohdistetaan loppuun.                 |
| `center`        | Kohdistetaan keskelle.                |
| `space-between` | Tasainen tila elementtien väliin.     |
| `space-around`  | Tasaista tilaa elementtien ympärille. |
| `space-evenly`  | Yhtäläinen tila kaikkien ympärillä.   |

```css
.container {
  display: flex;
  justify-content: center; /* Kohdistaa keskelle */
}
```

## Align Items (Tasaus poikkiakselilla)

Määrittää elementtien kohdistuksen **poikkiakselilla**.

| Arvo         | Kuvaus                                        |
| ------------ | --------------------------------------------- |
| `stretch`    | Oletus. Elementit venyvät täyttämään säiliön. |
| `flex-start` | Kohdistetaan yläreunaan.                      |
| `flex-end`   | Kohdistetaan alareunaan.                      |
| `center`     | Kohdistetaan keskelle.                        |
| `baseline`   | Kohdistetaan tekstin peruslinjan mukaan.      |

```css
.container {
  display: flex;
  align-items: center; /* Kohdistaa keskelle poikkiakselilla */
}
```

## Flex Wrap

Oletuksena elementit yritetään mahduttaa yhdelle riville. Käytä `flex-wrap`-ominaisuutta rivittämiseen.

| Arvo           | Kuvaus                                                |
| -------------- | ----------------------------------------------------- |
| `nowrap`       | Oletus. Elementit pysyvät yhdellä rivillä.            |
| `wrap`         | Elementit siirtyvät seuraavalle riville tarvittaessa. |
| `wrap-reverse` | Rivitetään käänteisessä järjestyksessä.               |

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

## Flex Grow, Shrink ja Basis

Nämä ominaisuudet määrittävät, miten flex-elementit käyttäytyvät flex-säiliön sisällä.

### Flex Grow (Laajentaa elementtejä täyttämään tilan)

```css
.item {
  flex-grow: 1; /* Jokainen elementti vie yhtä paljon tilaa */
}
```

### Flex Shrink (Määrittää kutistumista)

```css
.item {
  flex-shrink: 0; /* Estää kutistumisen */
}
```

### Flex Basis (Asettaa alkukoon)

```css
.item {
  flex-basis: 200px; /* Elementtien lähtöleveys on 200px */
}
```

**Lyhennysmuoto**

```css
.item {
  flex: 1 1 200px; /* Kasvu, kutistuminen ja peruskoko yhdellä rivillä */
}
```

## Align Content (Useita rivejä)

Säätää **rivitysten välistä tilaa**. Eli riveillä on käytössä `flex-wrap: wrap` tai `wrap-reverse`. Ei toimi yksittäiselle riville.

| Arvo            | Kuvaus                             |
| --------------- | ---------------------------------- |
| `flex-start`    | Rivien kohdistus ylös.             |
| `flex-end`      | Rivien kohdistus alas.             |
| `center`        | Rivien kohdistus keskelle.         |
| `space-between` | Tasainen väli rivien välillä.      |
| `space-around`  | Tasainen väli rivien ympärillä.    |
| `stretch`       | Rivien venytys täyttämään säiliön. |

```css
.container {
  display: flex;
  flex-wrap: wrap;
  align-content: center;
}
```

## Yhteenveto

`display: flex;` ottaa flexboxin käyttöön.  
`flex-direction` määrittää rivin/sarakkeen suunnan.  
`justify-content` tasaa elementit pääakselilla.  
`align-items` tasaa elementit poikkiakselilla.  
`flex-wrap` määrittää, saavatko elementit rivittyä.  
`flex-grow`, `flex-shrink` ja `flex-basis` säätävät elementin kokoa.

Erinomainen ohje: [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
