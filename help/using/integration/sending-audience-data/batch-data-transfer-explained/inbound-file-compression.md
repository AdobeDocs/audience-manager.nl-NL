---
description: Als optie kunt u gegevensbestanden comprimeren wanneer u ze naar Audience Manager verzendt.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden{#file-compression-for-inbound-data-transfer-files}

U kunt gegevensbestanden comprimeren wanneer u ze naar Audience Manager verzendt.

<!-- inbound-file-compression.xml -->

Audience Manager steunt gzip (`.gz`) compressie voor binnenkomende, asynchrone gegevensoverdrachten.

Audience Manager ondersteunt ook ongecomprimeerde bestanden.

>[!IMPORTANT]
>
>Wij steunen geen encryptie op binnenkomende die dossiers met gzip worden gecomprimeerd (`.gz`).
>
>Om binnenkomende dossiers te coderen en te comprimeren, gebruik [&#x200B; encryptie PGP &#x200B;](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] -codering omvat bestandscompressie.

## Amazon S3-compressie

Voor levering aan [!DNL Amazon S3], moet u `.gz` of niet samengedrukte dossiers gebruiken. Gecomprimeerde bestanden moeten 1 GB of kleiner zijn. Als de bestanden groter zijn, bespreek dan het bestands- en overdrachtsproces met de klantenservice. Hoewel [!DNL Audience Manager] zeer grote bestanden kan verwerken, zijn er mogelijk manieren om de bestandsgrootte te verkleinen of gegevensoverdracht efficiënter te maken.

>[!IMPORTANT]
>
>De [!DNL FTP] -client moet de binaire modus gebruiken om gecomprimeerde of gecodeerde bestanden over te brengen. Gecomprimeerde of gecodeerde bestanden die in de modus [!DNL ASCII] worden verzonden, beschadigen het bestand voor gegevensoverdracht.

## Aanbevolen procedures

* Bestanden moeten [!DNL .gzip] gecomprimeerd zijn (en de bestandsextensie [!DNL .gz] hebben).
* De maximale gecomprimeerde bestandsgrootte voor een `.gz` gecomprimeerd bestand is 1 GB.
* De optimale gesplitste formaten, voor de snelste/vroegste verwerking van uw dossiers, zijn ongeveer 1 GB ongecomprimeerd of 200-300 MB gecomprimeerd.
* [!DNL Amazon S3] stelt een eigen, bestandsgroottelimiet van 5 GB op voor geüploade bestanden.
