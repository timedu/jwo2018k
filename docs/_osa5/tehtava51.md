---
layout: exercise_page
title: "Tehtävä 5.1: Viestit (2p)"
exercise_template_name: W5E01.Viestit
exercise_discussion_id: 94003
exercise_upload_id: 372511
modified_at: 8.2.2018
---

Perusta tehtäväpohjan `data`-kansioon *SQLite*-tietokanta `viestikanta.db` ja
tietokantaan taulu `viestit`. Talleta tauluun muutama viesti käyttäen
tietokannan komentoperustaista tai graafista käyttöliittymää. Laadi sitten
ohjelma `viestit.js`, joka tulostaa tietokantatauluun talletetut viestit
(viimeisin ensin) seuraavasti:

![Viestit](../img/viestit.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Viestien tulostus</small>


**Palauta** tehtävän ratkaisuna tiedostot `viestit.js` ja `viestikanta.db`.

### Vihjeitä ja lisätietoja

#### Tietokannan perustamisesta

Tietokannan ja taulun perustamiseen sekä tietojen tallettamiseen voi käyttää
esim.  [DB Browser for SQLite][browser] -ohjelmaa, jonka voi ladata tuotteen
sivustolta. Työkalusta löytyy painike ja menuvalilta, jonka kautta tietokannan
voi perustaa haluamaansa kansioon. Taulun sarakkeineen voi perustaa ao.
ikkunassa:


[browser]: http://sqlitebrowser.org

![Create Table](../img/create_table.png "Create Table"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. viestit-taulun luonti</small>

Dataa viestit-tauluun voi tallentaa taulukkomuotoisen näkymän kautta:

![Insert Rows](../img/insert_rows.png "Insert Rows"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 3. Rivien talletus viestit-tauluun</small>


Tietokannan datoineen voi luoda myös komentopohjaisella työkalulla, jonka voi
ladata [SQLite:n sivustolta][download][^atk-luokat] eri käyttöjärjestelmille:


[download]: https://www.sqlite.org/download.html
[^atk-luokat]: Tämän työkalun voi tarvittaessa asentaa itse myös luokkakoneisiin esim. laitteen `C:\Temp`-kansioon.


![SQLite CLI](../img/sqlite3_cli.png "SQLite CLI"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 4. SQLite CLI</small>

*Kuva 4* esittämässä istunnossa käynnistetään ensin `sqlite3`-työkalu, jolle
annetaan parametriksi tietokannan sisältävän tiedoston nimi, tässä: `viestikanta.db`:

{% highlight shell %}

sqlite3 viestikanta.db

{% endhighlight %}

<small>Listaus 1. *sqlite3*-työkalun käynnistys ja tietokannan *viestikanta.db* perustaminen. </small>

Tämän jälkeen työkalun avulla `CREATE TABLE` -komennolla luodaan `viestit`-tietokatataulu:


{% highlight sql %}

CREATE TABLE `viestit` (
  `id`	      INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
  `lahettaja` TEXT NOT NULL,
  `aika`      TEXT NOT NULL,
  `sanoma`    TEXT NOT NULL
);

{% endhighlight %}

<small>Listaus 2. *viestit*-taulun luova sql-komento.</small>


Ja sitten  tauluun lisätään `INSERT`-komennolla yksi viesti:


{% highlight sql %}

INSERT INTO viestit (lahettaja, aika, sanoma)
VALUES ('Ned', '2018-02-02', 'Hello world');

{% endhighlight %}

<small>Listaus 3. Viestin talletus viestit-tauluun</small>


Lopuksi tulostetaan `viestit`-taulun kaikki tiedot `SELECT`-komennolla:


{% highlight sql %}

SELECT * FROM viestit;

{% endhighlight %}

<small>Listaus 4. *viestit*-taulun tietojen tulostus.</small>

#### Sovelluksen rakentamisesta

Sovellus tarvitsee toimiakseen moduulin, jonka kautta tapahtuu *SQLite*-tietokannan
käsittely. Tämä riippuvuus on kuvattu tehtäväpohjassa olevassa tiedostossa
`package.json`. Siten moduulin voi ladata sovelluksen käyttöön komennolla `npm install`[^npm-install].

[^npm-install]: Komento annetaan hakemistossa, jossa `package.json` sijaitsee.

Tietokantarajapinta saadaan tässä sovelluksen käyttöön seuraavasti:

{% highlight js %}

const sqlite3 = require('sqlite3').verbose();
const db = new sqlite3.Database('./data/viestikanta.db');

{% endhighlight %}

Viestit voidaan lukea tietokannasta [rajapinnan][api] [all][all]- tai [each][each]-metodeilla.
Seuraava ote on poimittu *sqlite3*-rajapinnan esimerkistä [simple-chaining.js][simple-chaining]:

[all]: https://github.com/mapbox/node-sqlite3/wiki/API#databaseallsql-param--callback
[each]: https://github.com/mapbox/node-sqlite3/wiki/API#databaseeachsql-param--callback-complete
[api]: https://github.com/mapbox/node-sqlite3/wiki/API



{% highlight js %}

db.all("SELECT rowid AS id, info FROM lorem", function(err, rows) {
  rows.forEach(function (row) {
    console.log(row.id + ": " + row.info);
  });
});

{% endhighlight %}



[simple-chaining]: https://github.com/mapbox/node-sqlite3/blob/master/examples/simple-chaining.js

<br/>

Alaviiteet
