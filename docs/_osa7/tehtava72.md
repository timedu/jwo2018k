---
layout: exercise_page
title: "Tehtävä 7.2: Tehtävälista, kysely (3p)"
exercise_template_name: # (edellinen tetävä)
exercise_discussion_id: 95783
exercise_upload_id: 374787
modified_at: 19.2.2018
---

Täydennä [edellisen tehtävän](../tehtava71) ratkaisua[^pohja] siten, sovellus esittää sivullaan
tietokannasta luettuja tehtäviä. Toiminnon toteuttaa selainpäässä moduuli
`code-select.js` ja palvelipäässä `taskit-select.js`.

[^pohja]: Pohjakoodina käytetään edellisen tehtävän ratkaisua

![Tehtävälista](../img/taskit_v2.png "Tehtävälista"){: style="display: block;  margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 1.</small>

Selainpään toteutuksen jälkeen sivun ulkoasu on *Kuvan 1* kaltainen, jolloin
siis palvelinpään moduuli palauttaa pyynnön vasteeksi vielä vakiotietoja (*Listaus 1*).


{% highlight js %}

const selectOwnerTasks = "SELECT ...";

function listOwnerTasks(req, res) {
    console.log('listOwnerTasks');
    res.json({
        err: null,
        rows: [
            {id: 32, owner: 'Ned', task: 'Study', status: 'done'},
            {id: 33, owner: 'Ned', task: 'Examine', status: 'todo'},
            {id: 34, owner: 'Ned', task: 'Research', status: 'todo'}
        ]
    });
}

{% endhighlight %}

<small>Listaus 1.</small>

Pyynnön vasteeksi palautetaan objekti, joka sisältää ominaisuudet `err` ja `rows`.
Ratkaisussa niiden
arvot tulevat suoraan tietokantarajapinnasta (ks. [all][all]). `rows` on taulukko,
joka sisältää kirjautuneen käyttäjän omistuksessa olevat tehtävät. Jos pyynnön
tehneeltä selaimelta ei ole kirjauduttu, pyyntöön palautetaan tyhjä taulukko:

[all]: https://github.com/mapbox/node-sqlite3/wiki/API#databaseallsql-param--callback


{% highlight json %}

{ "err": null, "rows": [] }  

{% endhighlight %}

<small>Listaus 2.</small>

Tietokantarajapinta näkyy tunnisteessa `db`. Tietokanta tauluineen muodostuu
sovelluksen käynnistyksen yhteydessä, jos se aiemmin ei ole ollut olemassa
(`taskit-db.js`). Kirjautuneen käyttäjän nimi löytyy pyynnöstä: `req.session['login-user']`.

Selainpään ratkaisua tukee moduulissa `code-dom.js` määritelty funktio
`createTaskElement`, joka muodostaa sivulle parametriensa määrittelemän
tehtävä -elementin. Sovelluksen selainpäähän valmiiksi rakennettu
kirjautuminen (`code-login.js`) käynnistää tehtävien haun selainpäähän.


**Palauta** tehtävän ratkaisuna tiedostot `code-select.js` ja
`taskit-select.js`.

<br/>
