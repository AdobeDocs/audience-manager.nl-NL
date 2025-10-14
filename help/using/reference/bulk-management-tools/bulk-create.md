---
description: Met de optie Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Bulk maken
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Bulk maken{#bulk-create}

Met de optie Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[&#x200B; RBAC groepstoestemmingen &#x200B;](../../features/administration/administration-overview.md) die in [!DNL Audience Manager] worden toegewezen UI wordt geëerd in [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>U mag objecttypen niet mengen in een aanvraag voor het maken van grote hoeveelheden. De kopteksten voor elk object zijn uniek en kunnen niet worden gecombineerd. Wis het aantekenvel en doe een afzonderlijk verzoek voor verschillende punten.

Als u meerdere objecten wilt maken, opent u het werkblad van [!UICONTROL Bulk Management Tools] en:

1. Klik op de tab **[!UICONTROL Headers]** en kopieer de kopteksten voor het item dat u wilt toevoegen.
2. Klik op de tab **[!UICONTROL Create]** .
3. Plak de aanmaakheaders in de eerste rij van het werkblad van de update.
4. Plak of typ de gegevens die u wilt wijzigen in een bijbehorende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het dialoogvenster [!UICONTROL Account Information] geopend.
6. Verstrek het vereiste [&#x200B; login informatie &#x200B;](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik **[!UICONTROL Submit]**.

In het werkblad wordt een kolom [!UICONTROL Results] gemaakt. De kolom [!UICONTROL Results] retourneert de JSON-reactie voor een geslaagde bewerking. Zie [&#x200B; REST APIs &#x200B;](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet het werkblad voor bulksgewijs maken er ongeveer zo uitzien als in het volgende voorbeeld. Niet alle verschillende opties voor het maken van bestanden worden hier weergegeven. Dit is inbegrepen om u te helpen begrijpen hoe een voltooid aantekenvel zou kunnen kijken.

![](assets/cretetraits.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie [&#x200B; het Oplossen van problemen voor de Hulpmiddelen van het Beheer van het Bulk &#x200B;](../../reference/bulk-management-tools/bulk-troubleshooting.md).
