---
layout: exercise_page
title: "Tehtävä 3.1: Tilauslomake (2p)"
exercise_template_name: W3E01.Tilauslomake
exercise_discussion_id: 92458
exercise_upload_id: 370619
modified_at: 26.1.2018
---

[Tehtävässä 1.6](../../osa1/tehtava16) rakennettiin yksinkertainen tilauslomake
tilausten kirjaamista varten. Laadi vastaavanlainen mutta [Bootstrap][Bootstrap] -kirjastoa
hyödyntävä lomake, jonka ulkoasu selaimessa on *Kuvan 1* kaltainen.

[Bootstrap]: http://getbootstrap.com


![Tilauslomake](../img/tilauslomake.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Tilauslomake.</small>

Rakenna lomake tehtäväpohjan tiedostoon `index.html`, jossa on jo valmiina
Bootstrap:in CSS -paketin käyttöönotto[^cnd] sekä sivun layoutin muodostamiseksi
tarvittavat html-elementit.

[^cnd]: Käyttöönotto tapahtuu tässä  verkon yli eräältä CND:lta ([Content Delivery Network](https://en.wikipedia.org/wiki/Content_delivery_network))


**Palauta** tehtävästä tiedosto `index.html`. Varmista ennen palautusta, että
sivun näyttää selaisessa *Kuvan 1* mukaiselta ja, että tehtäväpohjan testit
menevät läpi.


### Vihjeitä ja lisätietoja

Tehtävän ratkaisu voidaan vaiheistaa vaikka seuraavasti

* layout
* lomake-elementit
* komponentit
* loppusilaukset

#### Layout

Bootstrap -[layout][layout] perustuu 12-sarakkeiseen ruudukkoon ([grid][grid]),
joka on sivun keskelle asettuvan `container` -elementin[^container] sisältönä.
Tilauslomakkeesta on löydettävissä kaksi varteenotettavaa ehdokasta
`container` -elementeiksi (*Kuva 2*).

[layout]: http://getbootstrap.com/docs/4.0/layout/overview/
[grid]: http://getbootstrap.com/docs/4.0/layout/grid/

[^container]: `class`-attribuutin arvona `container`


![Tilauslomake](../img/tilauslomake-2.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 2. Tilauslomakeen *container* -elementit.</small>

[Grid][grid] muodostuu `row`-elementeistä[^row], joiden sisältönä on erityyppisiä
*col*-elementtejä, esim. `col-sm-2`[^col-sm-2]. Elementissä `2` viittaa siihen,
että sarake käyttää 2/12 osaa *container:in* leveydestä. `sm` on lyhenne sanasta
*small*. Tällaisia sarakkeita sisältävä *grid* soveltuu esitettäväksi suhteellisen
pieninäyttöisilläkin laitteilla.

[^row]: `class`-attribuutin arvona `row`
[^col-sm-2]: `class`-attribuutin arvona `col-sm-2`


![Tilauslomake](../img/tilauslomake-3.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 3. Tilauslomakeen ylemmän *container* -elementin sisältämät
rivit ja sarakkeet.</small>


*Kuvassa 3* on esitetty tilauslomakkeesta löydettävissä olevat rivit ja
sarakkeet, jotka sisältyvät sivun ylempään *container* -elementtiin. Tässä
vaiheessa tehtäväpohjan `index.html` -tiedostoa voisi täydentää css-luokilta
ja vakioteksteillä siten, että sivu näyttää selaimessa *Kuvan 4* kaltaiselta.


![Tilauslomake](../img/tilauslomake-layout-1.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 4. Tilauslomake , joka sisältää layoutin määrittelevät CSS-luokat.</small>


*Kuvan 4* tilanteeseen pääsemiseksi tarvittaneen seuraavia Bootstrap:n
CSS-luokkia: `container`, `row`, `col-sm`[^col-sm], `col-sm-2` ja
`offset-sm-2`[^offset-sm-2].

[^col-sm]: `col-sm` "päättelee" käyttöönottamansa tilan
[^offset-sm-2]: siirtää edelementtiä kaksi "pykälää" eteenpäin

Tehtäväpohja sisältää seuraavat layoutin rakentamiseen liittyvät testit:

* Sisältää 2 container-elementtiä
  - form>div.container
  - footer>div.container
* Sisältää 8 row-elementtiä
  - form>div>div.row: 7
  - footer>div>div.row: 1
* Sisältää riveillä 11 "col-*" -elementtiä
  - nimi-kentän otsikko "col-sm-2"-sarakkeessa
  - osoite-kentän otsikko "col-sm-2"-sarakkeessa
  - tuote-nappien otsikko "col-sm-2"-sarakkeessa
  - opiskelija-laatikon sijaintia siirretty oikealle (offset-sm-2)



#### Lomake-elementit

Tässä tarvittavat lomake-elementit ovat samoja, jotka tuli laatia
[Tehtävän 1.6](../../osa1/tehtava16) ratkaisuun, josta ne voi kopioida
kutakuinkin sellaisenaan. Tämän jälkeen lomakkeen tulisi olla selaimessa
*Kuvan 5* mukainen.

![Tilauslomake](../img/tilauslomake-layout-2.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 5. Tilauslomake, jossa edellisen vaiheen vakiotekstit on
korvattu lomake-elementeillä.</small>

Huomio myös tuotteen oletusarvo (Vasara)[^checked] sekä se, että
*Lähetä* -panikkeen klikkauksen tuottaa
selaimeen samanlaisen vasteen kuin [Tehtävän 1.6](../../osa1/tehtava16)
ratkaisu.

[^checked]: Vihje: `checked`-attribuutti

Tehtäväpohja sisältää seuraavat lomake-elementtien sijoitteluun liittyvät
liittyvät testit:

* Yhteensä 7 input -elementtiä
  - Nimi-kenttä (text)
  - Osoite-kenttä (text)
  - Opiskelija-valinta (checkbox)
  - Tuote-valinnat (radio)
  - Lähetä-painike (submit)
* Yksi textarea-elementti
  - Erikoistoivomukset-alue (textarea)

#### Bootstrap -komponentit

Lomakkeissa esiintyviä elementtejä voidaan muotoilla tähän liittyvillä
Bootstrapin CSS-luokilla. Seuraa, miten sivu selaimessa muuttuu, kun
seuraavat ehdot täyttyvät:

* Tekstikentillä on "**[form][form]**-control"-luokka
* Tekstialueella on "form-control"-luokka
* Valintanapeilla (radio, checkbox) on "form-check-input"-luokka
* Lähetä-painikkeella on "**[btn][btn]**"- ja "btn-primary"-luokat
* Opiskelija-valinta kehystetty "form-check"-elementillä (div)
* Tuote-valinnat kehystetty "form-check-inline"-elementeillä (div)
* Navigointipalkilla (nav) on "**[navbar][navbar]**"-, "navbar-light"- ja "bg-light"-luokat
* Navigointipalkin linkillä (a) on "navbar-brand"-luokka

[form]: http://getbootstrap.com/docs/4.0/components/forms/
[btn]: http://getbootstrap.com/docs/4.0/components/buttons/
[navbar]: http://getbootstrap.com/docs/4.0/components/navbar/

Edellinen lista on samalla luettelo komponentteihin liittyvistä tehtäväpohjan
testeistä.

#### Ulkoasun loppusilaukset

Seuraavilla luokilla erotetaan lomake-elementtejä pystysuunnassa hieman
toisistaan sekä tuotetaan vaakasuuntainen viiva erottamaan sivun alatunniste
(footer) sen yläpuolisesta sisällöstä.

* input- ja textarea-elementtejä sisältävillä "row"-elementeillä on myös
"<strike>form-control</strike> form-group"-luokka
* footer-elementillä on "border" ja "border-bottom-0"-luokat

Myös näihin liityvät testit löytyvät tehtäväpohjasta.


<br/>

Alaviitteet
