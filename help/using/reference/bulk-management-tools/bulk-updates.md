---
description: Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.
keywords: baaam
seo-description: Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.
seo-title: Bulkupdates
solution: Audience Manager
title: Bulkupdates
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 30d4cec4502a2cf8b217816ea4ae62eb1b22f641

---


# Bulkupdates{#bulk-updates}

Met een bulkupdate kunt u meerdere segmenten, kenmerken, modellen, gegevensbronnen en segment- of kenmerkelementen in één bewerking bewerken. Volg deze instructies om bulkupdates uit te voeren.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Het [!UICONTROL Bulk Management Tools] wordt niet *ondersteund door* [!DNL Audience Manager]. Dit instrument is bedoeld voor het gemak en alleen als hoffelijkheid. Voor grote wijzigingen raden we u aan om in plaats daarvan met de API&#39;s van [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) te werken. [RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) die zijn toegewezen in de [!DNL Audience Manager] gebruikersinterface, worden in de [!UICONTROL Bulk Management Tools]gebruikersinterface gerespecteerd.

Als u bulkupdates wilt maken, opent u het [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op het **[!UICONTROL Headers]** tabblad en kopieer de updatekoppen voor het item dat u wilt bewerken.
1. Klik op het **[!UICONTROL Update]** tabblad.
1. Plak de updatekoppen in de eerste rij van het updatewerkblad. Let op het volgende:

   * Bij het bijwerken van een map zijn alle kopteksten vereist.
   * Wanneer het bijwerken van segmenten of trekken, hebt u slechts segmentidentiteitskaart (SID) en kopbalelement nodig dat moet worden veranderd. Ongebruikte koppen verwijderen.

1. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
1. Klik in de werkbladwerkbalk op een updateknop die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het [!UICONTROL Account Information] dialoogvenster geopend.

1. Geef de vereiste [aanmeldingsgegevens](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) op en klik op **[!UICONTROL Submit]**.

   In het werkblad wordt een [!UICONTROL Results] kolom gemaakt. De [!UICONTROL Results] kolom retourneert de JSON-reactie voor een geslaagde bewerking. Zie de API&#39;s [REST](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/update.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie het Oplossen van [problemen voor de Hulpmiddelen](../../reference/bulk-management-tools/bulk-troubleshooting.md)van het Beheer van het Bulk.
