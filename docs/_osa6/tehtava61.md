---
layout: exercise_page
title: "Tehtävä 6.1: Elokuva-arviot, vaihe 1 (3p)"
exercise_template_name: # (Moodlessa)
exercise_discussion_id: 94967
exercise_upload_id: 373508
modified_at: 12.2.2018
---

Lisää [tehtäväpohjan][pohja][^pohja] tiedostoon `tmnt.html` tarvittavat [Bootstrap][Bootstrap]-luokat
sekä pohjan tiedostossa `css/styles.css` määritellyt css-luokat siten, että
sivun ulkoasu selaimessa on *Kuvien 1-3* mukainen.

[pohja]: https://moodle2.tut.fi/mod/resource/view.php?id=373505
[^pohja]: Tämän tehtävän [pohjakoodi][pohja] on Moodlessa.
[Bootstrap]: https://getbootstrap.com

{% assign spacer = '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;' %}

{{spacer}} Kuva 1.
[Sivun yläosa](https://moodle2.tut.fi/mod/resource/view.php?id=373489)   
{{spacer}} Kuva 2.
[Sivun alaosa](https://moodle2.tut.fi/mod/resource/view.php?id=373490)   
{{spacer}} Kuva 3.
[Sivu pieninäyttöisellä laitteella](https://moodle2.tut.fi/mod/resource/view.php?id=373491)


**Palauta** tehtävän ratkaisuna tiedosto `tmnt.html`. Tiedostoon ei ole tarkoitus
lisätä `style`-elementtejä eikä `style`-attribuutteja.

### Vihjeitä ja lisätietoja

Aiemmassa [Tehtävässä 3.1](../../osa3/tehtava31) ratkaistiin vastaavanlainen
ongelma. Tuon tehtävän tapaan myös tässä tehtävän voi ratkaista askelittain.

#### 1. Layout

Liikkeelle voi lähteä [layoutista][layout] so. sijoittaa merkkaukseen Bootstrap:in
gridin muodostavat luokat. Sarakkeista tässä voi käyttää "small"-versioita.
*Kuvien 4 ja 5* peruslayoutin rakentamiseen tässä pärjättäneen luokilla
`container`, `row`, `col-sm`, `col-sm-2`, `col-sm-4` ja `col-sm-8`.

[layout]: https://getbootstrap.com/docs/4.0/layout/overview/

{{spacer}} Kuva 4.
[Sivun yläosa](https://moodle2.tut.fi/mod/resource/view.php?id=373522)  
{{spacer}} Kuva 5.
[Sivun alaosa](https://moodle2.tut.fi/mod/resource/view.php?id=373523)

*Kuvien 1 ja 2* perusteella voidaan kuitenkin todeta, että sivua vieritettäessä,
sivulla olevien ylä- ja alapalkkien tulisi pysyä paikoillaan. Tämä ongelma
ratkennee elementtien sijaintia määrittelevien [apuluokkien][position] tuella
(`fixed-top`, `fixed-bottom`). Esiin noussee kuitenkin uusi ongelma, joka
hoituneen kayttäen tehtäväpohjassa määriteltyä luokkaa `jwo-body`. Sen myötä
sivulle muodostunee myös taustakuvio.

[position]: https://getbootstrap.com/docs/4.0/utilities/position/

#### 2. Perusmuotoilu

Tässä vaiheessa *Kuvissa 1 ja 2* esitettyä sivua voi lähteä tutkiskelemaan
järjestyksessä vaikka ylhäältä alaspäin:

1. sivun ylä- ja alapalkien kuva on keskitetty ja palkeissa on
kuvaan sointuva tausta
2. sivun pääotsikko on keskitetty ja sillä on varjostus
3. sisätöalueen ympärillä on ohut pyöristetty raami
4. sisältöalueen ylä- ja alapalkeissa on niissä oleviin kuviin sointuva tausta
5. sisältöalueen teksti on valkoista lukuunottamatta kookasta lukua,
joka esitetään punaisena
6. toisin kuin koko sivun tausta, sisältöalueen tausta liikkuu sivua vieritettäessä
7. sisältöalueella olevilla arvioilla on ohut pyöristetty raami
8. arvioteksti ei ole aivan kiinni arvion raamista ja arvion raami ei ole aivan
kiinni (esim.) sisältöalueen yläpalkissa
9. arvioiden alapuolella oleva yhteenvetorivi on taustaltaan vihreä ja rivillä
oleva teksti on keskitetty
10. sisältöalueen yleiskuvaus-sarakkeen tausta on vihreä ja sen sisältämien
otsikoiden alapuolinen teksti on hieman sisennetty
11. yleiskuvaukseen liittyvä juliste on kiinni sarakkeen reunassa
12. julisteen ja sen alapuolella olevan tekstin välissä on jonkin verran tyhjää
tilaa

{% comment %}

Luokat
1. text-center, jwo-page-banner
2. text-center, jwo-text-shadow
3. border, border-secondary, rounded
4. jwo-content-banner
5. text-white, jwo-huge-text
6. jwo-content-background
7. (vrt. kohta 3)
8. mt-3, p-2
9. jwo-backgroud, text-center
10. jwo-backgroud, pl-3
11. pl-0, pr-0

{% endcomment %}

Edellä luetellut ominaisuudet edellyttänevät seuraavien `styles.css` -tiedostossa
määriteltyjen luokkien käyttöä:
`jwo-page-banner`,
`jwo-text-shadow`,
`jwo-content-banner`,
`jwo-huge-text`,
`jwo-content-background`,
`jwo-backgroud`.

Seuraavia Bootstrap:in luokilla hoitunee sivulle sopivat [raamit][borders]:
`border`, `border-secondary`, `rounded`. [Tekstiä][text] (ml. kuvat) voi asemoida
esim. luokalla `text-center` ja [värittää][colors] esim. luokan `text-white` avulla.

[borders]: https://getbootstrap.com/docs/4.0/utilities/borders/
[text]: https://getbootstrap.com/docs/4.0/utilities/text/
[colors]: https://getbootstrap.com/docs/4.0/utilities/colors/

Elemettien välisiä [etäisyyksiä][boxmodel] voi säädellä marginaaleilla (*margin*)
ja täytteellä (*padding*), joihin liittyen Bootstrap sisältää [joukon][spacing]
"m"- ja "p"-luokkia. Esim. luokka `mt-3` viittaa kolmen yksikön suuruiseen
elementin yläpuoliseen (*top*) marginaaliin ja `pl-3` kolmen yksikön suuruiseen
vasemmanpuoleiseen (*left*) täytteeseen. Edellisten lisäksi tässä saatetaan
tarvita vielä esim. seuraavia:  `p-2`,  `pl-0`, `pr-0`.

[boxmodel]: https://www.w3schools.com/css/css_boxmodel.asp
[spacing]: https://getbootstrap.com/docs/4.0/utilities/spacing/


#### 3. Loppusäädöt


Edellisten askelien suorittamisen jälkeen sivun pitäisi muistuttaa jo melko paljon
*Kuvia 1 ja 2*, mutta joitakin pieniä eroavaisuksia lienee havaittavissa:

1. arvioiden ja arvioijien ikonien rinnalla tulisi olla kaksi tekstiriviä yhden
sijaan
2. sisältöalueen oikeassa sarakkeessa oleva kuva ("juliste") tulisi skaalautua tietyyn
pisteeseen asti, kun selainikkunan leveyttä muutetaan
3. sisältöalueen ylä- ja alapalkeissa olevan tekstin tulisi olla lähempänä
palkin alareunaa ja hieman lähempänä vasemmalla puolella olevaa kuvaa
4. arvioiden alapuolella olevan yhteenvetorivin tulisi olla sisältöalueen
alaosassa ala-palkin yläpuolella


{% comment %}

Luokat
1. float-left
2. img-fluid
3. d-flex, align-self-end/mt-auto (, pl-1)
4. flex-column, d-flex,  mt-auto

{% endcomment %}


Tällaisetkin säädöt hoituvat Bootstrap-luokilla (, jotka siis perustuvat
CSS -tyylisääntöihin). Teksti saadaan kiertämään kuvaa asettamalla kuvalle
[float][float] -luokka, tässä: `float-left`. [Kuva][images] taas skaalautuu
luokan `img-fluid` avulla.

Mm. elementtien vertikaalista asemointia voidaan toteuttaa CSS:n
[Flexible Box Layout][mdn-flex] -moduulilla, jota [Bootstrap-luokat][flex]
hyödyntävät. Tässä elementin siirto isä-elementin alareunaan voidaan
hoitaa niin, että elementille asetetaan "automaattinen" ylämarginaali, `mt-auto`,
ja isä-elementille asetetaan luokka `d-flex`. Tämän lisäksi *Yhteenvetorivin*
siirto edellyttää isä-elementille luokkaa `flex-column`.

[float]: https://getbootstrap.com/docs/4.0/utilities/float/
[images]: https://getbootstrap.com/docs/4.0/content/imaages/

[flex]: https://getbootstrap.com/docs/4.0/utilities/flex/
[mdn-flex]: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout


Kun sivu näytää työaseman selaimessa halutunlaisesta, kannattaa vielä tarkistaa,
miten se muotoutuu vaikka kännykän kokoisella näytöllä. Selaimissa on tähän
liittyviä apuvälineitä, esim. Firefoxin web-työkalupaletista löytyvä
*Responsive Design Mode*. *Kuvan 3* kuvaruutukaappaukset ovat tuosta työkalusta,
kun tarkasteltavaksi laitteeksi on valittu eräs hieman yli 5 tuuman näytöllä
varustetta mobiililaite.


<br/>

<small>
Tehtävän lähde: Homeworks Movie Review & Movie Review Part Deux.<br/>
[Web Programming][cse154], University of Washington, Computer Science & Engineering.<br/>
Copyright © Marty Stepp / Jessica Miller, licensed under Creative Commons Attribution 2.5 License.<br/>
(alkuperäistä tehtävää muokattu)
</small>

[cse154]: https://courses.cs.washington.edu/courses/cse154/


<br/>
