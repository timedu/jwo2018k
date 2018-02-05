---
layout: exercise_page
title: "Tehtävä 5.4: VatsNew (2p)"
exercise_template_name: W5E04.VatsNew
exercise_discussion_id: 94006
exercise_upload_id: 372709
modified_at: 5.2.2018
---

Täydennä [edellisen tehtävän](../tehtava53) ratkaisua siten, että sovelluksella
voi lähettää uusia viestejä. Selaimen esittämää käyttöliittymää on
hieman täydennettävä (*Kuva 1*), ja palvelinpään tulee kyetä vastaanottamaan
selaimen lähettämä data ja tallettamaan se tietokantaan.


![Viestit](../img/vats_new_insert.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Uuden viestin lisäys käyttäjänä *Bart*.</small>


Sivulla, viestiluettelon yläpuolella, on teksialueen ja painikkeen sisältävä
lomake. Kun lomakkeen painiketta klikataan, tekstialueelle kirjattu viesti
ilmestyy viestiluetteloon harmaalle pohjalla (*Kuva 2*).


![Viestit](../img/vats_new_list.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Viestiluettelo - kirjautuneena *Bart*.</small>


"Toinen käyttäjä" (esim. kehityslaitteen toisella selaimella) näkee lisätyn viestin keltaisella pohjavärillä (*Kuva 3*). Uuden viestin esiinsaaminen kuitenkin edellyttää luettelon
"virkistämistä" klikkaamalla sivun yläosan *refresh* -linkkiä tai lataamalla sivu
uudelleen selaimen vakiopainikkeella.


![Viestit](../img/vats_new_list_ned.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 3. Viestiluettelo - kirjautuneena *Ned*.</small>


Viestin lisääminen edellyttää kirjautumista. Muussa tapauksessa tekstialueelle
ei voi kirjoittaa eikä sen vieressä oleva painike ole aktiivinen (*Kuva 4*).


![Viestit](../img/vats_new_insert_anon.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 4. Uuden viestin lisäys ei onnistu kirjautumatta.</small>


Ratkaise tehtävä täydentämällä tehtäväpohjan tiedostoja `vatsi.js` ja `messages.html`,
ja **palauta** ne, kun sovellus toimii odotetusti.


### Vihjeitä ja lisätietoja

Tehtäväpohjan `messges.html` sisältää Bootsrtap:in gridin, jossa on
yksi-sarakkeinen rivi tarvittavaa lomaketta varten. Lomakkeen  sisällön voi
edelleen jäsentää riviksi ja kahdeksi sarakkeeksi.

Lomakkeen  muotoilussa voi käyttää mm. Bootstrap-luokkia `align-items-end`,
`form-control` ja `btn-sm`. Näistä ensimmäinen riville asetettuna aikaansaa
painikkeen siirtymisen rivin alareunan tasalle ja viimeksi mainittu pienentää
painiketta jonkin verran. Tekstialueelle asetettu `form-control` venyttää sen
koko sarakkeen levyiseksi.

Sopivan merkin painikkeelle voi poimia [vapaasti käytettävissä olevien ikonien
joukosta](https://useiconic.com/open). Pohjassa olevalle *Login* -lomakkeelle
on poimittu *check* ja tähän voisi sopia *share*.

Jos käyttäjä ei ole kirjautunut sovellukseen, lomakeen `textarea`-elementillä
tulisi olla `readonly` -attribuutti ja painikkeella `disabled`-attribuutti.

Lomake tulisi lähettää `post`-metodilla polkuun `/new` (vrt. pohjan
tiedostossa `login.html` oleva kirjatumislomake, joka lähetetään `post`-metodilla
polkuun `/login`), ja siten lomakkeen tietojen vastaanottamiseen tarvitaan
vastaava sovelluskehyksen `post`-metodin kutsu tiedostoon `vatsi.js`
(vrt. kutsu `app.post('/login', function(req, res){..});`). Tähän siis tulisi
laatia koodi, joka tallettaa viestin tietokantaan ja ohjaa sitten käsittelyn
viestiluettelon muodostavalle toiminnolle.

Talletettavan viestin *sanoma* saadaan lomakkeelta, *aika*
[Tehtävän 5.2](../tehtava52) tapaan funktion `currentDate` avulla ja
*lahettaja* evästeestä (vrt. [edellinen tehtävä](../tehtava53)).
