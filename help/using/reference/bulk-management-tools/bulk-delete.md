---
description: Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.
seo-description: Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.
seo-title: Bulk verwijderen
solution: Audience Manager
title: Bulk verwijderen
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Bulk verwijderen{#bulk-delete}

Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) die zijn toegewezen in de [!DNL Audience Manager] gebruikersinterface, worden in de [!UICONTROL Bulk Management Tools]gebruikersinterface gerespecteerd.

>[!NOTE]
>
>Een bulkschrapping voor bestemmingstoewijzingen zal ontbreken als u segmenten in kaart gebracht aan de bestemming hebt. Verwijder uw segmenten uit die bestemming in het gebruikersinterface alvorens te proberen om bestemmingen bulksgewijs te schrappen. Ook, moeten de eigenschap en de segmentomslagen leeg zijn alvorens u hen kunt schrappen.

Als u meerdere items wilt verwijderen, opent u het [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op het **[!UICONTROL Headers]** tabblad en kopieer de kopteksten voor het item dat u wilt toevoegen.
2. Klik op het **[!UICONTROL Delete]** tabblad.
3. Plak de verwijderkoppen in de eerste rij van het updatewerkblad.
4. Plak of typ de id&#39;s voor de objecten die u wilt verwijderen in de kolom onder de koptekst.
5. Geef de vereiste [aanmeldingsgegevens](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) op en klik op **[!UICONTROL Submit]**.

   In het werkblad wordt een [!UICONTROL Results] kolom gemaakt. De [!UICONTROL Results] kolom retourneert een bericht dat aangeeft of het item is verwijderd of een foutbericht.
Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/delete.png)

Als uw bulkupdate een fout terugkeert of ontbreekt, zie het Oplossen van [problemen voor de Hulpmiddelen](../../reference/bulk-management-tools/bulk-troubleshooting.md)van het Beheer van het Bulk.
