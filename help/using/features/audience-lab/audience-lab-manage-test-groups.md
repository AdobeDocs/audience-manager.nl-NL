---
description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-description: Deze procedure begeleidt u door de stappen nodig om, een testgroep in het Laboratorium van de Auditie tot stand te brengen uit te geven of te schrappen
seo-title: Testgroepen beheren
solution: Audience Manager
title: Testgroepen beheren
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1003'
ht-degree: 0%

---


# Testgroepen beheren {#manage-test-groups}

Deze procedure begeleidt u door de stappen nodig om, een testgroep in [!UICONTROL Audience Lab] tot stand te brengen uit te geven of te schrappen.

## Segmenttestgroepen maken {#create-test-groups}

### Vereisten

<!-- create-test-group.xml -->

* U moet minstens één **conversietekenmerk** opstelling hebben. U kunt omzettingseigenschappen in [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md) plaatsen, door **omzetting** als gebeurtenistype te selecteren. Voor meer informatie over welke omzettingseigenschappen zijn en hoe te om hen te opstelling, hebben wij [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) voor u voorbereid.

   >[!IMPORTANT]
   >
   >[Mapkenmerken ](../../features/traits/about-folder-traits.md) worden  **niet** ondersteund door  [!UICONTROL Audience Lab]. Als u [Gebeurtenistype](../../features/traits/create-onboarded-rule-based-traits.md) van een mapkenmerk instelt op **conversie**, worden er geen gegevens gegenereerd in [!UICONTROL Audience Lab] voor die specifieke mapeigenschap.

* Voor bedrijven die [Op rollen gebaseerd Toegangsbeheer](../../features/administration/administration-overview.md) gebruiken: Wijs [!UICONTROL Audience Lab] [vervangingstoestemming](../../features/administration/administration-overview.md#wild-card-permissions) aan **[!UICONTROL User Groups]** toe om toegang te verlenen. Met deze machtiging kan de gebruiker de resultaten van een test maken en bekijken. Een gebruiker kan alleen segmenten gebruiken uit een gegevensbron waarvoor **read** en **map aan doel** rechten gelden. De gebruiker zal omzettingseigenschappen van een gegevensbron slechts kunnen gebruiken waarvoor zij **&quot;lees&quot;toestemmingen** hebben. Een gebruiker zal slechts bestemmingen kunnen zien zij tot ook toegang hebben. Zo, alvorens de [!DNL Audience Lab] vervangingstoestemming aan een groep toe te voegen, zorg ervoor de groep heeft:
   * toegang tot leesbare relevante omzettingskenmerken;
   * toegang tot lees- en kaartrelevante segmenten voor tests;
   * toegang tot relevante bestemmingen.

Nieuwe [!UICONTROL Segment Test Group] maken:

1. Selecteer **[!UICONTROL Create New Test Group]** in [!UICONTROL Audience Lab] dashboard om de tovenaar te beginnen.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Vul een **[!UICONTROL Test Group Name]** en een **[!UICONTROL Description]** in.
   * Kies **[!UICONTROL Base Segment]** door in de bestandenbrowser te navigeren of door in de zoekbalk te typen, bevestig door op **[!UICONTROL Choose Segment.]** te drukken
   * U kunt de testgroep opslaan als een concept en er later opnieuw aan werken.
   * Er verschijnt een waarschuwing als het geselecteerde basissegment al in andere testgroepen wordt gebruikt. Het tweemaal gebruiken van het basissegment kan de omzettingsresultaten voor beide tests vervormen.

1. **[!UICONTROL Allocate Test Segments]**

   * U kunt **tot 15 testsegmenten** tot stand brengen en het percentage apparaten verdelen aangezien u wenst.
   * U kunt de naam van de testsegmenten bewerken door erop te klikken.
   * De percentages worden automatisch gelijkmatig verdeeld naar 100% wanneer nieuwe testsegmenten worden toegewezen. U kunt de percentages vervolgens handmatig bewerken. Klik op het selectievakje nadat u de percentages hebt bewerkt en zorg ervoor dat ze optellen tot 100%. Als dit niet het geval is, kunt u niet verder gaan naar de volgende stap.

1. **[!UICONTROL Set a Control Segment]**

   * Selecteer een controlesegment als u een bepaald deel van het segment wilt opzij zetten dat als controlegroep moet worden gebruikt. Met controlegroepen kunt u de impact zien van de testsegmenten die u hebt gemaakt in vergelijking met een benchmark.
   * U kunt een testsegment als controlesegment in de drop-down lijst selecteren, of u kunt **[!UICONTROL None]** voor geen controle kiezen.
   * Klik **[!UICONTROL Next]** wanneer u wordt gedaan.

1. **[!UICONTROL Select Conversion Traits]**

   * Conversietekenmerken toevoegen door deze te typen in het venster Conversietekenmerken. Dit is een **verplichte** stap en u kunt niet naar de volgende stap verdergaan tenzij u minstens één omzettingseigenschap toevoegt.
   * U kunt maximaal vijf conversietekenmerken desgewenst toevoegen.
   * Er verschijnt een waarschuwing voor het geval u een conversietekenmerk selecteert die al voor andere testgroepen wordt gebruikt.
   * Merk op dat de Audience Manager het gebruiken van [omslageigenschappen ](/help/using/features/traits/about-folder-traits.md) als omzettingskenmerken niet steunt. Als u een mapkenmerk selecteert als conversietekenmerk, resulteert dit in 0 aggregaat- en trendrapporten die tijdens de test worden weergegeven.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Typ de gewenste doelen in het zoekveld of gebruik de vervolgkeuzepijl. [!UICONTROL Audience Lab] testsegmenten kunnen naar URL-, cookie- of server-naar-server doelen worden verzonden.
   * Segmenten naar bestemmingen slepen en neerzetten.
   * Nadat u een segment op een bestemming hebt neergezet, vult u **[!UICONTROL Destination Mapping Value]** in de doeken in.
   * U kunt het zelfde testsegment naar veelvoudige bestemmingen verzenden en u kunt veelvoudige testsegmenten aan één enkele bestemming toevoegen.
   * Doelen worden grijs weergegeven als deze niet beschikbaar zijn voor een bepaald testsegment op basis van [Besturingselementen voor gegevensexport](../../features/data-export-controls.md).
   * Gebruikers zien alleen de doelen waartoe zij toegang hebben op basis van de [RBAC-gebruikersgroep](../../features/administration/administration-overview.md) waartoe zij behoren.
   * Tot slot moet u een begindatum voor uw testgroep selecteren. Deze datum geeft het begin aan van de periode waarin uw testgroep wordt gepubliceerd naar bestemmingen. Selecteer **Geen einddatum** voor een onbepaalde vergelijking van de testsegmenten.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] met een geverifieerd profiel alleen worden ondersteund in realtime-doelen. Als een testsegment met een regel van de profielfusie van die configuratie naar een op dossier-gebaseerde server-aan-server bestemming wordt verzonden, zou het publiek niet kunnen bevolken.

   Klik **[!UICONTROL Next]** om uw testgroep te herzien en te voltooien.

