---
description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.
seo-description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.
seo-title: Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden
solution: Audience Manager
title: Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden{#file-compression-for-inbound-data-transfer-files}

U kunt gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.

<!-- inbound-file-compression.xml -->

Audience Manager ondersteunt gzip-compressie (`.gz`) voor binnenkomende, asynchrone gegevensoverdracht.

Audience Manager ondersteunt ook ongecomprimeerde bestanden.

>[!IMPORTANT]
>
>Codering voor inkomende bestanden die zijn gecomprimeerd met gzip (`.gz`) wordt niet ondersteund.
>
>Gebruik [PGP-codering](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)om binnenkomende bestanden te coderen en te comprimeren. [!DNL PGP] codering omvat bestandscompressie.

## Amazon S3-compressie

Voor levering aan [!DNL Amazon S3], moet u `.gz` of ongecomprimeerde dossiers gebruiken. Gecomprimeerde bestanden moeten 1 GB of kleiner zijn. Als de bestanden groter zijn, bespreek dan het bestands- en overdrachtsproces met de klantenservice. Hoewel u zeer grote bestanden [!DNL Audience Manager] kunt verwerken, zijn er mogelijk manieren om de bestandsgrootte te verkleinen of om de gegevensoverdracht efficiënter te maken.

>[!IMPORTANT]
>
>Uw [!DNL FTP] client moet de binaire modus gebruiken om gecomprimeerde of gecodeerde bestanden over te brengen. Gecomprimeerde of gecodeerde bestanden die in de [!DNL ASCII] modus worden verzonden, beschadigen het bestand voor gegevensoverdracht.

## Aanbevolen werkwijzen

* Bestanden moeten worden [!DNL .gzip] gecomprimeerd (en een [!DNL .gz] bestandsextensie hebben).
* De maximale gecomprimeerde bestandsgrootte voor een `.gz` gecomprimeerd bestand is 1 GB.
* De optimale gesplitste formaten, voor de snelste/vroegste verwerking van uw dossiers, zijn ongeveer 1 GB ongecomprimeerd of 200-300 MB gecomprimeerd.
* [!DNL Amazon S3] Hiermee stelt u een eigen, maximale bestandsgrootte van 5 GB in voor geüploade bestanden.
