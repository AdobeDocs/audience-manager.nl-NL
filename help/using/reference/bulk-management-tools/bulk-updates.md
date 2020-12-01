---
description: Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.
keywords: baaam
seo-description: Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.
seo-title: Bulkupdates
solution: Audience Manager
title: Bulkupdates
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# Bulkupdates{#bulk-updates}

Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen die ](../../features/administration/administration-overview.md) zijn toegewezen in de  [!DNL Audience Manager] gebruikersinterface, worden gerespecteerd in de  [!UICONTROL Bulk Management Tools].

Als u bulkupdates wilt maken, opent u het [!UICONTROL Bulk Management Tools]-werkblad en:

1. Klik op het tabblad **[!UICONTROL Headers]** en kopieer de updatekoppen voor het item dat u wilt bewerken.
2. Klik op het tabblad **[!UICONTROL Update]**.
3. Plak de updatekoppen in de eerste rij van het updatewerkblad. Let op het volgende:

   * Bij het bijwerken van een map zijn alle kopteksten vereist.
   * Wanneer het bijwerken van segmenten of trekken, hebt u slechts segmentidentiteitskaart (SID) en kopbalelement nodig dat moet worden veranderd. Ongebruikte koppen verwijderen.

4. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op een updateknop die overeenkomt met de knop        object dat je bijwerkt.
Met deze handeling wordt het dialoogvenster [!UICONTROL Account Information] geopend.

6. Geef de vereiste [aanmeldingsgegevens op](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

   Het aantekenvel leidt tot een [!UICONTROL Results] kolom. De [!UICONTROL Results] kolom keert de reactie JSON voor een succesvolle verrichting terug. Zie [REST APIs](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/update.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie [Oplossen van problemen voor de Hulpmiddelen van het Beheer van het Bulk](../../reference/bulk-management-tools/bulk-troubleshooting.md).
