---
description: Met Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.
seo-description: Met Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.
seo-title: Bulk maken
solution: Audience Manager
title: Bulk maken
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk maken{#bulk-create}

Met Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>Het [!UICONTROL Bulk Management Tools] wordt niet *ondersteund door* [!DNL Audience Manager]. Dit instrument is bedoeld voor het gemak en alleen als hoffelijkheid. Voor grote wijzigingen raden we u aan om in plaats daarvan met de API&#39;s van [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) te werken. [RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) die zijn toegewezen in de [!DNL Audience Manager] gebruikersinterface, worden in de [!UICONTROL Bulk Management Tools]gebruikersinterface gerespecteerd.

>[!CAUTION]
>
>U mag objecttypen niet mengen in een aanvraag voor het maken van grote hoeveelheden. De kopteksten voor elk object zijn uniek en kunnen niet worden gecombineerd. Wis het aantekenvel en doe een afzonderlijk verzoek voor verschillende punten.

Als u meerdere objecten wilt maken, opent u het [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op het **[!UICONTROL Headers]** tabblad en kopieer de kopteksten voor het item dat u wilt toevoegen.
1. Klik op het **[!UICONTROL Create]** tabblad.
1. Plak de aanmaakheaders in de eerste rij van het werkblad van de update.
1. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
1. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het [!UICONTROL Account Information] dialoogvenster geopend.

1. Geef de vereiste [aanmeldingsgegevens](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) op en klik op **[!UICONTROL Submit]**.

In het werkblad wordt een [!UICONTROL Results] kolom gemaakt. De [!UICONTROL Results] kolom retourneert de JSON-reactie voor een geslaagde bewerking. Zie de API&#39;s [REST](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet het werkblad voor bulksgewijs maken er ongeveer zo uitzien als in het volgende voorbeeld. Niet alle verschillende opties voor het maken van bestanden worden hier weergegeven. Dit is inbegrepen om u te helpen begrijpen hoe een voltooid aantekenvel zou kunnen kijken.

![](assets/cretetraits.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie het Oplossen van [problemen voor de Hulpmiddelen](../../reference/bulk-management-tools/bulk-troubleshooting.md)van het Beheer van het Bulk.
