---
layout: exercise_page
title: "Tehtävä 7.4: Tehtävälista, muutos (3p)"
exercise_template_name: # (ed. tehtävästä)
exercise_discussion_id: 95785
exercise_upload_id: 374789
modified_at: 12.3.2018
---

Täydennä [edellisen tehtävän](../tehtava73) ratkaisua[^pohja] siten, sovelluksella
voi muuttaa tehtävän statusta (*todo/done*). Toiminnon toteuttaa selainpään moduuli
`code-update.js` yhdessä palvelipään moduulin `taskit-update.js` kanssa.

[^pohja]: Pohjakoodina käytetään edellisen tehtävän ratkaisua

Ratkaisussa moduulin `code-update.js`  funktio `updateTask`
lähettää palvelupyynnön[^esim] `PUT`-metodilla osoitteeseen `/api/taskit/id`,
jossa `id` on päivitettävän tehtävän perusavaimen arvo[^id].
Pyynnön mukana välittyy tieto tehtävään suoritettavasta muutoksesta, esim: `{status: "done"}`.
Vasteen saatuaan funktio siirtää ao. tehtävän dokumentissa olevasta listasta
toiseen (*Todo/Done*)
`moveTaskElement`-funktiota[^moveTaskElement] käyttäen
tai tulostaa ao. tilanteessa konsolille vasteessa olevan virheen.

[^id]: Moduulissa `code-dom.js` oleva funktio `createTaskElement` paketoi id:n elementtiin siten, että se löytyy funktiossa `updateTask` viittauksella `$(taskElement).data('task-id')`.
[^esim]: Käsikirjasta poimittu esimerkki: [Tehtävä 7.1](../tehtava71) / Listaus 2
[^moveTaskElement]: Sisältyy moduuliin `code-dom.js`.

Palvelipään moduulissa `taskit-update.js` oleva funktio `changeTaskStatus` käsittelee
pyynnön muuttaen tehtävän status-sarakkeen arvon tietokannassa.
Funktio tuottaa pyyntöön seuraavan muotoisen vasteen:

{% highlight javascript  %}

res.json({
    err: null,
    changes: 1
});

{% endhighlight %}

<small>Listaus 1.</small>

Vaste on kuten [edellisen tehtävän](../tehtava73) ratkaisussa mutta ilman
`lastID`-attribuuttia.


**Palauta** tehtävän ratkaisuna tiedostot `code-update.js` ja
`taskit-update.js`.

<br/>
