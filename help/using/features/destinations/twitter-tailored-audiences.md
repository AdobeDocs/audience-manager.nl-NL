---
description: In dit artikel wordt uitgelegd hoe u Aangepast publiek voor Twitter kunt configureren voor zowel nieuwe als bestaande integratie.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Aangepast publiek voor Twitter configureren als op apparaat gebaseerde zelfbediening
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 0%

---

# Configureren [!DNL Twitter Custom Audiences] als op apparaat-Gebaseerde Bestemming van de Zelfbediening {#configure-twitter}

Dit artikel verklaart hoe te om een integratie te vormen met [Aangepast publiek voor twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Vereisten {#prerequisites}

Voordat u uw [!DNL Twitter Custom Audiences] doel, zorg ervoor u aan de volgende voorwaarden voldoet.

* Uw [!DNL Twitter Ads] account moet in aanmerking komen voor reclame. Nieuw [!DNL Twitter Ads] de rekeningen komen de eerste twee weken na het aanmaken ervan niet in aanmerking voor reclame.
* Uw [!DNL Twitter] gebruikersaccount waarvoor u in Audience Manager toegang hebt toegestaan, moet [Partner-publieksmanager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) machtiging ingeschakeld.
* Bij het maken van de eerste [!DNL Twitter Custom Audiences] doel in uw Audience Manager-instantie, neemt u contact op met de Adobe Consulting of de klantenservice om de [!DNL Twitter] ID-synchronisatie (gegevensbron-id = 1123) voor uw account. Dit is vereist voor de juiste synchronisatie tussen Audience Manager en [!DNL Twitter].

## Een nieuwe toevoegen [!DNL Twitter Custom Audiences] Doel {#add-new-twitter-destination}

In deze sectie worden de stappen beschreven die u moet volgen bij het configureren van een nieuwe, op apparaten gebaseerde bestemming voor [!DNL Twitter Custom Audiences]. In dit scenario wordt ervan uitgegaan dat u geen bestaand scenario hebt [!DNL Twitter Custom Audiences] bestemming geconfigureerd via uw Adobe-consultant of klantenservice.

### Stap 1. Verifiëren met [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Voordat u de op een apparaat gebaseerde bestemming kunt toevoegen, moet u de Audience Manager en uw [!DNL Twitter Custom Audiences] account. Dit doet u als volgt:

1. Meld u aan bij uw Audience Manager-account en ga naar **[!DNL Administration > Integrated Accounts]**. Als u een eerder gevormde integratie met een bestemmingsplatform hebt, zou u het in deze pagina moeten zien die. Anders is de pagina leeg.
1. Klik op **[!DNL Add Account]**.
1. Selecteren [!DNL Twitter Custom Audiences] en klik op **[!DNL Confirm]** om te worden omgeleid naar de authentificatiepagina.

   ![geïntegreerde platforms](assets/dbd-integrated-platforms.png)

1. Nadat u de verificatie hebt voltooid, wordt u doorgestuurd naar de Audience Manager waar u de bijbehorende adverteerderaccounts kunt bekijken. Selecteer het adverteerderaccount dat u wilt gebruiken en klik op **[!DNL Confirm]**.

### Stap 2. Een nieuwe op apparaten gebaseerde bestemming maken {#step2-create-new-destination}

Nadat u Audience Manager en uw [!DNL Twitter Custom Audiences]kunt u de nieuwe bestemming maken. Dit doet u als volgt:

>[!NOTE]
>
>U kunt de naam van een bestaand op apparaat gebaseerd doel niet wijzigen. Zorg ervoor om een naam te verstrekken die u zal helpen de bestemming correct identificeren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!DNL Audience Data > Destinations]** en klik op **[!DNL Create Destination]**.
1. In de **[!DNL Basic Information]** in, voert u een **[!DNL Name]** en **[!DNL Description]** voor uw nieuwe bestemming, en gebruik de montages hieronder: ![instellen](assets/dbd-new-basic.png)
1. Klik op **[!DNL Next]**.
1. Kies de optie [Labels voor gegevensexport](/help/using/features/data-export-controls.md#controls-labels) die u voor dit doel wilt instellen.
1. Klik op **[!DNL Save]**.
1. In de **[!DNL Segment Mappings]** selecteert u de publiekssegmenten die u naar deze bestemming wilt verzenden.
1. Sla het doel op.

## Overwegingen bij het toewijzen van segmenten {#segment-mapping-considerations}

Wanneer doelsegmenten worden toegewezen aan [!UICONTROL Twitter]moet u ervoor zorgen dat aan de volgende vereisten voor segmentnaamgeving wordt voldaan:

* Verstrek de mens-leesbare namen van de segmentafbeelding. Wij adviseren gebruikend de zelfde naam die u voor de segmenten van de Audience Manager gebruikte.
* Gebruik geen speciale tekens (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in segment- en segmenttoewijzingsnamen. Als de naam van het segment van uw Audience Manager deze tekens bevat, verwijdert u deze voordat u het segment toewijst aan een [!UICONTROL Twitter] bestemming.

### Voorbeeld

* Segment- of toewijzingsnaam corrigeren: &quot;Amerikaanse en Europese kopers&quot;;
* Onjuiste segment- of toewijzingsnaam: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>U kunt de namen van al toegewezen segmenten niet wijzigen. Audience Manager gebruikt de segmentnamen om de segmenten in de integratie correct te identificeren.

## Aandachtspunten {#match-rates-considerations}

* De integratie tussen Audience Manager en [!UICONTROL Twitter Custom Audiences] ondersteunt historische publieksbackfills. Alle segmentkwalificaties worden verzonden naar [!UICONTROL Twitter] wanneer u de bestemming maakt.

## Problemen oplossen {#troubleshooting}

Wanneer het vormen van of het verzenden van gegevens naar de bestemming van het publiek van de Douane van Twitter, zou u op de hieronder beschreven fouten kunnen lopen. In deze sectie wordt uitgelegd wat de fouten kan veroorzaken en hoe u deze kunt corrigeren.

| Foutbericht | Voorval/Reden | Resolutie |
|---|---|---|
| `Internal server error` | Dit foutbericht wordt weergegeven in de gebruikersinterface van de Audience Manager wanneer u een nieuwe toepassing probeert toe te voegen [!DNL Twitter] een verouderde versie van de Twitter API gebruiken. | Neem contact op met de klantenservice van Adobe. |
| `Twitter Error: This request is not properly authenticated` | Dit foutenbericht wordt getoond in de UI van de Audience Manager wanneer het proberen om segmenten met niet gestaafde segmentnamen aan de bestemming in kaart te brengen. | Controleer de toegewezen segmentnamen en zorg ervoor dat deze geen niet-ondersteunde tekens bevatten. Zie [segmenttoewijzingsoverwegingen](#segment-mapping-considerations) voor de lijst met niet-ondersteunde tekens. |
| `Twitter Error: Account XXXXXXXXX was not found` | Dit foutenbericht wordt getoond in de Audience Manager UI wanneer de geloofsbrieven die voor de bestemming worden gevormd niet worden gemachtigd om tot de overeenkomstige rekening van Twitter te toegang te hebben Adds. | <ul><li>Zorg ervoor dat de accountgegevens die u gebruikt, voldoen aan de [voorwaarden](#prerequisites).</li><li>Navigeer naar de gebruikersinterface voor Twitter-advertenties met dezelfde referenties en controleer of het juiste publiek onder de bijbehorende interface wordt weergegeven `XXXXXXXXX` account. </li></ul> |