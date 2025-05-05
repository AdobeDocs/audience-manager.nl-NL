---
description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP-adressen onzichtbaar maken
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '518'
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

Zie ook, Verzamel IP adressen en IP de Verduistering van het Adres in ons [Sectie Gegevensprivacy](/help/using/overview/data-security-and-privacy/data-privacy.md).

### IP Voorrang van de Verduistering {#precedence}

[IP-verwarring op gegevensstroomniveau](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=nl-NL#create) neemt belangrijkheid over om het even welke IP die optieoptie in Audience Manager wordt geplaatst, en het wordt toegepast op alle IP adressen. Elke opzoekhandeling van de geolocatie door de Audience Manager wordt beïnvloed door het niveau van de gegevensstroom [!UICONTROL IP obfuscation] -optie. Een opzoekhandeling naar een geolocatie in de Audience Manager op basis van een volledig verduisterde IP resulteert in een onbekend gebied en alle segmenten op basis van de resulterende geolocatiegegevens worden niet uitgevoerd.

## IP de Vereisten van de Obfuscatie van het Adres {#ip-obfuscation-requirements}

IP de adresverwarring is beschikbaar slechts aan de rekeningen van de Audience Manager beheerder. Zie [Gebruikers maken](/help/using/features/administration/administration-overview.md#create-users) om te begrijpen hoe u beheerdersrechten voor een gebruiker kunt toewijzen.

>[!NOTE]
>
> Door het grote volume van gegevens die door Audience Manager worden verwerkt, kunnen de IP verduisteringsveranderingen tot 4 uren duren om van kracht te worden, vanaf het ogenblik dat u de montages bijwerkt.

## Vorm IP de Obfuscatie van het Adres {#configure-ip-obfuscation}

Volg de stappen hieronder om IP adresverwarring te vormen.

1. Meld u aan bij de Audience Manager met een beheerdersaccount en ga naar **Beheer > Privacy**.
2. Kies het type van IP verduistering dat u wilt gebruiken.
   1. **Obfusceer alle IP adressen:** Selecteer deze optie als u wilt dat de Audience Manager de laatste octet van alle IP-adressen van de bezoeker verduistert, ongeacht het gebied waaruit deze afkomstig zijn.
   2. **Obfuscate IP adressen voor specifieke landen:** Selecteer deze optie om de Audience Manager te laten verduisteren het laatste octet van bezoekerIP adressen voor specifieke landen. Gebruik de **Landen** of de overeenkomstige **Zoeken** gebied om de landen te vinden om IP verwarring voor toe te laten, en + pictogram te klikken om hen aan toe te voegen **Geselecteerd voor Verduistering** lijst. Zodra u alle vereiste landen aan hebt toegevoegd **Geselecteerd voor Verduistering** lijst, klik **Opslaan**.

![](assets/ip-obfuscation.png)

## IP de Obfuscatie van het Adres onbruikbaar maken {#disable-ip-obfuscation}

Om IP adresverwarring globaal onbruikbaar te maken, ga **Beheer > Privacy**, selecteert u **IP-adressen niet verduisteren** en klik op **Opslaan**.

Om IP adresverwarring voor specifieke landen onbruikbaar te maken, vind de landen in **Geselecteerd voor Verduistering** lijst, en klik dan hun overeenkomstige **X** pictogram. Klikken **Opslaan** als je klaar bent.

## Verwante begrippen {#related-concepts}

* [Data Privacy](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP de Demonstratie van de Video van de Verduistering van het Adres
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
