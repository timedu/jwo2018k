---
layout: exercise_page
title: "Tehtävä 6.3: Elokuva-arviot, vaihe 3 (3p)"
exercise_template_name: #
exercise_discussion_id: 94969
exercise_upload_id: 373510
julkaisu: täydennettynä 14.2.2018
kesken: 1
modified_at: 13.2.2018
---

Muodosta [edellisen tehtävän](../tehtava62) ratkaisua hyödyntäen
[tehtäväpohjaan][pohja][^pohja] template siten, että esim. pyynnöllä polkuun `/tmnt`
sovellus tuottaa selaimeen *Kuvien 1 ja 2* mukaisen sivun ja  pyynnöllä polkuun
`/princessbride` *Kuvien 3 ja 4* mukaisen sivun.

[pohja]: https://moodle2.tut.fi/mod/resource/view.php?id=373624
[^pohja]: Tämän tehtävän [pohjakoodi][pohja] on Moodlessa.

{% assign spacer = '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;' %}

{{spacer}} Kuva 1. [TMNT - sivun yläosa][kuva1]   
{{spacer}} Kuva 2. [TMNT - sivun alaosa][kuva2]   
{{spacer}} Kuva 3. [Princess Bride - sivun yläosa][kuva3]  
{{spacer}} Kuva 4. [Princess Bride - sivun alaosa][kuva4]

[kuva1]: https://moodle2.tut.fi/mod/resource/view.php?id=373489
[kuva2]: https://moodle2.tut.fi/mod/resource/view.php?id=373490
[kuva3]: https://moodle2.tut.fi/mod/resource/view.php?id=373613
[kuva4]: https://moodle2.tut.fi/mod/resource/view.php?id=373614


Tehtäväpohjassa oleva runko on [edellisen tehtävän](../tehtava62) vastaavaan
verrattuna hivenen toisenlainen (*Kuva 5*). Pyynnön polussa olevaa parametria
vastaava elokuvan tunniste on sivun otsikko-osassa ja arvioita esittäviä
template-moduuleja tässä on ainoastaan yksi edellisen kahden sijaan.

![Templaten runko](../img/template-skeleton-2.png "Templaten runko"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 5. Templaten runko.</small>

Tehtäväpohjassa on objekti `movies`, joka sisältää neljän elokuvan
(`mortalkombat`, `princessbride`, `tmnt`, `tmnt2`) arvioinnit. Sovellus toimii
niin, että pyynnön parametri määrää, mihin elokuvaan liittyvä arviointisivu
palautetaan selaimelle. Pyyntö käsitellään siten, että ao. elokuvaan liittyvä
`movies`-objektin ominaisuus (siis myös objekti) välitetään templatelle:

{% highlight js %}

app.get('/:id', function (req, res) {
    ...
    res.render('movie-review-page', {
        movie: movies[req.params.id]
    });
});

{% endhighlight %}


<small>Listaus 1. Elokuvan tietojen välitys templatelle.</small>


Elokuviin liittyvät tiedot löytyvät tehtäväpohjan `data`-hakemistosta
`json`-muotoisina, esim. `tmnt.json`:

~~~
{
    "id": "tmnt",
    "name": "TMNT",
    "year": "2007",
    "...": "..."
}
~~~

<small>Listaus 2. Ote tiedostosta *data/tmnt.json*</small>

Nämä tiedostostot otetaan pohjassa käyttöön siten, että esim. *Lastauksessa 2* esiintyvään
elokuvan nimeen voidaan viitata templatessa seuraavasti:
{% raw %}`{{movie.name}}`{% endraw %}. Elokuvan, sivulla oikealla
puolella näkyvä, "juliste" sijaitsee `img/movies` -kansiossa.  Kuvaan
viitataan templatessa seuraavasti:
{% raw %}`src="img/movies/{{movie.id}}/overview.png"`{% endraw %}.


Elokuvan tiedot vaikuttavat myös sivulla
esitettäviin muihin kuviin. Jos arvioija on antanut elokuvasta arvosanan (`score`)
"FRESH", esitetään tekstimuotoisen arvion yhteydessä kuva `fresh.gif`. Jos
arvosana on "ROTTEN", esitettävä kuva on `rotten.gif`. (ks. esim. *[Kuva 3][kuva3]*)

Elokuvilla on myös numeerinen kokonaisarvosana (`score`). Jos kokonaisarvosana
on vähintään 60, sivun sisältöosan ylä- ja alapalkeissa esitetään kuva
`freshlarge.png`. Muussa tapauksessa palkeissa esitettävä kuva on `rottenlarge.png`.
(ks. *[Kuva 1][kuva1]* ja *[Kuva 3][kuva3]*)

Seuraavissa templateen kuuluvissa tiedostoissa on
elokuvan tiedoista riippuvia osia: `heading-row.html`, `content-banner-row.html`,
`review-col.html`, `review-summary-col.html` ja `overview-col.html`. Kahdessa
tiedostossa tulee vastaan silmukkarakenteen käyttö ja muutamassa on luonteva soveltaa
pohjakoodiin sisällytettyjä apufunktioita. Näitä on käsitellään lyhyesti seuraavassa
kohdassa.

**Palauta** tehtävän ratkaisuna zip-arkisto `partials`-hakemiston sisällöstä.

### Vihjeitä ja lisätietoja

...

<br/>

<small>
Tehtävän lähde: Homeworks Movie Review & Movie Review Part Deux.<br/>
[Web Programming][cse154], University of Washington, Computer Science & Engineering.<br/>
Copyright © Marty Stepp / Jessica Miller, licensed under Creative Commons Attribution 2.5 License.<br/>
(alkuperäistä tehtävää muokattu)
</small>

[cse154]: https://courses.cs.washington.edu/courses/cse154/

<br/>
