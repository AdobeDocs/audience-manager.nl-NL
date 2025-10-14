---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---
# Instructies

**Nota: Deze pagina (of om het even welke readme.md- pagina) zal niet aan de klant publiceren die documentatie** onder ogen ziet

## Inhoudsopgave

+ `TOC.md` bij de wortel van de gebruikersgids verstrekt de organisatie van de onderwerpen die in de gids voor deze oplossing bevat zijn.
+ Elke gebruikershandleiding heeft zijn eigen unieke `TOC.md` , waarin u alle pagina&#39;s/onderwerpen naar wens kunt bestellen.
+ De eerste pagina van alle gebruikershandleidingen is `overview.md` .

## Gebruikershandleiding

+ De inleiding tot de gebruikershandleiding wordt `overview.md` genoemd
+ Elk onderwerp in de gebruikersgids heeft zijn eigen afzonderlijke folder.
   + Als er een onderwerp in de gids genoemd *Implementatie* is, is de overeenkomstige folder `/implementation`
+ Alle afbeeldingselementen worden opgeslagen in `/assets` aan de basis van de gebruikershandleiding.
   + Alle afbeeldingen in de map `/assets` worden gelokaliseerd.
   + Afbeeldingen in de map `/no-localize` worden niet gelokaliseerd (dit is een verrassing!). Dit kan worden gebruikt om er in lokale versies voor te zorgen dat specifieke elementen niet onnodig worden gereproduceerd.

## Metagegevens gebruikersgids Niveau

+ Metagegevens die de gebruikershandleiding beschrijven, worden opgeslagen in de `TOC.md` . Dit omvat:
   + product - naam van product/capaciteit.
   + cloud - cloud waartoe dit product behoort.
   + publiek - publiek of archetype waarop de gids is gericht.
   + gebruikershandleiding - naam van de gebruikershandleiding.

## Metagegevens paginaniveau

+ Metagegevens die nodig zijn om een document te beschrijven, worden opgeslagen als onderdeel van elke afzonderlijke pagina. Dit omvat:
   + titel - titel van de pagina.
   + beschrijving - beschrijving van de pagina.
   + tweede titel - tweede alternatieve titel.
   + seo-description - alternatieve titel voor SEO-doeleinden.
   + korte titel - (optioneel veld).
   + index - ja/nee - de pagina wordt geïndexeerd door het zoekplatform van Adobe.
   + vertalen - ja / nee - zal deze pagina worden gelokaliseerd .
   + versie - vooral gebruikt voor AEM en Campagne, om de versie van het product aan te duiden.
   + private-feature-pack - voornamelijk gebruikt voor AEM.
   + bèta - is dit product in bèta?
   + omleiding - kan worden gebruikt om een verwijzing naar een nieuwe pagina tot stand te brengen als dat wordt vereist.
   + doc-type: referentie (standaard) / problemen oplossen / ontwikkelaar / zelfstudie / kb / whitepaper.

## Meer informatie

Voor meer het publiceren instructies, stijlgidsen, steekproeven en andere middelen, gelieve te bezoeken de [&#x200B; Samenwerken Documentatie Repo &#x200B;](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
