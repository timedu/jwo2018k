---
layout: exercise_page
title: "Tehtävä 3.5: Tilausdata  (2p)"
exercise_template_name: W3E05.TilausData
exercise_discussion_id: 92463
exercise_upload_id: 370648
modified_at: 24.1.2018
---

Tehtävissä [1.6](../../osa1/tehtava16)  ja [3.1](../tehtava31) rakennettiin
lomake, jolla voi lähettää tilaustietoja palvelimelle. Tässä datan välitys
toteutetaan toiseen suuntaan: tilauksen tiedot haetaan palvelimelta ja
esitetään palautuneet tiedot lomakemuotoisella sivulla (*Kuva 1*).

![TilausData](../img/tilausdata.png "TilausData"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Tilausdata.</small>

Tehtäväpohjassa oleva html-sivu (*Kuva 2*) on periaateratkaisuun riittävä.
Sivua voi halutessaan stilisoida kopioimalla html-koodin sekä viittauksen
Bootstrap:in CSS-pakettiin [Tehtävän 3.1](../tehtava31) ratkaisusta. Kopioidusta
html-koodista voi poistaa `form`-elementin ja *Lähetä* -painikkeen, koska nyt
dataa ei lähetetä palvelimelle. Kenttien ja valintojen olisi myös luontevaa olla
sellaisia, että käyttäjä ei voi muuttaa niiden sisältöä
(ks. `readonly`-  ja `disable`-attribuutit pohjan `index.html`-tiedostossa).

![Pelkistetty tilausdata](../img/tilausdata-pure.png "Pelkistetty tilausdata"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Pelkistetty tilausdata.</small>

Tehtäväpohjassa on valmis "perus-JavaScript" -pohjainen ratkaisu, joka sivun
latauksen yhteydessä lukee ("hakee palvelimelta") tiedostossa `data/tilaus.json`
oleva datan ja esittää tiedot esiin tulevalla sivulla.

Laadi perus-JavaScriptia vastaava jQuery-pohjainen toteutus
tiedostoon `code-jQuery.js` siten, että sekä
datan haku että tietojen sijoittaminen dokumenttiin tapahtuu jQueryn metodeja
käyttäen.

Jotta sivu käyttää jQuery-toteutusta, vaihda tiedostossa `index.html`
olevien kommenttimerkkien paikkaa seuraavasti:

{% highlight html %}

...
<!--<script src="./js/code-JavaScript.js"></script>-->
<script src="./js/code-jQuery.js"></script>
...

{% endhighlight %}


**Palauta** tehtävän ratkaisuna tiedosto `code-jQuery.js`.

### Vihjeitä ja lisätietoja

Pohjan ratkaisussa (`code-JavaScript.js`) palvelimelta haetaan [JSON][JSON] -muotoinen data
[XMLHttpRequest][XMLHttpRequest] -tyyppistä objektia käyttäen. Helsingin
materiaalissa näitä asioita käsitellään [luvun 7][luku-7] alussa. Tässä tosin
käytetään objektin *load* -tapahtumaa materiaalissa esiintyvän
*readystatechange* -tapahtuman sijaan.

[JSON]: http://www.json.org
[XMLHttpRequest]: https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest
[luku-7]: http://web-selainohjelmointi.github.io/#7-Keskustelu-palvelimen-kanssa

*jQuery*-pohjaisessa ratkaisussa data haku hoituu kätevästi
[$.getJSON][getJSON] -funktiolla, mikä on esillä Helsingin materiaalissa
kohdassa [10.1.4][kohta-10-1-4].

[getJSON]: http://api.jquery.com/jQuery.getJSON/
[kohta-10-1-4]: http://web-selainohjelmointi.github.io/#10.1.4-Kyselyt-palvelimelle

Pohjan JavaScript-koodissa elementtien paikannus dokumentissa tapahtuu
[querySelector][querySelector] -metodilla, jolle annetaan parametriksi
CSS-valitsin. Tässä käytetään elementin
[attribuuttien arvoihin perustuvia valitsimia][Attribute_selectors].
Kun käsiteltävät elementit on paikannettu, muutetaan niiden
`value`/`checked`
-ominaisuuksia palvelimelta luetun datan perusteella.

[querySelector]: https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector
[Attribute_selectors]: https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors

jQuery:n käytettäessä elementit paikannetaan `document.querySelector`-metodin
sijaan jQuery -funktiolla (`$`), jolle querySelector:in tapaan annetaan parametriksi
CSS-valitsin (ks. esim. Helsinki: [kohta 10.1.1][kohta-10-1-1]). Paikannettujen
elementtien ominaisuuksien muutos hoituu tässä jQuery:n
[val][val]- ja [prop][prop] -metodeilla.

[kohta-10-1-1]: http://web-selainohjelmointi.github.io/#10.1.1-Valitsimet

[val]: http://api.jquery.com/val/
[prop]: http://api.jquery.com/prop/
