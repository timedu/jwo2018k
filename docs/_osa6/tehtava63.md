---
layout: exercise_page
title: "Tehtävä 6.3: Elokuva-arviot, vaihe 3"
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





{% comment %}

> The Fifteen Puzzle (also called the Sliding Puzzle) is a simple classic game consisting of a 4×4 grid of numbered squares with one square missing. The object of the game is to arrange the tiles into numerical order by repeatedly sliding a square that neighbors the missing square into its empty space.

Laadi selaimessa toimiva liukupalapeli täydentämällä oheistettua projektirunkoa.

![Peli alussa](../img/peli_alussa.png "Peli alussa"){: style="display: block;  margin-top: 10px; width: 400px;"}

<small>Kuva 1.</small>

Sovelluksen käynnistymisen yhteydessä koodi muodostaa pelin palat pelialueelle siten, että palat ovat pelialueella numerojärjestyksessä (*Kuva 1*). Alkutilateessa palaa 12 tai 15 voi siirtää pelialueella olevaan tyhjään paikkaan. Siirto tapahtuu palaa klikkaamalla. Kun hiiren kursori on siirrettävissä olevan palan yläpuolella, kursorin muoto on *pointer*, ja palan numero ja raami ovat punaisia.

![Peli sekoitettu](../img/peli_sekoitettu.png "Peli sekoitettu"){: style="display: block;  margin-top: 10px; width: 400px;"}

<small>Kuva 2.</small>

Palat voidaan sekoittaa klikkaamalla *Sekoita* -painiketta. *Kuvassa 2* on eräs mahdollinen tilanne pelialueella palojen sekoittamisen jälkeen. *Kuvan 2* pelitilanteessa voidaan siirtää palaa 2, 7, 10 tai 13.

Tehtäväpohjan tiedostossa `js/code.js` on kuvattu eräs, *Kuvan 3* kutsukaavion mukainen, design sovelluksen koodiksi. Tehtävän ratkaisussa voi noudattaa tätä periaatetta, mutta tarvittavan funktiokokonaisuuden voi muodostaa myös muulla tavalla. JavaScript koodin ohella myös tiedoston `css/styles.css` tyylistö kaipaa pientä täydennystä.

![Kutsukaavio](../img/kutsukaavio.png "Kutsukaavio"){: style="display: block; margin: auto; margin-top: 10px;"}

<small>Kuva 3.</small>

**Palauta** tehtävän ratkaisuna tiedostot `code.js` ja `styles.js`

### Vihjeitä ja lisätietoja

Pohjakoodin tiedostossa `index.html` on poiskommentoituna merkkaus, joka vastaa pelialueen tilaa sivun latauksen jälkeen. Kommentit voi avata, jos tarvittavan css-täydennyksen laatii ennen JavaScript-koodia.

Seuraavat [document][document] -objektin metodit saattavat olla ratkaisussa tarpeellisia: [createElement][createElement], [getElementById][getElementById] ja [querySelectorAll][querySelectorAll].
Myös [käyttöliittymäelementtien][Element] seuraavia metodeja ja ominaisuuksia voidaan tarvita: [appendChild][appendChild], [className][className], [firstElementChild][firstElementChild], [id][id], [nextElementSibling][nextElementSibling], [parentElement][parentElement], [style][style].left, [style][style].top ja [textContent][textContent].
Muita käyttökelpoisia apuneuvoja tässä voivat olla [parseInt][parseInt] sekä [Math][Math]-objektin [floor][floor] ja [random][random].

[document]: https://www.w3schools.com/jsref/dom_obj_document.asp
[createElement]: https://www.w3schools.com/jsref/met_document_createelement.asp
[getElementById]: https://www.w3schools.com/jsref/met_document_getelementbyid.asp
[querySelectorAll]: https://www.w3schools.com/jsref/met_document_queryselectorall.asp

[Element]: https://www.w3schools.com/jsref/dom_obj_all.asp
[appendChild]: https://www.w3schools.com/jsref/met_node_appendchild.asp
[className]: https://www.w3schools.com/jsref/prop_html_classname.asp
[firstElementChild]: https://www.w3schools.com/jsref/prop_element_firstelementchild.asp
[id]: https://www.w3schools.com/jsref/prop_html_id.asp
[nextElementSibling]: https://www.w3schools.com/jsref/prop_element_nextelementsibling.asp
[parentElement]: https://www.w3schools.com/jsref/prop_node_parentelement.asp
[style]: https://www.w3schools.com/jsref/prop_html_style.asp
[textContent]: https://www.w3schools.com/jsref/prop_node_textcontent.asp

[Math]: https://www.w3schools.com/jsref/jsref_obj_math.asp
[floor]: https://www.w3schools.com/jsref/jsref_floor.asp
[random]: https://www.w3schools.com/jsref/jsref_random.asp

[parseInt]: https://www.w3schools.com/jsref/jsref_parseint.asp


Tehtävän [lähteenä käytetty spesifikaatio][speksi] löytyy Moodlesta.

[speksi]: https://moodle2.tut.fi/mod/resource/view.php?id=319595


<br/><small>
Tehtävän lähde: Homework Assignment - Fifteen Puzzle.<br/>
[Web Programming][cse154], University of Washington, Computer Science & Engineering.<br/>
Copyright © Marty Stepp / Jessica Miller, licensed under Creative Commons Attribution 2.5 License.
</small>

<br/>

[cse154]:https://courses.cs.washington.edu/courses/cse154/

{% endcomment %}
