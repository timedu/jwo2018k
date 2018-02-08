---
layout: exercise_page
title: "Tehtävä 4.6: Quiz (5p)"
exercise_template_name:
exercise_discussion_id: 93300
exercise_upload_id:
no_review: 1
modified_at: 1.2.2018
---

Tämä Moodlessa oleva [sarja monivalintatehtäviä][quiz] on luonteva suorittaa
ohjelmointitehtävien jälkeen. Kysymyksiin vastaaminen oletettavasti edelyttää
pienten kokeilujen tekemistä aikaisempien tehtävien ratkaisuilla. Saattaa olla,
että kokeiluja ei pysty tekemään tentin vastaamisajan puitteissa, joten
ensimmäinen vastaamiskerta mennee kysymyksiin tutustumiseen. Jos jokin kysymyksistä tuntuu moniselitteiseltä, siitä kannattaa raportoida "keskusteluun".

[quiz]:  https://moodle2.tut.fi/mod/quiz/view.php?id=372266

Kuten aiemmat vastaavat tämä [tehtäväkokonaisuus][quiz] on "Moodle-tentti", jossa on 12 monivalintatehtävää. Vastaamiseen on kuitenkin aikaa nyt 20 minuuttia. Kukin oikeaksi tulkittu vastaus tuottaa yhden pisteen väärän vähentäessä puoli pistettä. Vastaamatta jäänyt kysymys ei lisää eikä vähennä pistepottia. Tentin suorituksen jälkeen saa kokonaispalautteen suorituksesta: vastausten myötä muodostunut kokonaispistemäärä. Tentin voi suorittaa enintään kolme kertaa, joista viimeisin suoritus huomioidaan.

Tentin tuottama pistemäärä (max 12) skaalataan tehtäväpisteiksi (max 5) kokonaisluvuksi pyöristäen.

### Lisätietoja

Eräissä monivalintakysymyksissä tiedustellaan tietyssä tilanteissa selaimen palvelimelle (tai palvelimille) tekevien pyyntöjen määrää. Tämän voi selvittää selaimiin sisältyvien web-työkalujen avulla. Seuraava kuva esittää, miten *Firefox*-selain esittää selaimen tekemät pyynnöt sivua ladattaessa:

![Eläimet](../img/elaimet_requests.png "Eläimet"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Eläimet -sivun hakuun liittyvät pyynnöt.</small>

Esimerkki liittyy [Tehtävän 2.1](../../osa2/tehtava21) `index.html` -sivuun,
joka sisältää kolme kuvaa. Siten sivun lataaminen edellyttää neljää pyyntöä. Web-työkalut esimerkkiympäristössä on saatu selaimen ikkunaan *Työkalut*-valikosta valinnalla *Web-työkalut>Toggle Tools*. Työkalupaletista on sitten valittu *Network* ja vielä *All*, joka tarkoittaa, että ollaan kiinnostuneita kaikenlaisiin kohteisiin liittyvistä pyynnöistä[^1]. *All*-sanan vieressä olevan *roskis*-merkin klikkaus tyhjentää pyyntöluettelon.

[^1]: Tutki vaikka, millaisia pyyntöjä aiheutuu, kun otat selaimeen sivun `www.tut.fi`.

Tietyt monivalinnat edelyttävät selaimeen luetun merkkauksen lähdekoodin selvittämistä. Esimerkkiympäristössä (FF/Mac/Fi) lähdekoodi saadaan esiin *Työkalut*-valikosta valinnalla *Web-työkalut>Sivun lähdekoodi* (*Kuva2*).

![Eläimet](../img/elaimet_source.png "Eläimet"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Eläimet -sivun lähdekoodi.</small>

*Kuvan 2* näkymä edustaa html-koodia, jonka selain lataa palvelimelta. Tämä näkymä ei muutu, vaikka dokumenttia muokattaisiin selaimen päässä. Ajantasaisen tiedon dokumetista saa selaimen *Inspector* -työkalulla (*Kuva 3*).


![Eläimet](../img/elaimet_inspector.png "Eläimet"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 3. Eläimet -sivun dokumenttipuu.</small>




<br/>
