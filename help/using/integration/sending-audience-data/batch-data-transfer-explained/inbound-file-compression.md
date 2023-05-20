---
description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Bestandscompressie voor binnenkomende dataoverdrachtbestanden
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 6%

---

# Bestandscompressie voor binnenkomende dataoverdrachtbestanden{#file-compression-for-inbound-data-transfer-files}

U kunt gegevensbestanden comprimeren wanneer u ze naar de Audience Manager verzendt.

<!-- inbound-file-compression.xml -->

Audience Manager ondersteunt gzip (`.gz`) voor binnenkomende, asynchrone gegevensoverdracht.

Audience Manager ondersteunt ook ongecomprimeerde bestanden.

>[!IMPORTANT]
>
>Codering voor inkomende bestanden die zijn gecomprimeerd met gzip (`.gz`).
>
>Om binnenkomende dossiers te coderen en te comprimeren, gebruik [PGP-codering](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] codering omvat bestandscompressie.

## Amazon S3-compressie

Voor levering aan [!DNL Amazon S3]moet u `.gz` of ongecomprimeerde bestanden. Gecomprimeerde bestanden moeten 1 GB of kleiner zijn. Als de bestanden groter zijn, bespreek dan het bestands- en overdrachtsproces met de klantenservice. Hoewel [!DNL Audience Manager] zeer grote bestanden kunnen verwerken. Mogelijk zijn er manieren om de bestandsgrootte te verkleinen of de gegevensoverdracht efficiënter te maken.

>[!IMPORTANT]
>
>Uw [!DNL FTP] client moet binaire modus gebruiken om gecomprimeerde of gecodeerde bestanden over te brengen. Gecomprimeerde of gecodeerde bestanden verzonden in [!DNL ASCII] wordt het gegevensoverdrachtbestand beschadigd.

## Aanbevolen werkwijzen

* Bestanden moeten [!DNL .gzip] gecomprimeerd (en een [!DNL .gz] bestandsextensie).
* De maximale gecomprimeerde bestandsgrootte voor een `.gz` gecomprimeerd bestand is 1 GB.
* De optimale gesplitste formaten, voor de snelste/vroegste verwerking van uw dossiers, zijn ongeveer 1 GB ongecomprimeerd of 200-300 MB gecomprimeerd.
* [!DNL Amazon S3] Hiermee stelt u een eigen, maximale bestandsgrootte van 5 GB in voor geüploade bestanden.
