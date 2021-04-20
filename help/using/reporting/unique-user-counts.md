---
description: Beschrijft de variatie in unieke gebruikerstotalen tussen rapporten voor het zelfde bezit en tijdspanne.
seo-description: Beschrijft de variatie in unieke gebruikerstotalen tussen rapporten voor het zelfde eigenschap en tijdperiode in Adobe Audience Manager
seo-title: Unieke gebruikers tellen in overlapping en Algemene rapporten in AAM
solution: Audience Manager
title: Unieke gebruikers tellen in overlaprapporten en algemene rapporten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Unieke gebruikers tellen in overlaprapporten en algemene rapporten{#counting-unique-users-in-overlap-and-general-reports}

Deze pagina beschrijft de variatie in unieke gebruikerstotalen tussen rapporten voor de zelfde eigenschap en tijdspanne.

<!-- 

c_unique_user_counts.xml

 -->

## Overlappingsrapport: Uniek aantal gebruikers

De overlappende rapporten tellen gebruikers als uniek wanneer zij voor een eigenschap in aanmerking komen:

* Tijdens het geselecteerde tijdinterval voor het rapport.
* Dat heeft een [tijd-aan-levende](../features/traits/segment-ttl-explained.md) waarde langer dan het geselecteerde tijdinterval voor het rapport.
* Als ze als actief in ons systeem worden beschouwd (dus gekwalificeerd voor andere kenmerken, een id-sync, enz.) in de afgelopen 60 dagen.

## Algemeen rapport: Uniek aantal gebruikers

Het rapport Algemeen beschouwt bezoekers van de site als uniek als ze tijdens de geselecteerde periode in aanmerking kwamen voor de eigenschap.

>[!MORELIKETHIS]
>
>* [Interactieve rapporten](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Algemene rapporten](../reporting/general-reports.md#general-reports-overview)

