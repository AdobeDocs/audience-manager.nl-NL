---
description: Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Bulk verwijderen
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Bulk verwijderen{#bulk-delete}

Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[ RBAC groepstoestemmingen ](../../features/administration/administration-overview.md) die in [!DNL Audience Manager] worden toegewezen UI wordt geëerd in [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Een bulkschrapping voor bestemmingstoewijzingen zal ontbreken als u segmenten in kaart gebracht aan de bestemming hebt. Verwijder uw segmenten uit die bestemming in het gebruikersinterface alvorens te proberen om bestemmingen bulksgewijs te schrappen. Ook, moeten de eigenschap en de segmentomslagen leeg zijn alvorens u hen kunt schrappen.

Als u meerdere items wilt verwijderen, opent u het werkblad van [!UICONTROL Bulk Management Tools] en:

1. Klik op de tab **[!UICONTROL Headers]** en kopieer de kopteksten voor het item dat u wilt toevoegen.
2. Klik op de tab **[!UICONTROL Delete]** .
3. Plak de verwijderkoppen in de eerste rij van het updatewerkblad.
4. Plak of typ de id&#39;s voor de objecten die u wilt verwijderen in de kolom onder de koptekst.
5. Verstrek het vereiste [ login informatie ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik **[!UICONTROL Submit]**.

   In het werkblad wordt een kolom [!UICONTROL Results] gemaakt. De kolom [!UICONTROL Results] retourneert een bericht dat aangeeft of het item is verwijderd of een foutbericht.
Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/delete.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie [ het Oplossen van problemen voor de Hulpmiddelen van het Beheer van het Bulk ](../../reference/bulk-management-tools/bulk-troubleshooting.md).
