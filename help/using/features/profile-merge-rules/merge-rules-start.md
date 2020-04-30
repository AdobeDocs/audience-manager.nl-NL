---
description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-description: Als u de revisie Regels voor samenvoegen van profielen wilt maken, voert u de stappen uit in elk van de procedures die in deze sectie worden beschreven.
seo-title: Aan de slag met regels voor het samenvoegen van profielen
solution: Audience Manager
title: Aan de slag met regels voor het samenvoegen van profielen
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Aan de slag met regels voor het samenvoegen van profielen {#getting-started-with-profile-merge-rules}

Om de stappen in elk van de in deze sectie beschreven procedures te creëren [!UICONTROL Profile Merge Rules], te herzien en te voltooien.

<!-- merge-rules-start.xml -->

## Een apparaatgegevensbron maken {#create-data-source}

Als u een apparaatgegevensbron wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken of bewerken van een apparaatgegevensbron.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Zie Instellingen [gegevensbron en Menuopties](../datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## Gegevens gegevensbron {#details}

De [!UICONTROL Data Source Details] sectie voltooien:

1. Geef de gegevensbron een naam.
2. *(Optioneel)* Beschrijf de gegevensbron. Met een beknopte beschrijving kunt u de rol of het doel van de gegevensbron definiëren.
3. Geef een integratiecode op. Een integratiecode is uw eigen unieke id voor deze gegevensbron.
4. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
5. Selecteer in de **[!UICONTROL ID Definition]** lijst een optie die het type gegevensbron definieert. De volgende opties zijn beschikbaar:
   * **[!UICONTROL Person]**: Een id die één persoon definieert. Deze id kan aan meerdere id&#39; [!DNL Audience Manager] s worden toegewezen.
   * **[!UICONTROL Household]**: Een id die een groep personen definieert. Deze id kan aan meerdere id&#39; [!DNL Audience Manager] s worden toegewezen.

## Besturingselementen voor gegevensexport {#export-controls}

[De Controles](../data-export-controls.md) van de Uitvoer van gegevens zijn facultatieve classificatieregels u op een gegevensbron en een bestemming kunt toepassen. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u deze niet gebruikt [!UICONTROL Data Export Controls].

## Instellingen gegevensbron {#settings}

[!UICONTROL Data Source Settings] biedt meerdere opties, maar deze 2 zijn belangrijk voor het maken van een gegevensbron voor verschillende apparaten:

* **[!UICONTROL Use as Authenticated Profile]**: Deze instelling is standaard geselecteerd. Met deze instelling kunt u een bestand maken [!UICONTROL Profile Merge Rule] met uw eigen geverifieerde gegevens.

* **[!UICONTROL Use as a Device Graph]**: Deze controle is beschikbaar slechts aan rekeningen die als gegevensleverancier worden vermeld. Als u dit selectievakje inschakelt, wordt uw gegevensbron gemaakt als een apparaatgrafiek en kunt u deze delen met andere [!DNL Audience Manager] klanten. Werk samen met uw [!DNL Audience Manager] consultant om als een gegevensaanbieder op te zetten en te bepalen met welke klanten dit [!UICONTROL Data Source] moet worden gedeeld. Uw consultant zal uw account en apparaatgrafiek delen via een intern inrichtingsproces.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Met dit besturingselement kunt u de bewaarperiode voor inactieve id&#39;s van de klant instellen. Dit bepaalt hoe lang de Manager van de Publiek identiteitskaart van de Klant in ons gegevensbestand houdt nadat zij het laatst op het platform van de Manager van de Publiek werden gezien. De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen. Publiek Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.

Met de tekstvelden die aan deze instellingen zijn gekoppeld, kunt u de naam van de toepassing wijzigen in een alias die wordt weergegeven in de opties [!UICONTROL Data Source] voor de regel voor het samenvoegen van [](merge-rule-definitions.md)profielen. Als u bijvoorbeeld een alias toevoegt aan **[!UICONTROL Use as Authenticated Profile]**, wordt die naam weergegeven in de [!UICONTROL Authenticated Profile Options] lijst. Als u een alias aan toevoegt **[!UICONTROL Use as a Device Graph]**, verschijnt die naam in de [!UICONTROL Device Options] lijst.

## Een regel voor het samenvoegen van profielen maken {#create-profile-merge-rule}

Als u een sectie wilt maken, gaat u naar [!UICONTROL Profile Merge Rule]**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** en voert u de stappen uit voor elke sectie die hier wordt beschreven.

U kunt maximaal drie samenvoegregels maken nadat u een apparaatgegevensbron hebt ingesteld. U krijgt toegang tot een vierde Regel van de Fusie van het Profiel ([!UICONTROL All Cross-Device Profiles]) als u omhoog voor [Mensen-Gebaseerde Doelen](../destinations/people-based-destinations-overview.md)ondertekent.

Beheerdersmachtigingen zijn vereist voor het maken, bewerken of verwijderen van een regel. Alle gebruikers kunnen bestaande bestanden weergeven en gebruiken [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Vereisten:** Voor het samenstellen van een [!UICONTROL Profile Merge Rule]bestand is een apparaatgegevensbron vereist. Zie [Een gegevensbron](../manage-datasources.md#create-data-source)maken.

>[!TIP]
>
>Zie Opties voor [profielsamenvoegregel Gedefinieerd](merge-rule-definitions.md) voor beschrijvingen van deze verschillende besturingselementen.

## Basisinformatie {#basic-info}

De [!UICONTROL Basic Information] sectie voltooien:

1. Geef de naam [!UICONTROL Profile Merge Rule].
2. *(Optioneel)* Beschrijf de [!UICONTROL Profile Merge Rule]. Een beknopte beschrijving helpt u de rol of het doel van uw regel bepalen.
3. *(Optioneel)* Selecteer deze optie **[!UICONTROL Set as default]** als u deze standaard wilt maken [!UICONTROL Profile Merge Rule]. Nieuwe segmenten worden automatisch gekoppeld aan de standaardregel.

## Besturingselementen voor gegevensexport {#data-export-controls}

[De Controles](../data-export-controls.md) van de Uitvoer van gegevens zijn facultatieve classificatieregels u op uw [!UICONTROL Profile Merge Rule]. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u deze niet gebruikt [!UICONTROL Data Export Controls].

## Opstelling van regel voor samenvoegen van profielen {#profile-merge-rule-setup}

De [!UICONTROL Proflie Merge Rule Setup] sectie voltooien:

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

## Code samenvoegregel configureren {#configure-merge-rule-code}

Volg deze instructies om opstelling de [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL], en mobiele [!DNL SDK] code om met uw fusieregels te werken.

<!-- merge-rules-configure-code.xml -->

### Vereisten

U moet een [apparaatgegevensbron](#create-data-source) en [profielfusieregels](#create-profile-merge-rule) instellen *voordat* u deze procedures voltooit.

## Voor klanten van Adobe Experience Platform Identity Service {#id-service-customers}

De [!UICONTROL Adobe Experience Platform Identity Service] en nieuwste versie van [DIL](../../dil/dil-overview.md) worden aanbevolen wanneer u werkt met [!UICONTROL Profile Merge Rules]. U hoeft deze functie echter niet te gebruiken [!UICONTROL Adobe Experience Platform Identity Service] om met deze functie te werken. Als u alleen werkt [!UICONTROL DIL], raadpleegt u de [oudere DIL-sectie](#legacy-dil) hieronder.

### De functie Customer ID instellen configureren

Wanneer de functie met de id werkt, geeft de [!UICONTROL Adobe Experience Platform Identity Service]functie gedeclareerde id&#39;s door aan `setCustomerIDs` [!DNL Audience Manager]. Als u een regel voor het samenvoegen van profielen wilt gebruiken, moet u zich aanpassen `setCustomerIDs` om de integratiecode te gebruiken die is opgegeven bij het maken van een apparaatgegevensbron. Bijvoorbeeld, zeg u een dwars-apparatengegevensbron met de integratiecode hebt gecreeerd `my_datasource_ic`. Als u een gedeclareerde id wilt doorgeven, voegt u de integratiecode toe aan de functie bezoekersidentiteitskaart, zoals in het onderstaande gewijzigde codevoorbeeld wordt getoond.

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

Zie [Een gegevensbron](#create-data-source) voor meerdere apparaten en een id voor [klanten en verificatiestatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)maken voor meer informatie.

### Functie `DIL.create` configureren

In de meest recente versies van [!UICONTROL DIL] nu wordt de [!UICONTROL declared ID] functie automatisch opgehaald uit de `visitorService` functie in `DIL.create` (zie [Gedeclareerde ID-variabelen](../declared-ids.md#declared-id-variables)). Controleer uw `DIL.create` functie om ervoor te zorgen dat deze op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

In het naamruimte-sleutelwaardepaar is de `*`MCORG`*` -variabele uw [!DNL Experience Cloud] organisatie-id. Als u deze id niet hebt, vindt u deze in het [!UICONTROL Administration] gedeelte van het [!DNL Experience Cloud] dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie [Toediening: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDK&#39;s configureren

Zie de sectie SDK&#39;s [configureren](#configure-sdks-legacy-dil) hieronder.

## Verouderde DIL {#legacy-dil}

Als je het nog niet gebruikt, zou je het echt moeten doen. [!DNL Adobe Experience Platform Identity Service] Maar we begrijpen dat de overgang naar nieuwe code zorgvuldig moet worden overwogen en getest. Controleer in deze gevallen of deze `DIL.create` functie op de juiste wijze is ingesteld, zoals in het onderstaande codevoorbeeld wordt getoond.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Voor meer informatie, zie de erfenissectie in de [!UICONTROL DIL] Gedeclareerde Variabelen [](../declared-ids.md#declared-id-variables)van identiteitskaart

### SDK&#39;s configureren {#configure-sdks-legacy-dil}

Controleer de methoden in de [!DNL SDK] code waarmee u gegevens kunt doorgeven [!UICONTROL declared IDs] van [!DNL Android] en [!DNL iOS] mobiele apparaten. De variabelenamen voor de [!DNL Android] en [!DNL iOS] codebibliotheken zijn hetzelfde:

* `dpid`: De bron-id voor het hele apparaat.
* `dpuuid`: De [!UICONTROL declared ID] (d.w.z. de gebruikersnaam).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type apparaat </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntaxis:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Voorbeeld:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
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

Zie ook Methoden voor [Audience Manager voor Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) en [Audience Manager Methods voor iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Een gegevensbron maken](../manage-datasources.md#create-data-source)

