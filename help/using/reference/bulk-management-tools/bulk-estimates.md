---
description: Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg deze instructies om een bulkschattingsverzoek te doen.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Bulkramingen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Bulkramingen{#bulk-estimates}

Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg deze instructies om een bulkschattingsverzoek te doen.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

Als u bulkupdates wilt maken, opent u de [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op de knop **[!UICONTROL Headers]** en kopieer de [!UICONTROL Estimate Segment Size] header.
2. Klik op de knop **[!UICONTROL Estimate]** tab.
3. Plak de schattingskoptekst in de eerste rij van het werkblad met schattingen.
4. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
5. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het dialoogvenster [!UICONTROL Account Information] in.
6. Verstrek de vereiste [loginformatie](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) en klik op **[!UICONTROL Submit]**.

Met deze handeling maakt u een [!UICONTROL Response] kolom in het werkblad die geschatte segmentgroottegegevens bevat. Voordat u gegevens invoert, moet het werkblad voor bulkramingen er ongeveer als volgt uitzien:

![](assets/estimate.png)
Als de bulkupdate een fout retourneert of mislukt, raadpleegt u [Problemen oplossen voor Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
