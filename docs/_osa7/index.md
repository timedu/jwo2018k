---
layout: collection_index
permalink: /:collection/index.html
---

Tämän osan muodostaa tehtäväsarja, jossa rakennetaan tietokantapohjainen
toteutus jo [Tehtävässä 3.4](../osa3/tehtava34) esillä olleesta *Tehtävälista* -sovelluksesta.

![Tehtävälista](./img/taskit.png "Tehtävälista"){: style="display: block;  margin: auto; margin-top: 10px; width: 500px;"}

<small>Kuva 1.</small>

Selaimen ja palvelimen välinen kommunikointi tässä tapahtuu samalla
periaatteella kuin [Tehtävän 4.4](../osa4/tehtava44) *Ajax-laskimessa*:
palvelimella suoritettavan operaation jälkeen sivua ei ladata uudelleen,
vaan sivua muokataan selaimessa operaation tuloksen edellyttämällä tavalla.

Sovellukseen sisältyy Tehtävien [5.3](../osa5/tehtava53),
[5.4](../osa5/tehtava54) ja [5.5](../osa5/tehtava55) viestisovelluksen tapaan
myös kirjautuminen, mutta nyt sen toteutusperiaate on toinen: tietoja selaimille
kirjautuneista käyttäjistä ylläpidetään palvelipäässä ns. istunnoissa siten,
että selainpäähän talletettavassa evästeessä on ainoastaan ao. istunnon tunnus.

### Tehtävät

Osaan sisältyy viisi tehtävää, joiden suorittamisen myötä sovellukseen
rakentuu tarvittava tietokantakäsittely. Suurin osa sovelluksen edellyttämästä
koodista on pohjassa kuitenkin valmiina.

{% include exercises_list.md %}

[Tehtävässä 7.1](tehtava71) rakennetaan alustava kommunikointi
tietokantakäsittelyyn liittyvien selaimen ja
palvelimen moduulien välille. [Tehtävän 7.2](tehtava72) ratkaisu lukee
tietokannasta kirjautuneen käyttäjän omistuksessa olevat tehtävät ja
muodostaa niitä vastaavat elementit selaimen esittämään dokumenttiin.
[Tehtävässä 7.3](tehtava73) rakennetaan toiminto, jolla tietokantaan voidaan
lisätä uusia tehtäviä. [Tehtävässä 7.4](tehtava74) toiminnallisuutta laajennetaan
niin, että selaimen esittämien tehtävien statusta (*ei tehty/tehty*) voidaan
muuttaa. [Tehtävän 7.5](tehtava75) ratkaisun toiminnolla tietokannasta voidaan
poistaa kirjautuneen käyttäjän valmiiksi merkityt tehtävät.
