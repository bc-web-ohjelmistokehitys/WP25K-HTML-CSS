# Saavutettavuuden ja suorituskyvyn testaus ennen julkaisua

Ennen kuin julkaiset verkkosivuston tai -sovelluksen, on tärkeää tarkistaa saavutettavuus- ja suorituskykyongelmat. Nämä vaikuttavat käyttökokemukseen, latausnopeuteen ja siihen, kuinka hyvin sivusto toimii kaikille – mukaan lukien käyttäjät, joilla on vammoja, tai joilla on hidas verkkoyhteys.

## 1. Saavutettavuustestaus

Saavutettavuus varmistaa, että verkkosivusto on käytettävissä ihmisille, joilla on erilaisia vammoja. Tämä kattaa esimerkiksi näppäimistönavigoinnin, ruudunlukijan tuen, värierojen kontrastin ja paljon muuta.

### Käytettävät työkalut

- Lighthouse (Chrome DevTools)

  - Aja DevToolsista → Lighthouse-välilehdeltä
  - Antaa pisteitä saavutettavuudesta, suorituskyvystä, SEO:sta jne.
  - Tuo esiin puuttuvat nimilaput, kontrastiongelmat, näppäimistöansat

- axe DevTools (Deque)

  - Selainlaajennus (Chrome/Firefox)
  - Nopeat saavutettavuusauditoinnit selityksineen
  - Tunnistaa WCAG-rikkomukset reaaliajassa

- Wave (web-saavutettavuusarviointityökalu)
  - Visuaalinen työkalu, joka näyttää ongelmat sivun päällä
  - Tunnistaa otsikkorakenteet, ARIA-roolit, kontrastiongelmat

### Parhaat käytännöt

- Käytä semanttista HTML:ää (`<button>`, `<nav>`, `<main>` jne.)
- Varmista näppäimistönavigointi (Tab, Enter, Esc)
- Lisää `alt`-teksti kaikille merkityksellisille kuville
- Nimeä kaikki lomakekentät `<label for="...">` -elementeillä
- Käytä korkeaa värikontrastia luettavuuden vuoksi
- Älä käytä vain väriä merkityksen ilmaisemiseen

## 2. Suorituskyvyn testaus

Suorituskyky vaikuttaa siihen, kuinka nopeasti sivu latautuu ja kuinka sujuvalta se tuntuu. Käyttäjät voivat poistua, jos sivusto on liian hidas.

### Käytettävät työkalut

- Lighthouse (uudelleen!)

  - Tunnistaa suuret JS/CSS-tiedostot, käyttämättömän koodin, hitaat renderöinnit
  - Ehdottaa parannuksia, kuten lazy loading, välimuisti, minimointi

- WebPageTest

  - Näyttää vesiputouskaavioita lataustapahtumista
  - Korostaa kriittiset pyynnöt, first byte -ajan jne.

- PageSpeed Insights
  - Googlen työkalu, joka arvioi mobiili- ja työpöytäsuorituskykyä
  - Antaa parannusehdotuksia sekä labra- että kenttädatan perusteella

### Ennen julkaisua: Optimoi nämä

#### HTML/CSS/JS-minifiointi

