---
layout: exercise_page
title: "Tehtävä 5.2: Uusi viesti (2p)"
exercise_template_name: W5E02.UusiViesti
exercise_discussion_id: 94004
exercise_upload_id: 372512
modified_at: 3.2.2018
---

Täydennä [edellisen tehtävän](../tehtava51) ratkaisua toiminnoilla, joilla
tietokantaan voidaan lisätä uusi viesti ja tietokannasta voidaan poistaa viesti:

![Viestit](../img/viestit_insert.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Uuden viestin lisäys ja viestin poisto.</small>

Edellisen tehtävän tapaan kaikki tietokannassa olevat viestit tulostuvat komennolla `node viestit`. Uusi viesti voidaan lisätä antamalla se komennolle parametriksi, esim:

{% highlight shell %}

node viestit "Uusi päivä, uudet kujeet"

{% endhighlight %}

Viestin talletuksesta tulee palaute `Viesti talletettu`.
Sovellus päättelee itse sekä viestin lähettäjän että lähetysajankohdan. Viesti
voidaan poistaa tietokannasta seuraavasti:

{% highlight shell %}

node viestit -d 2

{% endhighlight %}

Komennon parametrina on tällöin siis `-d` ja poistettavan viestin `id`-attribuutin
arvo. Onnistuneesta poistosta tulostuu palaute `Viesti poistettu`. Jos parametrin
osoittamaa viestiä ei löydy tietokannasta, tulostuu palautteeksi `Viestiä ei löydy`.


Ratkaise tehtävä täydentämällä tehtäväpohjan tiedostoa `viestit.js` ja **palauta** se,
kun sovellus toimii odotetusti.


### Vihjeitä ja lisätietoja

Tehtäväpohjassa otetaan käyttöön moduulit [current-date][current-date] ja
[username][username]:

[username]: https://www.npmjs.com/package/username
[current-date]: https://www.npmjs.com/package/current-date


{% highlight js %}

const currentDate = require('current-date');
const username = require('username');

{% endhighlight %}

Näiden moduulien avulla tietokantaan talletettavan viestin käyttäjä ja
lähetysajankohta saadaan seuraavasti:

{% highlight js %}

var lahettaja = username.sync();
var aika = currentDate('date');

{% endhighlight %}

Tarvittavan tietokantamoduulin ohella nämä riippuvuudet on kuvattu tehtäväpohjan
tiedostossa `package.json` ja siten ne asentuvat sovelluksen käyttöön komennolla
`npm install`.

Sovelluksessa viestien lisäyksen ja poiston voi hoitaan tietokantarajapinnan [prepare][prepare]- ja
[run][run]-metodeilla (ks. [esimerkki][chaining]). Tosin *prepare*- metodia ei
tässä välttämättä tarvita (ks. [insert][insert]- ja [delete][delete] -esimerkit).

[run]: https://github.com/mapbox/node-sqlite3/wiki/API#databaserunsql-param--callback
[prepare]: https://github.com/mapbox/node-sqlite3/wiki/API#databasepreparesql-param--callback

[chaining]: https://github.com/mapbox/node-sqlite3/blob/master/examples/simple-chaining.js

[insert]: http://www.sqlitetutorial.net/sqlite-nodejs/insert/
[delete]: http://www.sqlitetutorial.net/sqlite-nodejs/delete/
