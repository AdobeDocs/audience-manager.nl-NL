---
description: Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg de onderstaande instructies om een aanvraag voor een bulkofferte in te dienen.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Bulkramingen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 2%

---

# Bulkramingen{#bulk-estimates}

Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg de onderstaande instructies om een aanvraag voor een bulkofferte in te dienen.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in de [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

Als u bulkupdates wilt maken, opent u de knop [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Headers]** en kopieer de [!UICONTROL Estimate Segment Size] header.
2. Klik op de knop **[!UICONTROL Estimate]** tab.
3. Plak de schattingskoptekst in de eerste rij van het werkblad met schattingen.
4. Plak of typ de gegevens die u wilt wijzigen in een bijbehorende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Deze handeling opent de [!UICONTROL Account Information] in.
6. Geef de vereiste [loginformatie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

Deze handeling maakt een [!UICONTROL Response] kolom in het werkblad die geschatte segmentgroottegegevens bevat. Voordat u gegevens invoert, moet het werkblad voor bulkramingen er ongeveer als volgt uitzien:

![](assets/estimate.png)
Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
