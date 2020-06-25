---
description: Beschrijft de variatie in unieke gebruikerstotalen tussen rapporten voor het zelfde bezit en tijdspanne.
seo-description: Beschrijft de variatie in unieke gebruikerstotalen tussen rapporten voor het zelfde bezit en tijdperiode in Adobe Audience Manager
seo-title: Unieke gebruikers tellen in overlapping en algemene rapporten in AAM
solution: Audience Manager
title: Unieke gebruikers tellen in overlapping en algemene rapporten
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---


# Unieke gebruikers tellen in overlapping en algemene rapporten{#counting-unique-users-in-overlap-and-general-reports}

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

