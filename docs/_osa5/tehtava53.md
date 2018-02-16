---
layout: exercise_page
title: "Tehtävä 5.3: VatsList (2p)"
exercise_template_name: W5E03.VatsList
exercise_discussion_id: 94005
exercise_upload_id: 372707
modified_at: 15.2.2018
---

Tehtäväpohjassa on hieman keskeneräiseksi jäänyt, lyhyt-viestien esittämiseen
tarkoitettu, sovellus. Täydennä sovellusta siten, että se lukee viestit *SQLite*-
tietokannasta ja toimii ulospäin *kuvien 1-3* mukaisesti.

![Viestit](../img/vats_list.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Viestiluettelo - kirjautuneena *Bart*.</small>

Sivu esittää luettelon kaikista tietokannan sisältämistä viesteistä siten, että
viimeisin viesti esitetään aina ylimpänä. Sovelluksen käyttäjän nimi esitetään
sivun oikeassa yläkulmassa (*Kuvassa 1* "Bart").

Viestien leveys on 11/12 osaa sisältöalueen kokonaisleveydestä. Kirjautuneen
käyttäjän viestit esitetään harmaalla pohjalla vasemmalle tasattuna kun taas
muiden lähettämät viestit keltaisella pohjalla oikealle tasattuna. Jokaisen
viestin yläpuolella on viestin lähetyspäivä. Koskien viestejä, joita ei ole
lähettävyt kirjautunut käyttäjä, viestin yläpuolella on myös lähettäjän
nimi.

*Kuva 2* esittää tilannetta, jossa sovellukseen ei ole kirjauduttu. Tällöin
kaikki viestit näkyvät keltaisella pohjalla.

![Viestit](../img/vats_list_anon.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Viestiluettelo - ei kirjauduttu.</small>

Kirjautuminen sovellukseen tehdään klikkaamalla sivun oikeassa yläkulmassa
olevaa *login* -linkkiä, jonka jälkee sivulle ilmestyy *Change Login User* -ikkuna (*Kuva 3*).
Sovellus tallettaa aktiivisen käyttäjän nimen istuntokohtaiseen
[evästeeseen](https://fi.wikipedia.org/wiki/Eväste) nimellä *login-user*.


![Viestit](../img/vatsi_login.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 3. Kirjauminen.</small>

Tehtäväpohjassa oleva sovellus tuottaa selaimeen juureen tehdyllä pyynnöllä *Kuvan 4*
mukaisen sivun, joka esittää *vakiotietoja* ja niitäkin hieman puutteellisesti:
*viestien sisällöt* eivät tule näkyviin ja "keltaisen viestin" yläpuolelta puuttuu
*lähettäjän nimi*.


![Viestit](../img/vats_list_pohja.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 4. Viestiluettelo tehtäväpohjassa.</small>

Ratkaise tehtävä täydentämällä tehtäväpohjan tiedostoja `vatsi.js` ja `messages.html`,
ja **palauta** ne, kun sovellus toimii odotetusti.


### Vihjeitä ja lisätietoja

Tietokanta tässä on aivan samarakenteinen kuin [Tehtävässä 5.1](../tehtava51).
Tietokannan  voi kopioida tuon tehtävän rakaisusta sellaisenaan tehtäväpohjan
`data`-hakemistoon. Pohjassa on apufuntio `success`, jota voi käyttää
tutkittaessa, onko tietokantakäsittely sujunut onnistuneesti. Virhetilanteen
voi hoitaa tässä siten, että selaimelle välitetään esitettäväksi (em. funktion
tuella) virhetilannetta kuvaava objekti muunnettuna merkkijonoksi.

Kirjautumiseen liittyvät toiminnot ovat tehtäväpohjassa valmiina (mm. evästeen kirjoitus),
mutta aktiivisen käyttäjän nimi on välitettävä evästeestä näkymälle. Evästeet
löytyvät *Request*-objektin [cookies][cookies] -ominaisuudesta. Koska evästeen nimessä
on tässä `-`-merkki, evästeen arvo on luettava taulukkotyyppisellä viittauksella
`req.cookies['user-name']`. Pohjassa on `clean`-apufunktio, jolla selaimelta
saadun evästeen voi "puhdistaa" ennen tiedon välittämistä näkymälle.

[cookies]: https://expressjs.com/en/4x/api.html#req.cookies

#### Tehtävän ratkaisun vaiheet

Tehtävän ratkaisun voi toteuttaa esim. seuraavien vaiheiden kautta.

**1. Lähtökohta**

Lataa tehtäväpohja ja ratkaise projektin riippuvuudet ulkopuolisista
moduuleista ("npm install"). Käynnistä sitten sovellus NetBeans:issa ja
mene selaimella osoitteeseen `localhost:3000/`. Jos kaikki on kunnossa,
selaimen ikkunaan pitäisi ilmestyä *Kuvan 4* mukainen sivu.

Pyyntöön vastaamiseen liittyvä koodi on tiedostossa `vatsi.list`:

{% highlight js %}

app.get('/', function (req, res) {
    res.redirect('/list');
});

app.get('/list', function (req, res) {
    ...
    res.render('messages', {
        viestit: viestit,
        loginUser: loginUser
    });
});

{% endhighlight %}

<small>Listaus 1.</small>

Edellä *Listauksessa 1*  on esitetty, että pyyntö polkuun `/` ohjaa ("redirect")
selaimen
tekemään toisen pyynnön polkuun `/list`, johon liitetty funktio hahmontaa ("render") näkymän
välittäen sille  muodostettavalle sivulle sijoitettavan datan
(`viestit`, `loginUser`).

**2. Näkymän täydentäminen**

Tehtäväpohjassa näkymälle välitetään vakiotietoja:  

{% highlight js %}

    ...
    const viestit = [
        {
            id: 20,
            lahettaja: 'lahettaja2',
            sanoma: 'sanoma2',
            aika: '2000-02-02'
        },
        {
            id: 10,
            lahettaja: 'lahettaja1',
            sanoma: 'sanoma1',
            aika: '1000-01-01'
        }
    ];
    const loginUser = 'lahettaja1';
    ...

});

{% endhighlight %}

<small>Listaus 2.</small>

*Listauksen 2* datalla selaimessa olevan sivun tulisi näyttää seuraavalta:


![Viestit](../img/vats_list_v2.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 5. Viestiluettelo pohjan vakiodatalla, kun näkymään on tehty ratkaisun edellyttämät muutokset.</small>

**3. Aktiivisen käyttäjän välittäminen näkymälle**

Tehtäväpohjasta poimitusta *Listauksessa 2* näkymälle välitettävälle muuttujalle
`loginUser` asetetaan vakio-arvo. Ratkaisu kuitenkin edellyttää sitä, että
näkymälle välitetään selaimelta pyynnön yhteydessä saatavan evästeen *login-user*
arvo (ks. tämän kohdan alku). Kun tämä on toteutettu, aktiivisen käyttäjän muutos
vaikuttaa sivun ulkoasuun.


![Viestit](../img/vats_list_v3.png "Viestit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 6. Viestiluettelo pohjan vakiodatalla, kun aktiivinen käyttäjä vaihdettu.</small>


*Kuva 6* esittää tilannetta, jossa aktiiviseksi käyttäjäksi on asettettu `lahettaja2`.


**4. Viestien luku tietokannasta**

Kopioi tietokanta `viestikanta.db` (esim.) [Tehtävän 5.1](../tehtava51) ratkaisusta
projektin `data`-kansioon ja korvaa
vakion `viestit` asetus (*Listaus 2*) tietokantakyselyllä, joka tuli laatia
osaksi [Tehtävän 5.1](../tehtava51) ratkaisua. Muutoksen jälkeen sivun tulisi
esittää vakiotietojen sijaan ao. tietokannan sisältämät viestit.