- Käytä työkaluja kuten [Minify](https://www.minifier.org/) tai rakennustyökalua (esim. Vite, Webpack)
- Poista tyhjät välit, kommentit ja tarpeeton koodi

#### Kuvien optimointi

- Pakkaa kuvat
- Käytä moderneja formaatteja kuten `WebP` tai `AVIF`
- Lisää `width`- ja `height`-attribuutit asettelun vakauden vuoksi

#### Tehokas CSS

- Vältä syvää sisäkkäisyyttä ja monimutkaisia valitsimia
- Poista käyttämättömät tyylit

#### JavaScriptin tehokkuus

- Vältä pääsäikeen estämistä
- Jaa bundlet ja käytä lazy loadingia (`import()`)
- Käytä `defer` tai `async` ei-kriittisille skripteille

#### Fontit

- Käytä järjestelmäfontteja aina kun mahdollista
- Lataa mukautetut fontit asynkronisesti (`font-display: swap`)
- Lataa vain tarvittavat fonttipainot

## Tarkistuslista

## HTML

| Tarkista tämä                                 | Miksi se on tärkeää                                   | Miten tarkistaa                                           | Esimerkki (koodi tai vinkki)                                                |
| --------------------------------------------- | ----------------------------------------------------- | --------------------------------------------------------- | --------------------------------------------------------------------------- |
| Käytä semanttista HTML:ää                     | Auttaa ruudunlukijoita ja parantaa rakennetta         | Tarkista HTML-rakenne manuaalisesti tai Lighthousella     | Käytä esim. `<nav>`, `<main>`, `<article>`, `<button>`                      |
| Lisää `lang`-attribuutti `<html>`-elementtiin | Auttaa ruudunlukijaa havaitsemaan oikean kielen       | Tarkista HTML-tiedoston alku                              | `<html lang="fi">`                                                          |
| Lisää viewport-metaelementti                  | Mahdollistaa responsiivisen käyttäytymisen mobiilissa | Tarkista `<head>`-osio                                    | `<meta name="viewport" content="width=device-width, initial-scale=1.0">`    |
| Lisää alt-tekstit kuville                     | Kuvailee sisällön näkövammaisille käyttäjille         | Käytä Lighthousea tai axe-laajennusta                     | `<img src="logo.png" alt="Yrityksen logo">`                                 |
| Oikea otsikkorakenne                          | Parantaa ruudunlukijanavigointia ja SEO:ta            | Käytä Wave- tai selaimen saavutettavuustyökaluja          | Käytä vain yhtä `<h1>`-elementtiä ja loogisesti sisennettyjä `<h2>`, `<h3>` |
| Nimeä kaikki lomakekentät                     | Varmistaa saavutettavuuden apuvälineiden käyttäjille  | Käytä axe-laajennusta tai tarkista manuaalisesti          | `<label for="email">Sähköposti</label><input id="email">`                   |
| ARIA-attribuutit tarvittaessa                 | Tuo lisäselvyyttä kun semantiikka ei riitä            | Käytä axe DevTools -laajennusta                           | Lisää `role`, `aria-label`, `aria-hidden` tarpeen mukaan                    |
| Näppäimistönavigointi                         | Mahdollistaa käytön ilman hiirtä                      | Testaa Tab/Shift+Tab- ja Enter-näppäimillä                | Navigoi lomakkeita ja valikoita vain näppäimistöllä                         |
| Riittävä värikontrasti                        | Parantaa luettavuutta heikkonäköisille                | Käytä Lighthousea, axe-työkalua tai kontrastintarkistinta | Käytä kontrastisuhdetta vähintään 4.5:1 normaalille tekstille               |
| Vältä pelkän värin käyttöä                    | Tärkeää värisokeille käyttäjille                      | Tarkista käyttöliittymä manuaalisesti tai Wave-työkalulla | Käytä kuvakkeita, tekstiä tai kuvioita värien lisäksi                       |

## CSS

| Tarkista tämä                             | Miksi se on tärkeää                              | Miten tarkistaa                                               | Esimerkki (koodi tai vinkki)                        |
| ----------------------------------------- | ------------------------------------------------ | ------------------------------------------------------------- | --------------------------------------------------- |
| Responsiivinen suunnittelu (media queryt) | Varmistaa hyvän ulkoasun kaikilla laitteilla     | Muuta selaimen kokoa tai käytä Chrome DevToolsin laitenäkymää | `@media (max-width: 768px) { ... }`                 |
| Käytä CSS-lyhennettä kun mahdollista      | Pitää CSS:n siistinä ja tehokkaana               | Tarkista CSS manuaalisesti                                    | `margin: 10px 20px;` yksittäisten sijaan            |
| Vältä `!important`-määrityksiä            | Vaikeuttaa ylläpitoa ja ylikirjoittamista        | Etsi `!important` koodista                                    | Refaktoroi tyylit ilman `!important`-komentoa       |
| Käytä `font-display: swap` fonteissa      | Estää tekstin näkymättömyyden fontin latauksessa | Lisää `font-display: swap` `@font-face`-määrittelyyn          | `font-display: swap;` `@font-face`:n sisällä        |
| Lataa vain tarvittavat fonttipainot       | Nopeuttaa fonttien lataamista                    | Valitse tietyt painot Google Fontsista                        | Käytä `display=swap&weights=400;700` fontti-URL:ssa |

## Suorituskyky & Media

| Tarkista tämä                              | Miksi se on tärkeää                           | Miten tarkistaa                                                  | Esimerkki (koodi tai vinkki)                         |
| ------------------------------------------ | --------------------------------------------- | ---------------------------------------------------------------- | ---------------------------------------------------- |
| Minifioi HTML, CSS, JS                     | Pienentää tiedostokokoa ja nopeuttaa latausta | Käytä build-työkaluja tai online-minifioijia                     | Käytä `vite build` tai `terser`                      |
| Optimoi ja pakkaa kuvat                    | Säästää kaistanleveyttä ja nopeuttaa latausta | Käytä Squooshia tai TinyPNG:tä                                   | Pakkaa JPG:t 80 %:iin tai käytä WebP-formaattia      |
| Käytä moderneja kuvatiedostomuotoja (WebP) | Latautuvat nopeammin kuin JPEG/PNG            | Vie kuvat WebP:nä ja testaa                                      | `<img src="image.webp">`                             |
| Käytä lazy-loadingia kuville ja videoille  | Nopeuttaa sivun ensilatausta                  | Lisää `loading="lazy"` `<img>`- tai `<iframe>`-elementteihin     | `<img src="..." loading="lazy">`                     |
| Ota käyttöön välimuisti (palvelinpuolella) | Nopeuttaa sivuston lataamista uudelleen       | Tarkista vastauksen otsikot DevToolsin Verkko-välilehdellä       | Käytä `Cache-Control`, `ETag`, `Expires` -otsikoita  |
| Testaa mobiilissa ja hitaalla verkolla     | Simuloi todellisia käyttöolosuhteita          | Käytä Chrome DevToolsin verkon hidastusta ja laitteen emulointia | Hidasta "Fast 3G":lle ja testaa ulkoasu ja reagointi |
