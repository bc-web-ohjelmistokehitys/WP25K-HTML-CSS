# Magic 8-pallo -simulaattori

### Tämä pop-kulttuurista tuttu lelu vastaa kysymyksiin.

Kysymykset ovat luonteeltaan sellaisia, joihin on kyllä tai ei vastaus esimerkiksi "Pitääkö ihastukseni minusta?" - tosin pallo vastaa muutenkin kuin vain "kyllä" tai "ei".

## Esimerkkitoteutuksia verkossa

- Jos haluat hifistellä, katso mallia tästä: [magic-8ball.io](https://magic-8ball.io/)
- Huomattavasti kämäisempi versio: [magic8online.com](https://magic8online.com/)

## Tehtävänanto:

### Tavoite

Rakenna interaktiivinen Magic 8-pallo -sovellus HTML\:llä, CSS\:llä ja JavaScriptillä. Harjoittele tekoälyn käyttöä CSS-suunnittelun apuna (pallo ja animaatio). Käytä CSS-animaatiota projektissa.

---

### 1. Projektin alustus

- Luo uusi kansio projektille.
- Luo sinne seuraavat tiedostot:

  - `index.html`
  - `styles.css`
  - `script.js`

- Varmista, että HTML-linkitykset (`<link>` ja `<script>`) toimivat.

---

### 2. HTML

- Rakenna yksinkertainen dokumentti, jossa on:

  1. Tekstikenttä kysymyksen syöttämistä varten.
  2. Kysy-painike.
  3. Visuaalinen Magic 8-pallo-elementti, jonka sisään vastaus ilmestyy.

- Käytä mieleisiäsi luokkia/ID-tunnisteita, jotta CSS ja JS löytävät elementit.

---

### 3. CSS-osuuden vaatimukset

1. **Pallon ulkonäkö**

   - Tee pallosta pyöreä ja noin **300 × 300 px** kokoinen.
   - **Suositelen käyttämään AI-työkaluja (esim. ChatGPT, CSS-generoijat) varjostusten, gradienttien ja tekstuurin luomiseksi.**
   - Tässä esimerkki tekoälyn tuottamasta pallosta, joka on toteutettu CSS:llä
  
     
     ![/kasipallo](/assets/kasipallo.png)

2. **Ikkuna ja sisäelementit**

   - Luo pallon sisälle “ikkuna” (toinen ympyrä), johon asetat vastauksen.
   - Voit halutessasi luoda myös kulmikkaan ja liikkuvan osan vastaukselle.
   - Varmista, että teksti pysyy reunojen sisällä.

3. **Animaatiot**

   - Määrittele `@keyframes shake`-animaatio pallon ravistelua varten.
   - Määrittele fade-in-efektit (opacity + transition) vastauksen ilmestymiselle.
   - Sovelluksessa JavaScript lisää ja poistaa luokat `.shake` ja `.show-answer`.

---

### 4. JavaScript-osuuden vaatimukset

**Vastauslista**

- Luo taulukko, jossa on vähintään 8 kappaletta enintään 25 merkin pituisia vastauksia.

**Elementtien haku**

- Hae DOM\:ista kysymyskenttä, nappi, pallo ja tekstielementti.

**Kyselylogiikka**

- Luo funktio, joka:

  1.  Tarkistaa tekstikentän (ei tyhjä).
  2.  Nollaa edellisen tuloksen.
  3.  Lisää palloon `.shake`-luokan.
  4.  Kuuntelee `animationend`-tapahtumaa ja sen jälkeen:

      - Valitsee satunnaisen vastauksen.
      - Asettaa tekstiksi.
      - Poistaa `.shake` ja lisää `.show-answer`.

**Tapahtumakuuntelijat**

- Napin `click` ja syötekentän Enter-näppäin laukaisevat funktion.
