<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Integrate Azure OpenAI into your app</source><target>Integrieren von Azure OpenAI mit Ihrer App</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Integrate Azure OpenAI into your app</source><target>Integrieren von Azure OpenAI mit Ihrer App</target>
        </trans-unit></group></group>
        <group id="p103-PARA"><group id="s103-PARA"><trans-unit id="103" translate="yes" xml:space="preserve">
          <source>With the Azure OpenAI Service, developers can create chatbots, language models, and other applications that excel at understanding natural human language.</source><target>Mit Azure OpenAI Service können Entwickler*innen Chatbots, Sprachmodelle und andere Anwendungen erstellen, die die natürliche menschliche Sprache besonders gut verstehen.</target>
        </trans-unit></group></group>
        <group id="p104-PARA"><group id="s104-PARA"><trans-unit id="104" translate="yes" xml:space="preserve">
          <source>The Azure OpenAI provides access to pre-trained AI models, as well as a suite of APIs and tools for customizing and fine-tuning these models to meet the specific requirements of your application.</source><target>Azure OpenAI bietet Zugriff auf vortrainierte KI-Modelle sowie eine Suite von APIs und Tools zum Anpassen und Optimieren dieser Modelle, um die spezifischen Anforderungen Ihrer Anwendung zu erfüllen.</target>
        </trans-unit></group></group>
        <group id="p105-PARA"><group id="s105-PARA"><trans-unit id="105" translate="yes" xml:space="preserve">
          <source>In this exercise, you'll learn how to deploy a model in Azure OpenAI and use it in your own application to summarize text.</source><target>In dieser Übung erfahren Sie, wie Sie ein Modell in Azure OpenAI bereitstellen und es in Ihrer eigenen Anwendung verwenden, um Text zusammenzufassen.</target>
        </trans-unit></group></group>
        <group id="p106-PARA"><group id="s106-PARA"><trans-unit id="106" translate="yes" xml:space="preserve">
          <source>This exercise will take approximately <bpt id="p1">**</bpt>30<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ungefähr <bpt id="p1">**</bpt>30<ept id="p1">**</ept> Minuten.</target>
        </trans-unit></group></group>
        <group id="p107-PARA"><group id="s107-PARA"><trans-unit id="107" translate="yes" xml:space="preserve">
          <source>Before you start</source><target>Vorbereitung</target>
        </trans-unit></group></group>
        <group id="p108-PARA"><group id="s108-PARA"><trans-unit id="108" translate="yes" xml:space="preserve">
          <source>You will need an Azure subscription that has been approved for access to the Azure OpenAI service.</source><target>Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p109-PARA"><group id="s109-PARA"><trans-unit id="109" translate="yes" xml:space="preserve">
          <source>To sign up for a free Azure subscription, visit <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>.</source><target>Besuchen Sie <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>, um sich für ein kostenloses Azure-Abonnement zu registrieren.</target>
        </trans-unit></group></group>
        <group id="p110-PARA"><group id="s110-PARA"><trans-unit id="110" translate="yes" xml:space="preserve">
          <source>To request access to the Azure OpenAI service, visit <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</source><target>Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</target>
        </trans-unit></group></group>
        <group id="p111-PARA"><group id="s111-PARA"><trans-unit id="111" translate="yes" xml:space="preserve">
          <source>Provision an Azure OpenAI resource</source><target>Bereitstellen einer Azure OpenAI-Ressource</target>
        </trans-unit></group></group>
        <group id="p112-PARA"><group id="s112-PARA"><trans-unit id="112" translate="yes" xml:space="preserve">
          <source>Before you can use Azure OpenAI models, you must provision an Azure OpenAI resource in your Azure subscription.</source><target>Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.</target>
        </trans-unit></group></group>
        <group id="p113-PARA"><group id="s113-PARA"><trans-unit id="113" translate="yes" xml:space="preserve">
          <source>Sign into the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com)</ept>.</source><target>Melden Sie sich beim <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com)</ept> an.</target>
        </trans-unit></group></group>
        <group id="p114-PARA"><group id="s114-PARA"><trans-unit id="114" translate="yes" xml:space="preserve">
          <source>Create an <bpt id="p1">**</bpt>Azure OpenAI<ept id="p1">**</ept> resource with the following settings:</source><target>Erstellen Sie eine <bpt id="p1">**</bpt>Azure OpenAI-Ressource<ept id="p1">**</ept> mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p115-PARA"><group id="s115-PARA"><trans-unit id="115" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: An Azure subscription that has been approved for access to the Azure OpenAI service.</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p116-PARA"><group id="s116-PARA"><trans-unit id="116" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Choose an existing resource group, or create a new one with a name of your choice.</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie entweder eine bereits bestehende Ressourcengruppe, oder erstellen Sie eine neue Ressourcengruppe mit einem beliebigen Namen.</target>
        </trans-unit></group></group>
        <group id="p117-PARA"><group id="s117-PARA"><trans-unit id="117" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Choose any available region.</source><target><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region aus.</target>
        </trans-unit></group></group>
        <group id="p118-PARA"><group id="s118-PARA"><trans-unit id="118" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: A unique name of your choice.</source><target><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: Wählen Sie einen Namen Ihrer Wahl aus.</target>
        </trans-unit></group></group>
        <group id="p119-PARA"><group id="s119-PARA"><trans-unit id="119" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Pricing tier<ept id="p1">**</ept>: Standard S0</source><target><bpt id="p1">**</bpt>Tarif<ept id="p1">**</ept>: Standard S0.</target>
        </trans-unit></group></group>
        <group id="p120-PARA"><group id="s120-PARA"><trans-unit id="120" translate="yes" xml:space="preserve">
          <source>Wait for deployment to complete.</source><target>Warten Sie, bis die Bereitstellung abgeschlossen ist.</target>
        </trans-unit></group></group>
        <group id="p121-PARA"><group id="s121-PARA"><trans-unit id="121" translate="yes" xml:space="preserve">
          <source>Then go to the deployed Azure OpenAI resource in the Azure portal.</source><target>Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.</target>
        </trans-unit></group></group>
        <group id="p122-PARA"><group id="s122-PARA"><trans-unit id="122" translate="yes" xml:space="preserve">
          <source>Navigate to <bpt id="p1">**</bpt>Keys and Endpoint<ept id="p1">**</ept> page, and save those to a text file to use later.</source><target>Navigieren Sie zur Seite <bpt id="p1">**</bpt>Schlüssel und Endpunkt<ept id="p1">**</ept>, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>Deploy a model</source><target>Bereitstellen eines Modells</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>To use the Azure OpenAI API, you must first deploy a model to use through the <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>.</source><target>Um die Azure OpenAI-API verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> verwendet werden kann.</target>
        </trans-unit></group></group>
        <group id="p125-PARA"><group id="s125-PARA"><trans-unit id="125" translate="yes" xml:space="preserve">
          <source>Once deployed, we will reference that model in our app.</source><target>Nach der Bereitstellung verweisen wir in unserer App auf dieses Modell.</target>
        </trans-unit></group></group>
        <group id="p126-PARA"><group id="s126-PARA"><trans-unit id="126" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Explore<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab.</source><target>Verwenden Sie auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressource die Schaltfläche <bpt id="p2">**</bpt>Erkunden<ept id="p2">**</ept>, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.</target>
        </trans-unit></group></group>
        <group id="p127-PARA"><group id="s127-PARA"><trans-unit id="127" translate="yes" xml:space="preserve">
          <source>In Azure OpenAI Studio, on the <bpt id="p1">**</bpt>Deployments<ept id="p1">**</ept> page, view your existing model deployments.</source><target>Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite <bpt id="p1">**</bpt>Bereitstellungen<ept id="p1">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p128-PARA"><group id="s128-PARA"><trans-unit id="128" translate="yes" xml:space="preserve">
          <source>If you don't already have one, create a new deployment of the <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept> model with the following settings:</source><target>Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept>-Modells mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p129-PARA"><group id="s129-PARA"><trans-unit id="129" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model<ept id="p1">**</ept>: gpt-35-turbo-16k</source><target><bpt id="p1">**</bpt>Modell<ept id="p1">**</ept>: gpt-35-turbo-16k</target>
        </trans-unit></group></group>
        <group id="p130-PARA"><group id="s130-PARA"><trans-unit id="130" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model version<ept id="p1">**</ept>: Auto-update to default</source><target><bpt id="p1">**</bpt>Modellversion<ept id="p1">**</ept>: Automatische Aktualisierung auf die Standardeinstellung</target>
        </trans-unit></group></group>
        <group id="p131-PARA"><group id="s131-PARA"><trans-unit id="131" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Deployment name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>A unique name of your choice<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Bereitstellungsname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Wählen Sie einen Namen Ihrer Wahl aus<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p132-PARA"><group id="s132-PARA"><trans-unit id="132" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Advanced options<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Erweiterte Optionen<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p133-PARA"><group id="s133-PARA"><trans-unit id="133" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Content filter<ept id="p1">**</ept>: Default</source><target><bpt id="p1">**</bpt>Inhaltsfilter<ept id="p1">**</ept>: Standard</target>
        </trans-unit></group></group>
        <group id="p134-PARA"><group id="s134-PARA"><trans-unit id="134" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tokens per minute rate limit<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></source><target><bpt id="p1">**</bpt>Ratenlimit für Token pro Minute<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></target>
        </trans-unit></group></group>
        <group id="p135-PARA"><group id="s135-PARA"><trans-unit id="135" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Enable dynamic quota<ept id="p1">**</ept>: Enabled</source><target><bpt id="p1">**</bpt>Dynamisches Kontingent aktivieren<ept id="p1">**</ept>: Aktiviert</target>
        </trans-unit></group></group>
        <group id="p136-PARA"><group id="s136-PARA"><trans-unit id="136" translate="yes" xml:space="preserve">
          <source><ph id="ph1">\*</ph> A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.</source><target><ph id="ph1">\*</ph> Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: In some regions, the new model deployment interface doesn't show the <bpt id="p2">**</bpt>Model version<ept id="p2">**</ept> option.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option <bpt id="p2">**</bpt>Modellversion<ept id="p2">**</ept> nicht an.</target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source>In this case, don't worry and continue without setting the option</source><target>Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source>Set up an application in Cloud Shell</source><target>Einrichten einer Anwendung in Cloud Shell</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source>To show how to integrate with an Azure OpenAI model, we'll use a short command-line application that runs in Cloud Shell on Azure.</source><target>Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>Open up a new browser tab to work with Cloud Shell.</source><target>Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>, select the <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>) button at the top of the page to the right of the search box.</source><target>Klicken Sie im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source>A Cloud Shell pane will open at the bottom of the portal.</source><target>Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.</target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source>Screenshot of starting Cloud Shell by clicking on the icon to the right of the top search box.</source><target>Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld</target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source>The first time you open the Cloud Shell, you may be prompted to choose the type of shell you want to use (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> or <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</source><target>Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> oder <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept>.</source><target>Wählen Sie <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>If you don't see this option, skip the step.</source><target>Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source>If you're prompted to create storage for your Cloud Shell, select <bpt id="p1">**</bpt>Show advanced settings<ept id="p1">**</ept> and select the following settings:</source><target>Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie <bpt id="p1">**</bpt>Erweiterte Einstellungen anzeigen<ept id="p1">**</ept> und dann die folgenden Einstellungen aus:</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: Your subscription</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Ihr Abonnement</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Cloud shell regions<ept id="p1">**</ept>: Choose any available region</source><target><bpt id="p1">**</bpt>Cloud Shell-Regionen<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Show VNET isolation setings<ept id="p1">**</ept> Unselected</source><target><bpt id="p1">**</bpt>VNET-Isolationseinstellungen anzeigen<ept id="p1">**</ept> Nicht ausgewählt</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Use the existing resource group where you provisioned your Azure OpenAI resource</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben</target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account<ept id="p1">**</ept>: Create a new storage account with a unique name</source><target><bpt id="p1">**</bpt>Speicherkonto<ept id="p1">**</ept>: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>File share<ept id="p1">**</ept>: Create a new file share with a unique name</source><target><bpt id="p1">**</bpt>Dateifreigabe<ept id="p1">**</ept>: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source>Then wait a minute or so for the storage to be created.</source><target>Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.</target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: If you already have a cloud shell set up in your Azure subscription, you may need to use the <bpt id="p2">**</bpt>Reset user settings<ept id="p2">**</ept> option in the ⚙️ menu to ensure the latest versions of Python and the .NET Framework are installed.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option <bpt id="p2">**</bpt>Benutzereinstellungen zurücksetzen<ept id="p2">**</ept> im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>Make sure the type of shell indicated on the top left of the Cloud Shell pane is <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept>.</source><target>Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> lautet.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>If it's <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept>, switch to <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept> by using the drop-down menu.</source><target>Sollte <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept> angezeigt werden, wechseln Sie über das Dropdownmenü zu <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source>Once the terminal starts, enter the following command to download the sample application and save it to a folder called <ph id="ph1">`azure-openai`</ph>.</source><target>Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens <ph id="ph1">`azure-openai`</ph> zu speichern.</target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source>The files are downloaded to a folder named <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept>.</source><target>Die Dateien werden in einen Ordner namens <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept> heruntergeladen.</target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source>Navigate to the lab files for this exercise using the following command.</source><target>Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.</target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source>Open the built-in code editor by running the following command:</source><target>Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:</target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>text-files<ept id="p1">**</ept> folder and select <bpt id="p2">**</bpt>sample-text.txt<ept id="p2">**</ept> to see the text that you will use your model to summarize.</source><target>Erweitern Sie im Code-Editor den Ordner <bpt id="p1">**</bpt>Textdateien<ept id="p1">**</ept> und wählen Sie <bpt id="p2">**</bpt>Beispieltext.txt<ept id="p2">**</ept> aus, um den Text zu sehen, den Ihr Modell zusammenfasst.</target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Consult the <bpt id="p2">[</bpt>documentation for the Azure cloud shell code editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept> for more details about using it to work with files in the Azure cloud shell environment.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der <bpt id="p2">[</bpt>Dokumentation für den Azure Cloud Shell-Code-Editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept>.</target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source>Configure your application</source><target>Konfigurieren der Anwendung</target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source>For this exercise, you'll complete some key parts of the application to enable using your Azure OpenAI resource.</source><target>In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source>Applications for both C# and Python have been provided.</source><target>Anwendungen für C# und Python wurden bereitgestellt.</target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source>Both apps feature the same functionality.</source><target>Beide Apps verfügen über die gleiche Funktionalität.</target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Python<ept id="p2">**</ept> folder, depending on your language preference.</source><target>Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> oder <bpt id="p2">**</bpt>Python<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source>Open the configuration file for your language</source><target>Öffnen der Konfigurationsdatei für Ihre Sprache</target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source>C#: <ph id="ph1">`appsettings.json`</ph></source><target>C#: <ph id="ph1">`appsettings.json`</ph></target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source>Python: <ph id="ph1">`.env`</ph></source><target>Python: <ph id="ph1">`.env`</ph></target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source>Update the configuration values to include the <bpt id="p1">**</bpt>endpoint<ept id="p1">**</ept> and <bpt id="p2">**</bpt>key<ept id="p2">**</ept> from the Azure OpenAI resource you created, as well as the model name that you deployed.</source><target>Aktualisieren Sie die Konfigurationswerte, um den <bpt id="p1">**</bpt>Endpunkt<ept id="p1">**</ept> und den <bpt id="p2">**</bpt>Schlüssel<ept id="p2">**</ept> aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen hinzuzufügen.</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>Save the file.</source><target>Speichern Sie die Datei .</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>In the console pane, enter the following commands to navigate to the folder for your preferred language and install the necessary packages</source><target>Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p177-PARA"><group id="s177-PARA"><trans-unit id="177" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p178-PARA"><group id="s178-PARA"><trans-unit id="178" translate="yes" xml:space="preserve">
          <source>Navigate to your preferred language folder, select the code file, and add the necessary libraries.</source><target>Navigieren Sie zu Ihrem bevorzugten Sprachordner, wählen Sie die Codedatei aus, und fügen Sie die erforderlichen Bibliotheken hinzu.</target>
        </trans-unit></group></group>
        <group id="p179-PARA"><group id="s179-PARA"><trans-unit id="179" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p180-PARA"><group id="s180-PARA"><trans-unit id="180" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p181-PARA"><group id="s181-PARA"><trans-unit id="181" translate="yes" xml:space="preserve">
          <source>Open up the application code for your language and add the necessary code for building the request, which specifies the various parameters for your model such as <ph id="ph1">`prompt`</ph> and <ph id="ph2">`temperature`</ph>.</source><target>Öffnen Sie den Anwendungscode für Ihre Sprache, und fügen Sie den erforderlichen Code für die Erstellung der Anforderung hinzu, in dem die verschiedenen Parameter für Ihr Modell wie <ph id="ph1">`prompt`</ph> und <ph id="ph2">`temperature`</ph> angegeben sind.</target>
        </trans-unit></group></group>
        <group id="p182-PARA"><group id="s182-PARA"><trans-unit id="182" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p183-PARA"><group id="s183-PARA"><trans-unit id="183" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p184-PARA"><group id="s184-PARA"><trans-unit id="184" translate="yes" xml:space="preserve">
          <source>Run your application</source><target>Ausführen der Anwendung</target>
        </trans-unit></group></group>
        <group id="p185-PARA"><group id="s185-PARA"><trans-unit id="185" translate="yes" xml:space="preserve">
          <source>Now that your app has been configured, run it to send your request to your model and observe the response.</source><target>Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten.</target>
        </trans-unit></group></group>
        <group id="p186-PARA"><group id="s186-PARA"><trans-unit id="186" translate="yes" xml:space="preserve">
          <source>In the Cloud Shell bash terminal, navigate to the folder for your preferred language.</source><target>Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.</target>
        </trans-unit></group></group>
        <group id="p187-PARA"><group id="s187-PARA"><trans-unit id="187" translate="yes" xml:space="preserve">
          <source>Run the application.</source><target>Führen Sie die Anwendung aus.</target>
        </trans-unit></group></group>
        <group id="p188-PARA"><group id="s188-PARA"><trans-unit id="188" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: <ph id="ph1">`dotnet run`</ph></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : <ph id="ph1">`dotnet run`</ph></target>
        </trans-unit></group></group>
        <group id="p189-PARA"><group id="s189-PARA"><trans-unit id="189" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python test-openai-model.py`</ph></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python test-openai-model.py`</ph></target>
        </trans-unit></group></group>
        <group id="p190-PARA"><group id="s190-PARA"><trans-unit id="190" translate="yes" xml:space="preserve">
          <source>Observe the summarization of the sample text file.</source><target>Sehen Sie sich die Zusammenfassung der Beispieltextdatei an.</target>
        </trans-unit></group></group>
        <group id="p191-PARA"><group id="s191-PARA"><trans-unit id="191" translate="yes" xml:space="preserve">
          <source>Navigate to your code file for your preferred language, and change the <bpt id="p1">*</bpt>temperature<ept id="p1">*</ept> value to <ph id="ph1">`1`</ph>.</source><target>Navigieren Sie zu Ihrer Codedatei für Ihre bevorzugte Sprache, und ändern Sie den <bpt id="p1">*</bpt>Temperaturwert<ept id="p1">*</ept> in <ph id="ph1">`1`</ph>.</target>
        </trans-unit></group></group>
        <group id="p192-PARA"><group id="s192-PARA"><trans-unit id="192" translate="yes" xml:space="preserve">
          <source>Save the file.</source><target>Speichern Sie die Datei .</target>
        </trans-unit></group></group>
        <group id="p193-PARA"><group id="s193-PARA"><trans-unit id="193" translate="yes" xml:space="preserve">
          <source>Run the application again, and observe the output.</source><target>Führen Sie die Anwendung erneut aus, und sehen Sie sich die Ausgabe an.</target>
        </trans-unit></group></group>
        <group id="p194-PARA"><group id="s194-PARA"><trans-unit id="194" translate="yes" xml:space="preserve">
          <source>Increasing the temperature often causes the summary to vary, even when provided the same text, due to the increased randomness.</source><target>Eine Erhöhung der Temperatur führt häufig dazu, dass die Zusammenfassung variiert, selbst wenn der gleiche Text bereitgestellt wird, was auf die erhöhte Zufälligkeit zurückzuführen ist.</target>
        </trans-unit></group></group>
        <group id="p195-PARA"><group id="s195-PARA"><trans-unit id="195" translate="yes" xml:space="preserve">
          <source>You can run it several times to see how the output may change.</source><target>Sie können sie mehrmals ausführen, um zu sehen, wie sich die Ausgabe ändern kann.</target>
        </trans-unit></group></group>
        <group id="p196-PARA"><group id="s196-PARA"><trans-unit id="196" translate="yes" xml:space="preserve">
          <source>Try using different values for your temperature with the same input.</source><target>Versuchen Sie, verschiedene Werte für Ihre Temperatur mit derselben Eingabe zu verwenden.</target>
        </trans-unit></group></group>
        <group id="p197-PARA"><group id="s197-PARA"><trans-unit id="197" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigung</target>
        </trans-unit></group></group>
        <group id="p198-PARA"><group id="s198-PARA"><trans-unit id="198" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the deployment or the entire resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> zu löschen.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>