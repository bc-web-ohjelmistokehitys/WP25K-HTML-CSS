## Fontit, värit ja taustat -harjoitus

---

### **Vaihe 1: Luo projektikansio**

- html_kurssi-kansion sisälle, luo kansio nimeltä **03_viikko**.
- 03_viikko-kansion sisälle, luo alikansio nimeltä:
  - **harjoitus_1**
- Luo **harjoitus_1** kansion sisälle seuraavat tiedostot:
  - **index.html**
  - **style.css**

---

### **Vaihe 2: Rakenna HTML-perusrakenne**

- Valitse sivulle aihe. Se voi olla **vapaavalintainen** tai yksi seuraavista: "_Sammakot_", "_Parasta keväässä_", "_Kirjallisuutta, josta pidän_".

- Lisää `index.html`-tiedostoon HTML5-perusrakenne:
  - Otsikkotagi `<title>`
  - `<head>` ja `<body>` -osiot
- Linkitä CSS-tiedosto `<head>` elementissä.
- Lisää `body`-elementin sisälle `<h1>`-otsikko ja kaksi `<p>`-kappaletta.

---

### **Vaihe 3: Lisää kaksi eri fonttia**

- Valitse kaksi eri fonttia [Google Fonts](https://fonts.google.com) -palvelusta.
  - Esimerkiksi yksi fontti **otsikolle** ja toinen **kappaleille**.
- Lisää valitut fontit `<head>`-osioon `link`-elementillä.
- Määrittele fontit **styles.css**-tiedostossa seuraavasti:
  - Otsikolle oma fontti.
  - Kappaleille toinen fontti.

---

### **Vaihe 4: Muotoile värit**

- Lisää tyylit:
  - Aseta **taustaväri** koko sivulle (body).
  - Määrittele **otsikolle tekstiväri**, joka erottuu taustasta.
  - Aseta kappaleille oma **tekstiväri**.

---

### **Vaihe 5: Lisää osio, jossa on liukuväri-tausta**

- Lisää HTML-tiedostoon uusi elementti, esim. `<section class="gradient-box">`.
- Kirjoita osion sisälle yksi alaotsikko `<h2>` ja yksi kappale `<p>`.
- Luo CSS-sääntö, joka antaa kyseiselle osalle **liukuvärin** taustaksi. Voit luoda sellaisen liukuväri-generaattorin ([esimerkki 1](https://cssgradient.io/), [esimerkki 2](https://www.css-gradient.com/)) avulla.
- Lisää CSS-sääntö tämän elementin taustaksi.
- Tarkista, että teksti säilyy luettavana. Vaihda tarvittaessa elementin tekstin väriä.

---

### **Vaihe 6: Testaa projektisi**

- Avaa `index.html` selaimessa Live Serverin avulla.
- Tarkista:
  - Fontit toimivat (otsikolla ja tekstillä eri fontti)
  - Värit näkyvät oikein
  - Likuväri-tausta näkyy vain yhdessä osiossa
