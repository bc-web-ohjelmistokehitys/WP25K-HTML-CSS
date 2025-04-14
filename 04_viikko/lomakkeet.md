# HTML-lomakkeet ja syötekenttäelementit

## Lomakkeen rakenne

Peruslomake koostuu `<form>`-elementistä, joka sisältää syötekenttiä ja lähetyspainikkeen.

### Esimerkki yksinkertaisesta lomakkeesta

```html
<form action="/submit" method="POST">
  <label for="name">Nimi:</label>
  <input type="text" id="name" name="name" required />

  <label for="email">Sähköposti:</label>
  <input type="email" id="email" name="email" required />

  <button type="submit">Lähetä</button>
</form>
```

### **Tärkeimmät attribuutit lomakkeissa**

- **`action`** → Mihin lomakedata lähetetään.
- **`method`** → `GET` (näkyy URL-osoitteessa) tai `POST` (turvallinen arkaluonteiselle tiedolle).
- **`name`** → Tunnistaa syötteen lomakkeen lähetyksessä.
- **`id`** → Linkittää syötteen sen `<label>`-elementtiin.
- **`required`** → Vaatii kentän täyttämistä ennen lomakkeen lähettämistä.

## Semanttiset lomake-elementit

Semanttisen HTML:n käyttö tekee lomakkeista helpommin luettavia ja saavutettavia.

### **Tärkeimmät semanttiset elementit**

| Elementti    | Kuvaus                                 |
| ------------ | -------------------------------------- |
| `<form>`     | Määrittää lomakeosion                  |
| `<label>`    | Kuvaa syötekenttää                     |
| `<input>`    | Tavallinen syötekenttä                 |
| `<textarea>` | Monirivinen tekstikenttä               |
| `<select>`   | Pudotusvalikko                         |
| `<option>`   | Yksittäinen valinta `<select>`issä     |
| `<fieldset>` | Ryhmittelee toisiinsa liittyvät kentät |
| `<legend>`   | Otsikko `<fieldset>`ille               |
| `<button>`   | Lomakkeen lähetyspainike               |

```html
<form>
  <fieldset>
    <legend>Henkilötiedot</legend>
    <label for="name">Nimi:</label>
    <input type="text" id="name" name="name" required />

    <label for="message">Viesti:</label>
    <textarea id="message" name="message" rows="4" cols="30"></textarea>
  </fieldset>

  <button type="submit">Lähetä</button>
</form>
```

## Yleiset syötekenttätyypit

| Syötekentän tyyppi | Kuvaus                                 |
| ------------------ | -------------------------------------- |
| `text`             | Perustekstikenttä                      |
| `email`            | Vaatii kelvollisen sähköpostiosoitteen |
| `password`         | Piilottaa syötetyt merkit              |
| `number`           | Sallii vain numerot                    |
| `tel`              | Hyväksyy puhelinnumerot                |
| `date`             | Päivämäärän valinta                    |
| `checkbox`         | Mahdollistaa useita valintoja          |
| `radio`            | Valitaan yksi vaihtoehto ryhmästä      |
| `file`             | Tiedoston lähetys                      |
| `submit`           | Lähettää lomakkeen                     |

### Esimerkki eri syötekenttätyypeistä

```html
<form>
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required />

  <label for="age">Ikä:</label>
  <input type="number" id="age" name="age" min="18" />

  <label for="dob">Syntymäaika:</label>
  <input type="date" id="dob" name="dob" />

  <label>Valitse vaihtoehto:</label>
  <input type="radio" id="option1" name="choice" value="1" /> Vaihtoehto 1
  <input type="radio" id="option2" name="choice" value="2" /> Vaihtoehto 2

  <button type="submit">Lähetä</button>
</form>
```

## Lomakkeiden parhaat käytännöt

- Käytä **semanttisia elementtejä**, kuten `<label>`, parantaaksesi saavutettavuutta.
- Lisää **`required`**- ja **`placeholder`**-attribuutit ohjataksesi käyttäjää.
- Käytä **`fieldset`**- ja **`legend`**-elementtejä ryhmittelemään toisiinsa liittyvät kentät.
- Varmista, että **label- ja input-elementit on linkitetty** oikein `for`-attribuutin avulla.
- Tarjoa **hyödyllisiä virheilmoituksia**, kun validointi epäonnistuu.
