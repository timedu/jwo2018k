---
layout: exercise_page
title: "Tehtävä 4.3: Handlebars-laskin (2p)"
exercise_template_name: W4E03.HandlebarsLaskin
exercise_discussion_id: 93297
exercise_upload_id: 371622
modified_at: 29.1.2018
---

[Tehtävässä 3.2](../../osa3/tehtava32) rakennettiin selaimen päässä
ajettava nelilaskin. Nyt laaditaan käyttöliittymältään likimain samanlainen
laskin, mutta sen taustalla oleva arkkitehtuuri on erilainen.

![Laskin](../img/handlebars_laskin.png "Laskin"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 1. Handlebars-laskin.</small>

Laskimen käyttöliittymän merkkaus sisältää lomakkeen. Klikattaessa jotakin
laskimen painikkeista, lomake välittää tiedot laskutoimituksesta palvelimelle.
Palvelin suorittaa laskennan ja palauttaa selaimelle sivun, joka sisältää
laskutoimituksen operandit sekä lasketun lausekkeen tuloksen kera (*Kuva 1*).

Tehtävä ratkaistaan[^1] täydentämällä tiedostoja `laskin.html` ja `laskuri.js`.
**Palauta** tiedostot, kun laskin toimii odotetusti.

[^1]: Kuten [edellisessä tehtävässä](../tehtava42) myös tässä, sovelluksen toiminta edellyttää ulkopuolisia moduuleja, jotka voidaan ladata komennolla/menuvalinnalla `npm install`.  

### Vihjeitä ja lisätietoja

Laskin vastaa sovelluksen juuressa (`/`) saaden tiedot laskutoimituksesta aivan
samoin kuin [edellisen tehtävän](../tehtava42) laskimen versio 1. Nyt palvelu
ei kuitenkaan palauta selaimelle pelkkää laskennan tulosta vaan html-sivun,
joka muodostetaan *Handlebars*-templaten avulla.

Tehtäväpohjassa on templaten käyttöön liittyvä esimerkki. Seuraavanlainen sivu
tulee esiin, kun sovelluksen ollessa käynnissä polkuun `/hello` tehdään pyyntö.

![Testisivu](../img/testisivu.png "Testisivu"){: style="display: block; margin: auto; margin-top: 10px; width: 600px;"}

<small>Kuva 2. Testisivu.</small>

Template on html-sivu (*Listaus 1*), johon on merkitty paikkoja tiedoille, tässä:
`{% raw %}{{message}}{% endraw %}`.

{% highlight html %}
{% raw %}

<!DOCTYPE html>
<html>
    <head>
        <title>Hello page</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    <body>
        <h2>{{message}}</h2>
    </body>
</html>

{% endraw %}
{% endhighlight %}

<small>Listaus 1. Testisivun merkkaus (*hello.html*).</small>

Template ja siihen liittyvän datan määrittelemä html-sivu palautetaan selaimelle kutsumalla *Response*-objektin `render`-metodia (*Listaus 2*).


{% highlight js %}

...

app.get('/hello', function (req, res) {
    res.render('hello', {message: "Test page"});
});

...

{% endhighlight %}

<small>Listaus 2. *render*-metodin kutsu (*laskuri.js*).</small>

Tehtäväpohjassa täydennettävänä olevasta templatesta (`tilaus.html`) puuttuu
ainoastaan paikkkojen merkintä laskutoimitukseen liittyville tiedoille.

<br/>

Alaviitteet
