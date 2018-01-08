---
layout: collection_index
permalink: /:collection/index.html
kesken: 1
---

JWO2018k / Osa 3

[jQuery](https://jquery.com),
[Bootstrap](http://getbootstrap.com)

{% comment %}

Opintojakson edellisten osien teemat käsittelivät tekniikoita (HTML, CSS, JavaScript), jotka tulkitaan web-selaimessa. Tässä osassa fokus siirtyy palvelinpäähän. Esillä on ehkä yleisin palvelinpään web-ohjelmointikieli, [PHP][PHP]. Samaa teemaa jatketaan vielä [seuraavassakin osassa](../osa4).

[PHP]: http://php.net

Tämän osa aineisto löytyy Viope-oppimisympäristön kurssilta *PHP-ohjelmoinnin perusteet (JWO2017k)*, jolle voi rekisteröityä [Moodlesta löytyvän linkin][viope] kautta. Materiaali sisältää joukon ohjelmointitehtäviä sekä niihin liittyviä teoriasivuja. Tämä osa käsittelee PHP:n näkökulmasta yleisiä ohjelmointiin liittyviä asioita kuten *muuttujat*, *ohjausrakenteet*, *lausekkeet* ja *taulukot* sekä sitä, miten PHP-koodi liitetään HTML-sivulle.

[viope]: https://moodle2.tut.fi/mod/url/view.php?id=315284

<hr/>
<small>
[Tehtäväpohjat](https://moodle2.tut.fi/mod/folder/view.php?id=317111) &nbsp;
[Keskustelu](https://moodle2.tut.fi/mod/forum/view.php?id=317112) &nbsp;
[Katselmointipyyntö](https://moodle2.tut.fi/mod/url/view.php?id=314337) &nbsp;
[Palautus katselmointiin](https://moodle2.tut.fi/mod/vpl/view.php?id=317152)
</small>

### Tehtävät

Osa sisältää 15 lyhyttä ohjelmointitehtävää, jotka ovat pisteytyksen näkökulmasta keskenään samanarvoisia. Viopen kurssi on avoinna tehtävien ratkaisemista varten 31.3.2017 asti. Luontevinta lienee ratkaista tehtävät Viopen omalla editorilla. Viope myös testaa ratkaisut automaattisesti.

Tukena voi halutessaan käyttää myös NetBeans IDE:ä, joka ohjaa tulosta syntaksin osalta oikeaan suuntaan. NetBeansissa on PHP-sovelluksia varten oma projektityyppinsä, *PHP Application*. Sovelluksen ajo kuitenkin edellyttää sitä, että ympäristöstä löytyy PHP-tulkki, jonka uudemmat versiot kykenevät toimimaan myös web-palvelimena.

NetBeans-projektille on kerrottava, minkälaista web-palvelinta käytetään sovellusta ajettaessa IDE:stä käsin. Jos tukeudutaan PHP-tulkin sisältämään palvelimeen, valinta on *PHP Built-in Web Server*. NetBeansin on myös tiedettävä, missä PHP-tulkki sijaitsee kehityslaitteessa. Luokkakoneissa sen polkunimi on `C:\Apps\PHP\PHP5.6\php.exe`. Omaan Windows-kehitysympäristöön tulkin voi ladata osoitteesta <http://windows.php.net/download>.

### Lisätietoja

Kattava esitys PHP:stä on sen [käsikirjasta][manual]. Myös W3Schools-sivustolla aiheesta on oma [osionsa][w3schools-php]. Ohjelmointiputkasta löytyy suomenkielinen [PHP-opas][putka-php].

[manual]: http://php.net/manual/en/
[w3schools-php]: https://www.w3schools.com/php/default.asp
[putka-php]: http://www.ohjelmointiputka.net/oppaat/opas.php?tunnus=php_01

Jos PHP-sovelluksia laatii NetBeansilla, niin seuraavaa funktiota voidaan käyttää virheiden jäljityksessä:

{% highlight php %}

    <?php
    function debug($data) {
        error_log(print_r($data, TRUE));
    }

{% endhighlight %}

Funktio tulostaa parametrinsa NetBeansin *Output*-ikunaan. Rakenteinenkin muuttaja saadaan tällä esille luettavassa muodossa.


{% endcomment %}
