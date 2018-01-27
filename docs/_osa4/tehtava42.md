---
layout: exercise_page
title: "Tehtävä 4.2: Express-laskin (2p)"
exercise_template_name: W4E02.ExpressLaskin
exercise_discussion_id:
exercise_upload_id:
julkaisu: 27.1.2018
---

Tässä jatketaan [edellsen tehtävän](../tehtava41) laskin-teemaa. Nyt rakennetaan
[Node:n][node] ja [Express:in][express] tuella laskentaan kykenevä web-palvelin.

[node]: https://nodejs.org
[express]: https://expressjs.com

![Laskin](../img/express_laskin.png "Laskin"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Express-laskin.</small>

Laskinta käytetää *Kuvan 1* esimerkin esittämällä tavalla. Selaimen osoiteriville
on kirjattu pyyntö, jonka määritelee palvelimen suorittaman lausekkeen
(kuvassa: `6 + 3`). Kun pyyntö välitetään palvelimelle, laskennan
tulos (kuvassa: `9`) saadaan selain-ikkunaan.

*Kuvassa 1* selaimen osoiteriville kirjattu pyyntö on seuravanlainen:

~~~
http://localhost:3000/?luku1=6&luku2=3&lasku=add
~~~

<small>Listaus 1.</small>

Palvelin osaa tulkita myös seuraavanlaisia pyyntöjä:

~~~
http://localhost:3000/add?luku1=6&luku2=3
~~~

<small>Listaus 2.</small>

... ja myöskin tällaisia:

~~~
http://localhost:3000/add/6/3
~~~

<small>Listaus 3.</small>

Laskin tuntee `add`-operaattorin lisäksi operaattorit `sub`, `mul` ja `div`.
Seuraavanlainen pyyntö tuottaa selaimen ikkunaan tekstin `oops` liittyen
tilanteeseen, jossa *Listauksen 1* muotoisessa pyynnössä on operaattori, jota
laskin ei tunne:

~~~
http://localhost:3000/?luku1=6&luku2=3&lasku=unknown
~~~

<small>Listaus 4.</small>

Jos pyyntö kohdistuu polkuun, jota palvelin ei tunnista (*Listaus 5*), selaimen ikkunaan
ilmestyy teksti `hupsista`.

~~~
http://localhost:3000/unknown
~~~

<small>Listaus 5.</small>

Tehtäpohja on NetBeans-projekti. Ratkaisu laaditaan tiedostoon `laskuri.js`.
Sovelluksen toiminta edellyttää *Express* -sovelluskehyksen asentamista.
Tämä riippuvuus on kuvattu pohjassa olevassa tiedostossa `package.json` ja
siten kehyksen asentamisen voi tehdä komennolla `npm install`
joko komentotasolta[^npm-install] tai NetBeans:ista[^npm-install-nb].

[^npm-install]: komento tulee antaa hakemistossa, jossa `package.json` sijaitsee

[^npm-install-nb]: ao. valikko tulee esiin klikkaamalla projektia hiiren oikealla näppäimellä

Pohjassa on mukana myös testejä. Testien ajamiseen tarvittava kalusto on
määritelty tiedostossa `package.json` ja siten kalusto asentuu Express:in
asentamisen yhteydessä. Testit tulee ajaa komentotasolla[^test] projektihakemistossa
komennolla `./node_modules/mocha/bin/mocha`[^test-windows] (*Kuva2*).

[^test]: periaatteessa tämä onnistuu myös NetBeans:issa, mutta NetBeans ei näytä testauksen tuloksia kaikissa tilanteissa oikein

[^test-windows]: windows-ympäristössä: `.\node_modules\mocha\bin\mocha` (?)

![Laskintesti](../img/express_laskin_testi.png "Laskintesti"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 2. Laskimen toiminnan testaaminen.</small>

Testijoukko `Test Laskuri v.1` liittyy *Listauksen 1* muotoisiin pyyntöihin
 (`Test Laskuri v.2` vs. *Listaus 2*; `Test Laskuri v.3` vs. *Listaus 3*).

**Palauta**  tehtävästä tiedosto `laskuri.js`, kun sovellus
toimii odotetusti ja läpäisee tehtäväpohjan sisältämät testit.

### Vihjeitä ja lisätietoja


Tehtävän ratkaisussa voi lähteä liikkeelle  *Express:in*
[Getting started][hello-world] -esimerkistä (*Listaus 6*), joka muodostaa ja
käynnistää web-palvelimen:

[hello-world]: https://expressjs.com/en/starter/hello-world.html


{% highlight js linenos %}

const express = require('express');
const app = express();

app.get('/', function(req, res) {
  res.send('Hello World!');
});

app.listen(3000, function() {
  console.log('Example app listening on port 3000!');
});

{% endhighlight %}

<small>Listaus 6.</small>

Esimerkistä kerrotaan sivustolla seuraavaa:

> This app starts a server and listens on port 3000 for connections. The app responds with “Hello World!” for requests to the root URL (/) or route. For every other path, it will respond with a 404 Not Found.

Jos  *Listauksen 6* koodi kopioidaan pohjan tiedostoon `laskuri.js`,
palvelin voidaan käynnistää  komennolla `node laskuri`[^start-nb], jolloin
komento-ikkunaan pitäisi tulostua teksti `Example app listening on port 3000!`.
Kun selaimen osoiteriville kirjataan nyt osoite `http://localhost:3000/`, selaimen
ikkunaan pitäisi ilmestyä teksti `Hello World!`. Palvelin voidaan pysäyttää
komentoikkunassa näppäimellä `ctrl-C`.

[^start-nb]: Palvelimena toimiva sovellus voidaan käynnistää myös NetBeans:issa kuten aiemmissa tehtävissä sovellusia on käynnistetty (selain ei tässä kuitenkaan käynnisty).

*Listauksen 6 rivillä 4* oleva `app.get`-metodin kutsu määrittelee, mitä
tapahtuu, kun sovelluksen juureen (`/`) tulee pyyntö. Tällöin siis suoritetaan
metodin toisena parametrina oleva funktio, jolla on kaksi parametria (objektia),
[req][req] ja [res][res]. Näistä ensimmäinen edustaa selaimen tekemää
pyyntöä ("Request") ja
jälkimmäinen selaimelle välitettävää vastetta ("Response"). Funktio toteuttaa muunnoksen
pyynnöstä vasteeksi.

[req]: https://expressjs.com/en/4x/api.html#req
[res]: https://expressjs.com/en/4x/api.html#res

#### Laskuri, versio 1

*Listauksessa 6* polkuun `/`  tulevan pyynnön vaste on sama riippumatta pyyntöä
edustavan `req`-parametrin arvosta, mutta laskimen tapauksessa tilanne on
toisenlainen. Pyynnön mukana tulee parametreja, laskutoimituksen operaattori ja
operandit (ks. *Listaus 1*), jotka määräävät pyyntöön annettavan vasteen. Parametrit
löytyvät `req`-objektin [query][query]-ominaisuudesta: `req.query.luku1`,
`req.query.luku2` ja `req.query.lasku`.

[query]: https://expressjs.com/en/4x/api.html#req.query

#### Laskuri, versio 2

*Listauksessa 2* pyyntö kohdistuu juuren sijaan polkuun `/add`. Tähän
reagointi edellyttää `app.get`-metodin kutsua siten, että kutsun ensimmäisenä
parametrina on merkkijono `/add`:

{% highlight js %}

app.get('/add', function(req, res) {
  // versio 2, yhteenlasku
});

{% endhighlight %}

<small>Listaus 7.</small>


Toisena parametrina on funktio, joka
toteuttaa yhteenlaskun pyynnön parametrien  `req.query.luku1` ja
`req.query.luku2` perusteella, ja palauttaa (`res.send`) sitten
tuloksen selaimelle. Tässä siis laskutoimituksen operaattori on polussa
pyynnön parametrin sijaan.

#### Laskuri, versio 3

*Listauksessa 3* myös laskutoimituksen operandit ovat pyynnön polussa ns.
polkuparametreina. Tällainen polku voidaan esittää `app.get` -metodin kutsussa
seuraavasti:

{% highlight js %}

app.get('/add/:luku1/:luku2', function(req, res) {
  // versio 3, yhteenlasku
});

{% endhighlight %}

<small>Listaus 8.</small>

Polkuparametrit löytyvät `req`-objektin [params][params]-ominaisuudesta.
*Listauksen 8* tapauksessa parametreihin viitataan tunnuksilla
`req.params.luku1` ja `req.params.luku2`.

[params]: https://expressjs.com/en/4x/api.html#req.params

`app.get` -metodin kutsussa ensimmäisenä parametrina oleva `*` tarkoittaa
mitä tahansa polkua. Tässä polku liittyy tilanteeseen, jossa selaimelle
on palautettava teksti `hupsista` (esim. *Listauksen  5* pyynnön seurauksena).


<br/>

Alaviitteet
