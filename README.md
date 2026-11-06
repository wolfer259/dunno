AI bylo použito na zformátování checklistu, vytvoření naprosto zbytečných vymožeností které jsem dělat nemusel (mapa v kontaktech), zorganizování a mírné optimalizace kódu.

https://github.com/wolfer259/dunno

https://zizkaji25.llmp.spse-net.cz/



# Checklist zadání – Zbrojnice Praha (inspirováno czfirearms.com)

Čísla řádků odpovídají aktuálním souborům v tomto balíčku.

## Struktura a architektura

|Požadavek|Kde je splněno|
|-|-|
|Min. 3 vzájemně navigovatelné stránky|`index.html`, `detail.html`, `kontakt.html`; odkazy v hlavní navigaci a v patičce|
|Domovská stránka – úvod projektu|`index.html` ř. 25–34 (hero), ř. 36–41 (představení)|
|Náhledy produktů/článků (mřížka)|`index.html` ř. 43–74 (produkty), ř. 76–92 (aktuality)|
|První náhled vede na detail, zbytek placeholder|`index.html` ř. 55 (`detail.html`); ř. 63 a 71 (`href="#"`)|
|Stránka detailu s dlouhým strukturovaným textem|`detail.html` ř. 43–94 (sekce: Připraveno na soutěž, Optics-Ready, Ergonomie, Závěr a hlaveň, Spoušť)|
|Produkt a texty z inspirační stránky|`detail.html` – CZ TS 3 Orange (přeloženo z czfirearms.com)|
|Prvek `<aside>`|`detail.html` ř. 96 (parametry produktu) a ř. 112 (glosář pojmů)|
|Kontakty s vymyšlenými údaji|`kontakt.html` ř. 31–49 (adresa, telefon, e-mail, IČO, otevírací doba)|

## Globální prvky

|Požadavek|Kde je splněno|
|-|-|
|Hlavní navigace (3 stránky)|všechny stránky, `<nav aria-label="Hlavní navigace">` na ř. 15–21|
|Patička s odkazem na inspirační web|`index.html` ř. 100, `detail.html` ř. 130, `kontakt.html` ř. 78|
|Vymyšlené IČO|`index.html` ř. 99, `detail.html` ř. 129, `kontakt.html` ř. 40 a 77|
|Mapa webu v patičce|`index.html` ř. 102–109, `detail.html` ř. 132–139, `kontakt.html` ř. 80–87|

## Sémantické HTML

|Požadavek|Kde je splněno|
|-|-|
|`<header>`|všechny stránky ř. 13; `detail.html` ř. 31 (hlavička článku)|
|`<nav>`|ř. 15 (hlavní), `detail.html` ř. 25 (drobečky), patička (mapa webu)|
|`<main>`|ř. 24 na všech stránkách|
|`<footer>`|`index.html` ř. 95, `detail.html` ř. 125, `kontakt.html` ř. 73|
|`<section>`|`index.html` ř. 25, 36, 43, 76; `detail.html` ř. 43–85; `kontakt.html` ř. 31, 51, 66|
|`<article>`|`index.html` ř. 49, 57, 65, 79, 83, 87; `detail.html` ř. 30|
|`<aside>`|`detail.html` ř. 96, 112|

## Mikrosémantika

|Požadavek|Kde je splněno|
|-|-|
|`<time>` (povinně)|`index.html` ř. 81, 85, 89; `detail.html` ř. 36; `kontakt.html` ř. 43–47|
|`<hgroup>` (povinně)|`index.html` ř. 28 a 44; `detail.html` ř. 32; `kontakt.html` ř. 25|
|`<address>`|`kontakt.html` ř. 33|
|`<abbr>`|`detail.html` ř. 45, 99, 115–117; `kontakt.html` ř. 40|
|`<mark>`|`index.html` ř. 39; `detail.html` ř. 54; `kontakt.html` ř. 48|
|`<data>`|ceny: `index.html` ř. 54, `detail.html` ř. 99; IČO: ř. 99 / 129 / 40|
|`<dfn>`, `<dl>`|`detail.html` ř. 100 (parametry), ř. 114–118 (glosář); `kontakt.html` ř. 42|
|`<figure>` + `<figcaption>`|`detail.html` ř. 37, 46, 55, 65, 73, 88|

## Multimédia

|Požadavek|Kde je splněno|
|-|-|
|Min. 1 `<iframe>`|`kontakt.html` ř. 68 (OpenStreetMap)|
|Logo z `./logo.svg`|`index.html`/`detail.html`/`kontakt.html` ř. 14; favicon ř. 8|
|Obrázky z inspirační stránky|`convert-images.sh` obsahuje zdrojové URL z czfirearms.com|
|Rastry pouze WEBP|všechny `src`/`srcset` odkazují na `img/\\\*.webp` (soubory vznikají skriptem `convert-images.sh`)|
|Min. 5 obrázků v detailu, všechny se `srcset`|`detail.html` ř. 38, 47, 56, 66, 74, 89 (článek) a ř. 97 (aside) = 7 obrázků|
|Responzivní obrázky na úvodní stránce|`index.html` ř. 26, 50, 58, 66|

## Další kvalita

* Přeskakovací odkaz „Přeskočit na obsah“, `aria-current`, viditelný `:focus-visible` (`style.css`).
* Material/flat styl: elevace stínů, jednobarevné plochy, akcent #e65100 (`style.css`).
* `width`/`height`, `loading="lazy"`, `decoding="async"` na obrázcích; hero obrázky mají `fetchpriority="high"`.

