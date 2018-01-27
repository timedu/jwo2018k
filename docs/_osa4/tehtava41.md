---
layout: exercise_page
title: "Tehtävä 4.1: Node-laskin (2p)"
exercise_template_name: W4E01.NodeLaskin
exercise_discussion_id: 93295
exercise_upload_id: 371620
modified_at: 27.1.2018
---

Tehtävissä [2.2](../../osa2/tehtava22) ja [3.2](../../osa3/tehtava32) rakennettiin web-pohjaset nelilaskimet. Tässä laaditaan toiminnoiltaan vastaana laskin,
mutta sen käyttö tapahtuu selaimen sijaan käyttöjärjestelmän komentotulkin
kautta (*Kuva 1*).
![Laskin](../img/node_laskin.png "Laskin"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}
<small>Kuva 1. Node-laskin.</small>

Koodi laaditaan tiedostoon `laske.js` ja se suoritetaan [Node:lla][node],
jolloin sovellus voidaan käynnistää  komennolla `node laske`. Laskimelle
annetaan kolme laskutoimituksen määrittelemää parametria, *2 operandia* ja
*operaattori*, ja siten komento parametreineen on esim. `node laske 6 3 +`.
Laskin tulostaa laskutoimituksen tuloksen, esim. `9`. Jos laskin ei tunnista
operaattoria, se tulostaa tekstin `oops`. Laskin tunnistaa
operaattorit `+`, `-`, `x` ja `/`.

[node]: https://nodejs.org


![Laskintesti](../img/node_laskin_testi.png "Laskintesti"){: style="display: block; margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 2. Laskimen toiminnan testaaminen.</small>

**Palauta**  tehtävästä tiedosto `laske.js`, kun sovellus
toimii odotetusti ja läpäisee tehtäväpohjan sisältämät testit (*Kuva 2*).

### Vihjeitä ja lisätietoja

Tehtävä edellyttää, että kehitysympäristöön on asennettu [Node.js][node], jonka
sivustolta paketin voi ladata. Sivustolta löytyy myös ohjeita *Node:n* asetamisesta
eri ympäristöihin. Luokkakoneisiin *Node* on asennettu.

Kun *Node* on käytettävissä, tehtäväpohjan koodin pitäisi tulostaa teksti
`Hello Node!` komennolla `node laske`.

Komentoriville annetut parametrit löytyvät
taulukosta
[process.argv](https://nodejs.org/dist/latest-v8.x/docs/api/process.html#process_process_argv).
Esim. seuraavalla koodilla voi tutkia komennolle annettuja parametreja:

{% highlight js %}

for(var i=0; i<process.argv.length; i++){
  console.log(i, ':', process.argv[i]);
}

{% endhighlight %}

Tämä tehtävä lienee luontevinta ratkaista *IDE:n* sijaan jollakin tekstieditorilla,
esim. luokkakoneista löytyvällä *Notepad++:lla*.
