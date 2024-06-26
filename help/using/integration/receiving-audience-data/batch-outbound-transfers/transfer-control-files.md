---
description: Transfer-control (.info) dossiers verstrekken meta-gegevensinformatie over dossieroverdrachten zodat de partners kunnen verifiëren dat de Audience Manager correct behandelde dossieroverdrachten.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: Overdrachtbeheerbestanden voor logboekbestandoverdracht
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Overdrachtbeheerbestanden voor logboekbestandoverdracht {#transfer-control-files-for-log-file-transfers}

Overdrachtscontrole ([!DNL .info]) bevatten metagegevens over bestandsoverdrachten, zodat partners kunnen controleren of de Audience Manager de bestandsoverdracht correct heeft verwerkt.

[!DNL Audience Manager] verzendt een overdracht-controle dossier naar een partner met elke dossieroverdracht. Vanwege de multithread-aard van de [!DNL FTP] uitgever, zou het overdrachtcontrole dossier kunnen worden verzonden alvorens de daadwerkelijke dossiers worden gebeëindigd overbrengend.

De metagegevens in het dialoogvenster [!DNL .info] bestand laat partners:

* bepalen wanneer een volledige overdrachtscyclus is voltooid (het totale aantal bestanden in de reeks is afgeleverd);
* Bepaal of een bestand in de reeks volledig/correct is (door de grootte van het bestand in bytes en het totale aantal regels te onderzoeken).
* Valideer het aantal rijen in Raw-bestanden in omgekeerde volgorde het aantal rijen nadat de bestanden in de database zijn geladen aan de ontvangende kant (bestandsgrootte in regels).

## Naamgevingsconventies voor bestanden {#file-naming-conventions}

Het overdrachtcontrole-bestand heeft dezelfde naam als de hoofdmap van de batch/reeks met een [!DNL .info] bestandsextensie.s

Als het eerste bestand in de reeks bijvoorbeeld een naam had: [!DNL ftp_12345_67890_full_1500727351632-1.sync], krijgt het controlebestand een naam [!DNL ftp_12345_67890_iter_1500727351632.info].

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
> De totale nummers van de batch zijn exclusief voor de [!DNL .info] bestand zelf. De totalen omvatten dus niet de [!DNL .info] bestand, de grootte van de byte of het aantal regels.
>
> De grootte van de byte van dossiers en de lijnaantallen zijn inclusief om het even welke kopbal en (lege) lijnen/rijen spacer. Als u het aantal feitelijke gegevenslijnen/rijen wilt ophalen, verwijdert u koppen.
>
> De totale regels in batch en de totale byte zijn inclusief koptekst- en spatietijen.
