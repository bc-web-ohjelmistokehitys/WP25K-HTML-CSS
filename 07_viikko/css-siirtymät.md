# CSS-siirtymät (Transitions)

CSS:n **siirtymät** mahdollistavat ominaisuuksien muuttumisen **pehmeästi ajan myötä** sen sijaan, että ne muuttuisivat välittömästi. Ne sopivat erityisesti **hover-efekteihin, värimuutoksiin ja yksinkertaisiin käyttöliittymäanimaatioihin**.

```css
.element {
  transition: property duration timing-function delay;
}
```

- **Property** → Animoitava CSS-ominaisuus (esim. `opacity`, `transform`).
- **Duration** → Kesto (esim. `0.5s` tai `300ms`).
- **Timing-function** → Nopeuden vaihtelu (`ease`, `linear`, `ease-in-out`).
- **Delay** _(valinnainen)_ → Viive ennen siirtymän alkamista.

```css
.button {
  background-color: blue;
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: red;
}
```

**Vaikutus**: Painikkeen väri muuttuu **sulavasti sinisestä punaiseksi** hover-tilassa.

## Usean ominaisuuden siirtäminen

Voit animoida **useita ominaisuuksia** samanaikaisesti:

```css
.box {
  width: 100px;
  height: 100px;
  background-color: green;
  transition: width 0.5s ease, height 0.5s ease;
}

.box:hover {
  width: 200px;
  height: 200px;
}
```

**Vaikutus**: Laatikko **kasvaa** kun sitä osoitetaan hiirellä.

## `all` useisiin siirtymiin

Yksittäisten ominaisuuksien sijaan voit käyttää `all` siirtämään **kaikkia** ominaisuuksia.

```css
.card {
  transition: all 0.5s ease;
}

.card:hover {
  transform: scale(1.1);
  background-color: lightblue;
}
```

**Vaikutus**: Kortti **suurenee ja vaihtaa väriä** hover-tilassa.

## Modernit esimerkit siirtymistä

### Sulava alasvetovalikko

```css
.menu {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.5s ease-in-out;
}

.menu.open {
  max-height: 300px;
}
```

**Vaikutus**: Valikko avautuu ja sulkeutuu sulavasti.

### Pehmeä painikkeen painallusefekti

```css
.button {
  transition: transform 0.2s ease;
}

.button:active {
  transform: scale(0.95);
}
```

**Vaikutus**: Painike näyttää painuvan hieman sisään klikatessa.

### Kuvan zoomaus hover-tilassa

```css
.image-container img {
  transition: transform 0.3s ease-in-out;
}

.image-container:hover img {
  transform: scale(1.1);
}
```

**Vaikutus**: Kuva zoomautuu hieman sisäänpäin, kun sitä osoitetaan hiirellä.

### Tekstin alleviivauksen animaatio hoverilla

```css
.link {
  display: inline-block;
  position: relative;
  text-decoration: none;
  color: #333;
}

.link::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  bottom: 0;
  left: 0;
  background-color: #007bff;
  transform: scaleX(0);
  transition: transform 0.3s ease-in-out;
}

.link:hover::after {
  transform: scaleX(1);
}
```

**Vaikutus**: Alleviivaus laajenee sulavasti, kun tekstiä osoitetaan hiirellä.

### Häivytysefekti vieritettäessä

```css
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```

**Vaikutus**: Elementit ilmestyvät sulavasti näkyviin, kun ne vieritetään näkymään (vaatii JavaScriptin lisäämään luokan `.visible`).

## Siirtymäviiveet ja mukautetut ajoitusfunktiot

Voit lisätä viiveen ja käyttää erilaisia nopeuskäyriä:

```css
.element {
  transition: opacity 0.5s ease-in-out 0.2s;
}
```

**Vaikutus**: Siirtymä alkaa **0,2 sekunnin** kuluttua ja etenee pehmeästi **ease-in-out**-käyrällä.

| Ajoitusfunktio | Vaikutus                                     |
| -------------- | -------------------------------------------- |
| `linear`       | Tasainen nopeus koko ajan                    |
| `ease`         | Hidas alku ja loppu, nopea keskiosa (oletus) |
| `ease-in`      | Hidas alku, sitten nopeutuu                  |
| `ease-out`     | Nopea alku, sitten hidastuu                  |
| `ease-in-out`  | Hidas alku ja loppu                          |

## Transform-siirtymien animointi

Voit animoida **sijaintia, kiertoa ja skaalausta**.

```css
.image {
  transform: scale(1);
  transition: transform 0.3s ease;
}

.image:hover {
  transform: scale(1.2);
}
```

**Vaikutus**: Kuva **zoomautuu** pehmeästi sisään.

## Parhaat käytännöt CSS-siirtymissä

- Käytä **lyhyempiä kestoja** nopeisiin interaktioihin.
- Suosi **ease-in-out**-ajoitusta luonnollisempaan tuntumaan.
- **Testaa eri laitteilla**, jotta suorituskyky säilyy sulavana.
