# BeeSplit — uitgiftepunt

Dit is geen open source en geen broncode. Deze repo bestaat om één reden: het
programma **BeeSplit** moet kunnen opzoeken of er een nieuwere versie van
zichzelf is.

Hier staat daarom niet meer dan:

- **`versie.json`** — een paar honderd bytes met het nieuwste versienummer, de
  downloadlink en de sha256 van dat bestand
- **`LICENSE`** — de voorwaarden waaronder BeeSplit mag worden gebruikt

De pakketten zelf hangen onder [Releases](../../releases) als bijlage, niet als
bestand in deze repo.

## Wat BeeSplit doet

BeeSplit splitst één PDF in losse PDF's van één pagina. De bestandsnamen komen
uit de tekening zelf: je trekt met de muis een kader om het tekeningnummer in
het stempel, en dat wordt op elk blad opnieuw uitgelezen — uit de tekstlaag, uit
de notities die AutoCAD bij SHX-tekst meelevert, of met de tekstherkenning van
Windows als de letters losse plaatjes zijn.

## Voor wie hier per ongeluk belandt

BeeSplit is een intern hulpmiddel. Het valt onder de **PolyForm Internal Use
License 1.0.0**: gebruiken en aanpassen mag voor de interne bedrijfsvoering van
je eigen organisatie, verspreiden niet — ook niet van een aangepaste versie, en
je kunt je toestemming niet doorgeven.

Aanvullend, buiten de tekst van PolyForm om: de software en de broncode ervan
mogen niet worden gebruikt als trainingsmateriaal voor machinaal lerende
modellen of AI-systemen.

De volledige tekst staat in [`LICENSE`](LICENSE) en gaat ook mee in elk pakket.

© 2026 W.C.J. Tiddens. Alle rechten die de licentie niet uitdrukkelijk geeft
blijven voorbehouden aan de maker.

## Hoe het bijwerken werkt

BeeSplit kijkt **niet** uit zichzelf. Onder Instellingen zit een knop; druk je
daarop, dan leest hij `versie.json` van `raw.githubusercontent.com`. Dat is
bewust niet de GitHub-API: die staat zonder inloggen op zestig verzoeken per uur
per IP-adres, en op een kantoornetwerk delen alle gebruikers er één.

Staat er een hoger versienummer, dan vraagt BeeSplit of je wilt bijwerken. Zeg
je ja, dan wordt de zip opgehaald, de sha256 gecontroleerd, en pas daarna
uitgepakt en geïnstalleerd.
