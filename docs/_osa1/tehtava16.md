---
layout: exercise_page
title: "Tehtävä 1.6: Tilauslomake (1p)"
exercise_template_name: W1E06.Tilauslomake
exercise_discussion_id: 91530
exercise_upload_id: 364644
modified_at: 9.1.2018
---


Muokkaa tehtäväpohjassa olevaa sivua `index.html` siten, että se näyttää selaimessa seuraavalta:

---

![Form](../img/form-empty.png "Form"){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

---
<small>Kuva 1. Täyttämätön lomake.</small>

Sivu sisältää yksinkertaisen tilauslomakkeen, joka on esitetty täyttämättömänä *Kuvassa 1* ja täytettynä *Kuvassa 2*.   


---

![Form](../img/form-filled.png "Form"){: style="display: block; margin: auto; margin-top: 10px; width: 350px;"}

---
<small>Kuva 2. Lomake täytettynä.</small>

Kun käyttäjä klikkaa lomakkeessa olevaa *Lähetä* -painiketta lomakkeen tiedot välitetään osoitteeseen `http://jkorpela.fi/cgi-bin/echo.cgi`[^echo], joka palauttaa selaimelle palvelimen vastaanottaman datan siten,
että selain esittää sen *Kuvan 3* kaltaisena.

[^echo]: Lähde: <http://jkorpela.fi/forms/testing.html>

---

![Form](../img/form-reply.png "Form"){: style="display: block; margin: auto; margin-top: 10px; width: 450px;"}

---
<small>Kuva 3. Lomakkeen vastaanottavan palvelun antama vaste.</small>


**Palauta** tehtävästä tiedosto `index.html`. Varmista ennen palautusta,
että lomake toimii edellä esitetyllä tavalla. Tehtäväpohjassa ei ole
erillistä testaussivua.


Vihjeitä: [form][form], [input][input], [textarea][textarea], [action][action],
[type][type], [name][name], [value][value], [placeholder][placeholder].

[form]: https://www.w3schools.com/tags/tag_form.asp
[input]: https://www.w3schools.com/tags/tag_input.asp
[textarea]: https://www.w3schools.com/tags/tag_textarea.asp
[action]: https://www.w3schools.com/tags/att_form_action.asp
[type]: https://www.w3schools.com/tags/att_input_type.asp
[placeholder]: https://www.w3schools.com/tags/att_input_placeholder.asp
[name]: https://www.w3schools.com/tags/att_input_name.asp
[value]: https://www.w3schools.com/tags/att_input_value.asp

<br/>

Alaviitteet
