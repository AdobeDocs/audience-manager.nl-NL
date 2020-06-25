---
description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-title: Bulkverzoeken
solution: Audience Manager
title: Bulkverzoeken
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Bulkverzoeken{#bulk-requests}

Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) die zijn toegewezen in de [!DNL Audience Manager] gebruikersinterface, worden in de [!UICONTROL Bulk Management Tools]gebruikersinterface gerespecteerd.

Het [!UICONTROL Request] aantekenvel heeft zijn eigen reeks kolomkopballen niet en u te hoeven om geen IDs aan om het even welke kolommen te kopiëren. In plaats daarvan worden gegevens geretourneerd op basis van de actieknop waarop u op de werkbalk klikt. En een optionele rapportfunctie retourneert een frequentietelling voor pixelbranden en een uniek aantal gebruikers voor verschillende vaste tijdintervallen.

Om bulkverzoeken te maken, open het [!UICONTROL Bulk Management Tools] aantekenvel en:

1. Klik op het **[!UICONTROL Request]** tabblad.
2. Klik in de werkbalk boven in het werkblad op een aanvraagknop die overeenkomt met de gegevens waarmee u wilt werken. U kunt het volgende aanvragen:

   * Algoritmische modellen
   * Gegevensbronnen
   * Afgeleide signalen
   * Doeltoewijzingen
   * Algorithmic, rule-based, and on-boeded traits
   * Segmenten
   * Trait and segment folder IDs
   De [!DNL Audience Manager] API schrijft bulkgegevens terug naar het [!UICONTROL Request] werkblad.

>[!NOTE]
>
>In uw resultaten geven de `createTime` kolommen en de `updateTime` kolommen gegevens in exponentiële notatie. De onderliggende datum-/tijdstempels worden opgenomen in UNIX UTC-tijd. Het werkblad kan momenteel geen datum-/tijdstempels in een leesbare indeling retourneren.

Als uw bulkupdate een fout terugkeert of ontbreekt, zie het Oplossen van [problemen voor de Hulpmiddelen](../../reference/bulk-management-tools/bulk-troubleshooting.md)van het Beheer van het Bulk.
