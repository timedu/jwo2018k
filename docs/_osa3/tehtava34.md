---
layout: exercise_page
title: "Tehtävä 3.4: Taskit (2p)"
exercise_template_name: W3E04.Taskit
exercise_discussion_id: 92462
exercise_upload_id: 370647
modified_at: 2.2.2018
---

Tehtäväpohjassa on käyttöliittymältään oheisen kuvan mukainen tehtävien
hallintaan tarkoitettu sovellus. Tiedostossa määritelty `index.html`
käyttöliittymä perustuu [Bootstrap][Bootstrap] -kirjastoon. Tiedostossa
`code/code-JavaScript.js` oleva soveluslogiikka on laadittu
"perus-JavaScriptilla".

[Bootstrap]: http://getbootstrap.com

Laadi perus-JavaScriptia vastaava [jQuery][jQuery]-toteutus tiedostoon
`code/code-jQuery.js`.

[jQuery]: http://jquery.com


![taskit](../img/taskit.png "taskit"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Taskit.</small>

Tutustu ensin sovelluksen toimintaan sitä ajamalla. Muokkaa sitten
tiedostoa `index.html` niin, että se käyttää kooditiedostoa `code/code-jQuery.js`
tiedoston `code/code-JavaScript.js` sijaan vaihtaen hieman kommenttimerkkien
paikkaa:

{% highlight html %}

...
<!--<script src="./js/code-JavaScript.js"></script>-->
<script src="./js/code-jQuery.js"></script>
...

{% endhighlight %}

Käytä *jQuery:ä* siten, että sen avulla tapahtuu dokumentissa olevien elementtien
paikannus, click-tapahtumien käsittelijöiden rekisteröinti sekä dokumentin
muokkaaminen. Älä talleta muuttujiin viiteitä dokumentin elementteihin.

**Palauta** tehtävästä tiedosto `code/code-jQuery.js`, kun sovellus toimii
odotetusti jQuery-perustaisena ratkaisua.


### Vihjeitä ja lisätietoja

Ratkaisussa saatetaan tarvita esim. seuraavia jQuery-metodeja:
[addClass](http://api.jquery.com/addClass/),
[appendTo](http://api.jquery.com/appendTo/),
[click](http://api.jquery.com/click/),
[remove](http://api.jquery.com/remove/),
[text](http://api.jquery.com/text/),
[toggleClass](http://api.jquery.com/toggleClass/),
[val](http://api.jquery.com/val/),
[has](http://api.jquery.com/has/),
[length](http://api.jquery.com/length/).
