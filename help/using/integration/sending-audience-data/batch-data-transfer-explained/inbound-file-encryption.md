---
description: Als optie kunt u gegevensbestanden versleutelen met PGP-codering wanneer u ze naar Audience Manager verzendt.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: PGP-codering van bestand voor binnenkomende gegevenstypen
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# PGP-codering van bestand voor binnenkomende gegevenstypen{#file-pgp-encryption-for-inbound-data-types}

U kunt gegevensbestanden versleutelen met [!DNL PGP] -codering wanneer u ze naar Audience Manager verzendt.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] -codering omvat bestandscompressie. Wanneer het verzenden van [!DNL PGP] gecodeerde binnenkomende dossiers zorg u niet [&#x200B; comprimeert &#x200B;](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) hen gebruikend gzip (`.gz`).
>
>[!DNL PGP] gecodeerde binnenkomende dossiers die ook [&#x200B; worden samengeperst &#x200B;](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) zijn ongeldig in Audience Manager.

Volg de onderstaande stappen om binnenkomende gegevensbestanden te coderen.

1. Download de [&#x200B; openbare sleutel van Audience Manager &#x200B;](./assets/adobe_pgp.pub).
2. Importeer de openbare sleutel naar de vertrouwde opslag.

   Als u bijvoorbeeld [!DNL GPG] gebruikt, kan de opdracht op het volgende lijken:

   `gpg --import adobe_pgp.pub`

3. Controleer of de sleutel correct is geïmporteerd met de volgende opdracht:

   `gpg --list-keys`

   U zou een bericht moeten zien gelijkend op het volgende:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Codeer de binnenkomende gegevens gebruikend het volgende bevel:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Alle gecodeerde gegevens moeten `.pgp` of `.gpg` gebruiken als de bestandsextensie (bijvoorbeeld `ftp_dpm_100_123456789.sync.pgp` of `ftp_dpm_100_123456789.overwrite.gpg` ).

   >[!NOTE]
   >
   >Audience Manager ondersteunt alleen het [!DNL Advanced Encryption Standard (AES)] -algoritme voor gegevenscodering. Audience Manager ondersteunt elke sleutellengte.
