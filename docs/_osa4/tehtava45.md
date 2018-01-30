---
layout: exercise_page
title: "Tehtävä 4.5: Tilaukset (2p)"
exercise_template_name: W4E05.Tilaukset
exercise_discussion_id: 93299
exercise_upload_id: 371624
modified_at: 30.1.2018
---

[Tehtävässä 3.1](../../osa3/tehtava31) laadittiin Bootstrapin tarjoamien CSS-
luokkien tuella yksinkertainen tilauslomake, joka lähetti tiedot tilauksesta
ulkopuoliseen kaiutuspalveluun. Tässä tehtävässä on esillä samainen lomake (*Kuva 1*),
mutta nyt sen lähettämät tiedot käsittelee itse laadittava palvelu.

![Tilauslomake](../img/uusi_tilaus.png "Tilauslomake"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Tilauslomake -sivu</small>

*Kuvan 1* tilauslomake on tehtäväpohjassa jo valmiina. Palvelinpään JavaScript-moduulia
`app.js` on kuitenkin hivenen muokattava sivun saamiseksi selaimelle. Lomakkeen pitäisi
tulla esiin, kun polkuun `/new` tehdään pyyntö (ks. K*uvan 1* osoiterivi). Sivun
yläosassa olevan navigointipalkin linkki *Uusi tilaus* tekee tällaisen pyynnön.

Kun *Uusi tilaus* -sivulla klikataan *Lähetä*-painiketta juuri kirjatun tilauksen
esittävä sivu ilmestyy selaimelle (*Kuva 2*). Sivu muistuttaa tilauslomaketta
(*Kuva 1*), mutta se ei sisällä *Lähetä* -painiketta eikä sen sisältämien
syötekenttien sisältöjä voi muuttaa. *Tilaus* -sivu tulee esiin pyynnöllä (esim.)
polkuun `/show/1`, jossa `1` edustaa juoksevaa tilausnumeroa.


![Tilaus](../img/tilaus.png "Tilaus"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Tilaus -sivu.</small>


*Kuvan 2* sivuun liittyvästä templatesta tehtäväpohjasta on alustava drafti
(*Kuva 3*). [Tehtävän 3.5](../../osa3/tehtava35) ratkaisua voinee hyödyntää
sivun muotoilussa.


![Tilaus draft](../img/tilaus_draft.png "Tilaus draft"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 3. tilaus -sivun drafti</small>


*Uusi tilaus* - ja *Tilaus* -sivujen lisäksi sovelluksessa on vielä kolmas
sivu, *Tilausluettelo* (*Kuva 4*), joka tulee esiin klikattaessa navigointipalkin
*Tilausluettelo* -linkkiä. Klikkauksesta aiheutuu pyyntö polkuun `/list`.


![Tilausluettelo](../img/tilausluettelo.png "Tilausluettelo"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 4.</small>

*Tlausluettelon* ensimmäisessä sarakkeessa esitettävä tilausnumero toimii
linkkinä, jonka klikkaus tuo esiin selaimelle ao. tilauksen *Tilaus*-sivulla.

Tehtävä ratkaistaan täydentämällä tiedostoja `tilaus.html`[^1] ja `app.js`[^2].
**Palauta** tiedostot, kun sovellus toimii odotetusti.

[^1]: Huomioi, että templateen ei tule "ylimääräistä". Se tulee osaksi *layoutia* (`default-layout.html`) samoin kuin pohjassa jo valmiina olevat templatet `tilauslomake.html` ja `tilausluettelo.html`.

[^2]: Tilauslomakkeen lähettämien tietojen käsittely määritellään `app.post` -metodin parametrina olevassa funktiossa. Tilaustiedot löytyvät *Request*-objektin *body* -ominaisuudesta (`req.body`).

<br/>
