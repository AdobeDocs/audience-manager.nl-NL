---
description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-title: Aan de slag met de regels voor profielsamenvoeging
solution: Audience Manager
title: Aan de slag met de regels voor profielsamenvoeging
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 3%

---

# Aan de slag met de regels voor profielsamenvoeging {#getting-started-with-profile-merge-rules}

Als u [!UICONTROL Profile Merge Rules] wilt maken, controleert en voltooit u de stappen in elk van de in deze sectie beschreven procedures.

<!-- merge-rules-start.xml -->

## Een apparaatgegevensbron maken {#create-data-source}

Als u een apparaatgegevensbron wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken of bewerken van een apparaatgegevensbron.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Zie [Instellingen gegevensbron en menuopties](../datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## Gegevens gegevensbron {#details}

De sectie [!UICONTROL Data Source Details] voltooien:

1. Geef de gegevensbron een naam.
2. *(Optioneel)* Beschrijf de gegevensbron. Met een beknopte beschrijving kunt u de rol of het doel van de gegevensbron definiëren.
3. Geef een integratiecode op. Een integratiecode is uw eigen unieke id voor deze gegevensbron.
4. Selecteer **[!UICONTROL Cross Device]** in de lijst **[!UICONTROL ID Type]**.
5. Selecteer in de lijst **[!UICONTROL ID Definition]** een optie die het type gegevensbron definieert. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Person]**: Een id die één persoon definieert. Deze id kan worden toegewezen aan meerdere [!DNL Audience Manager]-id&#39;s.
   * **[!UICONTROL Household]**: Een id die een groep personen definieert. Deze id kan worden toegewezen aan meerdere [!DNL Audience Manager]-id&#39;s.

## Besturingselementen voor data-export {#export-controls}

[De Controles ](../data-export-controls.md) van de Uitvoer van gegevens zijn facultatieve classificatieregels u op een gegevensbron en een bestemming kunt toepassen. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## Instellingen gegevensbron {#settings}

[!UICONTROL Data Source Settings] biedt meerdere opties, maar deze 2 zijn belangrijk voor het maken van een gegevensbron voor verschillende apparaten:

* **[!UICONTROL Use as Authenticated Profile]**: Deze instelling is standaard ingeschakeld. Met deze instelling kunt u een  [!UICONTROL Profile Merge Rule] bestand maken met uw eigen geverifieerde gegevens.

* **[!UICONTROL Use as a Device Graph]**: Deze controle is beschikbaar slechts aan rekeningen die als gegevensleverancier worden vermeld. Als u dit selectievakje inschakelt, wordt uw gegevensbron gemaakt als een apparaatgrafiek en kunt u deze delen met andere [!DNL Audience Manager]-klanten. Werk samen met uw [!DNL Audience Manager]-consultant om op te richten als een gegevensaanbieder en om op te geven met welke klanten dit [!UICONTROL Data Source] moet worden gedeeld. Uw consultant zal uw account en apparaatgrafiek delen via een intern inrichtingsproces.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Met dit besturingselement kunt u de bewaarperiode voor inactieve id&#39;s van de klant instellen. Dit bepaalt hoe lang de Audience Manager identiteitskaart van de Klant in ons gegevensbestand houdt nadat zij het laatst op het platform van de Audience Manager werden gezien. De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen. Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.

Met de tekstvelden die aan deze instellingen zijn gekoppeld, kunt u de naam van de [!UICONTROL Data Source] wijzigen in een alias die wordt weergegeven in de [Opties voor samenvoegregel profiel](merge-rule-definitions.md). Als u bijvoorbeeld een alias toevoegt aan **[!UICONTROL Use as Authenticated Profile]**, wordt die naam weergegeven in de lijst [!UICONTROL Authenticated Profile Options]. Als u een alias aan **[!UICONTROL Use as a Device Graph]** toevoegt, verschijnt die naam in [!UICONTROL Device Options] lijst.

## Een regel voor het samenvoegen van profielen maken {#create-profile-merge-rule}

Als u een [!UICONTROL Profile Merge Rule] wilt maken, gaat u naar **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** en voert u de stappen uit voor elke sectie die hier wordt beschreven.

