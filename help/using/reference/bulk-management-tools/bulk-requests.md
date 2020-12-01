---
description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-title: Bulkaanvragen
solution: Audience Manager
title: Bulkaanvragen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Bulkaanvragen{#bulk-requests}

Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen die ](../../features/administration/administration-overview.md) zijn toegewezen in de  [!DNL Audience Manager] gebruikersinterface, worden gerespecteerd in de  [!UICONTROL Bulk Management Tools].

Het werkblad [!UICONTROL Request] heeft geen eigen set kolomkoppen en u hoeft geen id&#39;s naar een van de kolommen te kopiëren. In plaats daarvan worden gegevens geretourneerd op basis van de actieknop waarop u op de werkbalk klikt. En een optionele rapportfunctie retourneert een frequentietelling voor pixelbranden en een uniek aantal gebruikers voor verschillende vaste tijdintervallen.

Om bulkverzoeken te maken, open [!UICONTROL Bulk Management Tools] aantekenvel en:

1. Klik op het tabblad **[!UICONTROL Request]**.
2. Klik in de werkbalk boven in het werkblad op een aanvraagknop die overeenkomt met de gegevens waarmee u wilt werken. U kunt het volgende aanvragen:

   * Algoritmische modellen
   * Gegevensbronnen
   * Afgeleide signalen
   * Doeltoewijzingen
   * Algorithmic, rule-based, and on-boeded traits
   * Segmenten 
   * Trait and segment folder IDs

   De [!DNL Audience Manager] API schrijft bulkgegevens terug naar [!UICONTROL Request] aantekenvel.

>[!NOTE]
>
>In uw resultaten geven de kolommen `createTime` en `updateTime` gegevens in exponentiële notatie. De onderliggende datum-/tijdstempels worden opgenomen in UNIX UTC-tijd. Het werkblad kan momenteel geen datum-/tijdstempels in een leesbare indeling retourneren.

Als uw bulkupdate een fout terugkeert of ontbreekt, zie [Oplossen van problemen voor de Hulpmiddelen van het Beheer van het Bulk](../../reference/bulk-management-tools/bulk-troubleshooting.md).
