---
Title: Load
Description: Analysis 2
Template: analysis
---

Laddnings hastigheter {.a-title}
=======================

I denna rapport skrivs det en analys om laddningshastigheter.
Jag kommer kolla på 3 hemsidor och se hur/om dom har gjort sin hemsida snabbare.

<br>
Urval
-----------------------

I denna urval fokuserar jag på mobila användare, för att jag ser att det är mest relevant för hastigheter.
Jag vill välja några sidor som inte är optimiserade för mobil och desktop.
Och någon sidan som är optimiserad.

<br>
### [FORSVARSMAKTEN.se][1]

![Forsvar](%base_url%/image/analys/forsvar.png?w=60%) {.img80p}

Hemsida för våran försvarsmakt.
Jag valde den här sidan för att den hade många bilder.

<br>
### [SAMSUNG.com][2]

![Samsung](%base_url%/image/analys/sam.png?w=60%) {.img80p}

Ett mobil företag.
Jag valde denna för att jag tänker mig att de som skapar mobiler ska kunna skapa en hemsida optimiserad för sånna.

<br>
### [RELIABLESOFT.net][3]

![Reliablesoft](%base_url%/image/analys/reliable.png?w=60%) {.img80p}

En hemsida om digital marketing.
Det var en sida jag hitta som hade jobbat hårt för optimisering.

<br>
Metod
-----------------------

Jag använder [PageSpeed][4] och chrome verktyget Lighthouse för att mäta hastigheterna.

<br>
Resultat
-----------------------

<iframe style="width: 100%; height: 160px" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vSBK0egAJd7U-wBONlB8efTJAO_vr1eHN1v6-kwzFlVKAyXwaooUDqUxbFBUhqlywnWVO1CHN5W2a3m/pubhtml?gid=0&amp;single=true&amp;widget=true&amp;headers=false"></iframe>

(ATF = Above the fold)

<br>
Som vi ser i mätningarna jag gjorde, så har forsvarsmakten.se väldigt dålig
bild format och skulle behöva lazy load.

<br>
Samsung.com har en massa onödig JS/CSS kod. Jag vet inte riktigt hur PageSpeed räknar onödig kod. Det kan vara så att det är kod som bara kör på dator, eller om man trycker på en specifik knapp?
I all fall är deras DOM-object väldigt stort också.

<br>
Reliablesoft.net har använt lazy load och rätt storlekar för bilder och därför får en snabb start.

<br>
Analys
-----------------------

Inte många hemsidar har gjort sin övergång till webP, vilket är bästa filformatet för bilder på webben.
Och inte många tänker på att optimisera bilder för alla enheter.
Även fast Samsung och Reliablesoft inte använder webP har dom använt JPGs bra för att inte få för stora filer.

<br>
Börja använda lazy loads!
Den enda hemsidan i mätningarna som använder lazy load är reliablesoft.
Det lazy load gör att bara ladda in det användaren kan see, allt under skärmen är inte laddat. Det sparar data och gör sidan snabbare. Man får inte glömma att sätta width och height när man använder lazy loading för att annars kan divs under flytta sig medans det laddar, vilket är ett problem ifall man läser något under bilden.

<br>
Kod måste också optimiseras.
Använd minified kod och kod compressors, alla hemsidor i denna rapport gör det. Ibland är det inte tillräckligt iall koden är dåligt skriven till att börja med.
Om jag kunde see lätt hur koden mättes i pagespeed hade jag haft mer att säga här.

<br>
Reliablesoft.net är en tydlig vinnare i detta urval av hemsidor.
Jag tycker en hemsida ska få framm bild och funktion inom 2 sekunder ifall de vill att man ska komma tillbaks till hemsidan. Mer än 4 är ok för en väldigt specifik hemsida man inte behöver komma tillbaka till, ofta iaf.
Inom dom här tiderna tycker jag alla sidor har gjort bra, men jag mäter med mitt internet och har inte testat med sämre.

<br>
Övrigt
-----------------------

Jag, Sharif (shou21) jobbade ensam på detta artikel.

[1]: https://forsvarsmakten.se/
[2]: https://samsung.com/
[3]: https://reliablesoft.net/
[4]: https://pagespeed.web.dev/