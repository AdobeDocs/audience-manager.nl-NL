---
description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
seo-description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
solution: Audience Manager
title: IP-adressen onzichtbaar maken
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 2%

---


# IP-adressen onzichtbaar maken {#ip-obfuscation}

Gebruik deze eigenschap om IP adressen te verduisteren die in Audience Manager worden verzameld.

## Overzicht en methode {#overview-and-methodology}

Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.

### IP Obfuscetiemethode

Volgens de beginselen van &quot;Privacy door Ontwerp&quot;, staat de Adobe Audience Manager klanten toe om IP verwarring van de UI, of globaal over alle geografische regio&#39;s of voor specifieke landen toe te laten. Wanneer u dit het plaatsen toelaat, wordt het laatste octet (het laatste gedeelte) van het IP adres onmiddellijk verworpen wanneer het IP adres in Audience Manager wordt opgenomen. De Audience Manager verwerpt dit deel van het IP adres voorafgaand aan verwerking (met inbegrip van vóór om het even welke facultatieve geografische raadpleging of registreren van het IP adres). Bijvoorbeeld:

* Voor verwarring: `255.255.255.255`
* Na verduistering: `255.255.255.0`

Zie ook, het Verzamelen van IP adressen en IP de Verduistering van het Adres in onze sectie [van de Privacy van](/help/using/overview/data-security-and-privacy/data-privacy.md)Gegevens.

## IP de Vereisten van de Obfuscatie van het Adres {#ip-obfuscation-requirements}

IP de adresverwarring is beschikbaar slechts aan de rekeningen van de Audience Manager beheerder. Zie Gebruikers [](/help/using/features/administration/administration-overview.md#create-users) maken om te begrijpen hoe u beheerdersrechten voor een gebruiker kunt toewijzen.

>[!NOTE]
>
> Door het grote volume van gegevens die door Audience Manager worden verwerkt, kunnen de IP verduisteringsveranderingen tot 4 uren duren om van kracht te worden, vanaf het ogenblik dat u de montages bijwerkt.

## Vorm IP de Obfuscatie van het Adres {#configure-ip-obfuscation}

Volg de stappen hieronder om IP adresverwarring te vormen.

1. Meld u aan bij de Audience Manager met een beheerdersaccount en ga naar **Beheer > Privacy**.
2. Kies het type van IP verduistering dat u wilt gebruiken.
   1. **Obfusceer alle IP adressen:** Selecteer deze optie als u wilt dat de Audience Manager de laatste octet van alle IP-adressen van de bezoeker verduistert, ongeacht het gebied waaruit deze afkomstig zijn.
   2. **Obfuscate IP adressen voor specifieke landen:** Selecteer deze optie om de Audience Manager te laten verduisteren het laatste octet van bezoekerIP adressen voor specifieke landen. Gebruik de **Lijst van Landen** of het overeenkomstige gebied van het **Onderzoek** om de landen te vinden om IP verwarring voor toe te laten, en + te klikken pictogram om hen aan de **Geselecteerde voor Verduistering** lijst toe te voegen. Als u alle vereiste landen hebt toegevoegd aan de lijst **Geselecteerd voor verwarring** , klikt u op **Opslaan**.

![](assets/ip-obfuscation.png)

## IP de Obfuscatie van het Adres onbruikbaar maken {#disable-ip-obfuscation}

Om IP adresverwarring globaal onbruikbaar te maken, ga naar **Beleid > Privacy**, selecteer **verduisteren IP adressen** niet, en klik **sparen**.

Om IP adresverwarring voor specifieke landen onbruikbaar te maken, vind de landen in **Geselecteerd voor Verduistering** lijst, dan hun overeenkomstige **X** pictogram klikken. Klik op **Opslaan** als u klaar bent.

## Verwante begrippen {#related-concepts}

* [Data Privacy](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP de Demonstratie van de Video van de Verduistering van het Adres
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

