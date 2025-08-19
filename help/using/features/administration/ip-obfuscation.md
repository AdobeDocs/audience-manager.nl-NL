---
description: Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP de Obfuscatie van het Adres
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# IP de Obfuscatie van het Adres {#ip-obfuscation}

Gebruik deze eigenschap om IP adressen te verduisteren die in Audience Manager worden verzameld.

## Overzicht en methodologie {#overview-and-methodology}

Uw bedrijf kan IP adres in vele landen wegens mondiale privacyverordeningen willen verduisteren. Met Audience Manager kunt u IP-adressen van bezoekers globaal of per land verduisteren.

### IP Obfuscetiemethode

Volgens de beginselen van &quot;Privacy door Ontwerp&quot; staat Adobe Audience Manager klanten toe om IP-verduistering vanuit de gebruikersinterface mogelijk te maken, globaal voor alle geografische regio&#39;s of voor specifieke landen. Wanneer u dit het plaatsen toelaat, wordt het laatste octet (het laatste gedeelte) van het IP adres onmiddellijk verworpen wanneer het IP adres in Audience Manager wordt opgenomen. Audience Manager verwerpt dit deel van het IP adres voorafgaand aan verwerking (met inbegrip van vóór om het even welke facultatieve geografische raadpleging of registreren van het IP adres). Bijvoorbeeld:

* Voor verwarring: `255.255.255.255`
* Na verduistering: `255.255.255.0`

Zie ook, het Verzamelen van IP adressen en IP de Verduistering van het Adres in onze [ sectie van de Privacy van Gegevens ](/help/using/overview/data-security-and-privacy/data-privacy.md).

### IP Voorrang van de Verduistering {#precedence}

[ datastream-vlakke IP verwarring ](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=nl-NL#create) neemt belangrijkheid over om het even welke IP die optieoptie in Audience Manager wordt geplaatst, en het wordt toegepast op alle IP adressen. Elke opzoekhandeling van de geolocatie door Audience Manager wordt beïnvloed door de optie op gegevensstroomniveau [!UICONTROL IP obfuscation] . Een opzoekhandeling naar een geolocatie in Audience Manager, gebaseerd op een volledig verduisterde IP, zal resulteren in een onbekend gebied en alle segmenten op basis van de resulterende geolocatiegegevens zullen niet worden uitgevoerd.

## IP de Vereisten van de Obfuscatie van het Adres {#ip-obfuscation-requirements}

IP de adresverwarring is beschikbaar slechts aan de beheerderrekeningen van Audience Manager. Zie [ Gebruikers ](/help/using/features/administration/administration-overview.md#create-users) creëren om te begrijpen hoe te om beheerdervoorrechten voor een gebruiker toe te wijzen.

>[!NOTE]
>
> Vanwege het grote volume gegevens dat door Audience Manager wordt verwerkt, kunnen wijzigingen in de IP-verduistering tot 4 uur in werking treden, vanaf het moment dat u de instellingen bijwerkt.

## Vorm IP de Obfuscatie van het Adres {#configure-ip-obfuscation}

Volg de stappen hieronder om IP adresverwarring te vormen.

1. Login aan Audience Manager met een beheerderrekening en ga naar **Beleid > Privacy**.
2. Kies het type van IP verduistering dat u wilt gebruiken.
   1. **verduisteren alle IP adressen:** selecteer deze optie om Audience Manager te hebben verduisteren het laatste octet van alle bezoekerIP adressen, ongeacht het gebied zij uit voortkomen.
   2. **Obfuscate IP adressen voor specifieke landen:** selecteer deze optie om Audience Manager te hebben verduisteren het laatste octet van bezoekerIP adressen voor specifieke landen. Gebruik de **Lijst van Landen** of het overeenkomstige **3&rbrace; gebied van het Onderzoek &lbrace;om de landen te vinden om IP verwarring voor toe te laten, en + pictogram te klikken om hen aan** toe te voegen Geselecteerd voor de lijst van de Verduistering **.** Zodra u alle vereiste landen aan **selecteerde voor Verduistering** lijst hebt toegevoegd, klik **sparen**.

![](assets/ip-obfuscation.png)

## IP de Obfuscatie van het Adres onbruikbaar maken {#disable-ip-obfuscation}

Om IP adresverwarring globaal onbruikbaar te maken, ga naar **Beleid > Privacy**, uitgezocht **verduisteren IP adressen** niet, en klik **sparen**.

Om IP adresverwarring voor specifieke landen onbruikbaar te maken, vind de landen in **Geselecteerd voor Verduistering** lijst, dan hun overeenkomstige **X** pictogram klikken. Klik **sparen** wanneer u wordt gedaan.

## Verwante concepten {#related-concepts}

* [ Privacy van Gegevens ](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP de Demonstratie van de Video van de Verduistering van het Adres
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
