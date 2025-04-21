# CSS-yksiköt: Absoluuttiset ja suhteelliset

CSS-yksiköt määrittävät elementtien, tekstin ja välien koot verkkosivulla. Yksiköt jaetaan kahteen päätyyppiin:

**Absoluuttiset yksiköt** – Kiinteät koot, jotka eivät muutu.  
**Suhteelliset yksiköt** – Koot, jotka mukautuvat suhteessa vanhempaan elementtiin tai näkymäikkunaan.

## Absoluuttiset yksiköt

Absoluuttisilla yksiköillä on kiinteä koko, eikä ne skaalaudu näytön tai vanhemman elementin mukaan.

| Yksikkö          | Kuvaus                                                     |
| ---------------- | ---------------------------------------------------------- |
| `px` (pikseliä)  | Yleisin yksikkö verkkosuunnittelussa. Kiinteä koko.        |
| `cm`, `mm`, `in` | Senttimetrit, millimetrit, tuumat – käytetään tulosteissa. |
| `pt`, `pc`       | Pisteet ja pikat – pääasiassa painettaviin materiaaleihin. |

```css
h1 {
  font-size: 24px; /* Kiinteä koko, ei muutu */
}
```

Käytä absoluuttisia yksiköitä, kun tarvitset tarkan, muuttumattoman koon, kuten reunuksissa tai tulostustyyleissä.

## Suhteelliset yksiköt

Suhteelliset yksiköt ovat joustavia ja mukautuvat näytön kokoon tai elementin vanhemman perusteella.

| Yksikkö        | Kuvaus                                                                                                  |
| -------------- | ------------------------------------------------------------------------------------------------------- |
| `%`            | Prosenttiosuus vanhemman koosta.                                                                        |
| `em`           | Suhteessa vanhemman fonttikokoon.                                                                       |
| `rem`          | Suhteessa juurielementin (`<html>`) fonttikokoon. (Käyttäjän selaimessa käyttämään oletusfonttikokoon.) |
| `vw`, `vh`     | Näkymäikkunan leveys ja korkeus (1vw = 1 % ruudun leveydestä).                                          |
| `vmin`, `vmax` | Pienemmän (`vmin`) tai suuremman (`vmax`) näkymämitan mukaan.                                           |
| `ch`           | Valitun fontin numeron 0 leveys.                                                                        |
| `ex`           | Valitun fontin pienen x-kirjaimen korkeus.                                                              |

```css
.container {
  width: 80%; /* Vie 80 % vanhemmasta elementistä */
}

h1 {
  font-size: 2rem; /* 2x juurielementin fonttikoko */
}

.box {
  height: 50vh; /* 50 % näkymäikkunan korkeudesta */
}
```

Käytä suhteellisia yksiköitä skaalautuvaan ja responsiiviseen asetteluun.

---

## Oikean yksikön valitseminen

| Käyttötarkoitus               | Suositellut yksiköt                           |
| ----------------------------- | --------------------------------------------- |
| Fonttikoot                    | `rem` (skaalautuu käyttäjän asetusten mukaan) |
| Välistykset (padding, margin) | `em`, `rem`, `%`                              |
| Responsiiviset asettelut      | `%`, `vw`, `vh`                               |
| Reunukset                     | `px` (kiinteä koko)                           |

---

## Tärkeimmät erot `em`- ja `rem`-yksiköiden välillä

| Yksikkö | Suhteessa mihin                          |
| ------- | ---------------------------------------- |
| `em`    | **Vanhemman** elementin fonttikokoon     |
| `rem`   | **Juurielementin (`html`)** fonttikokoon |

```css
html {
  font-size: 16px;
}

.parent {
  font-size: 20px;
}

.child {
  font-size: 1.5em; /* 1.5 x 20px = 30px */
}

.another-child {
  font-size: 1.5rem; /* 1.5 x 16px = 24px */
}
```

Käytä `rem`-yksikköä johdonmukaiseen skaalaukseen koko sivustolla.

## Näkymäikkunayksiköt koko näytön asetteluihin

Näkymäikkunayksiköt (`vw`, `vh`, `vmin`, `vmax`) ovat hyödyllisiä täysruutuelementtien suunnittelussa.

```css
.hero {
  width: 100vw; /* Koko näytön leveys */
  height: 100vh; /* Koko näytön korkeus */
}
```

Käytä näkymäikkunayksiköitä täysnäyttöisiin osioihin ja dynaamisiin asetteluihin.

## Yhteenveto

- Absoluuttiset yksiköt (`px`, `cm`, `pt`) – Sopivat parhaiten kiinteisiin kokoihin.
- Suhteelliset yksiköt (`%`, `em`, `rem`, `vw`, `vh`) – Parhaita responsiivisiin suunnitelmiin.
- Käytä `rem` fonttikokoihin, `%` joustaviin asetteluihin ja `vh`/`vw` koko ruudun kokoisiin elementteihin.
