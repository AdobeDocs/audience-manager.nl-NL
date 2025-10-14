---
description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Testgroepen beheren
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Testgroepen beheren {#manage-test-groups}

Deze procedure begeleidt u door de stappen nodig om, een testgroep in [!UICONTROL Audience Lab] tot stand te brengen uit te geven of te schrappen.

## Segmenttestgroepen maken {#create-test-groups}

### Vereisten

<!-- create-test-group.xml -->

* U moet minstens één **opstelling hebben van het omzettingsspoor**. U kunt de eigenschappen van de opstellingsomzetting in [&#x200B; Trait Builder &#x200B;](../../features/traits/create-onboarded-rule-based-traits.md), door **omzetting** als gebeurtenistype te selecteren. Voor meer informatie over welke omzettingseigenschappen zijn en hoe te opstelling hen, hebben wij a [&#x200B; video &#x200B;](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) voor u voorbereid.

  >[!IMPORTANT]
  >
  >[&#x200B; de sporen van de Omslag &#x200B;](../../features/traits/about-folder-traits.md) worden **niet gesteund** door [!UICONTROL Audience Lab]. Het plaatsen van het [&#x200B; Type van Gebeurtenis &#x200B;](../../features/traits/create-onboarded-rule-based-traits.md) van een omslagspoor aan **omzetting** zal geen gegevens in [!UICONTROL Audience Lab] voor dat specifieke omslagspoor produceren.

* Voor bedrijven die [&#x200B; op rol-Gebaseerd Toegangsbeheer &#x200B;](../../features/administration/administration-overview.md) gebruiken: wijs [!UICONTROL Audience Lab] [&#x200B; vervangingstoestemming &#x200B;](../../features/administration/administration-overview.md#wild-card-permissions) aan **[!UICONTROL User Groups]** toe om toegang te verlenen. Met deze machtiging kan de gebruiker de resultaten van een test maken en bekijken. Een gebruiker zal slechts segmenten van een gegevensbron kunnen gebruiken zij **lezen** en **kaart aan bestemmings** voorrechten voor hebben. De gebruiker zal omzettingseigenschappen van een gegevensbron slechts kunnen gebruiken waarvoor zij **&quot;gelezen&quot;** toestemmingen hebben. Een gebruiker zal slechts bestemmingen kunnen zien zij tot ook toegang hebben. Voordat u dus de jokertekenmachtiging [!DNL Audience Lab] aan een groep toevoegt, moet u controleren of de groep het volgende heeft:
   * toegang tot leesbare relevante omzettingskenmerken;
   * toegang tot lees- en kaartrelevante segmenten voor tests;
   * toegang tot relevante bestemmingen.

Een nieuwe [!UICONTROL Segment Test Group] maken:

1. Selecteer **[!UICONTROL Create New Test Group]** in het [!UICONTROL Audience Lab] dashboard om de wizard te starten.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Vul een **[!UICONTROL Test Group Name]** en een **[!UICONTROL Description]** in.
   * Kies **[!UICONTROL Base Segment]** door in de bestandsbrowser te navigeren of door in de zoekbalk te typen, bevestig door op **[!UICONTROL Choose Segment.]** te drukken
   * U kunt de testgroep opslaan als een concept en er later opnieuw aan werken.
   * Er verschijnt een waarschuwing als het geselecteerde basissegment al in andere testgroepen wordt gebruikt. Het tweemaal gebruiken van het basissegment kan de omzettingsresultaten voor beide tests vervormen.

1. **[!UICONTROL Allocate Test Segments]**

   * U kunt **tot 15 testsegmenten** tot stand brengen en het percentage apparaten verdelen aangezien u wenst.
   * U kunt de naam van de testsegmenten bewerken door erop te klikken.
   * De percentages worden automatisch gelijkmatig verdeeld naar 100% wanneer nieuwe testsegmenten worden toegewezen. U kunt de percentages vervolgens handmatig bewerken. Klik op het selectievakje nadat u de percentages hebt bewerkt en zorg ervoor dat ze optellen tot 100%. Als dit niet het geval is, kunt u niet verder gaan naar de volgende stap.

1. **[!UICONTROL Set a Control Segment]**

   * Selecteer een controlesegment als u een bepaald deel van het segment wilt opzij zetten dat als controlegroep moet worden gebruikt. Met controlegroepen kunt u de impact zien van de testsegmenten die u hebt gemaakt in vergelijking met een benchmark.
   * U kunt een testsegment selecteren als besturingssegment in de vervolgkeuzelijst of u kunt **[!UICONTROL None]** kiezen als geen besturingselement.
   * Klik op **[!UICONTROL Next]** wanneer u klaar bent.

1. **[!UICONTROL Select Conversion Traits]**

   * Conversietekenmerken toevoegen door deze te typen in het venster Conversietekenmerken. Dit is a **verplichte** stap en u kunt niet aan de volgende stap te werk gaan tenzij u minstens één omzettingseigenschap toevoegt.
   * U kunt maximaal vijf conversietekenmerken desgewenst toevoegen.
   * Er verschijnt een waarschuwing voor het geval u een conversietekenmerk selecteert die al voor andere testgroepen wordt gebruikt.
   * Merk op dat Audience Manager het gebruiken van [&#x200B; omslagtreksporen &#x200B;](/help/using/features/traits/about-folder-traits.md) niet als omzettingseigenschappen steunt. Als u een mapkenmerk selecteert als conversietekenmerk, resulteert dit in 0 aggregaat- en trendrapporten die tijdens de test worden weergegeven.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Typ de gewenste doelen in het zoekveld of gebruik de vervolgkeuzepijl. [!UICONTROL Audience Lab] -testsegmenten kunnen naar URL-, cookie- of server-naar-server doelen worden verzonden.
   * Segmenten naar bestemmingen slepen en neerzetten.
   * Nadat u een segment op een bestemming hebt neergezet, vult u de **[!UICONTROL Destination Mapping Value]** in de doeken in.
   * U kunt het zelfde testsegment naar veelvoudige bestemmingen verzenden en u kunt veelvoudige testsegmenten aan één enkele bestemming toevoegen.
   * De bestemmingen worden grayed uit als zij niet beschikbaar voor een bepaald testsegment zijn dat op [&#x200B; wordt gebaseerd de Controles van de Uitvoer van Gegevens &#x200B;](../../features/data-export-controls.md).
   * De gebruikers zullen slechts de bestemmingen zien zij toegang hebben tot gebaseerd op de [&#x200B; RBAC Gebruikersgroep &#x200B;](../../features/administration/administration-overview.md) zij tot behoren.
   * Tot slot moet u een begindatum voor uw testgroep selecteren. Deze datum geeft het begin aan van de periode waarin uw testgroep wordt gepubliceerd naar bestemmingen. Selecteer **Geen Datum van het Eind** voor een onbepaalde vergelijking van de testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] met een geverifieerd profiel wordt alleen ondersteund in realtime-doelen. Als een testsegment met een regel van de profielfusie van die configuratie naar een op dossier-gebaseerde server-aan-server bestemming wordt verzonden, zou het publiek niet kunnen bevolken.

   Klik op **[!UICONTROL Next]** om de testgroep te bekijken en af te ronden.

1. **[!UICONTROL Summary & Finalize]**

   * Controleer de gegevens die u in de vorige stappen hebt toegevoegd en selecteer **[!UICONTROL Finalize Group]** .
   * Vergeet niet dat een testgroep na het voltooien ervan kan worden gedupliceerd of verwijderd, maar niet kan worden bewerkt.

   >[!NOTE]
   >* U kunt de testgroepen op elk gewenst moment in het ontwerpproces opslaan en later terugkeren naar de wizard. De status van de testgroep zal **[!UICONTROL Draft]** zijn en de testgroep zal geen gegevens naar bestemmingen verzenden tot u de groep van de segmenttest voltooit.
   >* Voor concepttests kunt u teruggaan en de testgroepen bewerken door op **[!UICONTROL Edit]** te klikken in de kaart van de testgroep in de hoofdweergave van [!UICONTROL Audience Lab] .

## Testgroepen segment bewerken {#edit-test-groups}

In [!UICONTROL Audience Lab] kunt u alleen concepttestgroepen bewerken. In de wizard [!UICONTROL Create Segment Test Group] kunt u uw testgroep opslaan als een concept en er later opnieuw aan werken.

1. Ga naar de hoofdweergave van [!UICONTROL Audience Lab] .
1. Zoek naar uw concept testgroepen en selecteer het besturingselement **[!UICONTROL Edit]** in de testgroepkaart.
1. Hervat [&#x200B; creeer de Groep van de Test van het Segment &#x200B;](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) tovenaar en selecteer **[!UICONTROL Finalize Group]** wanneer u wordt gedaan.

## Segmenttestgroepen verwijderen {#delete-test-groups}

1. Ga naar de hoofdweergave van [!UICONTROL Audience Lab] .
1. Zoek de testgroep die u wilt verwijderen. U kunt:

   * drukt u op het besturingselement **[!UICONTROL Delete]** in de testgroepkaart, of
   * druk de titel van de testgroep in de kaart van de testgroep om naar de [&#x200B; mening van de Informatie van de Groep van de Test &#x200B;](../../features/audience-lab/audience-lab-information-view.md) te gaan en de **[!UICONTROL Delete]** controle in de titelbar te drukken.

1. Voor [&#x200B; voltooide testsegmenten &#x200B;](../../features/audience-lab/audience-lab.md#status), zal een alarm u ertoe aanzetten om het Csv- dossier te downloaden om het melden te bewaren als u wenst.
