Autominutes
===========

LaTeX package voor notulisten van USCKI Incognito.

Deze package is bedoeld voor leden van de Utrechtse Studievereniging van Cognitieve Kunstmatige Intelligentie: Incognito.
Deze package moet het notuleren tijdens vergaderingen makkelijker maken, door het toevoegen van todo's in notulen automatisch door LaTeX te laten afhandelen.

De package kent automatisch kleuren toe aan de ontvangers van de todo's. 
De todo's verschijnen vervolgens in de text.
Achteraf kan met één simpel commando een tabel met alle todo's uit de notulen worden gegenereerd.

<h3>Vereiste packages</h3>
Deze package maakt gebruik van de volgende LaTeX-packages, welke geïnstalleerd moeten zijn voordat deze package te gebruiken is:
- etoolbox
- listing
- xstring
- anysize
Waarschijnlijk zal uw LaTeX-software deze packages automatisch proberen te installeren bij het gebruik van deze package.

<h3>Gebruik</h3>
Voordat todo's toegewezen kunnen worden, moeten de namen bekend zijn in dit LaTeX-bestand.

Dat kan door het volgende commando aan te roepen:
```TeX
\aanwezigheid{aanwezigen}{afwezigen}
```
Waarin  _aanwezigen_ een lijst is van mensen die aanwezig zijn bij de vergadering, gescheiden door puntcomma's, en  _afwezigen_  een lijst is van mensen die afwezig zijn bij de vergadering, opnieuw gescheiden door puntcomma's.

Dit commando voegt zowel de volledige namen als de voornamen van alle mensen in beide lijsten toe en kent voor ieder persoon een aparte kleur toe (LET OP: de namen zijn hoofdlettergevoelig), als dat het al deze namen op de plek van het commando in het document zet als aanwezig of afwezig. 
De voornaam wordt gezien als het eerste woord van de volledige naam (dus een spatie eindigt de voornaam).

Vervolgens kan een todo worden toegekend met:
```TeX
\todo{Naam}{Todo}{deadline}
```
Waarin:
- _Naam_  de voornaam of volledige naam van de desbetreffende persoon is, zoals ingevoerd bij de aanwezigheid.
- _Todo_  de beschrijving van de todo is
- _deadline_  de deadline van de todo is.

De todo wordt op de plek waar dit commando wordt aangeroepen ingevoegd in het document als:
    <Naam>: <Todo>
in de kleur die hoort bij de desbetreffende naam.
De deadline wordt alleen in de automatisch gegenereerde tabel gebruikt.

Wanneer een naam moet worden gebruikt, die niet in de de lijst van aan- of afwezigen staat, kan de naam worden toegevoegd door het commando
```TeX
\newName{Naam}
```
te gebruiken. Hierna kan een todo op dezelfde manier worden toegekend.
Deze naam wordt niet gesplitst zoals de namen in de aan- of afwezigheidslijsten. De naam in een todo moet dus exact overeenkomen met de hier ingevoerde naam.

Wanneer een nieuwe naam moet worden toegevoegd en gelijk een todo aan die naam moet worden gegeven, kan de aanroep
```TeX
\todoName{Naam}{Todo}{Deadline}
```
Dit commando combineert de twee hiervoor besproken commando's.

LET OP: het opnieuw toevoegen van een al bestaande naam resulteert er in dat alle namen na de nieuwe toewijzing van de naam een andere kleur krijgen dan daarvoor.

De tabel met todo's kan worden gegenereerd met het commando:
```TeX
\todos
```
Dit commando genereert een tabel van alle todo's die voor de aanroep van dit commando in het document zijn ingevoerd. 
De todo's verschijnen in volgorde van invoering van het document.

<h3>Opmerkingen</h3>
- Deze package past automatisch de margins aan naar een iets leesbaarder formaat.
- De namen van het bestuur 2014 zijn gereserveerd zodat deze altijd dezelfde kleur hebben. Deze kunnen worden ge-overridet.

<h3>Installatie</h3>
Om deze package te gebruiken, kun je de package installeren, of zorgen dat het bestand  _autominutes.sty_ altijd in dezelfde map staat als het LaTeX-bestand waarin het wordt gebruikt.

Voor het installeren van het bestand, doe het volgende:
1) Maak een map aan (buiten de LaTeX installatiedirectory). Bijvoorbeeld  _texmf_  in  _Mijn Documenten_
2) Zet het  _autominutes.sty_  bestand in de directory  _texmf/tex/latex/_  
3) Open MiKTeX Settings als Administrator
4) Ga naar het tabblad  _root_  en voeg de _texmf_-map toe
5) Ga terug naar het tabblad  _general_  en klik op  _Refresh FNDB_

Als het goed is, kun je nu de uscki-package in elk LaTeX-bestand op de computer gebruiken.

Als je geen MiKTeX geïnstalleerd hebt, weet ik het ook niet. Ik heb dit zelf getest op Ubuntu en op Windows. Hoe het onder andere besturingssystemen werkt, weet ik niet.


