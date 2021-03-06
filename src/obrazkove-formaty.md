---
layout: base
title: Obrázkové formáty
---

Velikost obrázkových souborů se snažíme držet co nejmenší, aby k návštěvníkům přes internet rychle doputovaly. Nepoužíváme proto zbytečně příliš kvalitní fotografie například pro malé náhledy v galerii. Pro zmenšení obrázků se ti může hodit online nástroj [Squoosh](https://squoosh.app/). Další možnou úsporou je volba vhodného formátu, přípony souboru. Na webu se najčastěji setkáváme s `.jpg`, `.png`, `.svg`.

## Nejčastější formáty

### JPG

Vhodný na fotografie, kdy není kladen důraz na přesnost každého pixelu, protože používá ztrátovou kompresi. (Často s nastavením „[progresivního renderování](https://www.google.com/search?q=progressive+jpeg&tbm=isch)“, kdy se obrázek na pomalém připojení postupně zaostřuje místo načítání po řádcích od shora dolů.)

![ukázka JPG](static/examples/stream.jpg)

### PNG

Občas za cenu větší velikosti nabízí na pixel přesné zaznamenání obrazu. Vhodné pro snímky obrazovky. Podporuje průhlednost.

![ukázka PNG](static/examples/czechitas.png)

### SVG

Vektorový formát vodný zejména pro ikonky, logo, obrázky složené z geometrických tvarů. Lze v prohlížeči zvětšovat bez ztráty kvality. Obsah souboru je v čitelné podobě připomínající HTML.

<img src="static/examples/house.svg" width="200" height="200" alt="ukázka SVG">

## Další používané

### GIF

Krátké animace s nízkým počtem barev. Vhodné pro krátké smyčky. Pro větší, delší záznamy používající více barev volíme spíše video formáty jako MP4.

![ukázka GIF](static/examples/kocka.gif)

### WEBP

Kombinuje výhody JPG a PNG, ale prohlížeče ho začali podporovat teprve [nedávno](https://caniuse.com/webp).

![ukázka WEBP](static/examples/stream.webp)

### ICO

Používaný pouze pro ikonku záložky (`favicon.ico`). Postupně nahrazovaný modernějšími formáty.

<img src="static/examples/favicon.ico" width="48" height="48" alt="ukázka SVG" style="border: 1px solid #303182; border-radius: 50%;">

## Volitelné čtení na doma

Responzivní weby často vyžadují různě veliké obrázky podle velikosti zařízení. Jeden soubor/fotografie může být zbytečně moc velký na malé obrazovce nebo naopak moc malý, nekvalitní na obrazovce velké. Pomocí atributů `srcset` a `sizes` můžeme jednomu HTML obrázku přiřadit více souborů s odlišnými parametry. Více například na [Vzhůru dolů](https://www.vzhurudolu.cz/prirucka/srcset-sizes) nebo [MDN](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images).
