---
description: Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Bulkverwijdering
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# Bulkverwijdering{#bulk-delete}

Met Bulk verwijderen kunt u meerdere segmenten, kenmerken, mappen, afgeleide signalen, gegevensbronnen, modellen en doelen met één bewerking verwijderen. Volg de onderstaande instructies om een aanvraag voor bulkverwijdering in te dienen.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Een bulkschrapping voor bestemmingstoewijzingen zal ontbreken als u segmenten in kaart gebracht aan de bestemming hebt. Verwijder uw segmenten uit die bestemming in het gebruikersinterface alvorens te proberen om bestemmingen bulksgewijs te schrappen. Ook, moeten de eigenschap en de segmentomslagen leeg zijn alvorens u hen kunt schrappen.

Als u meerdere items wilt verwijderen, opent u het dialoogvenster [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Headers]** en kopieer de aanmaakheaders voor het item dat u wilt toevoegen.
2. Klik op de knop **[!UICONTROL Delete]** tab.
3. Plak de verwijderkoppen in de eerste rij van het updatewerkblad.
4. Plak of typ de id&#39;s voor de objecten die u wilt verwijderen in de kolom onder de koptekst.
5. Verstrek de vereiste [loginformatie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

   Het werkblad maakt een [!UICONTROL Results] kolom. De [!UICONTROL Results] de kolom keert een bericht terug dat erop wijst als het punt of een foutenmelding is geschrapt.
Voordat u gegevens invoert, moet uw bulkupdatewerkblad er ongeveer als volgt uitzien:

![](assets/delete.png)

Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