U kunt maximaal drie samenvoegregels maken nadat u een apparaatgegevensbron hebt ingesteld. U krijgt toegang tot een 4de Regel van de Fusie van het Profiel ([!UICONTROL All Cross-Device Profiles]) als u omhoog voor [Op mensen-Gebaseerde Doelen](../destinations/people-based-destinations-overview.md) ondertekent.

Beheerdersmachtigingen zijn vereist voor het maken, bewerken of verwijderen van een regel. Alle gebruikers kunnen bestaande [!UICONTROL Profile Merge Rules] bekijken en gebruiken.

<!-- create-profile-merge-rule.xml -->

**Vereisten:** een apparaatgegevensbron is vereist om een  [!UICONTROL Profile Merge Rule]bestand te maken. Zie [Een gegevensbron maken](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Zie [Gedefinieerde opties voor het samenvoegen van profielen](merge-rule-definitions.md) voor beschrijvingen van deze verschillende besturingselementen.

## Basisinformatie {#basic-info}

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef de [!UICONTROL Profile Merge Rule] een naam.
2. *(Optioneel)* Beschrijf de  [!UICONTROL Profile Merge Rule]code. Een beknopte beschrijving helpt u de rol of het doel van uw regel bepalen.
3. *(Optioneel)* Selecteer  **[!UICONTROL Set as default]** of u dit als de standaardinstelling wilt instellen  [!UICONTROL Profile Merge Rule]. Nieuwe segmenten worden automatisch gekoppeld aan de standaardregel.

## Besturingselementen voor data-export {#data-export-controls}

[De Controles van de Uitvoer van gegevens ](../data-export-controls.md) zijn facultatieve classificatieregels u op uw kunt toepassen  [!UICONTROL Profile Merge Rule]. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## Opstelling van de Regel van de Samenvoeging van het profiel {#profile-merge-rule-setup}

De sectie [!UICONTROL Proflie Merge Rule Setup] voltooien:

1. Selecteer een **[!UICONTROL Authenticated Option]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Selecteer een **[!UICONTROL Authenticated Profile Option]** (maximaal 3). Dit zijn de [apparaatgegevensbronnen](merge-rules-start.md) die u eerder hebt gemaakt.
3. Selecteer een **[!UICONTROL Device Option]**. De volgende opties zijn beschikbaar:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klik op **[!UICONTROL Save]**.

### Overwegingen bij Adobe Campaign-doelen die ID&#39;s voor andere apparaten gebruiken als gebruikersnamen {#considerations}

Eind 2019 hebben we een aantal verbeteringen in de regels voor het samenvoegen van profielen gepubliceerd om de nauwkeurigheid van batchbestanden die met id&#39;s voor meerdere apparaten zijn gegenereerd, te verbeteren. Deze verbeteringen worden strikt nageleefd in uw Audience Manager-instantie die op maandag 16 maart 2020 wordt gestart. Dientengevolge, zullen de segmenten die aan een bestemming worden in kaart gebracht gebruikend cross-device IDs ophouden producerend de uitvoer in sommige configuraties van de Regels van de Fusie van het Profiel.

Om de correcte integratie tussen uw instantie van de Audience Manager en bestemmingen te verzekeren gebruikend dwars-apparaat IDs, zoals Adobe Campaign, zorg ervoor u aan de volgende vereisten voldoet:

1. Controleer de regel voor het samenvoegen van profielen die wordt gebruikt door de segmenten die zijn toegewezen aan de bestemming van de door Adobe Campaign aangegeven id. De regel voor het samenvoegen van profielen moet de optie [!UICONTROL Last Authenticated Profile] gebruiken, zodat alle geverifieerde profielen kunnen worden opgenomen in de exportbewerking. Als de regel voor het samenvoegen van profielen een andere optie gebruikt, schakelt u deze over naar [!UICONTROL Last Authenticated Profile].
2. Selecteer de gegevensbron voor de Adobe Campaign-declaratie-id in de instellingen voor de regel voor het samenvoegen van profielen.

>[!NOTE]
>
> Als u uw maximumaantal [!UICONTROL Profile Merge Rules] hebt bereikt en hulp nodig hebt bij het configureren van deze op basis van de bovenstaande instructies, neemt u contact op met de klantenservice.

## Code samenvoegregel {#configure-merge-rule-code} configureren

Volg deze instructies om [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL], en mobiele [!DNL SDK] code aan opstelling met uw fusieregels te werken.

<!-- merge-rules-configure-code.xml -->

### Vereisten

U moet een [apparaatgegevensbron](#create-data-source) en [profielfusieregels](#create-profile-merge-rule) *vóór* instellen om deze procedures te voltooien.

## Voor klanten {#id-service-customers} van de Identiteitsdienst van Adobe Experience Platform

De [!UICONTROL Adobe Experience Platform Identity Service] en de recentste versie van [DIL](../../dil/dil-overview.md) worden geadviseerd wanneer het werken met [!UICONTROL Profile Merge Rules]. Nochtans, moet u niet [!UICONTROL Adobe Experience Platform Identity Service] gebruiken om met deze eigenschap te werken. Als u enkel [!UICONTROL DIL] gebruikt, zie [erfenis DIL sectie](#legacy-dil) hieronder.

### De functie Customer ID instellen configureren

Wanneer u met de functie [!UICONTROL Adobe Experience Platform Identity Service] werkt, geeft de functie `setCustomerIDs` gedeclareerde id&#39;s door aan [!DNL Audience Manager]. Als u een regel voor het samenvoegen van profielen wilt gebruiken, moet u `setCustomerIDs` wijzigen om de opgegeven integratiecode te gebruiken wanneer u een gegevensbron voor meerdere apparaten hebt gemaakt. Bijvoorbeeld, zeg u een dwars-apparatengegevensbron met de integratiecode `my_datasource_ic` hebt gecreeerd. Als u een gedeclareerde id wilt doorgeven, voegt u de integratiecode toe aan de functie bezoekersidentiteitskaart, zoals in het onderstaande gewijzigde codevoorbeeld wordt getoond.

#### Generic code sample

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Voorbeeld van gewijzigde code

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Zie [Een apparaatgegevensbron maken](#create-data-source) en [Klantid&#39;s en verificatiestatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) voor meer informatie.

### Functie `DIL.create` configureren

In de meest recente versies van [!UICONTROL DIL] wordt de [!UICONTROL declared ID] nu automatisch opgehaald uit de functie `visitorService` in `DIL.create` (zie [Gedeclareerde ID-variabelen](../declared-ids.md#declared-id-variables)). Controleer de functie `DIL.create` om te controleren of deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

In het namespace zeer belangrijk-waardepaar, is `*`MCORG`*` variabele uw [!DNL Experience Cloud] identiteitskaart van de Organisatie. Als u deze id niet hebt, vindt u deze in de sectie [!UICONTROL Administration] van het [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Beheer: Core Services](https://docs.adobe.com/content/help/nl-NL/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDK&#39;s configureren

Zie de sectie [SDK&#39;s configureren](#configure-sdks-legacy-dil) hieronder.

## Legacy DIL {#legacy-dil}

Als u [!DNL Adobe Experience Platform Identity Service] nog niet gebruikt, zou u echt moeten. Maar we begrijpen dat de overgang naar nieuwe code zorgvuldig moet worden overwogen en getest. Controleer in deze gevallen de functie `DIL.create` om te controleren of deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Zie de sectie [!UICONTROL DIL] in [Gedeclareerde id-variabelen](../declared-ids.md#declared-id-variables) voor meer informatie.

### SDK&#39;s {#configure-sdks-legacy-dil} configureren

Controleer de methoden in uw [!DNL SDK]-code waarmee u [!UICONTROL declared IDs] kunt doorgeven vanaf [!DNL Android] en [!DNL iOS] mobiele apparaten. De variabelenamen voor de codebibliotheken [!DNL Android] en [!DNL iOS] zijn het zelfde:

* `dpid`: De bron-id voor het hele apparaat.
* `dpuuid`: De gebruikersnaam  [!UICONTROL declared ID] (dus de gebruikersnaam).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type apparaat </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android  </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Voorbeeld:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS  </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntaxis:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Voorbeeld:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Zie ook [Methoden voor Audience Managers voor Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) en [Methoden voor Audience Managers voor iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Een databron maken](../manage-datasources.md#create-data-source)

