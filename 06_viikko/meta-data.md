# Meta-tiedot HTML:ssä

Meta-tiedot HTML:ssä tarjoavat tärkeää tietoa verkkosivusta ja auttavat hakukoneita, sosiaalista mediaa ja selaimia ymmärtämään sivun sisältöä. Ne lisätään HTML-dokumentin `<head>`-osioon.

## Miksi meta-tiedot ovat tärkeitä

- Auttaa hakukoneita **ymmärtämään** verkkosivusi.
- Parantaa **hakukonenäkyvyyttä (SEO)**.
- Määrittää, miltä sivu näyttää **sosiaalisessa mediassa**.
- Asettaa merkistön ja näkymäasetukset paremman **käyttökokemuksen** takaamiseksi.

## Yleiset meta-tagit

### 1. **Title-tag**

Määrittää sivun otsikon, joka näkyy selaimen välilehdessä ja hakutuloksissa.

```html
<title>Upea verkkosivuni</title>
```

### 2. **Meta-kuvaus (description)**

Lyhyt yhteenveto verkkosivun sisällöstä, usein näkyvissä hakutuloksissa.

```html
<meta
  name="description"
  content="Opi käyttämään HTML-meta-tageja SEO:n ja käyttökokemuksen parantamiseen."
/>
```

### 3. **Meta-avainsanat (keywords)** _(Harvoin käytetty nykyään)_

Sisälsi aiemmin sisältöön liittyviä avainsanoja, mutta ei ole enää tärkeä SEO:ssa.

```html
<meta name="keywords" content="HTML, meta tagit, SEO, web-kehitys" />
```

### 4. **Viewport-meta-tag** _(Responsiivista suunnittelua varten)_

Varmistaa, että sivu skaalautuu oikein mobiililaitteilla.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### 5. **Merkistökoodaus (Character Encoding)**

Määrittää käytettävän merkistön, jotta erikoismerkit näkyvät oikein.

```html
<meta charset="UTF-8" />
```

## Sosiaalisen median meta-tagit

### 6. **Open Graph (OG) -tagit** _(Facebookia, LinkedIniä jne. varten)_

Parantaa, miltä verkkosivu näyttää jaettuna sosiaalisessa mediassa.

```html
<meta property="og:title" content="Upea verkkosivuni" />
<meta property="og:description" content="Opi HTML-meta-tageista!" />
<meta property="og:image" content="https://example.com/image.jpg" />
<meta property="og:url" content="https://example.com" />
```

### 7. **Twitter Card -tagit** _(Twitter-jakoja varten)_

Mukauttaa, miltä linkit näyttävät Twitterissä.

```html
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Upea verkkosivuni" />
<meta name="twitter:description" content="Opi HTML-meta-tageista!" />
<meta name="twitter:image" content="https://example.com/image.jpg" />
```

## Robots-meta-tag _(Hakukoneita varten)_

Määrittää, saavatko hakukoneet indeksoida sivun ja seurata linkkejä.

```html
<meta name="robots" content="index, follow" />
```

- `index, follow` → Salli indeksointi ja linkkien seuraaminen.
- `noindex, nofollow` → Estä indeksointi ja linkkien seuraaminen.

## Refresh & Redirect -meta-tag _(Käytä varoen)_

Päivittää tai ohjaa sivun uudelleen määräajan kuluttua.

```html
<meta http-equiv="refresh" content="5; url=https://newpage.com" />
```

- Uudelleenohjaa osoitteeseen "newpage.com" **5 sekunnin** kuluttua.
