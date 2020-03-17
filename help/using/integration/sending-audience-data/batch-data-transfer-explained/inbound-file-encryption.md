---
description: Als optie kunt u gegevensbestanden versleutelen met PGP-codering wanneer u ze naar Audience Manager verzendt.
seo-description: Als optie kunt u gegevensbestanden versleutelen met PGP-codering wanneer u ze naar Audience Manager verzendt.
seo-title: PGP-codering van bestand voor binnenkomende gegevenstypen
solution: Audience Manager
title: PGP-codering van bestand voor binnenkomende gegevenstypen
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: b2e0b560a944f2ad63a48476be647f1355712342

---


# PGP-codering van bestand voor binnenkomende gegevenstypen{#file-pgp-encryption-for-inbound-data-types}

U kunt gegevensbestanden coderen met [!DNL PGP] codering wanneer u deze naar Audience Manager verzendt.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] codering omvat bestandscompressie. Wanneer het verzenden van [!DNL PGP] gecodeerde binnenkomende dossiers zorg ervoor u hen niet [comprimeert](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) gebruikend gzip (`.gz`).
>
>[!DNL PGP] Gecodeerde binnenkomende bestanden die ook worden [gecomprimeerd](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) , zijn ongeldig in Audience Manager.

Volg de onderstaande stappen om binnenkomende gegevensbestanden te coderen.

1. Download de openbare sleutel [van](./assets/adobe_pgp.pub)Audience Manager.
2. Importeer de openbare sleutel naar de vertrouwde opslag.

   Als u bijvoorbeeld [!DNL GPG]de opdracht gebruikt, kan deze op het volgende lijken:

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

   Alle gecodeerde gegevens moeten worden gebruikt `.pgp` of `.gpg` als bestandsextensie (bijvoorbeeld `ftp_dpm_100_123456789.sync.pgp` of `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager ondersteunt alleen het algoritme voor [!DNL Advanced Encryption Standard (AES)] gegevenscodering. Audience Manager ondersteunt alle sleutelgrootten.
