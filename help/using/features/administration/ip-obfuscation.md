---
description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
seo-description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
solution: Audience Manager
title: IP-adressen onzichtbaar maken
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 2%

---

# IP-adressen onzichtbaar maken {#ip-obfuscation}

Gebruik deze eigenschap om IP adressen te verduisteren die in Audience Manager worden verzameld.

## Overzicht en methodologie {#overview-and-methodology}

Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.

### IP Obfuscetiemethode

Volgens de beginselen van &quot;Privacy door Ontwerp&quot; staat Adobe Audience Manager klanten toe om IP-verduistering vanuit de gebruikersinterface mogelijk te maken, globaal voor alle geografische regio&#39;s of voor specifieke landen. Wanneer u dit het plaatsen toelaat, wordt het laatste octet (het laatste gedeelte) van het IP adres onmiddellijk verworpen wanneer het IP adres in Audience Manager wordt opgenomen. De Audience Manager verwerpt dit deel van het IP adres voorafgaand aan verwerking (met inbegrip van vóór om het even welke facultatieve geografische raadpleging of registreren van het IP adres). Bijvoorbeeld:

* Voor verwarring: `255.255.255.255`
* Na verduistering: `255.255.255.0`

Zie ook, het Verzamelen van IP adressen en IP de Verduistering van het Adres in onze [sectie van de Privacy van Gegevens](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Vereisten van de Obfuscatie van het Adres {#ip-obfuscation-requirements}

IP de adresverwarring is beschikbaar slechts aan de rekeningen van de Audience Manager beheerder. Zie [Gebruikers maken](/help/using/features/administration/administration-overview.md#create-users) om te begrijpen hoe u beheerdersrechten voor een gebruiker kunt toewijzen.

>[!NOTE]
>
> Door het grote volume van gegevens die door Audience Manager worden verwerkt, kunnen de IP verduisteringsveranderingen tot 4 uren duren om van kracht te worden, vanaf het ogenblik dat u de montages bijwerkt.

## Vorm IP de Verduistering van het Adres {#configure-ip-obfuscation}

Volg de stappen hieronder om IP adresverwarring te vormen.

1. Meld u aan bij de Audience Manager met een beheerdersaccount en ga naar **Beheer > Privacy**.
2. Kies het type van IP verduistering dat u wilt gebruiken.
   1. **Verduisteren alle IP adressen:** selecteer deze optie om Audience Manager te hebben verduisteren het laatste octet van alle bezoekerIP adressen, ongeacht het gebied zij uit voortkomen.
   2. **Obfuscate IP adressen voor specifieke landen:** selecteer deze optie om Audience Manager te hebben verduisteren het laatste octet van bezoekerIP adressen voor specifieke landen. Gebruik **Lijst van Landen** of het overeenkomstige **Onderzoek** gebied om de landen te vinden om IP verwarring voor toe te laten, en klik + pictogram om hen toe te voegen aan **Geselecteerd voor Verduistering** lijst. Nadat u alle vereiste landen hebt toegevoegd aan de lijst **Geselecteerd voor Verduistering**, klikt u op **Opslaan**.

![](assets/ip-obfuscation.png)

## IP van het Adres Obfuscation {#disable-ip-obfuscation} onbruikbaar maken

Om IP adresverwarring globaal onbruikbaar te maken, ga naar **Beleid > Privacy**, uitgezocht **verduisteren IP adressen** niet, en klik **sparen**.

Om IP adresverwarring voor specifieke landen onbruikbaar te maken, vind de landen in **Geselecteerd voor Verduistering** lijst, dan hun overeenkomstige **X** pictogram. Klik **Opslaan** wanneer u klaar bent.

## Verwante begrippen {#related-concepts}

* [Data Privacy](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP de Demonstratie van de Video van de Verduistering van het Adres
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
