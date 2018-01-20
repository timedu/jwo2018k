---
layout: exercise_page
title: "Tehtävä 3.1: Tilauslomake (2p)"
exercise_template_name:
exercise_discussion_id:
exercise_upload_id:
kesken: 1
modified_at: 19.1.2018
no_review: 1
julkaisu: 21.1.2018
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


**Palauta** tehtävästä tiedosto `index.html`.


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


#### Lomake-elementit

Tässä tarvittavat lomake-elementit ovat samoja, jotka tuli laatia
[Tehtävän 1.6](../../osa1/tehtava16) ratkaisuun, josta ne voi kopioida
kutakuinkin sellaisenaan. Tämän jälkeen lomakkeen tulisi olla selaimessa
*Kuvan 5* mukainen.

![Tilauslomake](../img/tilauslomake-layout-2.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 5. Tilauslomake, jossa edellisen vaiheen vakiotekstit on
korvattu lomake-elementeillä.</small>

Huomio myös varsinainen `form`-elementti sekä tuotteen oletusarvo
(Vasara)[^checked]. *Lähetä* -panikkeen klikkauksen tuli nyt myös tuottaa
selaimeen samanlainen vaste kuin [Tehtävässä 1.6](../../osa1/tehtava16).

[^checked]: Vihje: `checked`-attribuutti

#### Bootstrap -komponentit

Lomakkeissa esiintyviä elementtejä voidaan muotoilla tähän liittyvillä
Bootstrapin [CSS-luokilla][forms]. Seuraa, mitä tapahtuu seuraavien
toimenpiteiden seurauksena:

* aseta `text`-tyyppisille `input`-elementeille sekä `textarea`-elementille
luokka `form-control`
* aseta `radio`- ja `checkbox`-tyyppisille `input`-elementeille
luokka `form-check-input`
* aseta `submit`-tyyppiselle `input`-elementille luokat `btn` ja `btn-primary`
* ...


[forms]: http://getbootstrap.com/docs/4.0/components/forms/

#### Ulkoasun loppusilaukset

...

<br/>

Alaviitteet
