# HTML-typografia

Typografialla on tärkeä rooli verkkosuunnittelussa – se varmistaa sisällön luettavuuden, visuaalisen miellyttävyyden ja selkeän rakenteen. HTML tarjoaa useita elementtejä tekstin muotoiluun ja lainausten esittämiseen tehokkaasti.

## Typografian perusteet

### **Otsikot**

- HTML tarjoaa kuusi otsikkotasoa, `<h1>` (tärkein) – `<h6>` (vähiten tärkeä).
- Käytä otsikoita määrittämään sisältösi hierarkia.

```html
<h1>Pääotsikko</h1>
<h2>Alaotsikko</h2>
<h3>Osion otsikko</h3>
```

### **Kappaleet**

- `<p>`-elementti määrittelee tekstikappaleen.
- Käytä kappaleita erottelemaan sisältölohkoja.

```html
<p>Tämä on tekstikappale.</p>
```

### **Tekstin muotoilu**

- **Lihavointi:** `<b>` tai `<strong>` korostukseen.
  ```html
  <strong>Tärkeä teksti</strong>
  ```
- **Kursivointi:** `<i>` tai `<em>` korostukseen.
  ```html
  <em>Korostettu teksti</em>
  ```
- **Alleviivaus:** `<u>` alleviivatulle tekstille.
  ```html
  <u>Alleviivattu teksti</u>
  ```
- **Ylä- ja alaviite:**
  ```html
  H<sub>2</sub>O (vesi), E=mc<sup>2</sup>
  ```

## Lainaukset

### **Lainauslohko (Blockquote)**

- Käytä `<blockquote>`-elementtiä pitkiin lainauksiin tai viittauksiin.
- Selaimet sisentävät sen yleensä automaattisesti.

```html
<blockquote>
  The only limit to our realization of tomorrow is our doubts of today.
</blockquote>
```

### **Rivin sisäiset lainaukset (Inline Quotes)**

- Käytä `<q>`-elementtiä lyhyisiin, rivin sisäisiin lainauksiin.
- Selaimet lisäävät lainausmerkit automaattisesti.

```html
<p>The philosopher said, <q>Knowledge is power.</q></p>
```

### **Lähdeviittaukset (Citations)**

- Käytä `<cite>`-elementtiä viitataksesi lainauksen tai tekstin lähteeseen.

```html
<cite>Franklin D. Roosevelt</cite>
```

### **Lyhenteet**

- Käytä `<abbr>`-elementtiä määritelläksesi lyhenteen, joka näyttää työkaluvihjeen täydestä muodosta.

```html
<abbr title="HyperText Markup Language">HTML</abbr>
```

## Typografian ja lainausten yhdistäminen

```html
<!DOCTYPE html>
<html lang="fi">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Typografia ja lainaukset</title>
  </head>
  <body>
    <h1>Typografian ymmärtäminen</h1>
    <p>Typografia parantaa sisällön luettavuutta ja rakennetta.</p>

    <h2>Lainauslohkon esimerkki</h2>
    <blockquote>
      The journey of a thousand miles begins with a single step.
    </blockquote>

    <h2>Rivin sisäinen lainaus</h2>
    <p>
      Lao Tzu sanoi,
      <q>The journey of a thousand miles begins with a single step.</q>
    </p>

    <h2>Lähteen mainitseminen</h2>
    <p>Tämä lainaus on peräisin henkilöltä <cite>Lao Tzu</cite>.</p>

    <h2>Lyhenteiden käyttö</h2>
    <p>
      Termi <abbr title="Cascading Style Sheets">CSS</abbr> on olennainen osa
      verkkokehitystä.
    </p>
  </body>
</html>
```
