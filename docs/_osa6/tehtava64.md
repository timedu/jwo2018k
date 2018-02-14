---
layout: exercise_page
title: "Tehtävä 6.4: Liukupalapeli, vaihe 1 (3p)"
exercise_template_name: W6E04.Puzzle
exercise_discussion_id: 95294
exercise_upload_id: 374039
modified_at: 14.2.2018
---

> The Fifteen Puzzle (also called the Sliding Puzzle) is a simple classic game consisting of a 4×4 grid of numbered squares with one square missing. The object of the game is to arrange the tiles into numerical order by repeatedly sliding a square that neighbors the missing square into its empty space.

Laadi *jQuery:ä*  hyödyntävä koodi, joka muodostaa selaimessa toimivan
liukupalapelin elementit sivun latauksen yhteydessä:

![Liukupalapeli](../img/puzzle.png "Liukupalapeli"){: style="display: block;  margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1.</small>

Muodostettavat elementit vastaavat seuraavaa merkkausta:

{% highlight html %}

<div class="mt-5" id="game-area">
    <div class="d-flex flex-row justify-content-center">
        <div><div class="piece m-1">1</div></div>
        <div><div class="piece m-1">2</div></div>
        <div><div class="piece m-1">3</div></div>
        <div><div class="piece m-1">4</div></div>            
    </div>
    <div class="d-flex flex-row justify-content-center">
        <div><div class="piece m-1">5</div></div>
        <div><div class="piece m-1">6</div></div>
        <div><div class="piece m-1">7</div></div>
        <div><div class="piece m-1">8</div></div>            
    </div>
    <div class="d-flex flex-row justify-content-center">
        <div><div class="piece m-1">9</div></div>
        <div><div class="piece m-1">10</div></div>
        <div><div class="piece m-1">11</div></div>
        <div><div class="piece m-1 movable">12</div></div>            
    </div>
    <div class="d-flex flex-row justify-content-center">
        <div><div class="piece m-1">13</div></div>
        <div><div class="piece m-1">14</div></div>
        <div><div class="piece m-1 movable">15</div></div>
        <div><div id="empty" class="m-1"></div></div>            
    </div>
    <div class="d-flex flex-row justify-content-center mt-3">
        <button class="btn btn-secondary btn-lg">Suffle Pieces</button>
    </div>
</div>

{% endhighlight %}

<small>Listaus 1.</small>

*Listauksen 1* merkkauksessa esiintyvät `d-flex`, `flex-row`,
`justify-content-center`, `mt-5`,  `m-1`, `mt-3`, `btn`, `btn-secondary` ja
`btn-lg` ovat [Bootstrap][Bootstrap]-luokkia. Tunnisteet `game-area`, `piece`,
`movable` ja `empty` ovat sovelluksessa määriteltyjä (ks. tehtäväpohjan
`styles.css`).

[Bootstrap]: https://getbootstrap.com

Tehtäväpohjan tiedostossa `code.js` on funktiorunko `createGame`[^runko], johon koodin voi rakentaa.
Muodostettaessa elementtejä, *jQuery*-funktion parametrina tulee olla ainoastaan
yksittäinen html-elementti, esim. `$('<div/>')`. Koodissa tulisi käyttää myös
silmukkarakenteita.

[^runko]: Tehtäväpohjassa on myös muita funktiorunkoja, joita voi hyödyntää [seuraavan tehtävän](../tehtava65) ratkaisussa.

**Palauta** tehtävän ratkaisuna tiedosto `code.js`.

### Vihjeitä ja lisätietoja

Esim. seuraavat jQuery-metodit saattavat tukea tehtävän ratkaisussa:
[addClass][addClass], [attr][attr], [appendTo][appendTo], [text][text].

[addClass]: https://api.jquery.com/addClass/
[attr]: https://api.jquery.com/attr/
[appendTo]: https://api.jquery.com/appendTo/
[text]: https://api.jquery.com/text/


<br/>

<small>
Tehtävän lähde: Homework Assignment - Fifteen Puzzle.<br/>
[Web Programming][cse154], University of Washington, Computer Science & Engineering.<br/>
Copyright © Marty Stepp / Jessica Miller, licensed under Creative Commons Attribution 2.5 License.<br/>
(tehtävää muokattu)
</small>

<br/>

[cse154]:https://courses.cs.washington.edu/courses/cse154/
