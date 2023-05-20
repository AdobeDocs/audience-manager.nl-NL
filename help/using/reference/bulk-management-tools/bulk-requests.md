---
description: Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Bulkaanvragen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# Bulkaanvragen{#bulk-requests}

Een bulkverzoek keert gegevens terug u met de verschillende kopballen in de Update, creeert, schat, en schrap aantekenvellen kunt gebruiken.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

De [!UICONTROL Request] werkblad heeft geen eigen set kolomkoppen en u hoeft geen id&#39;s naar een van de kolommen te kopiëren. In plaats daarvan worden gegevens geretourneerd op basis van de actieknop waarop u op de werkbalk klikt. En een optionele rapportfunctie retourneert een frequentietelling voor pixelbranden en een uniek aantal gebruikers voor verschillende vaste tijdintervallen.

Om bulkverzoeken te maken, open [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Request]** tab.
2. Klik in de werkbalk boven in het werkblad op een aanvraagknop die overeenkomt met de gegevens waarmee u wilt werken. U kunt het volgende aanvragen:

   * Algoritmische modellen
   * Gegevensbronnen
   * Afgeleide signalen
   * Doeltoewijzingen
   * Algorithmic, rule-based, and on-boeded traits
   * Segmenten 
   * Trait and segment folder IDs

   De [!DNL Audience Manager] API schrijft bulkgegevens terug naar de [!UICONTROL Request] werkblad.

>[!NOTE]
>
>In uw resultaten kunt u de opdracht `createTime` en `updateTime` kolommen retourneren gegevens in exponentiële notatie. De onderliggende datum-/tijdstempels worden opgenomen in UNIX UTC-tijd. Het werkblad kan momenteel geen datum-/tijdstempels in een leesbare indeling retourneren.

Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
