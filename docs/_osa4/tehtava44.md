---
layout: exercise_page
title: "Tehtävä 4.4: Ajax-laskin (2p)"
exercise_template_name: W4E04.AjaxLaskin
exercise_discussion_id: 93298
exercise_upload_id: 371623
modified_at: 29.1.2018
---


[Edellisen tehtävän](../tehtava43) laskin toimi niin, että sivu ladattiin
palvelimelta aina uudelleen jokaisella laskentakerralla. Nyt laadittava
laskin on sellainen, että sivu ladataan selaimeen ainoastaan kerran, mutta
laskenta suoritetaan palvelimella.

![Laskin](../img/ajax_laskin.png "Laskin"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Ajax-laskin.</small>

{% comment %}

Nämä tehtävät voisivat hyödyntää toistensa ratkaisuja - esim. tässä voisi
kayttää tehtävän 4.2 ratkaisua laskennan suorittamiseen.

{% endcomment %}

Laskimen käyttöliittymä tulee selaimeen pyynnöllä `http://localhost:3000/` tai
`http://localhost:3000/laskin.html`. Merkkaukseen liittyy JavaScript-koodi,
`code.js`, joka laskimen painikkeiden klikkausten seurauksena lähettää
laskentapyynnön palvelimelle ja ottaa vastaan laskennan tuloksen, minkä
jälkeen se tuottaa lausekkeen tuloksen kera käyttöliittymään.

Esim. *Kuvan 1* tilanteessa koodi lähettää pyynnön osoitteeseen `/api?lasku=mul&luku1=5&luku2=4`. Pyynnön käsittelee palvelimella tiedostossa `laskuri.js`
oleva, polkuun `/api` liittyvä, funktio. `lasku`-parametrin arvona voi olla
`add`, `sub`, `mul` tai `div.`

Tehtävä ratkaistaan[^1] täydentämällä tiedostoja `laskin.html` ja `laskuri.js`.
**Palauta** tiedostot, kun laskin toimii odotetusti.

[^1]: Kuten edellisissä tehtävissä myös tässä, sovelluksen toiminta edellyttää ulkopuolisia moduuleja, jotka voidaan ladata komennolla/menuvalinnalla `npm install`.  

### Vihjeitä ja lisätietoja

Tässä palvelimen polkuun `/api` tulevan pyynnön käsittelijä voi olla täysin sama
kuin [Tehtävän 4.2](../tehtava42) laskimen versio 1 (polkuun `/` tulevan pyynnön
käsittelijä).

[Tehtävässä 3.2](../../osa3/tehtava32) laskennan ja käyttöliittymän päivityksen
toteutti JavaScript-koodi. Tässä ratkaisu on muuten sama, mutta selaimessa tapahtuvan
laskennan sijaan lähetetään laskentapyyntö palvelimelle.

[Tehtävässä 3.5](../../osa3/tehtava35) JavaScript-koodi luki dataa palvelimelta
käyttäen jQueryn *$.getJSON*-funktioa. Tässä lähetettävä laskentapyyntö vastaa em.
tehtävässä tapahtunutta datan lukua. Tosin nyt kannatta käyttää jQuery-funktiota
[$.get][get], koska paluudata ei ole JSON-muodossa.

[get]: https://api.jquery.com/jquery.get/


<br/>

Alaviitteet
