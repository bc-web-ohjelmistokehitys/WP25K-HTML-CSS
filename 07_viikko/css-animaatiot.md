# CSS-animaatiot

CSS:n **animaatiot** mahdollistavat elementtien liikkeen, häivytyksen, kasvamisen tai muun monimutkaisemman muutoksen verrattuna siirtymiin (transitions). Toisin kuin siirtymissä, animaatioissa voi olla useita vaiheita ja ne voivat toistua loputtomasti.

```css
@keyframes animaation-nimi {
  0% {
    ominaisuus: arvo;
  }
  100% {
    ominaisuus: arvo;
  }
}

.element {
  animation: animaation-nimi kesto ajoitus-funktio viive toistojen-määrä suunta;
}
```

- **`@keyframes`** → Määrittää animaation vaiheet.
- **`animation-name`** → Animaation nimi.
- **`duration`** → Kuinka kauan animaatio kestää.
- **`iteration-count`** → Kuinka monta kertaa animaatio toistetaan (`infinite` = loputon).
- **`direction`** → `normal`, `reverse`, `alternate` jne.

```css
@keyframes bounce {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0);
  }
}

.box {
  width: 100px;
  height: 100px;
  background-color: orange;
  animation: bounce 0.5s ease infinite;
}
```

**Vaikutus**: Laatikko **pomppii ylös ja alas**.

## Useiden keyframe-vaiheiden käyttö

```css
@keyframes colorChange {
  0% {
    background-color: red;
  }
  50% {
    background-color: blue;
  }
  100% {
    background-color: green;
  }
}

.box {
  animation: colorChange 3s ease infinite;
}
```

**Vaikutus**: Laatikko **vaihtaa väriä punaisesta siniseen ja vihreään**.

## Animaation nopeuden ja toistojen hallinta

| Ominaisuus                  | Vaikutus                                |
| --------------------------- | --------------------------------------- |
| `animation-duration`        | Kesto yhdelle kierrokselle (esim. `2s`) |
| `animation-delay`           | Viive ennen aloitusta (esim. `1s`)      |
| `animation-iteration-count` | Toistojen määrä (`1`, `3`, `infinite`)  |
| `animation-direction`       | `normal`, `reverse`, `alternate`, jne.  |

Esimerkki:

```css
.element {
  animation: spin 2s linear 1s infinite alternate;
}
```

**Vaikutus**: Elementti pyörii loputtomasti ja vaihtaa suuntaa joka kierroksella.

## Hover-pohjaiset animaatiot

Animaatio voidaan käynnistää `hover`-toiminnolla ilman JavaScriptiä.

```css
@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.circle {
  animation: none;
}

.circle:hover {
  animation: rotate 1s linear;
}
```

**Vaikutus**: Ympyrä **pyörii vain, kun sen päälle viedään hiiri**.

## Parhaat käytännöt CSS-animaatioille

- Käytä `@keyframes`-määrittelyjä **monimutkaisiin liikkeisiin**.
- Vältä liiallista animaatiota **suorituskyvyn parantamiseksi**.
- Suosi **GPU-kiihdytettyjä ominaisuuksia** kuten `transform` ja `opacity`.
