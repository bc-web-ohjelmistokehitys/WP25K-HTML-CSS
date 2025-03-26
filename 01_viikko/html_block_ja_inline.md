# Lohko- ja rivinsisäiset elementit HTML:ssä

HTML-elementit jaotellaan **lohkoelementteihin (block)** ja **rivinsisäisiin elementteihin (inline)**, joilla on omat roolinsa verkkosivun rakenteen ja ulkoasun määrittelyssä. Näiden luokkien ymmärtäminen on olennaista hyvin jäsennellyn ja visuaalisesti miellyttävän sisällön luomisessa.

## Lohkoelementit

### Ominaisuudet

- Lohkoelementit alkavat uudelta riviltä ja vievät koko rivin leveyden.
- Niitä käytetään pääasiassa verkkosivun rakenteen määrittelyyn.
- Esimerkkejä ovat otsikot, kappaleet ja jakokontit.

### Yleisiä lohkoelementtejä

1. `<div>`: Yleiskäyttöinen kontti sisällön ryhmittelyyn.

   ```html
   <div>Tämä on lohkoelementti.</div>
   ```

2. `<p>`: Määrittelee tekstikappaleen.

   ```html
   <p>Tämä on kappale.</p>
   ```

3. `<h1>`–`<h6>`: Edustavat eri tasoisia otsikoita.

   ```html
   <h1>Pääotsikko</h1>
   <h2>Alaotsikko</h2>
   ```

4. `<ul>` ja `<ol>`: Järjestämättömät ja järjestetyt listat.

   ```html
   <ul>
     <li>Kohta 1</li>
     <li>Kohta 2</li>
   </ul>
   ```

5. `<blockquote>`: Käytetään pitkiin lainauksiin.
   ```html
   <blockquote>Tässä on lainauslohko.</blockquote>
   ```

## Rivinsisäiset elementit

### Ominaisuudet

- Rivinsisäiset elementit eivät ala uudelta riviltä ja vievät vain tarvitsemansa tilan.
- Niitä käytetään pääasiassa sisällön yksityiskohtaiseen muotoiluun tai korostamiseen lohkoelementin sisällä.

### Yleisiä rivinsisäisiä elementtejä

1. `<span>`: Yleiskäyttöinen rivinsisäinen kontti tekstin muotoiluun tai ryhmittelyyn.

   ```html
   <span style="color: red;">Tämä teksti on punainen.</span>
   ```

2. `<a>`: Määrittelee hyperlinkkejä.

   ```html
   <a href="https://example.com">Vieraile Example-sivustolla</a>
   ```

3. `<strong>` ja `<b>`: Tekevät tekstistä lihavoidun.

   ```html
   <strong>Tärkeä teksti</strong>
   ```

4. `<em>` ja `<i>`: Kursivoivat tekstin.

   ```html
   <em>Korostettu teksti</em>
   ```

5. `<img>`: Upottaa kuvia.

   ```html
   <img src="image.jpg" alt="Kuvaus" />
   ```

6. `<abbr>`: Merkitsee lyhenteet työkaluvihjeellä.
   ```html
   <abbr title="HyperText Markup Language">HTML</abbr>
   ```

## Lohko- ja rivinsisäisten elementtien yhdistäminen

Lohko- ja rivinsisäisiä elementtejä voidaan yhdistää hyvin jäsennellyn ja tyylitellyn sisällön luomiseksi. Esimerkiksi:

```html
<div>
  <h1>Tervetuloa sivustolleni</h1>
  <p>
    Tämä on kappale, jossa on <a href="#">rivinsisäinen linkki</a> ja hieman
    <strong>lihavoitua tekstiä</strong>.
  </p>
</div>
```

## Eroavaisuudet yhdellä silmäyksellä

| Ominaisuus                | Lohkoelementit      | Rivinsisäiset elementit        |
| ------------------------- | ------------------- | ------------------------------ |
| **Alkaa uudelta riviltä** | Kyllä               | Ei                             |
| **Vie koko leveyden**     | Kyllä               | Ei                             |
| **Yleinen käyttö**        | Rakenne ja asettelu | Muotoilu ja vuorovaikutteisuus |
