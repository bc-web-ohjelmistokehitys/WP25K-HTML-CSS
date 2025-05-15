# Vanilla\* JavaScript -projektin julkaisu

\*Termi **Vanilla JavaScript** viittaa puhtaaseen JavaScriptiin, ilman mitään kirjastoja tai kehyksiä, kuten jQuery tai React. Se tarkoittaa JavaScriptin käyttöä sen alkuperäisessä muodossa.

Vanilla JavaScript -projektin julkaisu on suoraviivaista ja sen voi tehdä useilla eri tavoilla. **Samat ohjeet koskevat myös sivuja, joissa on käytössä ainoastaan HTML ja CSS.**

## 1. Projektin valmistelu julkaisua varten

Varmista ennen julkaisua, että:

- Koodisi on siisti ja hyvin jäsennelty.
- Kaikki riippuvuudet (jos niitä on) on linkitetty oikein.
- Projekti toimii paikallisesti kehityspalvelimella.
- Projektissa on `index.html`-tiedosto pääsivuna.

## 2. Julkaisumenetelmät

### 2.1 GitHub Pages (statisten sivujen julkaisuun)

**Sopii parhaiten:** Yksinkertaisille projekteille ilman taustatoimintoja.

1. Pushaa projektisi GitHub-repositorioon.
2. Siirry repositorion asetuksiin.
3. Kohdassa **Pages**, valitse `main`-haara ja `/ (root)`-kansio.
4. Klikkaa **Save** – projektisi julkaistaan osoitteessa `https://käyttäjänimesi.github.io/repositorio-nimi/`.

### 2.2 Netlify (helppoon julkaisuun)

**Sopii parhaiten:** Staattisille sivustoille, joissa voi olla lomakkeita tai serverless-toimintoja.

1. Luo tili osoitteessa [Netlify](https://www.netlify.com/).
2. Linkitä GitHub-repositoriosi.
3. Valitse haara ja julkaisuasetukset.
4. Klikkaa **Deploy** – Netlify antaa käyttöön live-linkin.

### 2.3 Vercel (instant-julkaisu)

**Sopii parhaiten:** Staattisille frontend-projekteille, joita voidaan myöhemmin laajentaa backendillä.

1. Luo tili osoitteessa [Vercel](https://vercel.com/).
2. Tuo GitHub-projektisi.
3. Klikkaa **Deploy** – saat käyttöön live-URL-osoitteen.

### 2.4 Firebase Hosting (skaalautuva hosting)

**Sopii parhaiten:** Projekteille, joissa tarvitaan esim. tietokanta tai kirjautumistoiminto.

1. Asenna Firebase CLI:

   ```sh
   npm install -g firebase-tools
   ```

2. Kirjaudu Firebaseen:

   ```sh
   firebase login
   ```

3. Alusta Firebase projektissasi:

   ```sh
   firebase init
   ```

4. Valitse **Hosting** ja konfiguroi asetukset.
5. Julkaise projekti:

   ```sh
   firebase deploy
   ```

6. Projektisi julkaistaan Firebase-URL-osoitteessa.

### 2.5 Perinteinen hosting (FTP / oma palvelin)

**Sopii parhaiten:** Itse hallittuihin palvelimiin tai klassiseen webhotellijulkaisuun.

1. Osta hosting esim. Bluehostilta, Hostingerilta tai DigitalOceanilta.
2. Siirrä projektin tiedostot FTP\:n kautta esim. FileZillalla.
3. Määritä domain ja DNS-asetukset.
4. Pääset sivustoosi määritellyllä domainilla.

## 3. Koodin optimointi tuotantoon

### 3.1 Minifioi ja niputa tiedostot

- Minifioi CSS-, JavaScript- ja HTML-tiedostot [Terser](https://terser.org/)\:n tai [UglifyJS](https://github.com/mishoo/UglifyJS)\:n avulla.
- Niputa useat JS-tiedostot yhteen esim. [Webpack](https://webpack.js.org/)\:illa.

### 3.2 Kuvien optimointi

- Pienennä kuvia esim. [TinyPNG](https://tinypng.com/) tai [ImageOptim](https://imageoptim.com/) -työkaluilla.
- Käytä moderneja formaatteja, kuten **WebP**.

### 3.3 Suorituskyvyn parantaminen

- Poista käyttämätön CSS ja JS.
- Lataa skriptejä `async` tai `defer` -attribuuteilla.
- Käytä kuvissa lazy loadingia: `loading="lazy"`.

### 3.4 Välimuisti ja pakkaus

- Käytä service workereita resurssien välimuistiin.
- Ota käyttöön Gzip tai Brotli -pakkaus palvelimella.

### 3.5 Koodin laatu

- Käytä ESLint\:ia yhtenäiseen koodityyliin.
- Jäsennä tiedostot selkeästi kansioihin kuten `css/`, `js/`, `assets/`.

## 4. Testaus ja virheiden tarkistus ennen julkaisua

- Suorita testit **Lighthouse**-työkalulla (Chrome DevToolsissa).
- Tarkista rikkinäiset linkit ja konsolivirheet.
- Testaa eri selaimilla ja laitteilla.

## 5. Yhteenveto

Valitse oikea julkaisumenetelmä projektisi mukaan:

- **GitHub Pages**: nopeaan julkaisuun ilman backendia.
- **Netlify / Vercel**: joustavat ja helppokäyttöiset ratkaisut.
- **Firebase**: jos tarvitset skaalautuvuutta ja lisäominaisuuksia.
- **Perinteinen hosting**: täydelliseen hallintaan ja omaan palvelinympäristöön.
