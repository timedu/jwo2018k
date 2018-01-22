---
layout: exercise_page
title: "Tehtävä 3.2: Laskin (2p)"
exercise_template_name: W3E02.Laskin
exercise_discussion_id: 92459
exercise_upload_id: 370645
modified_at: 22.1.2018
---

[Tehtävässä 2.2](../../osa2/tehtava22) rakennettiin yksinkertainen nelilaskin.
Laadi toiminoiltaan vastaavanlainen mutta [Bootstrap][Bootstrap]- ja
[jQuery][jQuery] -kirjastoja hyödyntävä laskin,
jonka ulkoasu selaimessa on *Kuvan 1* kaltainen.

[Bootstrap]: http://getbootstrap.com
[jQuery]: http://jquery.com

![Laskin](../img/laskin.png "Laskin"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Laskin.</small>

Sivun latauksen jälkeen esillä on ainoastaan *Laskin-painike*, jota klikkaamalla
*Laskin-ikkuna* tulee näkyviin.

Tehtäväpohjassa oleva koodi toteuttaa jo laskennan, mutta ulkoasu ei ole
vielä halutun kaltainen. Laskennan yhteydessäkään ei vielä hyödynnetä *jQuery*-
kirjastoa kuten tehtävä edellyttää.

Muokkaa tiedostoja `index.html` ja `js/code.js`. **Palauta** ne, kun sovellus
toimii odotetusti ja läpäisee tehtäväpohjan sisältämät testit.

### Vihjeitä ja lisätietoja

Tehtäväpohjassa on seuraavat kuusi testijoukkoa, joista kahden ensimmäisen
(*Lähtökohta*, *Laskenta*)
pitäisi mennä läpi ilman, että tiedostoihin tehdään mitään muutoksia:

1. Lähtökohta
  - sivulla 13 div-elementtiä
  - sivulla 6 button-elementtiä
  - sivulla 3 input-elementtiä
  - sivulla 1 h5-elementti
  - sivulla "container-fluid"
  - "container-fluid" sisältää 2 riviä (row)
  - rivit sisältävät yhteensä 4 saraketta (col-sm)
2. Laskenta
  - Yhteenlasku ok
  - Vähennyslasku ok
  - Kertolasku ok
  - Jakolasku ok
3. Dialogi-ikkunan rakenne
  - sivulla oikein sijoitettuna "modal"
  - sivulla oikein sijoitettuna "modal-dialog"
  - sivulla oikein sijoitettuna "modal-content"
  - sivulla oikein sijoitettuna "modal-header"
  - sivulla oikein sijoitettuna "modal-body"
  - sivulla oikein sijoitettuna "modal-title"
4. Dialogi-ikkunan avaaminen ja sulkeminen
  - Laskin-napilla avaamisen edellyttämät attribuutit (data-toggle, data-target)
  - Dialogin sulkemisnapilla sitä muoteileva luokka (close)
  - Dialogin sulkemisnapilla sulkemisen edellyttämä attribuutti (data-dismiss)
5. Dialogin sisältämät lomake-elementit
  - Riveille asetettu luokka "form-group"
  - input-elementteille asetettu luokka "form-control"
  - Laskentapainikkeille asetettu luokat "btn" ja "btn-secondary"
  - Laskentapainikkeet asetetty "btn-group"-elementin (div) sisällöksi
6. jQuery:n käyttö laskennan yhteydessä
  - plus-painikkeen click-käsittelijä määritelty jQuery:llä
  - miinus-painikkeen click-käsittelijä määritelty jQuery:llä
  - kerto-painikkeen click-käsittelijä määritelty jQuery:llä
  - jako-painikkeen click-käsittelijä määritelty jQuery:llä
  - text-metodia käytetty kerran
  - val-metodia käytetty 3 kertaa
  - val-metodia käytetty tuloksen esittämisessä

*Testijoukot 3 ja 4* liittyvät Bootstrapin [Modal][modal]-komponentin
soveltamiseen. Komponentin [dokumentaatiosta][modal] löytyy esimerkejä,
joiden perusteella tämä osa tehtävästä saataneen ratkaistuksi.
*Testijoukko 5* kohdistuu dialogi-ikkunassa oleviin laskennan "widgetteihin"
(ks. [Forms][forms]- ja [Button group][button-group]-komponentit).
*Testijoukko 6* edellyttää *jQuery*-objektin [click][click]-, [text][text]- ja [val][val]-metodien käyttöä. Esim. Helsingin materiaalista löytyy lyhyt [jQuery-esittely][weso-jquery].

[modal]: http://getbootstrap.com/docs/4.0/components/modal/

[forms]: http://getbootstrap.com/docs/4.0/components/forms/
[button-group]: http://getbootstrap.com/docs/4.0/components/button-group/

[click]: http://api.jquery.com/click/
[text]: http://api.jquery.com/text/
[val]: http://api.jquery.com/val/

[weso-jquery]: http://web-selainohjelmointi.github.io/#10.1-jQuery
