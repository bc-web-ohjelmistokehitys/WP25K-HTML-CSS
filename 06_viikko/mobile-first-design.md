# Mobile-First -suunnittelu

Mobile-first -suunnittelu tarkoittaa sitä, että verkkosivu rakennetaan **ensin mobiililaitteille**, ja sen jälkeen mukautetaan isommille näytöille. Tämä auttaa sivua latautumaan nopeammin, toimimaan sujuvasti ja olemaan helppokäyttöinen millä tahansa laitteella.

## Miksi aloittaa mobiilista?

- Enemmistö selaa nettiä puhelimella eikä tietokoneella.
- Mobiiliystävällinen sivu on **helpompi käyttää** kaikille.
- Google suosii mobiilioptimoituja sivuja hakutuloksissa.
- Monen mielestä on psykologisesti mukavampi asetella asioita loppuvaiheessa isommalle näytölle kuin rajata pieneen tilaan.

## Miten rakentaa Mobile-First-sivusto

Aloita **yksinkertaisilla tyyleillä pienille näytöille** ja lisää tyylejä suuremmille näytöille.

```css
/* Oletustyylit mobiilille */
body {
  font-size: 16px;
  line-height: 1.5;
}

.container {
  display: flex;
  flex-direction: column;
  padding: 10px;
}
```

## Mukautus suuremmille näytöille

Käytä **CSS-media queryja**, jotta asettelu mukautuu kun näyttö on leveämpi.

```css
@media (min-width: 768px) {
  .container {
    flex-direction: row;
    justify-content: space-between;
  }
}
```

- `min-width: 768px;` tarkoittaa, että nämä tyylit pätevät **vain**, kun näytön leveys on vähintään **768 pikseliä**.
- Näin suunnittelu **skaalautuu sujuvasti**, kun näyttö kasvaa.

## Yleisiä näyttökokoja

| Laite       | Näytön leveys |
| ----------- | ------------- |
| Puhelimet   | 0 - 767px     |
| Tabletit    | 768 - 1023px  |
| Tietokoneet | 1024px+       |

Voit mukauttaa nämä koot tarpeidesi mukaan.

## Kuvien responsiivisuus

Kuvien tulisi **muuttua koon mukaan**, jotta ne latautuvat nopeammin ja näyttävät paremmilta.

### `<picture>`-elementti: Näytä oikea kuva

Tällä menetelmällä voit ladata pienemmän kuvan mobiilille ja suuremman kuvan isoille näytöille.

```html
<picture>
  <source srcset="image-small.jpg" media="(max-width: 767px)" />
  <source srcset="image-medium.jpg" media="(max-width: 1023px)" />
  <img src="image-large.jpg" alt="Kaunis maisema" />
</picture>
```

- Puhelimet saavat **pienimmän** kuvan.
- Isommat näytöt saavat **suurempia** kuvia.
- Tämä **säästää dataa** ja nopeuttaa latausta.

### `srcset`: Säädä kuvan laatua

Tämä tapa lataa tarkemmat kuvat korkean resoluution näytöille, kuten **retina-näytöille**.

```html
<img
  src="image.jpg"
  srcset="image-2x.jpg 2x, image-3x.jpg 3x"
  alt="Kaunis maisema"
/>
```

- `2x` ja `3x` kertovat selaimelle, että se valitsee sopivan kuvan **korkean resoluution näytöille**.
