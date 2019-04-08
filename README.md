# Sjerps VS code tips en trucs!

He wat leuk dat je meedoet!

Deze tips zijn te vinden op [github](https://github.com/sjerp-indrukwekkend/vscode-instructies)
en zijn geschreven in Markup, de taal voor technisch schrijven. Zie de [tutorial](https://guides.github.com/features/mastering-markdown/)

## Over deze tips

Deze demo is gebaseerd op ❤❤❤ VS code ❤❤❤. Een groot deel van wat ik behandel werkt ook in oudere tekstverwerkers, tenzij je echt met oude software werkt. In dat geval is het volgende een uitleg waarom je over zou moeten stappen 🛐.

Het is niet de bedoeling dat je onthoudt wat ik zeg. Dat krijg je in de vingers door het te doen. Wat mijn doel is, is over te brengen wat een aantal van de mogelijkheden zijn van VS Code. Die dien je grosso modo te onthouden. Als je weet wat je wilt doen kan je via het commandopaneel (control shift p) zoeken naar de functionaliteit. De toetsencombinatie staat er dan vaak direct naast.

Bonus vandaag voor het zo min mogelijk gebruik maken van de muis.
Grootmeesters gebruiken hun muis en tastblad amper... toetsenborden heersen!
Dat heeft vele redenen, ga ik niet hier uiteenzetten, neem het voor nu maar van me aan.

Wil iemand nòg een drogreden? Wes Bos, je weet wel van die Javascript cursus en die podcasts etc?
Die is dus beroemd geworden met een verzameling tips & trucs voor Sublime Text, de tekstbewerker die ik gebruikte (en alle anderen met goede smaak) vóór VS Code. Dus dit is allemaal su-per belangrijk.

## Vereisten voor deze tips

1. VS Code
2. PHP
3. PHP intellisense
4. GIT

Dit zijn mijn extensies:

![sjerp vscode extensies](https://github.com/sjerp-indrukwekkend/vscode-instructies/blob/master/vscode%20extensies%20sjerp.png)

## Installeer de componentenbibliotheek lokaal om mee te doen

```bash
cd ~;
git clone https://github.com/indrukwekkend/WP-componenten;
code WP-componenten;
```

## Vind waar je dient te programmeren

Eén van de meest tijdrovende en cognitief vermoeiende taken als programmeur is vinden wáár je nu moet programmeren en daarheen navigeren.
Dat wordt op grofweg twee manieren opgelost:

1. De runtime (zoals de browser) contekst meegeven over de oorsprong van code, zoals codemaps (CSS, JS). Daar kijken we nu niet naar.
2. Binnen de codebase navigatie aanbrengen.

Naar dat laatste gaan we kijken en dat doen we aan de hand van wat concrete voorbeelden.

Het is nu echt belangrijk dat je je muis zo min mogelijk aanraakt binnen de contekst van je tekstbewerker. In de browser mag het wel.

### Control p is je beste vriend.

VS code is fijn omdat het veel kan maar ook uit legt waar nodig. Mijn rol is hier dan ook vooral te wijzen op VS Code.
Doe

`ctrl p; ?`

#### Symbolen zoeken

De eerste optie is `ctrl p; #`.
Stel, je hebt een fout gemaakt en de debugger geeft aan: het gaat fout in **functie** **maakTaxlijst()**. Je vindt die functie het snelste door de alt-tabben naar je tekstverwerker en dan te tikken: `ctrl p; #maakT`. De fuzzy search geeft je al snel een tip. Je hoeft niet exact te tikken, zodra de eerste optie de jouwe is kan je op enter drukken en je navigeert. Je kan met de pijltjes (...of zelfs met je muis) door de suggesties heen en de juiste selecteren.
Let op dat deze 'symbolen' geen CSS selectoren bevatten. Dit gaat om PHP en JS.

Als je specifieker wilt zoeken kan je binnen een bestand naar symbolen zoeken via `ctrl p; @`. Stel, je wilt binnen **artikel_class.php** zoeken naar de **functie maak()** dan is het beter om `ctrl p; @maa` te tikken dan `ctrl p; #maa`, alhoewel VS code natuurlijk slim genoeg is om je eerste hit je meest lokale hit te laten zijn.

#### Simpel bestanden zoeken

Stel je bent ergens binnen je workspace en je wilt snel naar bestand. Stel je zit in bijvoorbeeld een gigantisch genest systeem zoals een Bedrock Wordpress en je wilt naar `/wp/blabla/foo/bar/faz/bedrock/horror/satan-bedacht-deze-mappenstructuur/wp-content/themes/40-45/templates/woocommerce/single-product.php`. Met de muis ben je dan aan het klikken en scrollen en pff... waardeloos! En hoe vaak doe je dat wel niet op een dag. Stel nu dat je een los op regex gebaseerde zoekopdracht kon doen op het bestandspad? VS Code verwerkt en indexeert dus alles in je codebase. Bovenstaand bestand kan ik vinden, zonder nadenken, met het volgende commando:

`ctrl p; horror 40-45 single-prod php`.

Stel je voor je hebt meerdere thema's in je workspace en die hebben allemaal een **style.css**. Hoe maak je dat verschil? Stel ze heten **agitatie** en **40-45**. Noem maar wat. De eerste vind je dan als `ctrl p; ag style` en de tweede vind je als `ctrl p; 40 style`.

Je kan zo weinig of zoveel tikken als je wilt. Minder tikken is obscuurder dus meer punten 👾👾👾

Ga naar de componenten en test het zoeken naar:
componenten/artikel_class.php
subcomponenten/titel_trait.php

#### Simpel zoeken + regel zoeken

Vaak weet je niet alleen het bestand waar je heen wilt, maar ook de regel. Stel, je hebt van je debugger te horen gekregen dat je op regel 173 van admin_frontend.php een fout heb gemaakt. Ga je nu je hele mappenstructuur openklikken met de muis, op het bestand klikken, en dan scrollen naar een regel... 🤔

lol nee.

`ctrl p; a fron:173`

Zoals je ziet tik ik iets in waarvan ik, gevoelsmatig, gok dat het juiste bestand pakt.
Hierachter zet je `:` en dan de regelnummer.

Binnen een bepaalt bestand kan je naar een regel gaan door `ctrl g; [regel]` te tikken of `ctrl p; :[regel]`
Als je met dit soort dingen begint, is éérst `ctrl p` en dan `ctrl g` natuurlijk meer dan prima 🧙‍♂️.

### Eindeloze commando's om te kunnen.

Ook ik weet het niet allemaal. Sinds ik begon met het ondersteboven leggen van mijn muis 3 jaar terug ben ik mega veel productiever geworden. Dit leer je echt door het te doen, en door stelselmatig niet je muis te gebruiken 🤓. Deze commando's zijn relatief universeel. Als je ze kent, en dan duurt echt niet lang, heb je daar je leven lang profijt van.

## Tekstbewerker en navigatie of selectie

Meer universele commando's.

### schakelen tussen bladen.

Stel, je hebt links een header.php open en rechts een header.scss open. Je wilt schakel tussen deze twee. Dat kan natuurlijk met de reeds bekende methode `ctrl p; hea scs`. Dat zijn veel toetsenaanslagen en mogelijk een cognitief lastigere stap dan: **blad naar rechts**. Een blad naar rechts ga je met: `ctrl pgdn`. Dat zijn 2 (of 3 op een laptop) toetsaanslagen.

> Misschien kan ik het uitleggen door te zeggen: alleen ISIS wil méér aanslagen.
> Wij willen minder.
> Daarom moet je zo efficient mogelijk tikken,
> anders 💣💣💣💣💣 winnen de terroristen.

Probeer: open meerdere bestanden en schakel er tussen heen en weer.

### meerdere cursors tegelijk

Stel je hebt een array waarbij je op meerdere plekken tegelijk wilt bewerken.

```php
$bla_array = [
    'hela' =>
    'hola' =>
    'kindercola' =>
];
```

Bekend verschijnsel. Dat kan je bereiken door je cursor ergens neer te zetten en dan
`ctrl alt pijlOmhoog` (of omlaag) te tikken. Als je dan bij hela, hola en kinderkola en cursor hebt druk je op `end` en dan ben je met al je cursors aan het eind van de regel.
