# Välttämättömiä vinkkejä ja yksityiskohtia verkkosivun kehittäjälle

Tässä kokoelma **aloittelijaystävällisiä** JavaScript-vinkkejä, joilla saat verkkosivustostasi **interaktiivisen, responsiivisen ja käyttäjäystävällisen**. Nämä ovat joitakin **yleisimpiä** ominaisuuksia nykyaikaisilla verkkosivuilla. Näiden yksityiskohtien avulla hiot sivut huippuunsa.

## **Mobiilivalikko (hampurilaisvalikko)**

Näytä tai piilota mobiilivalikko painikkeella.

**HTML**

```html
<button id="menu-toggle" aria-expanded="false">☰ Menu</button>
<nav id="menu" class="mobile-menu">
  <ul>
    <li><a href="#">Etusivu</a></li>
    <li><a href="#">Tietoa</a></li>
    <li><a href="#">Palvelut</a></li>
    <li><a href="#">Yhteystiedot</a></li>
  </ul>
</nav>
```

**JavaScript**

```js
const menuToggle = document.querySelector("#menu-toggle");
const menu = document.querySelector("#menu");

menuToggle.addEventListener("click", () => {
  menu.classList.toggle("active");
  menuToggle.setAttribute("aria-expanded", menu.classList.contains("active"));
});

document.addEventListener("click", (event) => {
  if (!menu.contains(event.target) && !menuToggle.contains(event.target)) {
    menu.classList.remove("active");
    menuToggle.setAttribute("aria-expanded", "false");
  }
});
```

**CSS**

```css
.mobile-menu {
  display: none;
}
.mobile-menu.active {
  display: block;
}
```

## Takaisin ylös -painike

Painike, joka näkyy sivua alaspäin rullattaessa ja vierittää takaisin ylös pehmeästi.

**HTML**

```html
<button id="back-to-top">Takaisin ylös</button>
```

**JavaScript**

```js
const backToTop = document.querySelector("#back-to-top");

window.addEventListener("scroll", () => {
  backToTop.style.display = window.scrollY > 300 ? "block" : "none";
});

backToTop.addEventListener("click", () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
});
```

## Modal-ikkuna

Avaa ponnahdusikkunan/modalin, joka sulkeutuu kun käyttäjä klikkaa sen ulkopuolelle tai painaa `Esc`.

**HTML**

```html
<button id="open-modal">Avaa Modal</button>
<div id="modal" class="modal">
  <div class="modal-content">
    <button id="close-modal">Sulje</button>
    <h2>Modal-ikkuna</h2>
    <p>Tämä on yksinkertainen modal.</p>
  </div>
</div>
```

**JavaScript**

```js
const modal = document.querySelector("#modal");
const openModal = document.querySelector("#open-modal");
const closeModal = document.querySelector("#close-modal");

openModal.addEventListener("click", () => modal.classList.add("show"));
closeModal.addEventListener("click", () => modal.classList.remove("show"));

document.addEventListener("keydown", (e) => {
  if (e.key === "Escape") modal.classList.remove("show");
});
```

## Tumma tila -kytkin

Vaihda vaalean ja tumman tilan välillä ja tallenna valinta paikallisesti selaimen muistiin.

```html
<button id="theme-toggle">Vaihda tumma tila</button>
```

**JavaScript**

```js
const themeToggle = document.querySelector("#theme-toggle");
themeToggle.addEventListener("click", () => {
  document.body.classList.toggle("dark-mode");
  localStorage.setItem(
    "theme",
    document.body.classList.contains("dark-mode") ? "dark" : "light"
  );
});

if (localStorage.getItem("theme") === "dark") {
  document.body.classList.add("dark-mode");
}
```

```css
body {
  background-color: #ffffff;
  color: #000000;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.dark-mode {
  background-color: #121212;
  color: #ffffff;
}
```

## Kopioi leikepöydälle

Kopioi teksti elementistä leikepöydälle.

**HTML**

```html
<p id="copyText">Tämä on teksti, joka kopioidaan.</p>
<button id="copyBtn">Kopioi</button>
```

**JavaScript**

```js
document.querySelector("#copyBtn").addEventListener("click", () => {
  const text = document.querySelector("#copyText").textContent;
  navigator.clipboard.writeText(text);
});
```

## Avaa/Sulje UKK-osio

Klikkaa kysymystä avataksesi tai sulkeaksesi vastauksen.

**JavaScript**

```js
document.querySelectorAll(".faq-question").forEach((item) => {
  item.addEventListener("click", () => {
    item.nextElementSibling.classList.toggle("visible");
  });
});
```

## Kirjoitusefekti

Luo animaation, jossa teksti kirjoitetaan kirjain kerrallaan.

**JavaScript**

```js
const text = "Hei, maailma!";
let i = 0;
function typeEffect() {
  if (i < text.length) {
    document.querySelector("#typing").textContent += text.charAt(i);
    i++;
    setTimeout(typeEffect, 100);
  }
}
typeEffect();
```
