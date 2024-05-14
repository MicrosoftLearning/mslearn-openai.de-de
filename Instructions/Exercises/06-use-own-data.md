<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Use your own data with Azure OpenAI</source><target>Verwenden Ihrer eigenen Daten mit Azure OpenAI</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Use your own data with Azure OpenAI</source><target>Verwenden Ihrer eigenen Daten mit Azure OpenAI</target>
        </trans-unit></group></group>
        <group id="p103-PARA"><group id="s103-PARA"><trans-unit id="103" translate="yes" xml:space="preserve">
          <source>The Azure OpenAI Service enables you to use your own data with the intelligence of the underlying LLM.</source><target>Mit Azure OpenAI Service können Sie Ihre eigenen Daten mit der Intelligenz der zugrunde liegenden Large Language Models (LLMs) verwenden.</target>
        </trans-unit></group></group>
        <group id="p104-PARA"><group id="s104-PARA"><trans-unit id="104" translate="yes" xml:space="preserve">
          <source>You can limit the model to only use your data for pertinent topics, or blend it with results from the pre-trained model.</source><target>Sie können das Modell so einschränken, dass Ihre Daten nur für relevante Themen verwendet werden, oder Sie können sie mit Ergebnissen aus dem vortrainierten Modell kombinieren.</target>
        </trans-unit></group></group>
        <group id="p105-PARA"><group id="s105-PARA"><trans-unit id="105" translate="yes" xml:space="preserve">
          <source>This exercise will take approximately <bpt id="p1">**</bpt>20<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ungefähr <bpt id="p1">**</bpt>20<ept id="p1">**</ept> Minuten.</target>
        </trans-unit></group></group>
        <group id="p106-PARA"><group id="s106-PARA"><trans-unit id="106" translate="yes" xml:space="preserve">
          <source>Before you start</source><target>Vorbereitung</target>
        </trans-unit></group></group>
        <group id="p107-PARA"><group id="s107-PARA"><trans-unit id="107" translate="yes" xml:space="preserve">
          <source>You will need an Azure subscription that has been approved for access to the Azure OpenAI service.</source><target>Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p108-PARA"><group id="s108-PARA"><trans-unit id="108" translate="yes" xml:space="preserve">
          <source>To sign up for a free Azure subscription, visit <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>.</source><target>Besuchen Sie <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>, um sich für ein kostenloses Azure-Abonnement zu registrieren.</target>
        </trans-unit></group></group>
        <group id="p109-PARA"><group id="s109-PARA"><trans-unit id="109" translate="yes" xml:space="preserve">
          <source>To request access to the Azure OpenAI service, visit <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</source><target>Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</target>
        </trans-unit></group></group>
        <group id="p110-PARA"><group id="s110-PARA"><trans-unit id="110" translate="yes" xml:space="preserve">
          <source>Provision an Azure OpenAI resource</source><target>Bereitstellen einer Azure OpenAI-Ressource</target>
        </trans-unit></group></group>
        <group id="p111-PARA"><group id="s111-PARA"><trans-unit id="111" translate="yes" xml:space="preserve">
          <source>Before you can use Azure OpenAI models, you must provision an Azure OpenAI resource in your Azure subscription.</source><target>Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.</target>
        </trans-unit></group></group>
        <group id="p112-PARA"><group id="s112-PARA"><trans-unit id="112" translate="yes" xml:space="preserve">
          <source>Sign into the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>.</source><target>Melden Sie sich beim <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> an.</target>
        </trans-unit></group></group>
        <group id="p113-PARA"><group id="s113-PARA"><trans-unit id="113" translate="yes" xml:space="preserve">
          <source>Create an <bpt id="p1">**</bpt>Azure OpenAI<ept id="p1">**</ept> resource with the following settings:</source><target>Erstellen Sie eine <bpt id="p1">**</bpt>Azure OpenAI-Ressource<ept id="p1">**</ept> mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p114-PARA"><group id="s114-PARA"><trans-unit id="114" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: An Azure subscription that has been approved for access to the Azure OpenAI service.</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p115-PARA"><group id="s115-PARA"><trans-unit id="115" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Choose an existing resource group, or create a new one with a name of your choice.</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie entweder eine bereits vorhandene Ressourcengruppe, oder erstellen Sie eine Ressourcengruppe mit einem beliebigen Namen.</target>
        </trans-unit></group></group>
        <group id="p116-PARA"><group id="s116-PARA"><trans-unit id="116" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Choose any available region.</source><target><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region aus.</target>
        </trans-unit></group></group>
        <group id="p117-PARA"><group id="s117-PARA"><trans-unit id="117" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: A unique name of your choice.</source><target><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: Wählen Sie einen Namen Ihrer Wahl aus.</target>
        </trans-unit></group></group>
        <group id="p118-PARA"><group id="s118-PARA"><trans-unit id="118" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Pricing tier<ept id="p1">**</ept>: Standard S0</source><target><bpt id="p1">**</bpt>Tarif<ept id="p1">**</ept>: Standard S0.</target>
        </trans-unit></group></group>
        <group id="p119-PARA"><group id="s119-PARA"><trans-unit id="119" translate="yes" xml:space="preserve">
          <source>Wait for deployment to complete.</source><target>Warten Sie, bis die Bereitstellung abgeschlossen ist.</target>
        </trans-unit></group></group>
        <group id="p120-PARA"><group id="s120-PARA"><trans-unit id="120" translate="yes" xml:space="preserve">
          <source>Then go to the deployed Azure OpenAI resource in the Azure portal.</source><target>Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.</target>
        </trans-unit></group></group>
        <group id="p121-PARA"><group id="s121-PARA"><trans-unit id="121" translate="yes" xml:space="preserve">
          <source>Deploy a model</source><target>Bereitstellen eines Modells</target>
        </trans-unit></group></group>
        <group id="p122-PARA"><group id="s122-PARA"><trans-unit id="122" translate="yes" xml:space="preserve">
          <source>To chat with the Azure OpenAI, you must first deploy a model to use through the <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>.</source><target>Um mit der Azure OpenAI-API-Instanz chatten zu können, müssen Sie zunächst ein Modell bereitstellen, das in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> verwendet werden kann.</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>Once deployed, we will use the model with the playground and use our data to ground its responses.</source><target>Nach der Bereitstellung verwenden wir das Modell mit dem Playground. Zudem verwenden wir unsere Daten, um eine Basis für die Antworten zu schaffen.</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Explore<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> directly.</source><target>Verwenden Sie auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressourcen die Schaltfläche <bpt id="p2">**</bpt>Erkunden<ept id="p2">**</ept>, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> navigieren.</target>
        </trans-unit></group></group>
        <group id="p125-PARA"><group id="s125-PARA"><trans-unit id="125" translate="yes" xml:space="preserve">
          <source>In Azure OpenAI Studio, on the <bpt id="p1">**</bpt>Deployments<ept id="p1">**</ept> page, view your existing model deployments.</source><target>Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite <bpt id="p1">**</bpt>Bereitstellungen<ept id="p1">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p126-PARA"><group id="s126-PARA"><trans-unit id="126" translate="yes" xml:space="preserve">
          <source>If you don't already have one, create a new deployment of the <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept> model with the following settings:</source><target>Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept>-Modells mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p127-PARA"><group id="s127-PARA"><trans-unit id="127" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model<ept id="p1">**</ept>: gpt-35-turbo-16k</source><target><bpt id="p1">**</bpt>Modell<ept id="p1">**</ept>: gpt-35-turbo-16k</target>
        </trans-unit></group></group>
        <group id="p128-PARA"><group id="s128-PARA"><trans-unit id="128" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model version<ept id="p1">**</ept>: Auto-update to default</source><target><bpt id="p1">**</bpt>Modellversion<ept id="p1">**</ept>: Automatische Aktualisierung auf die Standardeinstellung</target>
        </trans-unit></group></group>
        <group id="p129-PARA"><group id="s129-PARA"><trans-unit id="129" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Deployment name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>A unique name of your choice<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Bereitstellungsname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Ein eindeutiger Name Ihrer Wahl<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p130-PARA"><group id="s130-PARA"><trans-unit id="130" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Advanced options<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Erweiterte Optionen<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p131-PARA"><group id="s131-PARA"><trans-unit id="131" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Content filter<ept id="p1">**</ept>: Default</source><target><bpt id="p1">**</bpt>Inhaltsfilter<ept id="p1">**</ept>: Standard</target>
        </trans-unit></group></group>
        <group id="p132-PARA"><group id="s132-PARA"><trans-unit id="132" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tokens per minute rate limit<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></source><target><bpt id="p1">**</bpt>Ratenlimit für Token pro Minute<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></target>
        </trans-unit></group></group>
        <group id="p133-PARA"><group id="s133-PARA"><trans-unit id="133" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Enable dynamic quota<ept id="p1">**</ept>: Enabled</source><target><bpt id="p1">**</bpt>Dynamisches Kontingent aktivieren<ept id="p1">**</ept>: Aktiviert</target>
        </trans-unit></group></group>
        <group id="p134-PARA"><group id="s134-PARA"><trans-unit id="134" translate="yes" xml:space="preserve">
          <source><ph id="ph1">\*</ph> A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.</source><target><ph id="ph1">\*</ph> Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.</target>
        </trans-unit></group></group>
        <group id="p135-PARA"><group id="s135-PARA"><trans-unit id="135" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: In some regions, the new model deployment interface doesn't show the <bpt id="p2">**</bpt>Model version<ept id="p2">**</ept> option.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option <bpt id="p2">**</bpt>Modellversion<ept id="p2">**</ept> nicht an.</target>
        </trans-unit></group></group>
        <group id="p136-PARA"><group id="s136-PARA"><trans-unit id="136" translate="yes" xml:space="preserve">
          <source>In this case, don't worry and continue without setting the option</source><target>Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source>Observe normal chat behavior without adding your own data</source><target>Beobachten des normalen Chatverhaltens ohne Hinzufügen eigener Daten</target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source>Before connecting Azure OpenAI to your data, first observe how the base model responds to queries without any grounding data.</source><target>Bevor Sie Azure OpenAI mit Ihren Daten verknüpfen, sollten Sie zunächst beobachten, wie das Basismodell auf Abfragen ohne Basisdaten reagiert.</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source>Navigate to the <bpt id="p1">**</bpt>Chat<ept id="p1">**</ept> playground, and make sure the model you deployed is selected in the <bpt id="p2">**</bpt>Configuration<ept id="p2">**</ept> pane (this should be the default, if you only have one deployed model).</source><target>Navigieren Sie zum <bpt id="p1">**</bpt>Chat<ept id="p1">**</ept>-Playground, und stellen Sie sicher, dass das von Ihnen bereitgestellte Modell im Bereich <bpt id="p2">**</bpt>Konfiguration<ept id="p2">**</ept> ausgewählt ist (dies sollte die Standardeinstellung sein, wenn Sie nur über ein einziges bereitgestelltes Modell verfügen).</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source>Enter the following prompts, and observe the output.</source><target>Geben Sie die folgenden Eingabeaufforderungen ein, und beobachten Sie die Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>Try similar questions about tourism and places to stay for other locations that will be included in our grounding data, such as London, or San Francisco.</source><target>Probieren Sie ähnliche Fragen zu Tourismus und Aufenthaltsmöglichkeiten für andere Orte aus, die in unseren Basisdaten enthalten sind, z. B. London oder San Francisco.</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>You'll likely get complete responses about areas or neighborhoods, and some general facts about the city.</source><target>Es werden wahrscheinlich vollständige Antworten zu Gebieten oder Stadtvierteln sowie allgemeine Fakten über die Stadt zurückgegeben.</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source>Connect your data in the chat playground</source><target>Verknüpfen Ihrer Daten im Chat-Playground</target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source>Next, add your data in the chat playground to see how it responds with your data as grounding</source><target>Fügen Sie als Nächstes Ihre Daten im Chat-Playground hinzu, um zu sehen, wie er mit Ihren Daten als Basis reagiert.</target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source><bpt id="p1">[</bpt>Download the data<ept id="p1">](https://aka.ms/own-data-brochures)</ept> that you will use from GitHub.</source><target>Laden Sie die Daten, die Sie verwenden werden, <bpt id="p1">[</bpt>von GitHub herunter<ept id="p1">](https://aka.ms/own-data-brochures)</ept>.</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>Extract the PDFs in the <ph id="ph1">`.zip`</ph> provided.</source><target>Extrahieren Sie die PDF-Dateien im bereitgestellten <ph id="ph1">`.zip`</ph>-Ordner.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>Navigate to the <bpt id="p1">**</bpt>Chat<ept id="p1">**</ept> playground, and select <bpt id="p2">*</bpt>Add your data<ept id="p2">*</ept> in the Assistant setup pane.</source><target>Navigieren Sie zum <bpt id="p1">**</bpt>Chat<ept id="p1">**</ept>-Playground, und wählen Sie im Bereich für die Assistenteneinrichtung die Option <bpt id="p2">*</bpt>Daten hinzufügen<ept id="p2">*</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Add a data source<ept id="p1">**</ept> and choose <bpt id="p2">*</bpt>Upload files<ept id="p2">*</ept> from the dropdown.</source><target>Wählen Sie <bpt id="p1">**</bpt>Datenquelle hinzufügen<ept id="p1">**</ept> und dann <bpt id="p2">*</bpt>Dateien hochladen<ept id="p2">*</ept> aus der Dropdownliste aus.</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source>You'll need to create a storage account and Azure Cognitive Search resource.</source><target>Sie müssen ein Speicherkonto und eine Azure Cognitive Search-Ressource erstellen.</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source>Under the dropdown for the storage resource, select <bpt id="p1">**</bpt>Create a new Azure Blob storage resource<ept id="p1">**</ept>, and create a storage account with the following settings.</source><target>Wählen Sie in der Dropdownliste für die Speicherressource die Option <bpt id="p1">**</bpt>Neue Azure Blob Storage-Ressource erstellen<ept id="p1">**</ept> aus, und erstellen Sie ein Speicherkonto mit den folgenden Einstellungen.</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source>Anything not specified leave as the default.</source><target>Alles, was nicht angegeben ist, wird als Standard beibehalten.</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same subscription as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Dasselbe Abonnement wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same resource group as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Dieselbe Ressourcengruppe wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Enter globally unique name<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Speicherkontoname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Geben Sie einen global eindeutigen Namen ein<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same region as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Dieselbe Region wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Redundancy<ept id="p1">**</ept>: Locally-redundant storage (LRS)</source><target><bpt id="p1">**</bpt>Redundanz<ept id="p1">**</ept>: Lokal redundanter Speicher (LRS)</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>Once the resource is being created, come back to Azure OpenAI Studio and select <bpt id="p1">**</bpt>Create a new Azure Cognitive Search resource<ept id="p1">**</ept> with the following settings.</source><target>Kehren Sie nach der Erstellung der Ressource zu Azure OpenAI Studio zurück, und wählen Sie <bpt id="p1">**</bpt>Neue Azure Cognitive Search-Ressource erstellen<ept id="p1">**</ept> mit den folgenden Einstellungen aus.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>Anything not specified leave as the default.</source><target>Alles, was nicht angegeben ist, wird als Standard beibehalten.</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same subscription as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Dasselbe Abonnement wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same resource group as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Dieselbe Ressourcengruppe wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Service name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Enter globally unique name<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Dienstname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Geben Sie einen global eindeutigen Namen ein.<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Location<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Same location as your Azure OpenAI resource<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Standort<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Derselbe Standort wie Ihre Azure OpenAI-Ressource<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Pricing tier<ept id="p1">**</ept>: Basic</source><target><bpt id="p1">**</bpt>Tarif<ept id="p1">**</ept>: Basic</target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source>Wait until your search resource has been deployed, then switch back to the Azure AI Studio and refresh the page.</source><target>Warten Sie, bis Ihre Suchressource bereitgestellt wurde, wechseln Sie dann zurück zu Azure AI Studio, und aktualisieren Sie die Seite.</target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Add data<ept id="p1">**</ept>, enter the following values for your data source, then select <bpt id="p2">**</bpt>Next<ept id="p2">**</ept>.</source><target>Geben Sie im Fenster <bpt id="p1">**</bpt>Daten hinzufügen<ept id="p1">**</ept> die folgenden Werte für Ihre Datenquelle ein und wählen Sie dann <bpt id="p2">**</bpt>Weiter<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Select data source<ept id="p1">**</ept>: Upload files</source><target><bpt id="p1">**</bpt>Datenquelle auswählen<ept id="p1">**</ept>: Laden Sie Dateien hoch.</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Select Azure Blob storage resouce<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Choose the storage resource you created<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Azure Blob Storage-Ressource auswählen:<ept id="p1">**</ept> <bpt id="p2">*</bpt>Wählen Sie die Speicherressource aus, die Sie erstellt haben.<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source>Turn on CORS when prompted</source><target>Aktivieren Sie CORS, wenn Sie dazu aufgefordert werden.</target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Select Azure Cognitive Search resource<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Choose the search resource you created<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Azure Cognitive Search-Ressource auswählen:<ept id="p1">**</ept> <bpt id="p2">*</bpt>Wählen Sie die von Ihnen erstellte Suchressource aus.<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Enter the index name<ept id="p1">**</ept>: margiestravel</source><target><bpt id="p1">**</bpt>Indexnamen eingeben:<ept id="p1">**</ept> margiestravel</target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Add vector search to this search resource<ept id="p1">**</ept>: unchecked</source><target><bpt id="p1">**</bpt>Hinzufügen der Vektorsuche zu dieser Suchressource<ept id="p1">**</ept>: deaktiviert</target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>I acknowledge that connecting to an Azure Cognitive Search account will incur usage to my account<ept id="p1">**</ept> : checked</source><target><bpt id="p1">**</bpt>Ich verstehe, dass die Verbindung zu einem Azure Cognitive Search-Konto eine Nutzung meines Kontos zur Folge hat<ept id="p1">**</ept>: aktiviert</target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Upload files<ept id="p1">**</ept> page, upload the PDFs you downloaded, and then select <bpt id="p2">**</bpt>Next<ept id="p2">**</ept>.</source><target>Laden Sie auf der Seite <bpt id="p1">**</bpt>Dateien hochladen<ept id="p1">**</ept> die PDFs hoch, die Sie heruntergeladen haben, und wählen Sie dann <bpt id="p2">**</bpt>Weiter<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Data management<ept id="p1">**</ept> page select the <bpt id="p2">**</bpt>Keyword<ept id="p2">**</ept> search type from the drop-down, and then select <bpt id="p3">**</bpt>Next<ept id="p3">**</ept>.</source><target>Wählen Sie auf der Seite <bpt id="p1">**</bpt>Datenverwaltung<ept id="p1">**</ept> den Suchtyp <bpt id="p2">**</bpt>Schlüsselwort<ept id="p2">**</ept> aus der Dropdown-Liste und wählen Sie dann <bpt id="p3">**</bpt>Weiter<ept id="p3">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Review and finish<ept id="p1">**</ept> page select <bpt id="p2">**</bpt>Save and close<ept id="p2">**</ept>, which will add your data.</source><target>Wählen Sie auf der Seite <bpt id="p1">**</bpt>Überprüfen und beenden<ept id="p1">**</ept> die Option <bpt id="p2">**</bpt>Speichern und schließen<ept id="p2">**</ept>, um Ihre Daten hinzuzufügen.</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source>This may take a few minutes, during which you need to leave your window open.</source><target>Dieser Vorgang kann einige Minuten in Anspruch nehmen. Schließen Sie das Fenster in diesem Zeitraum nicht.</target>
        </trans-unit></group></group>
        <group id="p177-PARA"><group id="s177-PARA"><trans-unit id="177" translate="yes" xml:space="preserve">
          <source>Once complete, you'll see the data source, search resource, and index specified in the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> pane.</source><target>Nach Abschluss des Vorgangs werden die Datenquelle, die Suchressource und der Index angezeigt, die im <bpt id="p1">**</bpt>Setupbereich des Assistenten<ept id="p1">**</ept> angegeben sind.</target>
        </trans-unit></group></group>
        <group id="p178-PARA"><group id="s178-PARA"><trans-unit id="178" translate="yes" xml:space="preserve">
          <source>Chat with a model grounded in your data</source><target>Chatten mit einem Modell, das auf Ihren Daten begründet ist</target>
        </trans-unit></group></group>
        <group id="p179-PARA"><group id="s179-PARA"><trans-unit id="179" translate="yes" xml:space="preserve">
          <source>Now that you've added your data, ask the same questions as you did previously, and see how the response differs.</source><target>Nachdem Sie Ihre Daten hinzugefügt haben, stellen Sie die gleichen Fragen wie zuvor, und beobachten Sie, wie sich die Daten verändern.</target>
        </trans-unit></group></group>
        <group id="p180-PARA"><group id="s180-PARA"><trans-unit id="180" translate="yes" xml:space="preserve">
          <source>You'll notice a very different response this time, with specifics about certain hotels and a mention of Margie's Travel, as well as references to where the information provided came from.</source><target>Dieses Mal wird eine vollkommen andere Antwort angezeigt. Diese enthält Informationen zu bestimmten Hotels und Margie‘s Travel sowie Referenzen zur Quelle der bereitgestellten Informationen.</target>
        </trans-unit></group></group>
        <group id="p181-PARA"><group id="s181-PARA"><trans-unit id="181" translate="yes" xml:space="preserve">
          <source>If you open the PDF reference listed in the response, you'll see the same hotels as the model provided.</source><target>Wenn Sie die in der Antwort aufgeführte PDF-Referenzdatei öffnen, werden dieselben Hotels wie im bereitgestellten Modell angezeigt.</target>
        </trans-unit></group></group>
        <group id="p182-PARA"><group id="s182-PARA"><trans-unit id="182" translate="yes" xml:space="preserve">
          <source>Try asking it about other cities included in the grounding data, which are Dubai, Las Vegas, London, and San Francisco.</source><target>Stellen Sie vielleicht Fragen zu anderen Städten, die in der Basisdatei enthalten sind, etwa zu Dubai, Las Vegas, London und San Francisco.</target>
        </trans-unit></group></group>
        <group id="p183-PARA"><group id="s183-PARA"><trans-unit id="183" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: <bpt id="p2">**</bpt>Add your data<ept id="p2">**</ept> is still in preview and might not always behave as expected for this feature, such as giving the incorrect reference for a city not included in the grounding data.</source><target><bpt id="p1">**</bpt>Hinweis:<ept id="p1">**</ept> Die Option <bpt id="p2">**</bpt>Daten hinzufügen<ept id="p2">**</ept> befindet sich noch in der Vorschauphase und verhält sich für dieses Feature möglicherweise nicht immer wie erwartet. Es werden beispielsweise falsche Referenzen für eine Stadt angegeben, die nicht in den Basisdaten enthalten ist.</target>
        </trans-unit></group></group>
        <group id="p184-PARA"><group id="s184-PARA"><trans-unit id="184" translate="yes" xml:space="preserve">
          <source>Connect your app to your own data</source><target>Verbinden Ihrer App mit Ihren eigenen Daten</target>
        </trans-unit></group></group>
        <group id="p185-PARA"><group id="s185-PARA"><trans-unit id="185" translate="yes" xml:space="preserve">
          <source>Next, explore how to connect your app to use your own data.</source><target>Erfahren Sie als nächstes, wie Sie Ihre App mit Ihren eigenen Daten verbinden.</target>
        </trans-unit></group></group>
        <group id="p186-PARA"><group id="s186-PARA"><trans-unit id="186" translate="yes" xml:space="preserve">
          <source>Set up an application in Cloud Shell</source><target>Einrichten einer Anwendung in Cloud Shell</target>
        </trans-unit></group></group>
        <group id="p187-PARA"><group id="s187-PARA"><trans-unit id="187" translate="yes" xml:space="preserve">
          <source>To show how to connect an Azure OpenAI app to your own data, we'll use a short command-line application that runs in Cloud Shell on Azure.</source><target>Zur Demonstration, wie Sie eine Azure OpenAI-App mit Ihren eigenen Daten verbinden, verwenden wir eine kurze Befehlszeilenanwendung in Azure Cloud Shell.</target>
        </trans-unit></group></group>
        <group id="p188-PARA"><group id="s188-PARA"><trans-unit id="188" translate="yes" xml:space="preserve">
          <source>Open up a new browser tab to work with Cloud Shell.</source><target>Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.</target>
        </trans-unit></group></group>
        <group id="p189-PARA"><group id="s189-PARA"><trans-unit id="189" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>, select the <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>) button at the top of the page to the right of the search box.</source><target>Klicken Sie im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p190-PARA"><group id="s190-PARA"><trans-unit id="190" translate="yes" xml:space="preserve">
          <source>A Cloud Shell pane will open at the bottom of the portal.</source><target>Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.</target>
        </trans-unit></group></group>
        <group id="p191-PARA"><group id="s191-PARA"><trans-unit id="191" translate="yes" xml:space="preserve">
          <source>Screenshot of starting Cloud Shell by clicking on the icon to the right of the top search box.</source><target>Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld</target>
        </trans-unit></group></group>
        <group id="p192-PARA"><group id="s192-PARA"><trans-unit id="192" translate="yes" xml:space="preserve">
          <source>The first time you open the Cloud Shell, you may be prompted to choose the type of shell you want to use (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> or <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</source><target>Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> oder <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p193-PARA"><group id="s193-PARA"><trans-unit id="193" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept>.</source><target>Wählen Sie <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p194-PARA"><group id="s194-PARA"><trans-unit id="194" translate="yes" xml:space="preserve">
          <source>If you don't see this option, skip the step.</source><target>Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.</target>
        </trans-unit></group></group>
        <group id="p195-PARA"><group id="s195-PARA"><trans-unit id="195" translate="yes" xml:space="preserve">
          <source>If you're prompted to create storage for your Cloud Shell, select <bpt id="p1">**</bpt>Show advanced settings<ept id="p1">**</ept> and select the following settings:</source><target>Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie <bpt id="p1">**</bpt>Erweiterte Einstellungen anzeigen<ept id="p1">**</ept> und dann die folgenden Einstellungen aus:</target>
        </trans-unit></group></group>
        <group id="p196-PARA"><group id="s196-PARA"><trans-unit id="196" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: Your subscription</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Ihr Abonnement</target>
        </trans-unit></group></group>
        <group id="p197-PARA"><group id="s197-PARA"><trans-unit id="197" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Cloud shell regions<ept id="p1">**</ept>: Choose any available region</source><target><bpt id="p1">**</bpt>Cloud Shell-Regionen<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region</target>
        </trans-unit></group></group>
        <group id="p198-PARA"><group id="s198-PARA"><trans-unit id="198" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Show VNET isolation setings<ept id="p1">**</ept> Unselected</source><target><bpt id="p1">**</bpt>VNET-Isolationseinstellungen anzeigen<ept id="p1">**</ept> Nicht ausgewählt</target>
        </trans-unit></group></group>
        <group id="p199-PARA"><group id="s199-PARA"><trans-unit id="199" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Use the existing resource group where you provisioned your Azure OpenAI resource</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben</target>
        </trans-unit></group></group>
        <group id="p200-PARA"><group id="s200-PARA"><trans-unit id="200" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account<ept id="p1">**</ept>: Create a new storage account with a unique name</source><target><bpt id="p1">**</bpt>Speicherkonto<ept id="p1">**</ept>: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p201-PARA"><group id="s201-PARA"><trans-unit id="201" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>File share<ept id="p1">**</ept>: Create a new file share with a unique name</source><target><bpt id="p1">**</bpt>Dateifreigabe<ept id="p1">**</ept>: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p202-PARA"><group id="s202-PARA"><trans-unit id="202" translate="yes" xml:space="preserve">
          <source>Then wait a minute or so for the storage to be created.</source><target>Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.</target>
        </trans-unit></group></group>
        <group id="p203-PARA"><group id="s203-PARA"><trans-unit id="203" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: If you already have a cloud shell set up in your Azure subscription, you may need to use the <bpt id="p2">**</bpt>Reset user settings<ept id="p2">**</ept> option in the ⚙️ menu to ensure the latest versions of Python and the .NET Framework are installed.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option <bpt id="p2">**</bpt>Benutzereinstellungen zurücksetzen<ept id="p2">**</ept> im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.</target>
        </trans-unit></group></group>
        <group id="p204-PARA"><group id="s204-PARA"><trans-unit id="204" translate="yes" xml:space="preserve">
          <source>Make sure the type of shell indicated on the top left of the Cloud Shell pane is <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept>.</source><target>Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> lautet.</target>
        </trans-unit></group></group>
        <group id="p205-PARA"><group id="s205-PARA"><trans-unit id="205" translate="yes" xml:space="preserve">
          <source>If it's <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept>, switch to <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept> by using the drop-down menu.</source><target>Sollte <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept> angezeigt werden, wechseln Sie über das Dropdownmenü zu <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p206-PARA"><group id="s206-PARA"><trans-unit id="206" translate="yes" xml:space="preserve">
          <source>Once the terminal starts, enter the following command to download the sample application and save it to a folder called <ph id="ph1">`azure-openai`</ph>.</source><target>Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens <ph id="ph1">`azure-openai`</ph> zu speichern.</target>
        </trans-unit></group></group>
        <group id="p207-PARA"><group id="s207-PARA"><trans-unit id="207" translate="yes" xml:space="preserve">
          <source>The files are downloaded to a folder named <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept>.</source><target>Die Dateien werden in einen Ordner namens <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept> heruntergeladen.</target>
        </trans-unit></group></group>
        <group id="p208-PARA"><group id="s208-PARA"><trans-unit id="208" translate="yes" xml:space="preserve">
          <source>Navigate to the lab files for this exercise using the following command.</source><target>Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.</target>
        </trans-unit></group></group>
        <group id="p209-PARA"><group id="s209-PARA"><trans-unit id="209" translate="yes" xml:space="preserve">
          <source>Open the built-in code editor by running the following command:</source><target>Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:</target>
        </trans-unit></group></group>
        <group id="p210-PARA"><group id="s210-PARA"><trans-unit id="210" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Consult the <bpt id="p2">[</bpt>documentation for the Azure cloud shell code editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept> for more details about using it to work with files in the Azure cloud shell environment.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der <bpt id="p2">[</bpt>Dokumentation für den Azure Cloud Shell-Code-Editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept>.</target>
        </trans-unit></group></group>
        <group id="p211-PARA"><group id="s211-PARA"><trans-unit id="211" translate="yes" xml:space="preserve">
          <source>Configure your application</source><target>Konfigurieren der Anwendung</target>
        </trans-unit></group></group>
        <group id="p212-PARA"><group id="s212-PARA"><trans-unit id="212" translate="yes" xml:space="preserve">
          <source>For this exercise, you'll complete some key parts of the application to enable using your Azure OpenAI resource.</source><target>In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.</target>
        </trans-unit></group></group>
        <group id="p213-PARA"><group id="s213-PARA"><trans-unit id="213" translate="yes" xml:space="preserve">
          <source>Applications for both C# and Python have been provided.</source><target>Anwendungen für C# und Python wurden bereitgestellt.</target>
        </trans-unit></group></group>
        <group id="p214-PARA"><group id="s214-PARA"><trans-unit id="214" translate="yes" xml:space="preserve">
          <source>Both apps feature the same functionality.</source><target>Beide Apps verfügen über die gleiche Funktionalität.</target>
        </trans-unit></group></group>
        <group id="p215-PARA"><group id="s215-PARA"><trans-unit id="215" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Python<ept id="p2">**</ept> folder, depending on your language preference.</source><target>Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> oder <bpt id="p2">**</bpt>Python<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p216-PARA"><group id="s216-PARA"><trans-unit id="216" translate="yes" xml:space="preserve">
          <source>Open the configuration file for your language.</source><target>Öffnen Sie die Konfigurationsdatei für Ihre Sprache.</target>
        </trans-unit></group></group>
        <group id="p217-PARA"><group id="s217-PARA"><trans-unit id="217" translate="yes" xml:space="preserve">
          <source>C#: <ph id="ph1">`appsettings.json`</ph></source><target>C#: <ph id="ph1">`appsettings.json`</ph></target>
        </trans-unit></group></group>
        <group id="p218-PARA"><group id="s218-PARA"><trans-unit id="218" translate="yes" xml:space="preserve">
          <source>Python: <ph id="ph1">`.env`</ph></source><target>Python: <ph id="ph1">`.env`</ph></target>
        </trans-unit></group></group>
        <group id="p219-PARA"><group id="s219-PARA"><trans-unit id="219" translate="yes" xml:space="preserve">
          <source>Update the configuration values to include:</source><target>Aktualisieren Sie die Konfigurationswerte, um Folgendes einzuschließen:</target>
        </trans-unit></group></group>
        <group id="p220-PARA"><group id="s220-PARA"><trans-unit id="220" translate="yes" xml:space="preserve">
          <source>The  <bpt id="p1">**</bpt>endpoint<ept id="p1">**</ept> and a <bpt id="p2">**</bpt>key<ept id="p2">**</ept> from the Azure OpenAI resource you created (available on the <bpt id="p3">**</bpt>Keys and Endpoint<ept id="p3">**</ept> page for your Azure OpenAI resource in the Azure portal)</source><target>Den <bpt id="p1">**</bpt>Endpunkt<ept id="p1">**</ept> und einen <bpt id="p2">**</bpt>Schlüssel<ept id="p2">**</ept> aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite <bpt id="p3">**</bpt>Schlüssel und Endpunkt<ept id="p3">**</ept> für Ihre Azure OpenAI-Ressource im Azure-Portal).</target>
        </trans-unit></group></group>
        <group id="p221-PARA"><group id="s221-PARA"><trans-unit id="221" translate="yes" xml:space="preserve">
          <source>The name you specified for your model deployment (available in the <bpt id="p1">**</bpt>Deployments<ept id="p1">**</ept> page in Azure OpenAI Studio).</source><target>Den Namen, den Sie für Ihre Modellbereitstellung angegeben haben (verfügbar auf der Seite <bpt id="p1">**</bpt>Bereitstellungen<ept id="p1">**</ept> in Azure OpenAI Studio).</target>
        </trans-unit></group></group>
        <group id="p222-PARA"><group id="s222-PARA"><trans-unit id="222" translate="yes" xml:space="preserve">
          <source>The endpoint for your search service (the <bpt id="p1">**</bpt>Url<ept id="p1">**</ept> value on the overview page for your search resource in the Azure portal).</source><target>Den Endpunkt für Ihren Suchdienst (der <bpt id="p1">**</bpt>URL<ept id="p1">**</ept>-Wert auf der Übersichtsseite Ihrer Search-Ressource im Azure-Portal).</target>
        </trans-unit></group></group>
        <group id="p223-PARA"><group id="s223-PARA"><trans-unit id="223" translate="yes" xml:space="preserve">
          <source>A <bpt id="p1">**</bpt>key<ept id="p1">**</ept> for your search resource (available in the <bpt id="p2">**</bpt>Keys<ept id="p2">**</ept> page for your search resource in the Azure portal - you can use either of the admin keys)</source><target>Einen <bpt id="p1">**</bpt>Schlüssel<ept id="p1">**</ept> für Ihre Search-Ressource (verfügbar auf der Seite <bpt id="p2">**</bpt>Schlüssel<ept id="p2">**</ept> Ihrer Search-Ressource im Azure-Portal – Sie können einen der Administratorschlüssel verwenden).</target>
        </trans-unit></group></group>
        <group id="p224-PARA"><group id="s224-PARA"><trans-unit id="224" translate="yes" xml:space="preserve">
          <source>The name of the search index (which should be <ph id="ph1">`margiestravel`</ph>).</source><target>Den Namen des Suchindexes (sollte <ph id="ph1">`margiestravel`</ph> sein).</target>
        </trans-unit></group></group>
        <group id="p225-PARA"><group id="s225-PARA"><trans-unit id="225" translate="yes" xml:space="preserve">
          <source>Save the updated configuration file.</source><target>Speichern Sie die aktualisierte Konfigurationsdatei.</target>
        </trans-unit></group></group>
        <group id="p226-PARA"><group id="s226-PARA"><trans-unit id="226" translate="yes" xml:space="preserve">
          <source>In the console pane, enter the following commands to navigate to the folder for your preferred language and install the necessary packages.</source><target>Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.</target>
        </trans-unit></group></group>
        <group id="p227-PARA"><group id="s227-PARA"><trans-unit id="227" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p228-PARA"><group id="s228-PARA"><trans-unit id="228" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p229-PARA"><group id="s229-PARA"><trans-unit id="229" translate="yes" xml:space="preserve">
          <source>In the code editor, navigate to your preferred language folder, select the code file, and add the necessary libraries.</source><target>Navigieren Sie im Code-Editor zum Ordner Ihrer bevorzugten Sprache, wählen Sie die Codedatei aus und fügen Sie die erforderlichen Bibliotheken hinzu.</target>
        </trans-unit></group></group>
        <group id="p230-PARA"><group id="s230-PARA"><trans-unit id="230" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: OwnData.cs</source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: OwnData.cs</target>
        </trans-unit></group></group>
        <group id="p231-PARA"><group id="s231-PARA"><trans-unit id="231" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: ownData.py</source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: ownData.py</target>
        </trans-unit></group></group>
        <group id="p232-PARA"><group id="s232-PARA"><trans-unit id="232" translate="yes" xml:space="preserve">
          <source>Review the code file, specifically where the search values are used when completing the parameters for the API call.</source><target>Überprüfen Sie die Codedatei, insbesondere die Stelle, an der die Suchwerte bei der Angabe der Parameter für den API-Aufruf verwendet werden.</target>
        </trans-unit></group></group>
        <group id="p233-PARA"><group id="s233-PARA"><trans-unit id="233" translate="yes" xml:space="preserve">
          <source>Run your application</source><target>Ausführen der Anwendung</target>
        </trans-unit></group></group>
        <group id="p234-PARA"><group id="s234-PARA"><trans-unit id="234" translate="yes" xml:space="preserve">
          <source>Now that your app has been configured, run it to send your request to your model and observe the response.</source><target>Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten.</target>
        </trans-unit></group></group>
        <group id="p235-PARA"><group id="s235-PARA"><trans-unit id="235" translate="yes" xml:space="preserve">
          <source>You'll notice the response is now grounded in your data similarly to the studio experience.</source><target>Wie Sie feststellen werden, basiert die Antwort jetzt auf Ihren Daten, ähnlich wie in Studio.</target>
        </trans-unit></group></group>
        <group id="p236-PARA"><group id="s236-PARA"><trans-unit id="236" translate="yes" xml:space="preserve">
          <source>In the Cloud Shell bash terminal, navigate to the folder for your preferred language.</source><target>Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.</target>
        </trans-unit></group></group>
        <group id="p237-PARA"><group id="s237-PARA"><trans-unit id="237" translate="yes" xml:space="preserve">
          <source>Expand the terminal to take up most of your browser window and run the application.</source><target>Erweitern Sie das Terminal so, dass es den größten Teil Ihres Browserfensters einnimmt, und starten Sie die Anwendung.</target>
        </trans-unit></group></group>
        <group id="p238-PARA"><group id="s238-PARA"><trans-unit id="238" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: <ph id="ph1">`dotnet run`</ph></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : <ph id="ph1">`dotnet run`</ph></target>
        </trans-unit></group></group>
        <group id="p239-PARA"><group id="s239-PARA"><trans-unit id="239" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python ownData.py`</ph></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python ownData.py`</ph></target>
        </trans-unit></group></group>
        <group id="p240-PARA"><group id="s240-PARA"><trans-unit id="240" translate="yes" xml:space="preserve">
          <source>Submit the prompt <ph id="ph1">`Tell me about London`</ph>, and you should see the response referencing your data.</source><target>Übermitteln Sie die Eingabeaufforderung <ph id="ph1">`Tell me about London`</ph>. Sie sollten nun eine Antwort erhalten, die sich auf Ihre Daten bezieht.</target>
        </trans-unit></group></group>
        <group id="p241-PARA"><group id="s241-PARA"><trans-unit id="241" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigen</target>
        </trans-unit></group></group>
        <group id="p242-PARA"><group id="s242-PARA"><trans-unit id="242" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept> zu löschen.</target>
        </trans-unit></group></group>
        <group id="p243-PARA"><group id="s243-PARA"><trans-unit id="243" translate="yes" xml:space="preserve">
          <source>Be sure to also include the storage account and search resource, as those can incur a relatively large cost.</source><target>Stellen Sie sicher, dass Sie auch das Speicherkonto und die Suchressource einschließen, da für diese relativ hohe Kosten entstehen können.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>