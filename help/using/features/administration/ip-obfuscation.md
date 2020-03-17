---
description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. De Manager van het publiek staat u toe om bezoekerIP adressen op een globaal of land-door-land basis te verduisteren.
seo-description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. De Manager van het publiek staat u toe om bezoekerIP adressen op een globaal of land-door-land basis te verduisteren.
solution: Audience Manager
title: IP de Obfuscatie van het Adres
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP de Obfuscatie van het Adres {#ip-obfuscation}

Gebruik deze eigenschap om IP adressen te verduisteren die in de Manager van het Publiek worden verzameld.

## Overzicht en methode {#overview-and-methodology}

Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. De Manager van het publiek staat u toe om bezoekerIP adressen op een globaal of land-door-land basis te verduisteren.

### IP Obfuscetiemethode

Volgens de beginselen van &quot;Privacy door Ontwerp&quot;, staat de Manager van het Publiek van Adobe klanten toe om IP verwarring van de UI, of globaal over alle geografische regio&#39;s of voor specifieke landen toe te laten. Wanneer u dit het plaatsen toelaat, wordt het laatste octet (het laatste gedeelte) van het IP adres onmiddellijk verworpen wanneer het IP adres in de Manager van de Publiek wordt opgenomen. De Manager van het publiek verwerpt dit deel van het IP adres voorafgaand aan verwerking (met inbegrip van vóór om het even welke facultatieve geografische raadpleging of registreren van het IP adres). Bijvoorbeeld:

* Voor verwarring: `255.255.255.255`
* Na verduistering: `255.255.255.0`

Zie ook, het Verzamelen van IP adressen en IP de Verduistering van het Adres in onze sectie [van de Privacy van](/help/using/overview/data-security-and-privacy/data-privacy.md)Gegevens.

## IP de Vereisten van de Obfuscatie van het Adres {#ip-obfuscation-requirements}

IP de adresverwarring is beschikbaar slechts aan de beheerderrekeningen van de Manager van de Auditie. Zie Gebruikers [](/help/using/features/administration/administration-overview.md#create-users) maken om te begrijpen hoe u beheerdersrechten voor een gebruiker kunt toewijzen.

>[!NOTE]
>
> Door het grote volume van gegevens die door de Manager van het Publiek worden verwerkt, kunnen IP de verduisteringsveranderingen tot 4 uren duren om van kracht te worden, vanaf het ogenblik dat u de montages bijwerkt.

## Vorm IP de Obfuscatie van het Adres {#configure-ip-obfuscation}

Volg de stappen hieronder om IP adresverwarring te vormen.

1. Meld u aan bij Audience Manager met een beheerdersaccount en ga naar **Beheer > Privacy**.
2. Kies het type van IP verduistering dat u wilt gebruiken.
   1. **Obfusceer alle IP adressen:** Selecteer deze optie als Audience Manager het laatste octet van alle IP-adressen van bezoekers moet verduisteren, ongeacht het gebied waaruit ze afkomstig zijn.
   2. **Obfuscate IP adressen voor specifieke landen:** Selecteer deze optie om Audience Manager te laten verduisteren het laatste octet van bezoekerIP adressen voor specifieke landen. Gebruik de **Lijst van Landen** of het overeenkomstige gebied van het **Onderzoek** om de landen te vinden om IP verwarring voor toe te laten, en + te klikken pictogram om hen aan de **Geselecteerde voor Verduistering** lijst toe te voegen. Als u alle vereiste landen hebt toegevoegd aan de lijst **Geselecteerd voor verwarring** , klikt u op **Opslaan**.

![](assets/ip-obfuscation.png)

## IP de Obfuscatie van het Adres onbruikbaar maken {#disable-ip-obfuscation}

Om IP adresverwarring globaal onbruikbaar te maken, ga naar **Beleid > Privacy**, selecteer **verduisteren IP adressen** niet, en klik **sparen**.

Om IP adresverwarring voor specifieke landen onbruikbaar te maken, vind de landen in **Geselecteerd voor Verduistering** lijst, dan hun overeenkomstige **X** pictogram klikken. Klik op **Opslaan** als u klaar bent.

## Verwante concepten {#related-concepts}

* [Gegevensprivacy](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP de Demonstratie van de Video van de Verduistering van het Adres
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

