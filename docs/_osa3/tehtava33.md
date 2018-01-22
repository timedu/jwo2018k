---
layout: exercise_page
title: "Tehtävä 3.3: BaseMOOC (2p)"
exercise_template_name: W3E03.BaseMOOC
exercise_discussion_id: 92461
exercise_upload_id: 370646
modified_at: 22.1.2018
---

[Tehtävässä 2.3](../../osa2/tehtava23) rakennettiin  hieman *Kuvan 1*  näkymää
muistuttava kurssisivu CSS:ää ja JavaScript:ia käyttäen. Tässä tehtävässä
kuvan kaltainen sivu rakennetaan [Bootstrap][Bootstrap]-kirjaston tuella.

[Bootstrap]: http://getbootstrap.com

![BaseMOOC](../img/basemooc.png "BaseMOOC"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. BaseMOOC.</small>

Sivun yläosassa on [Tehtävää 3.1](../tehtava31) vastaava navigointipalkki
kuitenkin niin, että sen väritys on hieman toisenlainen. Tässä palkki sisältää
myös linkkejä, joiden klikkaus tosin ei saa mitään havaittavaa aikaan. Klikkaus
tuottaa selaimeen juuri esillä olevan sivun.

Sivun alareunassa on [Tehtävää 3.1](../tehtava31) vastaava alatunniste
("footer"). Tässä alatunniste kuitenkin pysyy ikkunan alareunassa siten,
että se ei liiku sivua ylös tai alas vieritettäessä.

Sivun keskellä on neljä välilehden ryhmä, joista ensimmäinen on esillä.
Välilehti saadaan esiin vastaavaa linkkiä klikkaamalla.

Tee tarvittavat muutokset tiedostoon `index.html`. **Palauta** se, kun sivu
toimii odotetusti ja läpäisee tehtäväpohjan sisältämät testit. Tehtävän
ratkaisu ei edellytä JavaScript-koodin laatimista.

### Vihjeitä ja lisätietoja

Tehtäväpohjassa on seuraavat viisi testijoukkoa, joista ensimmäisen
pitäisi mennä läpi ilman mitään muutoksia:

1. Lähtökohta
  - sivulla on 1 nav-elementti
  - sivulla on 7 a-elementtiä
  - sivulla on 2 ul-elementtiä
  - sivulla on 6 li-elementtiä
  - sivulla on 11 div-elementtiä
  - sivulla on 4 h4-elementtiä
  - sivulla on 1 footer-elementti
  - sivulla on 1 small-elementti
2. Yläosan navigointipalkki
  - valikolla on luokka "navbar-nav"
  - valinnoilla on luokka "nav-item"
  - valintojen linkeillä on luokka "nav-link"
  - navigointipalkilla on luokat "navbar-dark" ja "bg-dark"
  - navigointipalkilla on luokat "navbar-expand-sm" ja "justify-content-between"
3. Välilehtien navigointipalkki
  - valikolla on luokat "nav" ja "nav-tabs"
  - valinnoilla on luokka "nav-item"
  - valintojen linkeillä on luokka "nav-link"
  - yksi linkeistä on aktiivinen (active)
  - aktiivinen on linkeistä ensimäinen
  - valintojen linkeillä on "data-toggle"-attribuutti
4. Välilehdet
  - välilehtiryhmällä on luokka "tab-content"
  - välilehdillä on luokka "tab-pane"
  - ensimmäinen välilehdistä on esillä ja aktiivinen (show, active)
5. Alatunniste (footer)
  - alatunniste on sijoitettu selain-ikkunan alareunaan
  - alatunnisteen yläpuolinen osa raamista on näkyvissä mutta alapuolinen ei ole

*Testijoukkoihin 2-4* liittyviin ongelmiin löytynee vihjeitä itse testien
lisäksi Bootstrap-dokumentaation kohdista [Navs][Navs] ja [Navbar][Navbar].
*Testijoukon 5* osalta voi tarvittaessa silmäillä kohtia
[Borders][Borders] ja [Position][Position].

[Navs]: http://getbootstrap.com/docs/4.0/components/navs/
[Navbar]: http://getbootstrap.com/docs/4.0/components/navbar/
[Borders]: https://getbootstrap.com/docs/4.0/utilities/borders/
[Position]: https://getbootstrap.com/docs/4.0/utilities/position/