1. **[!UICONTROL Summary & Finalize]**

   * Controleer de informatie die u in de vorige stappen hebt toegevoegd en selecteer **[!UICONTROL Finalize Group]**.
   * Vergeet niet dat een testgroep na het voltooien ervan kan worden gedupliceerd of verwijderd, maar niet kan worden bewerkt.

   >[!NOTE]
   >* U kunt de testgroepen op elk gewenst moment in het ontwerpproces opslaan en later terugkeren naar de wizard. De status van de testgroep zal **[!UICONTROL Draft]** zijn en de testgroep zal geen gegevens naar bestemmingen verzenden tot u de groep van de segmenttest voltooit.
   >* Voor ontwerp tests, kunt u terug gaan en de testgroepen uitgeven door **[!UICONTROL Edit]** in de kaart van de testgroep in de belangrijkste [!UICONTROL Audience Lab] mening te klikken.


## Testgroepen segment bewerken {#edit-test-groups}

In [!UICONTROL Audience Lab] kunt u alleen concepttestgroepen bewerken. In [!UICONTROL Create Segment Test Group] tovenaar, kunt u uw testgroep als ontwerp opslaan en het werken aan het later hervatten.

1. Navigeer naar de hoofdweergave [!UICONTROL Audience Lab].
1. Zoek naar uw ontwerp testgroepen en selecteer **[!UICONTROL Edit]** controle in de kaart van de testgroep.
1. Hervat de [Create Groep van de Test van het Segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) tovenaar en selecteer **[!UICONTROL Finalize Group]** wanneer u wordt gedaan.

## Segmenttestgroepen {#delete-test-groups} verwijderen

1. Navigeer naar de hoofdweergave [!UICONTROL Audience Lab].
1. Zoek de testgroep die u wilt verwijderen. U kunt:

   * drukken op het **[!UICONTROL Delete]** besturingselement in de testgroepkaart, of
   * Druk op de titel van de testgroep in de testgroepkaart om naar de weergave [Informatie over testgroep](../../features/audience-lab/audience-lab-information-view.md) te gaan en druk op **[!UICONTROL Delete]** in de titelbalk.

1. Voor [voltooide testsegmenten](../../features/audience-lab/audience-lab.md#status), zal een alarm u ertoe aanzetten om het Csv- dossier te downloaden om het rapport te bewaren als u wenst.
