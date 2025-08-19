---
description: Transfer-control (.info) dossiers verstrekken meta-gegevensinformatie over dossieroverdrachten zodat de partners kunnen verifiëren dat Audience Manager correcte dossieroverdrachten behandelde.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: Bestanden voor bestandsoverdracht overdragen van logbestanden
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Bestanden voor bestandsoverdracht overdragen van logbestanden {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) dossiers verstrekken meta-gegevensinformatie over dossieroverdrachten zodat de partners kunnen verifiëren dat Audience Manager correct dossieroverdrachten behandelde.

[!DNL Audience Manager] verzendt een overdracht-controle dossier naar een partner met elke dossieroverdracht. Vanwege de multithread-aard van de [!DNL FTP] -uitgever kan het overdrachtcontrole-bestand worden verzonden voordat de eigenlijke bestanden zijn overgebracht.

De meta-gegevens in het [!DNL .info] dossier laten partners:

* bepalen wanneer een volledige overdrachtscyclus is voltooid (het totale aantal bestanden in de reeks is afgeleverd);
* Bepaal of een bestand in de reeks volledig/correct is (door de grootte van het bestand in bytes en het totale aantal regels te onderzoeken).
* Valideer het aantal rijen in Raw-bestanden in omgekeerde volgorde het aantal rijen nadat de bestanden in de database zijn geladen aan de ontvangende kant (bestandsgrootte in regels).

## Naamgevingsconventies voor bestanden {#file-naming-conventions}

Het overdrachtsbesturingsbestand heeft dezelfde naam als de hoofdmap van de batch/reeks met een bestandsextensie van [!DNL .info] .

Als het eerste bestand in de reeks bijvoorbeeld de naam [!DNL ftp_12345_67890_full_1500727351632-1.sync] heeft, krijgt het besturingsbestand de naam [!DNL ftp_12345_67890_iter_1500727351632.info] .

## Bestandsindeling {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> Het totale aantal batches is exclusief voor het [!DNL .info] -bestand zelf. Dat wil zeggen dat de totalen geen rekening houden met het bestand [!DNL .info] , de grootte van de byte of het aantal regels.
>
> De grootte van de byte van dossiers en de lijnaantallen zijn inclusief om het even welke kopbal en (lege) lijnen/rijen spacer. Als u het aantal feitelijke gegevenslijnen/rijen wilt ophalen, verwijdert u koppen.
>
> De totale regels in batch en de totale byte zijn inclusief koptekst- en spatietijen.
