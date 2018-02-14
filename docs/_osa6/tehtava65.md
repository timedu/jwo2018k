---
layout: exercise_page
title: "Tehtävä 6.5: Liukupalapeli, vaihe 2 (3p)"
exercise_template_name: # (edellinen tehtävä)
exercise_discussion_id: 95295
exercise_upload_id: 374040
modified_at: 15.2.2018
---

Täydennä [edellisen tehtävän](../tehtava64) ratkaisua siten, että pelialueella olevat palat
voi sekoittaa ja yksittäisen palan voi siirtää sen vieressä olevaan tyhjään
paikkaan.

![Liukupalapeli](../img/puzzle-suffled.png "Liukupalapeli"){: style="display: block;  margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1.</small>

*Kuva 1* esittää tilannetta, jossa pelin alussa on klikkattu
*Suffle Pieces* -painiketta. Kuvan pelitilanteessa voidaan siirtää paloja
2, 7, 12 tai 15.  Kun hiiren kursori on siirrettävissä olevan palan yläpuolella,
kursorin muoto on *pointer*, ja palan numero esitetään valkoisella. Tämän
aikaansaamiseksi, siirrettävissä oleville paloille tulee asettaa luokka `movable`
(ks.`styles.css`).

Tässä jatketaan [edellisen tehtävän](../tehtava64) pohjan täydentämistä.
Tehtäväpohjassa on eräs mahdollinen funktiorakenne. Ratkaisussa voi noudattaa
tätä periaatetta, mutta tarvittavan funktiokokonaisuuden voi muodostaa
myös muulla tavalla.

**Palauta** tehtävän ratkaisuna tiedosto `code.js`.

### Vihjeitä ja lisätietoja

Seuraavat jQuery tarjoamat apuvälineet voivat olla hyödyllisiä:
[addClass][addClass],
[data][data],
[click][click],
[each][each],
[insertAfter][insertAfter],
[length][length],
[parent][parent],
[replaceWith][replaceWith],
[removeClass][removeClass].

[addClass]: https://api.jquery.com/addClass/
[data]: https://api.jquery.com/data/
[click]: https://api.jquery.com/click/
[each]: https://api.jquery.com/each/
[insertAfter]: https://api.jquery.com/insertAfter/
[length]: https://api.jquery.com/length/
[parent]: https://api.jquery.com/parent/
[replaceWith]: https://api.jquery.com/replaceWith/
[removeClass]: https://api.jquery.com/removeClass/

Muita käyttökelpoisia apuneuvoja tässä voivat olla [parseInt][parseInt] sekä [Math][Math]-objektin [abs][abs], [floor][floor] ja [random][random].

[Math]: https://www.w3schools.com/jsref/jsref_obj_math.asp
[abs]: https://www.w3schools.com/jsref/jsref_abs.asp
[floor]: https://www.w3schools.com/jsref/jsref_floor.asp
[random]: https://www.w3schools.com/jsref/jsref_random.asp
[parseInt]: https://www.w3schools.com/jsref/jsref_parseint.asp

<br/>

<small>
Tehtävän lähde: Homework Assignment - Fifteen Puzzle.<br/>
[Web Programming][cse154], University of Washington, Computer Science & Engineering.<br/>
Copyright © Marty Stepp / Jessica Miller, licensed under Creative Commons Attribution 2.5 License.<br/>
(alkuperäistä tehtävää on muokattu)
</small>

[cse154]:https://courses.cs.washington.edu/courses/cse154/
