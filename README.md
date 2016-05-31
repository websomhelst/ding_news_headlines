Ding News Headlines
=================
 * Introduction
 * Installation
 * Configuration
 * Customisation
 * Maintainer

INTRODUCTION
-----------------
Forsidewidget baseret på Ding News, der viser overskrift og dato fra nyheder af en bestemt kategori, der er forfremmet til forsiden. 


INSTALLATION
-----------------
Installer modulet som du plejer. Vent med at aktivere det, til du har gennemført 1 og 2 under CONFIGURATION.


CONFIGRUATION 
---------------------
1. Lav 1a eller 1b

1a. Hvis du vil bruge nyhedskategorien "Vigtige beskeder" og ikke har den i forvejen, skal du oprette den
 * Gå til /admin/structure/taxonomy/news_category og klik på "Tilføj ord"
 * I feltet "Navn" skriv: Vigtige beskeder
 * Tryk "Gem"

1b. Hvis du vil bruge en anden kategori end "Vigtige beskeder", er du nødt til at ændre et par steder i det view, modulet opretter.
 * Gå til admin/structure/views/view/ding_news_headlines/edit
 * Under "PAGER" find "Mere-link" og klik på "Ja". Fjern hak i "Opret mere"-link, eftersom det linker til oversigten nyheder/vigtige-beskeder. Tryk "Anvend (dette display)"
 * Under "TITEL" ud for "Titel:" klik på linket "Vigtige beskeder". Skriv din nye tekst i feltet. Tryk "Anvend (dette display)"
 * Under "Avanceret" > "OPFØRSEL VED INGEN RESULTATER" ud for "Global:" klik på linket "Tekstområde (Ingen vigtige beskeder)" og tilpas teksten, så det passer til jer. Tryk "Anvend (dette display)"
 * Gem viewet
 
2. Definér, hvilke(n) kategori(er) nyheder, widgetten skal vise:
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "FILTRERINGSKRITERIER" Klik på linket "Indhold: Category(=[tilfældig kategori fra din hjemmeside])"
 * I listen "Vælg termer fra ordforrådet News Category" vælg "Vigtige beskeder" kategorien eller en anden kategori. Du kan godt vælge flere fra listen. Tryk "Anvend (dette display)"
 * Gem viewet 

2. Aktiver modulet 
 
3. Tilføj widget til forsiden
 * Struktur > Sider > Ud for [navnet på din forside. Fx ding_frontpage] tryk "Rediger" > Indhold
 * Klik på tandhjul i venstre side af den kolonne, widget skal i.
 * Klik Tilføj indhold > News panes > View: News headlines: News headlines with category (frontpage) > Afslut
 * Træk eventuelt widgetten op i toppen af området
 * Tryk "Opdater og gem"
 * Tøm cachen

 
OTHER CUSTOMISATIONS
------------------------------
Du kan ændre flere ting ved listen, hvis du ikke er tilfreds med standardindstillingerne, ved at ændre i dets view. Nedenfor er beskrevet et par almindelige eksempler.

* Ændr antallet af nyheder i oversigten
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "Pager" Klik på "3 overskrifter". I linjen "Antal elementer" skriv hvor mange nyheder, listen skal vise.
 * Tryk "Anvend (dette display)"
 * Gem viewet

Modulet er stylet til også at kunne håndtere et mere simpelt datoformat, 15/7 i stedet for 17. juli. Hvis du vil bruge det, skal du oprette nyt datoformat.
*Opret nyt datoformat og skift til formatet
 * Gå til admin/config/regional/date-time/formats
 * Klik "Tilføj format" og skriv i feltet "Formatstreng": d/m
 * Tryk "Tilføj format"
 * Vælg fanen "Typer" (admin/config/regional/date-time)
 * Klik "Tilføj datotype"
 * Vælg det nyoprettede format i "Datoformat" dropdown'en (ligger typisk nederst) og skriv i feltet "Datotype": Dato simpel (bruges i forsidewidgets)
 * Klik "Tilføj datotype"
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "FELTER" klik på "Date" og vælg i dropdo´wn'en under "Datoformat" det datoformat, du vil bruge. Tryk "Anvend (dette display)".
 * Gem viewet

Du skal tømme cachen for, at ændringer slår igennem.
 
 
MAINTAINERS
----------------
Nuværende vedligeholder: Tina Skjærbæk Søeborg (websomhelst), HvidovreBibliotekerne