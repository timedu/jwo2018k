---
layout: exercise_page
title: "Tehtävä 7.1: Tehtävälista, runko (3p)"
exercise_template_name: W7E01.TaskIT
exercise_discussion_id: 95782
exercise_upload_id: 374786
modified_at: 20.2.2018
---

Pohjakoodissa on *Tehtävälista* -sovelluksen runko, josta puuttuu palvelinpäässä
tapahtuva tietokantakäsittely sekä tietokantaoperaatioihin liittyvien pyyntöjen
välitys selaimelta palvelimelle. Täydennä runkoa tässä vaiheessa siten, että
selainpäässä suoritettava koodi lähettää palvelimelle pyynnöt ja tulostaa
web-konsolille palvelimen pyyntöihin antamat vakioarvoiset vasteet (*Kuva 1*).


![Tehtävälista](../img/taskit_skeleton.png "Tehtävälista"){: style="display: block;  margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1.</small>

*Kuvan 1*  tilanteessa käyttäjä on kirjautunut, jonka jälkeen konsolille on
tulostunut teksti `selectTasks` merkkinä tuon nimisen funktion suorittamisesta.
Tekstin alla on palvelimen antama vaste funktion suorittamaan pyyntöön.

Sitten
käyttäjä on syöttänyt sivulla olevaan tekstikenttään joitakin merkkejä ja
klikannut *Add todo* -painiketta. Tämän seurauksena sovellus on suorittanut funktion
`insertTask`, joka on aikaansaanut seuraavat tulosteet konsolille. Tulosteista
jälkimmäinen, `{err: null, lastID: 95, changes: 1}`, on taas palvelimen vaste
funktion toteuttamaan pyyntöön.

Vastaavanlaiset tulosteet ovat syntyneet
painikkeiden *Test task* (`updateTask`) ja *Delete done* (`deleteTasks`)
klikkausten seurauksena.

**Palauta** tehtävän ratkaisuna tiedostot `code-select.js`, `code-insert.js`,
`code-update.js` ja `code-delete.js`, jotka sisältävät edellä viitatut funktiot.


### Vihjeitä ja lisätietoja

Selainpään ohjelmakoodi on jaettu kuuteen tiedostoon (*Listaus 1*), joista
kaksi, `code-dom.js` ja `code-login.js`, on pohjassa valmiina. Näistä ensimmäinen
sisältää funktioita, joilla voi manipuloida selaimessa olevaa dokumenttia.
Jälkimmäisen tehtävävä on lähettää kirjautumistiedot palvelimelle.

{% highlight html %}

<script src="./js/code-dom.js"></script>
<script src="./js/code-login.js"></script>

<script src="./js/code-select.js"></script>
<script src="./js/code-insert.js"></script>
<script src="./js/code-update.js"></script>
<script src="./js/code-delete.js"></script>

{% endhighlight %}

<small>Listaus 1. Selainpään ohjelmakoodi (ote tiedostosta *layout.html*)</small>

Muita tiedostoja tulisi täydentää lisäämällä niihin palvelimella
tapahtuvaan tietokantakäsittelyyn liittyvät pyynnöt. Tosin tässä vaiheessa
pyyntöjen ei vielä tarvitse välittää palvelimelle tietoja. Kaikki pyynnöt
voidaan toteuttaa *jQuery:n* [$.ajax][ajax]-funktiolla, jonka käytöstä
seuraavassa on käsikirjasta poimittu esimerkki:

[ajax]: http://api.jquery.com/jQuery.ajax/


{% highlight js %}

$.ajax({
  method: "POST",
  url: "some.php",
  data: { name: "John", location: "Boston" }
}).done(function( msg ) {
    alert( "Data Saved: " + msg );
});

{% endhighlight %}

<small>Listaus 2. Esimerkki ajax-funtion käytöstä. (Copyright [The jQuery Foundation][foundation]. [jQuery License][license].)</small>

[ajax]: http://api.jquery.com/jQuery.ajax/
[foundation]: https://jquery.org/team
[license]: https://jquery.org/license/

Myös palvelinpään ohjelmakoodi on jäsennetty useaksi tiedostoksi. Seuraavassa
*Listauksessa 3* on ote tiedostosta `taskit/index.js`, joka määrittelee polut,
joihin sovellus vastaa. Kuhunkin listauksen esittämään polkuun liittyvä funktio
on erillisessä tiedostossa.

{% highlight js %}

const listTasks = require('./taskit-select');
const addNewTask = require('./taskit-insert');
const changeTaskStatus = require('./taskit-update');
const removeDoneTasks = require('./taskit-delete');

app.get('/api/taskit', listTasks);
app.post('/api/taskit', addNewTask);
app.put('/api/taskit/:id', changeTaskStatus);
app.delete('/api/taskit', removeDoneTasks);

{% endhighlight %}

<small>Listaus 3. Palvelinpään ohjelmatiedostoja (ote tietostosta *taskit/index.js*).</small>

*Listauksessa 3* esiintyvät `app`-objektin metodit antavat vihjeen siitä,
minkälaisia arvoja `$.ajax`-funktion parametrina olevan objektin `method`-ominaisuudelle
tulee asettaa eri pyyntöjen yhteydessä.


<br/>
