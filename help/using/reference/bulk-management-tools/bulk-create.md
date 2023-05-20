---
description: Met Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Bulk maken
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Bulk maken{#bulk-create}

Met Bulk kunt u meerdere gegevensbronnen, afgeleide signalen, segmenten, kenmerken en andere items samenstellen met één bewerking. Volg de onderstaande instructies om een aanvraag voor het maken van bulkobjecten in te dienen.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>U mag objecttypen niet mengen in een aanvraag voor het maken van grote hoeveelheden. De kopteksten voor elk object zijn uniek en kunnen niet worden gecombineerd. Wis het aantekenvel en doe een afzonderlijk verzoek voor verschillende punten.

Als u meerdere objecten tegelijk wilt maken, opent u het dialoogvenster [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Headers]** en kopieer de aanmaakheaders voor het item dat u wilt toevoegen.
2. Klik op de knop **[!UICONTROL Create]** tab.
3. Plak de aanmaakheaders in de eerste rij van het werkblad van de update.
4. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het dialoogvenster [!UICONTROL Account Information] in.
6. Verstrek de vereiste [loginformatie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

Het werkblad maakt een [!UICONTROL Results] kolom. De [!UICONTROL Results] de kolom keert de reactie JSON voor een succesvolle verrichting terug. Zie de [REST API&#39;s](../../api/rest-api-main/rest-api-main.md) voor voorbeelden. Voordat u gegevens invoert, moet het werkblad voor bulksgewijs maken er ongeveer zo uitzien als in het volgende voorbeeld. Niet alle verschillende opties voor het maken van bestanden worden hier weergegeven. Dit is inbegrepen om u te helpen begrijpen hoe een voltooid aantekenvel zou kunnen kijken.

![](assets/cretetraits.png)

Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
