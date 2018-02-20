---
layout: exercise_page
title: "Tehtävä 7.5: Tehtävälista, poisto (3p)"
exercise_template_name: # (e. tehtävästä)
exercise_discussion_id: 95786
exercise_upload_id: 374790
modified_at: 20.2.2018
---

Täydennä [edellisen tehtävän](../tehtava74) ratkaisua[^pohja] siten, sovelluksella
voi poistaa kirjautuneen käyttäjän omistuksessa olevat tehdyksi (*done*) merkityt
tehtävät. Toiminnon toteuttavat moduulit `code-delete.js` selainpäässä ja
 `taskit-delete.js` palvelinpäässä.

[^pohja]: Pohjakoodina käytetään edellisen tehtävän ratkaisua

Selainpään moduulin `code-delete.js` funktion `deleteTasks` tehtävänä on
lähettää palvelupyyntö[^esim] `DELETE`-metodilla osoitteeseen `/api/taskit`.
Vasteen saatuaan funktio poistaa selaimessa olevasta dokumentista
`removeDoneElements`-funktiota[^removeDoneElements]  käyttäen
*Done*-luettelossa olevat tehtävät
tai tulostaa ao. tilanteessa konsolille vasteessa olevan virheen.

[^esim]: Käsikirjasta poimittu esimerkki: [Tehtävä 7.1](../tehtava71) / Listaus 2
[^removeDoneElements]: Sisältyy moduuliin `code-dom.js`.

Palvelipään moduulissa `taskit-delete.js` oleva funktio `removeDoneTasks` käsittelee
pyynnön poistaen tietokannasta kirjautuneen käyttäjän (`req.session['user-name']`)
valmiiksi merkityt (status="done") tehtävät. Funktio tuottaa pyyntöön [edellisen tehtävän](../tehtava74) ratkaisuun verrattuna samanmuotoisen vasteen.

**Palauta** tehtävän ratkaisuna tiedostot `code-delete.js` ja
`taskit-delete.js`.

<br/>
