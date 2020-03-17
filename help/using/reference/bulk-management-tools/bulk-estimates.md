---
description: Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg deze instructies om een bulkschattingsverzoek te doen.
seo-description: Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg deze instructies om een bulkschattingsverzoek te doen.
seo-title: Bulkramingen
solution: Audience Manager
title: Bulkramingen
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulkramingen{#bulk-estimates}

Een bulkraming retourneert de segmentgroottegegevens op basis van segmentregels. Volg deze instructies om een bulkschattingsverzoek te doen.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Het [!UICONTROL Bulk Management Tools] wordt niet *ondersteund door* [!DNL Audience Manager]. Dit instrument is bedoeld voor het gemak en alleen als hoffelijkheid. Voor grote wijzigingen raden we u aan om in plaats daarvan met de API&#39;s van [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) te werken. [RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) die zijn toegewezen in de [!DNL Audience Manager] gebruikersinterface, worden in de [!UICONTROL Bulk Management Tools]gebruikersinterface gerespecteerd.

Als u bulkupdates wilt maken, opent u het [!UICONTROL Bulk Management Tools] werkblad en:

1. Klik op het **[!UICONTROL Headers]** tabblad en kopieer de [!UICONTROL Estimate Segment Size] koptekst.
1. Klik op het **[!UICONTROL Estimate]** tabblad.
1. Plak de schattingskoptekst in de eerste rij van het werkblad met schattingen.
1. Plak of typ de gegevens die u wilt wijzigen in een corresponderende kolom op basis van het koptekstlabel.
1. Klik in de werkbladwerkbalk op de knop Maken die overeenkomt met het item dat u bijwerkt.
Met deze handeling wordt het [!UICONTROL Account Information] dialoogvenster geopend.

1. Geef de vereiste [aanmeldingsgegevens](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) op en klik op **[!UICONTROL Submit]**.

Deze actie leidt tot een [!UICONTROL Response] kolom in het aantekenvel die geschatte segmentgrootte gegevens bevat. Voordat u gegevens invoert, moet het werkblad voor bulkramingen er ongeveer als volgt uitzien:

![](assets/estimate.png)
Als uw bulkupdate een fout terugkeert of ontbreekt, zie het Oplossen van [problemen voor de Hulpmiddelen](../../reference/bulk-management-tools/bulk-troubleshooting.md)van het Beheer van het Bulk.

