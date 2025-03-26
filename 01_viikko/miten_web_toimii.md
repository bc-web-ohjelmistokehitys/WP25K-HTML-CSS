# Miten verkko toimii

Verkkokehityksessä on tärkeää ymmärtää, miten verkko toimii. Tässä jaamme prosessin ja käsitteet yksinkertaisiin osiin, jotta perustoiminta olisi helpompi hahmottaa.

## Verkon rakennuspalikat

### Asiakas–palvelin-malli

- **Asiakas:** Selain (esim. Chrome, Firefox), joka pyytää ja näyttää tietoa.
- **Palvelin:** Tietokone, joka tallentaa ja toimittaa verkkosivun tiedot asiakkaalle.

### HTTP ja HTTPS

- **HTTP:** Lyhenne sanoista HyperText Transfer Protocol; mahdollistaa viestinnän asiakkaiden ja palvelimien välillä.
- **HTTPS:** Suojattu versio HTTP:stä, joka käyttää salausta tiedonsiirron turvaamiseksi.

### DNS (Domain Name System)

- Muuntaa ihmisten lukemat verkkotunnukset (kuten `example.com`) IP-osoitteiksi (kuten `192.168.1.1`).
- Toimii verkon puhelinluettelona.

## Miten se toimii: vaihe vaiheelta

1. **Kirjoitat selaimeen URL-osoitteen.**

   - Esimerkki: `www.example.com`

2. **Selain lähettää pyynnön DNS-palvelimelle.**

   - DNS-palvelin etsii verkkosivun IP-osoitteen.

3. **Selain pyytää tietoja palvelimelta.**

   - HTTP- tai HTTPS-protokollalla se pyytää tiedostoja, joista verkkosivu muodostuu.

4. **Palvelin vastaa verkkosivun tiedostoilla.**

   - Tiedostoihin kuuluu HTML (rakenne), CSS (tyyli) ja JavaScript (vuorovaikutteisuus).

5. **Selain renderöi verkkosivun.**
   - Se käsittelee tiedostot ja näyttää verkkosivun näytölläsi.

```plaintext
URL -> DNS -> Palvelin -> Vastaus -> Renderöinti
```

## Verkkosivun keskeiset osat

- **HTML:** Määrittää sisällön rakenteen (esim. otsikot, kappaleet, linkit).
- **CSS:** Tyylittelee sivun (esim. värit, fontit, asettelut).
- **JavaScript:** Lisää vuorovaikutteisuutta (esim. animaatiot, lomaketarkistukset).

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Esimerkki</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Tervetuloa verkkoon</h1>
    <p>Näin se toimii!</p>
    <script src="script.js"></script>
  </body>
</html>
```
