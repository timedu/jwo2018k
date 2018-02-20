---
layout: exercise_page
title: "Tehtävä 7.3: Tehtävälista, lisäys (3p)"
exercise_template_name: # (ed. tehtävästä)
exercise_discussion_id: 95784
exercise_upload_id: 374788
modified_at: 20.2.2018
---

Täydennä [edellisen tehtävän](../tehtava72) ratkaisua[^pohja] siten, että sovellus
kykenee tallettamaan tietokantaan kirjautuneen käyttäjän omistukseen uusia tehtäviä.
Toiminnon toteuttavat selainpään moduuli
`code-insert.js` ja palvelipään moduuli `taskit-insert.js`.

[^pohja]: Pohjakoodina käytetään edellisen tehtävän ratkaisua

Tarkoitus on, että moduulissa `code-insert.js` oleva funktio `insertTask`
lähettää palvelupyynnön[^esim] `POST`-metodilla osoitteeseen `/api/taskit` välittäen
pyynnön mukana tietokantaan talletettavan uuden tehtävän, esim: `{task: "homma"}`.
Vasteen saatuaan funktio lisää uuden tehtävän selaimessa olevaan dokumenttiin
`createTaskElement`-funktiota[^createTaskElement] käyttäen
tai tulostaa ao. tilanteessa konsolille vasteessa olevan virheen.

[^esim]: Käsikirjasta poimittu esimerkki: [Tehtävä 7.1](../tehtava71) / Listaus 2
[^createTaskElement]: Sisältyy moduuliin `code-dom.js`.

Palvelipään moduulissa `taskit-insert.js` oleva funktio `addNewTask` käsittelee
pyynnön tallettaen uuden tehtävän tietokantaan. Taulun `owner`-sarakkeen
arvoksi tulee istunnosta löytyvä kirjautuneen käyttäjä nimi
(`req.session['user-name']`). Funktio tuottaa pyyntöön seuraavan muotoisen
vasteen:

{% highlight javascript  %}

res.json({
    err: null,
    lastID: 95,
    changes: 1
});

{% endhighlight %}

<small>Listaus 1.</small>

*Listaukssa 1* esitetyn objektin kaikkien attribuuttien arvot saadaan
tietokantajapinnasta. `err` tulee rajapinnan [run][run]-metodille
annettavan callback-funktion  parametrina. `lastID`  ja `changes` ovat
käytettävissä callback-funktiossa `this`-viitteen kautta[^esim2].

[run]: https://github.com/mapbox/node-sqlite3/wiki/API#databaserunsql-param--callback
[^esim2]: Ks. esim. <http://www.sqlitetutorial.net/sqlite-nodejs/insert/>


**Palauta** tehtävän ratkaisuna tiedostot `code-insert.js` ja
`taskit-insert.js`.

<br/>
