---
description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Bulkverzoeken
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Bulkverzoeken{#bulk-requests}

Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[ RBAC groepstoestemmingen ](../../features/administration/administration-overview.md) die in [!DNL Audience Manager] worden toegewezen UI wordt geëerd in [!UICONTROL Bulk Management Tools].

Het werkblad van [!UICONTROL Request] heeft geen eigen reeks kolomkopballen en u te hoeven om geen IDs aan om het even welke kolommen te kopiëren. In plaats daarvan worden gegevens geretourneerd op basis van de actieknop waarop u op de werkbalk klikt. En een optionele rapportfunctie retourneert een frequentietelling voor pixelbranden en een uniek aantal gebruikers voor verschillende vaste tijdintervallen.

Als u aanvragen voor grote hoeveelheden wilt indienen, opent u het werkblad van [!UICONTROL Bulk Management Tools] en:

1. Klik op de tab **[!UICONTROL Request]** .
2. Klik in de werkbalk boven in het werkblad op een aanvraagknop die overeenkomt met de gegevens waarmee u wilt werken. U kunt het volgende aanvragen:

   * Algoritmische modellen
   * Gegevensbronnen
   * Afgeleide signalen
   * Doeltoewijzingen
   * Algorithmic, rule-based, and on-boeded traits
   * Segmenten
   * Trait and segment folder IDs

   De API van [!DNL Audience Manager] schrijft bulkgegevens terug naar het [!UICONTROL Request] werkblad.

>[!NOTE]
>
>In uw resultaten retourneren de kolommen `createTime` en `updateTime` gegevens in exponentiële notatie. De onderliggende datum-/tijdstempels worden opgenomen in UNIX UTC-tijd. Het werkblad kan momenteel geen datum-/tijdstempels in een leesbare indeling retourneren.

Als uw bulkupdate een fout terugkeert of ontbreekt, zie [ het Oplossen van problemen voor de Hulpmiddelen van het Beheer van het Bulk ](../../reference/bulk-management-tools/bulk-troubleshooting.md).
