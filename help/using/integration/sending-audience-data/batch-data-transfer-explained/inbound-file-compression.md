---
description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.
seo-description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.
seo-title: Bestandscompressie voor binnenkomende dataoverdrachtbestanden
solution: Audience Manager
title: Bestandscompressie voor binnenkomende dataoverdrachtbestanden
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 9%

---

# Bestandscompressie voor binnenkomende dataoverdrachtbestanden{#file-compression-for-inbound-data-transfer-files}

U kunt gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.

<!-- inbound-file-compression.xml -->

Audience Manager ondersteunt gzip-compressie (`.gz`) voor binnenkomende, asynchrone gegevensoverdracht.

Audience Manager ondersteunt ook ongecomprimeerde bestanden.

>[!IMPORTANT]
>
>We ondersteunen geen codering voor binnenkomende bestanden die zijn gecomprimeerd met gzip (`.gz`).
>
>Om binnenkomende dossiers te coderen en te comprimeren, gebruik [PGP encryptie](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] codering omvat bestandscompressie.

## Amazon S3-compressie

Voor levering aan [!DNL Amazon S3], moet u `.gz` of ongecomprimeerde dossiers gebruiken. Gecomprimeerde bestanden moeten 1 GB of kleiner zijn. Als de bestanden groter zijn, bespreek dan het bestands- en overdrachtsproces met de klantenservice. Hoewel [!DNL Audience Manager] zeer grote bestanden kan verwerken, zijn er mogelijk manieren om de bestandsgrootte te verkleinen of gegevensoverdracht efficiënter te maken.

>[!IMPORTANT]
>
>De [!DNL FTP]-client moet de binaire modus gebruiken om gecomprimeerde of gecodeerde bestanden over te brengen. Gecomprimeerde of gecodeerde bestanden die in de modus [!DNL ASCII] worden verzonden, beschadigen het bestand voor gegevensoverdracht.

## Aanbevolen werkwijzen

* Bestanden moeten [!DNL .gzip] zijn gecomprimeerd (en de bestandsextensie [!DNL .gz] hebben).
* De maximale gecomprimeerde bestandsgrootte voor een `.gz` gecomprimeerd bestand is 1 GB.
* De optimale gesplitste formaten, voor de snelste/vroegste verwerking van uw dossiers, zijn ongeveer 1 GB ongecomprimeerd of 200-300 MB gecomprimeerd.
* [!DNL Amazon S3] Hiermee stelt u een eigen, maximale bestandsgrootte van 5 GB in voor geüploade bestanden.
