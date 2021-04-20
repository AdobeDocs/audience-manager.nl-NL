---
description: Als optie kunt u gegevensbestanden versleutelen met PGP-codering wanneer u ze naar de Audience Manager verzendt.
seo-description: Als optie kunt u gegevensbestanden versleutelen met PGP-codering wanneer u ze naar de Audience Manager verzendt.
seo-title: PGP-bestandsversleuteling voor binnenkomende datatypen
solution: Audience Manager
title: PGP-bestandsversleuteling voor binnenkomende datatypen
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 10%

---

# PGP-bestandsversleuteling voor binnenkomende datatypen{#file-pgp-encryption-for-inbound-data-types}

U kunt gegevensbestanden coderen met [!DNL PGP] encryptie wanneer het verzenden van hen naar Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] codering omvat bestandscompressie. Wanneer het verzenden van [!DNL PGP] gecodeerde binnenkomende dossiers zorg ervoor u niet [comprimeert ](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) hen gebruikend gzip (`.gz`).
>
>[!DNL PGP] versleutelde inkomende bestanden die ook zijn  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) gecomprimeerd, zijn ongeldig in de Audience Manager.

Volg de onderstaande stappen om binnenkomende gegevensbestanden te coderen.

1. Download [Audience Manager public key](./assets/adobe_pgp.pub).
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

   Alle gecodeerde gegevens moeten `.pgp` of `.gpg` als bestandsextensie gebruiken (bijvoorbeeld `ftp_dpm_100_123456789.sync.pgp` of `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager ondersteunt alleen het gegevensversleutelingsalgoritme [!DNL Advanced Encryption Standard (AES)]. Audience Manager ondersteunt elke sleutellengte.
