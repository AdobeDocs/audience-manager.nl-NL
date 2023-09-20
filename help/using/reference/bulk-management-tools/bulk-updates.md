---
description: Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.
keywords: baaien
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Bulkupdates
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Bulkupdates{#bulk-updates}

Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in de [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

Als u bulkupdates wilt maken, opent u de knop [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Headers]** en kopieert u de updatekoppen voor het item dat u wilt bewerken.
2. Klik op de knop **[!UICONTROL Update]** tab.
3. Plak de updatekoppen in de eerste rij van het updatewerkblad. Let op het volgende:

   * Bij het bijwerken van een map zijn alle kopteksten vereist.
   * Wanneer het bijwerken van segmenten of trekken, hebt u slechts segmentidentiteitskaart (SID) en kopbalelement nodig dat moet worden veranderd. Ongebruikte koppen verwijderen.

4. Plak of typ de gegevens die u wilt wijzigen in een bijbehorende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op een updateknop die overeenkomt met het item dat u bijwerkt.
Deze handeling opent de [!UICONTROL Account Information] in.

6. Geef de vereiste [loginformatie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

   Het werkblad maakt een [!UICONTROL Results] kolom. De [!UICONTROL Results] de kolom keert de reactie JSON voor een succesvolle verrichting terug. Zie de [REST API&#39;s](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/update.png)

Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
