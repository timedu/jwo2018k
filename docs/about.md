---
layout: site_page
title: Web-sovellusten ympäristöstä ja toteutustekniikoista
permalink: /about/index.html
modified_at: 5.1.2018
---

*Johdatus web-ohjelmointiin* on otsikkonsa mukaisesti aihepiirinsä johdantokurssi.
Seuraavassa on lyhyesti, mikälaisessa ympäristössä web-ohjelmoinnin
myötä syntyvät web-sovellukset toimivat, ja minkälaisia tekniikoita käytetään
sovelluksia laadittaessa.


#### Web

"*[World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web)
tai WWW on
[Internet](https://en.wikipedia.org/wiki/Internet)-verkossa
toimiva hajautettu
[hyperteksti](https://en.wikipedia.org/wiki/Hypertext)järjestelmä.
Hypertekstiä luetaan
[selaimella](https://en.wikipedia.org/wiki/Web_browser),
joka hakee web-sivuiksi kutsuttuja dokumentteja
[web-palvelimilta](https://en.wikipedia.org/wiki/Web_server)
ja esittää niitä käyttäjälle piirtämällä ne näytölle. Hyperteksti sisältää linkkejä toisiin dokumentteihin.*"
[[wikipedia](https://fi.wikipedia.org/wiki/World_Wide_Web)]


![Selain ja web-palvelin](../img/browser_server.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 1. Selain hakee web-palvelimelta dokumentin ja esittää sen käyttäjälle.
</small>


![hyperteksti](https://upload.wikimedia.org/wikipedia/commons/4/41/Sistema_hipertextual.jpg){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 2. Hypertekstijärjestelmä: dokumentteja, jotka sisältävät hyperlinkkejä toisiin dokumentteihin[^hyperteksti].
</small>

[^hyperteksti]: Kuvan lähde: <https://en.wikipedia.org/wiki/Hypertext>


Tämä sivu on esimerkki hypertekstijärjestelmään kuuluvasta dokumentista. Sivulle on on hyperlinkki kurssisivuston [aloitussivulta](..), jonne taas johtaa
[kurssin Moodle-sivulla](https://moodle2.tut.fi/course/view.php?id=11411)
oleva linkki. Myös tällä sivulla on useita linkkejä toisiin dokumentteihin.

#### URL, HTTP

Web-sivuihin viitataan [URL](https://en.wikipedia.org/wiki/URL)[^URL]
-muotoista osoitetta käyttäen (*Kuva 3*). Esim. tämän sivun *URL* on `https://timedu.github.io/jwo2018k/about`, joka määrittelee
selaimen ja palvelimen välisen yhteyskäytännön (`https`),
palvelimen tunnisteen (`timedu.github.io`) sekä
palvelimella sijaitsevan resurssin (`/jwo2018k/about`).
Tämän sivun saa esille selaimeen kirjoittamalla em. URL:n selaimen
osoitekenttään tai klikkaamalla sivulle osoittavaa [linkkiä](.).

[^URL]: [URL](https://fi.wikipedia.org/wiki/URI) - Uniform Resource Locator


![URL, HTTP](../img/url_http.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 3. Web-sivun osoite (*URL*) sekä selaimen ja palvelimen välinen kommunikointikäytäntö (*HTTP*).
</small>


Selaimen ja web-palvelimen välinen kommunikointi tapahtuu [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)[^HTTP] -muotoisia
*pyyntöjä* ja *vasteita* käyttäen (*Kuva 3*). Tämän sivun osoitteessa oleva
[HTTPS](https://en.wikipedia.org/wiki/HTTPS) on edellisen turvallinen versio,
jossa mm. web-palvelimen ja selaimen välillä kulkeva tieto on salattua.

[^HTTP]: [HTTP](https://fi.wikipedia.org/wiki/HTTP) - Hypertext Transfer Protocol


#### HTML, CSS

Web-sivut ovat [HTML][HTML][^HTML]
-muotoisia dokumentteja (*Kuva 4*). Firefox -selaimessa sivun
HTML -merkkauksen saa esillä näppäinyhdistelmällä `ctrl-U` (Mac: `cmd-U`).
Tosin esim. tämän sivun merkkaus ei ole kovin hyvin muotoiltu, koska sivu on
tuotettu generoimalla.

[HTML]: https://en.wikipedia.org/wiki/HTML
[^HTML]: [HTML](https://fi.wikipedia.org/wiki/HTML) - Hypertext Markup Language

Web-sivu voi sisältää tekstin ohella myös erilaista mediaa kuten
kuvia, ääntä ja videoita. Tällainen media on tyypillisesti talletettu
HTML -merkkauksesta erillään oleviin tiedostoihin.
Dokumentin sisältämän kuvan saa erillisenä
selaimen ikkunaan klikkaamalla kuvaa hiiren oikealla näppäimellä ja valitsemalla
esiin tulevasta valikosta `Näytä kuva` (Firefox). Tällöin kuvan URL ilmestyy
selaimen osoitekenttään. Esim. seuraavan *Kuvan 4* osalta
voidaan todeta, että kuva sijaitsee tiedostossa `/img/html_css.png` samalla palvelimella (`timedu.github.io`) kuin tämä HTML-dokumentti. Jos vastaavanlaisen tutkimuksen
kohdistaa edellä olevaan *Kuvaan 2*, huomataan, että kuva onkin lainattu
Wikipediasta siten, että se sijaitsee aivan toisella
palvelimella (`upload.wikimedia.org`).


![HTML, CSS](../img/html_css.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 4. *HTML*-dokumentti sekä siihen liittyvät mediatiedostot ja tyyliohjeet (*CSS*).
</small>


*HTML* -merkkauksella määritellään web-sivun rakenne ja sisältö.
Pelkän merkkauksen avulla dokumentin ulkoasua voidaan muotoilla
suhteellisen vähän. Ulkoasun  tehdään erillisillä
[CSS][CSS][^CSS]-tyyliohjeilla (*Kuva 4*).
Tämän sivun tyyliohjeet saa esiin kirjaamalla selaimen osoitekentään URL:n
`https://timedu.github.io/jwo2018k/css/main.css`.
Firefox -selaimessa sivun tyyliohjeet saa pois käytöstä menuvalinnalla
`Näytä > Sivun tyylit > Ei tyylimäärittelyjä`. Esim. tämän sivun ulkoasu muuttuu
melkoisesti ottamalla tyylit pois käytöstä.

[CSS]: https://en.wikipedia.org/wiki/Cascading_Style_Sheets
[^CSS]: [CSS](https://fi.wikipedia.org/wiki/Cascading_Style_Sheets) - Cascading Style Sheets

#### JavaScript

Web-sivu voi sisältää myös ohjelmakoodia (*Kuva 5*), jolloin ohjelmointikielenä käytännössä
on [JavaScript][JS][^JS]. Tällöin selain
suorittaa sivun sisältämän ohjelmakoodin, joka voi esim. muokata selaimeen
palvelimelta haettua dokumenttia.

[JS]: https://en.wikipedia.org/wiki/JavaScript
[^JS]: Ks. myös [JavaScript](https://fi.wikipedia.org/wiki/JavaScript)

![JS (client)](../img/javascript-client.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 5. *HTML*-dokumentti ja siihen liittyvä *JavaScript*-ohjelma haettu palvelimelta selaimeen.
</small>

Esim. klikkaamalla oheista painiketta, se poistuu sivulta, jos selaimen
asetuksissa ei ole estetty JavaScriptin käyttöä. Painikkeen saa takaisin
esiin lataamalla sivun uudelleen (Firefox: `ctrl-R`).
<button onclick="this.style.display = 'none';">CLICK TO HIDE</button>

Selaimen ohella web-sovelluksissa ohjelmakoodia suoritetaan myös palvelimella.
Tällöin selain viittaa palvelimella olevaan
ohjelmaan, jonka suorituksen tuloksena muodostuu selaimelle välitettävä
dokumentti (*Kuva 6*). Usein dokumentiin tulevat tiedot haetaan tietokannasta.


![JS (server)](../img/js-server.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 6.Selain viittaa palvelimella olevaan ohjelmaan, jonka muodostaa selaimelle välitettävän tiedoston.
</small>


Palvelimella ajettava ohjelma voi olla kirjoitettu
*JavaScriptin* ohella periaatteessa millä tahansa ohjelmointikielellä. Yleisimpiä
web-sovellusten palvelinpään kieliä lienevät tällä hetkellä
[PHP](https://en.wikipedia.org/wiki/PHP),
[Python](https://en.wikipedia.org/wiki/Python_(programming_language)) ja
[Java](https://en.wikipedia.org/wiki/Java_(programming_language)).
Eräs *JavaScriptin* eduista on se, että samaa kieltä voi käyttää sekä selain-
että palvelinpäässä.

Esimerkki *Kuvan 6* kaltaisesta tilanteesta on tämän kurssin Moodle-sivu,
jonka URL on <https://moodle2.tut.fi/course/view.php?id=11411>. URL viittaa
palvelimella olevaan PHP-ohjelmaan `/course/view.php`, jolle annetaan
parametriksi tämän kurssin Moodle-tunnus: `id=11411`.


![JS (client-server)](../img/js-client-server.png){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

<small>
  Kuva 7. Selaimessa ja palvelimessa ajettavien ohjelmien kommunikointi.
</small>

Selainpäässä ajettava JavaScript voi kommunikoida palvelimella ajettavan ohjelman
kanssa (*Kuva 7*). Tällöin selaimen koodi voi esim. hakea palvelimelta dataa ja muokata
selaimessa olevaa dokumentia haetun datan perusteella. Tällaiseen käytäntöön
viitataan usein lyhenteellä [Ajax](https://en.wikipedia.org/wiki/Ajax_(programming)).
Esimerkki Ajax-sovelluksesta on vaikka [Google Maps](https://www.google.fi/maps/),
jossa JavaScript hakee palvelimelta karttadataa käyttäjän toiminnan seurauksena.


#### Kurssilla esillä olevista tekniikoista

Tällä kurssilla käsitellään web-sovellusten rakentumista edellä esitettyjen
kuvien *4-7* tapaan. Esillä ovat jo mainitut perustekniikat: [HTML][HTML],
[CSS][CSS] ja [JavaScript][JS] sekä selain- että palvelinpään
ohjelmointikielenä. Oletusselaimena toimii
[Firefox](https://www.mozilla.org/en-US/firefox/), palvelinpään JavaScriptin
ajaa [Node.js](https://nodejs.org/en/) ja esimerkkitietokantana on
[SQLite](https://www.sqlite.org) -relaatiotietokanta.
Sovellusten laatimista yksinkertaistaa selainpäässä
[jQuery](https://jquery.com)- ja
[Bootstrap](http://getbootstrap.com) -kirjastot sekä palvelinpäässä
[Express](https://expressjs.com) -sovelluskehys ja
[Handlebars](http://handlebarsjs.com) -sivupohjat.

Ohjelmakoodin laatimisessa voi käyttää jotakin tekstieditoria kuten
Windows-ympäristöön saatavissa olevaa
[notepad++](https://notepad-plus-plus.org):aa.
Tutustumisen arvoinen lienee myös [Atom](https://atom.io), joka toimii
Windowsin ohella myös Macissa ja Linuxissa. Käyttökelpoinen työkalu on myös
ohjelmointikursseilta tuttu [NetBeans IDE](https://netbeans.org), josta
tarvitaan `HTML5/JavaScript`-kaluston sisältävä paketti.

<br/> Alaviitteet
