Ding News Headlines
=================
 * Introduction
 * Installation
 * Configuration
 * Customisations
 * Versioning
 * Maintainer

INTRODUCTION
-----------------
Forsidewidget baseret på Ding News, der viser overskrift og dato fra nyheder af en bestemt kategori, der er forfremmet til forsiden. 


INSTALLATION
-----------------
Installér og aktivér modulet som du plejer. 

Aktivér modulet 'Views UI' (installér det, hvis du ikke har det i forvejen) - det gør det muligt at se stierne, der er angivet nedenfor.

Følg derefter beskrivelsen under CONFIGURATION.


CONFIGURATION 
---------------------
1. Lav i eller ii
  1. Hvis du vil bruge nyhedskategorien "Vigtige beskeder" og ikke har den i forvejen, skal du starte ned at oprette den:
    * Gå til admin/structure/taxonomy/news_category og klik på "Tilføj ord"
    * I feltet "Navn" skriv: Vigtige beskeder
    * Tryk "Gem" for at gemme ændringerne i viewet
  2. Hvis du vil bruge en anden kategori end "Vigtige beskeder", skal du rette teksten i widgetten til, så det passer til din kategori:
    * Gå til admin/structure/views/view/ding_news_headlines/edit
    * Skift overskrift i widgetten: Under "TITEL" ud for "Titel:" klik på linket "Vigtige beskeder". Skriv din nye tekst i feltet. Tryk "Anvend (dette display)"
    * Skift teksten der vises ved ingen resultater: Under "Avanceret" > "OPFØRSEL VED INGEN RESULTATER" ud for "Global:" klik på linket "Tekstområde (Ingen vigtige beskeder)" og tilpas teksten, så det passer til jer. Tryk "Anvend (dette display)"
    * Tryk "Gem" for at gemme ændringerne i viewet
 
2. Væg hvilke(n) kategori(er) nyheder, widgetten skal vise:
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "FILTRERINGSKRITERIER" Klik på linket "Indhold: Category(=[tilfældig kategori fra din hjemmeside])"
 * I listen "Vælg termer fra ordforrådet News Category" vælg "Vigtige beskeder" kategorien eller en anden kategori. Du kan godt vælge flere fra listen. Tryk "Anvend (dette display)"
 * Tryk "Gem" for at gemme ændringerne i viewet
 
3. Tilføj widget til forsiden
 * Struktur > Sider > Ud for [navnet på din forside. Fx ding_frontpage] tryk "Rediger" > Indhold
 * Klik på tandhjul i venstre side af den kolonne, widget skal i.
 * Klik Tilføj indhold > News panes > View: News headlines: News headlines with category (frontpage) > Afslut
 * Træk eventuelt widgetten op i toppen af området
 * Tryk "Opdater og gem"
 * Tøm cachen

 
CUSTOMISATIONS
------------------------------
Du kan ændre flere ting ved listen, hvis du ikke er tilfreds med standardindstillingerne, ved at ændre i dets view. Nedenfor er beskrevet et par almindelige eksempler.

I modulets 'Assets' mappe finder du en pdf med forslag til css til at ændre widget'ens udseende.

* DDB CMS: Fjern kategori fra den almindelige nyhedsoversigt på forsiden for at undgå at dublere nyheder
 * Gå til admin/structure/views/view/ding_news/edit
 * I dropdown menuen ud for "FILTRERINGSKRITERIER" vælg "tilføj"
 * I feltet "Søg" skriv: category
 * Sæt hak ud for Indhold: Category (field_ding_news_category) Optræder i: node:ding_news.
 * Tryk "Anvend (dette display)"
 * Sæt hak i "Rullemenu" og tryk "Anvend og fortsæt"
 * Under "Operand" sæt hak ud for "Er ingen af"
 * Under "Vælg termer fra ordforrådet News Category" sæt hak ud for den eller de kategorier, der ikke skal vises (den der vises i den nye widget, fx "Vigtige beskeder").
 * Tryk "Anvend (dette display)"
 * Tryk "Gem" for at gemme ændringerne i viewet

* Ændr antallet af nyheder i oversigten
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "Pager" Klik på "3 overskrifter". I linjen "Antal elementer" skriv hvor mange nyheder, listen skal vise.
 * Tryk "Anvend (dette display)"
 * Tryk "Gem" for at gemme ændringerne i viewet

* Fjern "Se alle nyheder"-linket
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der) 
 * Under "PAGER" find "Mere-link" og klik på "Ja". Fjern hak i "Opret mere"-link. Tryk "Anvend (dette display)"
 * Tryk "Gem" for at gemme ændringerne i viewet

Modulet er indstillet til at bruge en standard DDB CMS datovisning (á la 17. juli 2016). Hvis du hellere vil have en anden visning af dato, fx uden årstal, kan du oprette et nyt datoformat. Vær opmærksom på, at det kan gøre det nødvendigt at lave ekstra css.

* Opret nyt datoformat (á la 15/7) og skift til formatet
 * Gå til admin/config/regional/date-time/formats
 * Klik "Tilføj format" og skriv i feltet "Formatstreng": d/m
 * Tryk "Tilføj format"
 * Vælg fanen "Typer" (admin/config/regional/date-time)
 * Klik "Tilføj datotype"
 * Vælg det nyoprettede format i "Datoformat" dropdown'en (ligger typisk nederst) og skriv i feltet "Datotype": Dato kort (forsidewidget)
 * Klik "Tilføj datotype"
 * Gå til admin/structure/views/view/ding_news_headlines/edit (hvis du ikke allerede er der)
 * Under "FELTER" klik på "Date" og vælg i dropdown'en under "Datoformat" det datoformat, du lige har oprettet. Tryk "Anvend (dette display)".
 * Tryk "Gem" for at gemme ændringerne i viewet

Du skal tømme cachen for, at ændringer slår igennem.


Versioning
----------------
Ding News Headlines 7.x-1.0 er testet på DDB CMS ding2-7.x-2.5.1
 
 
MAINTAINERS
----------------
Nuværende vedligeholder: Tina Skjærbæk Søeborg (websomhelst), HvidovreBibliotekerne