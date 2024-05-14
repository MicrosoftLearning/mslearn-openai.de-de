<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Generate images with a DALL-E model</source><target>Generieren von Bildern mit einem DALL-E-Modell</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Generate images with a DALL-E model</source><target>Generieren von Bildern mit einem DALL-E-Modell</target>
        </trans-unit></group></group>
        <group id="p103-PARA"><group id="s103-PARA"><trans-unit id="103" translate="yes" xml:space="preserve">
          <source>The Azure OpenAI Service includes an image-generation model named DALL-E.</source><target>Der Azure OpenAI Service enthält ein Bildgenerierungsmodell mit dem Namen DALL-E.</target>
        </trans-unit></group></group>
        <group id="p104-PARA"><group id="s104-PARA"><trans-unit id="104" translate="yes" xml:space="preserve">
          <source>You can use this model to submit natural language prompts that describe a desired image, and the model will generate an original image based on the description you provide.</source><target>Sie können dieses Modell verwenden, um Eingabeaufforderungen in natürlicher Sprache zu übermitteln, die ein gewünschtes Bild beschreiben, und das Modell generiert ein Originalbild basierend auf der von Ihnen angegebenen Beschreibung.</target>
        </trans-unit></group></group>
        <group id="p105-PARA"><group id="s105-PARA"><trans-unit id="105" translate="yes" xml:space="preserve">
          <source>This exercise will take approximately <bpt id="p1">**</bpt>25<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ungefähr <bpt id="p1">**</bpt>25<ept id="p1">**</ept> Minuten.</target>
        </trans-unit></group></group>
        <group id="p106-PARA"><group id="s106-PARA"><trans-unit id="106" translate="yes" xml:space="preserve">
          <source>Before you start</source><target>Vorbereitung</target>
        </trans-unit></group></group>
        <group id="p107-PARA"><group id="s107-PARA"><trans-unit id="107" translate="yes" xml:space="preserve">
          <source>You will need an Azure subscription that has been approved for access to the Azure OpenAI service, including DALL-E.</source><target>Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde, einschließlich DALL-E.</target>
        </trans-unit></group></group>
        <group id="p108-PARA"><group id="s108-PARA"><trans-unit id="108" translate="yes" xml:space="preserve">
          <source>If you have previously applied for access to the Azure openAI service, you may need to submit another application to gain access to DALL-E.</source><target>Wenn Sie zuvor Zugriff auf den Azure OpenAI Service beantragt haben, müssen Sie möglicherweise einen anderen Antrag stellen, um Zugriff auf DALL-E zu erhalten.</target>
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
          <source><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Choose <bpt id="p2">**</bpt>EastUS<ept id="p2">**</ept> as region</source><target><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Wählen Sie <bpt id="p2">**</bpt>EastUS<ept id="p2">**</ept> als Region</target>
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
          <source>Navigate to <bpt id="p1">**</bpt>Keys and Endpoint<ept id="p1">**</ept> page.</source><target>Navigieren Sie zur Seite <bpt id="p1">**</bpt>Schlüssel und Endpunkt<ept id="p1">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>You can retrieve the unique endpoint and authentication keys for your service from here - you'll need these later!</source><target>Sie können den eindeutigen Endpunkt und die Authentifizierungsschlüssel für Ihren Dienst von hier abrufen. Sie benötigen diese später.</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>Explore image-generation in the DALL-E playground</source><target>Erkunden der Bildgenerierung im DALL-E-Playground</target>
        </trans-unit></group></group>
        <group id="p125-PARA"><group id="s125-PARA"><trans-unit id="125" translate="yes" xml:space="preserve">
          <source>You can use the DALL-E playground in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> to experiment with image-generation.</source><target>Sie können den DALL-E-Playground in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> verwenden, um mit der Bildgenerierung zu experimentieren.</target>
        </trans-unit></group></group>
        <group id="p126-PARA"><group id="s126-PARA"><trans-unit id="126" translate="yes" xml:space="preserve">
          <source>In the Azure portal, on the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Explore<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> directly.</source><target>Verwenden Sie im Azure-Portal auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressourcen die Schaltfläche <bpt id="p2">**</bpt>Erkunden<ept id="p2">**</ept>, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> navigieren.</target>
        </trans-unit></group></group>
        <group id="p127-PARA"><group id="s127-PARA"><trans-unit id="127" translate="yes" xml:space="preserve">
          <source>Select the <bpt id="p1">**</bpt>DALL-E Playground<ept id="p1">**</ept>.</source><target>Wählen Sie den <bpt id="p1">**</bpt>DALL-E-Playground<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p128-PARA"><group id="s128-PARA"><trans-unit id="128" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Prompt<ept id="p1">**</ept> box, enter a description of an image you'd like to generate.</source><target>Geben Sie im Feld <bpt id="p1">**</bpt>Eingabeaufforderung<ept id="p1">**</ept> eine Beschreibung eines Bilds ein, das Sie generieren möchten.</target>
        </trans-unit></group></group>
        <group id="p129-PARA"><group id="s129-PARA"><trans-unit id="129" translate="yes" xml:space="preserve">
          <source>For example, <bpt id="p1">*</bpt>An elephant on a skateboard<ept id="p1">*</ept>.</source><target>Beispiel: <bpt id="p1">*</bpt>Ein Elefant auf einem Skateboard<ept id="p1">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p130-PARA"><group id="s130-PARA"><trans-unit id="130" translate="yes" xml:space="preserve">
          <source>Then select <bpt id="p1">**</bpt>Generate<ept id="p1">**</ept> and view the image that is generated.</source><target>Wählen Sie dann <bpt id="p1">**</bpt>Generieren<ept id="p1">**</ept> aus, und zeigen Sie das generierte Bild an.</target>
        </trans-unit></group></group>
        <group id="p131-PARA"><group id="s131-PARA"><trans-unit id="131" translate="yes" xml:space="preserve">
          <source>The DALL-E Playground in Azure OpenAI Studio with a generated image.</source><target>Der DALL-E-Playground in Azure OpenAI Studio mit einem generierten Bild.</target>
        </trans-unit></group></group>
        <group id="p132-PARA"><group id="s132-PARA"><trans-unit id="132" translate="yes" xml:space="preserve">
          <source>Modify the prompt to provide a more specific description.</source><target>Ändern Sie die Eingabeaufforderung, um eine spezifischere Beschreibung bereitzustellen.</target>
        </trans-unit></group></group>
        <group id="p133-PARA"><group id="s133-PARA"><trans-unit id="133" translate="yes" xml:space="preserve">
          <source>For example <bpt id="p1">*</bpt>An elephant on a skateboard in the style of Picasso<ept id="p1">*</ept>.</source><target>Zum Beispiel: <bpt id="p1">*</bpt>Ein Elefant auf einem Skateboard im Stil von Picasso<ept id="p1">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p134-PARA"><group id="s134-PARA"><trans-unit id="134" translate="yes" xml:space="preserve">
          <source>Then generate the new image and review the results.</source><target>Generieren Sie dann das neue Bild, und überprüfen Sie die Ergebnisse.</target>
        </trans-unit></group></group>
        <group id="p135-PARA"><group id="s135-PARA"><trans-unit id="135" translate="yes" xml:space="preserve">
          <source>The DALL-E Playground in Azure OpenAI Studio with two generated images.</source><target>Der DALL-E-Playground in Azure OpenAI Studio mit zwei generierten Bildern.</target>
        </trans-unit></group></group>
        <group id="p136-PARA"><group id="s136-PARA"><trans-unit id="136" translate="yes" xml:space="preserve">
          <source>Use the REST API to generate images</source><target>Verwenden der REST-API zum Generieren von Bildern</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source>The Azure OpenAI service provides a REST API that you can use to submit prompts for content generation - including images generated by a DALL-E model.</source><target>Der Azure OpenAI Service stellt eine REST-API bereit, die Sie verwenden können, um Eingabeaufforderungen zur Inhaltsgenerierung zu übermitteln, einschließlich der Bilder, die von einem DALL-E-Modell generiert wurden.</target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source>Prepare the app environment</source><target>Vorbereiten der App-Umgebung</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source>In this exercise, you'll use a simple Python or Microsoft C# app to generate images by calling the REST API.</source><target>In dieser Übung verwenden Sie eine einfache Python- oder Microsoft-C#-App, um Bilder zu generieren, indem Sie die REST-API aufrufen.</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source>You'll run the code in the cloud shell console interface in the Azure portal.</source><target>Sie führen den Code in der Cloud Shell-Konsolenschnittstelle im Azure-Portal aus.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>, select the <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>) button at the top of the page to the right of the search box.</source><target>Klicken Sie im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>A Cloud Shell pane will open at the bottom of the portal.</source><target>Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source>Screenshot of starting Cloud Shell by clicking on the icon to the right of the top search box.</source><target>Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld</target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source>The first time you open the Cloud Shell, you may be prompted to choose the type of shell you want to use (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> or <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</source><target>Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> oder <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept>.</source><target>Wählen Sie <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>If you don't see this option, skip the step.</source><target>Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>If you're prompted to create storage for your Cloud Shell, select <bpt id="p1">**</bpt>Show advanced settings<ept id="p1">**</ept> and select the following settings:</source><target>Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie <bpt id="p1">**</bpt>Erweiterte Einstellungen anzeigen<ept id="p1">**</ept> und dann die folgenden Einstellungen aus:</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: Your subscription</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Ihr Abonnement</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Cloud shell regions<ept id="p1">**</ept>: Choose any available region</source><target><bpt id="p1">**</bpt>Cloud Shell-Regionen<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Show VNET isolation settings<ept id="p1">**</ept> Unselected</source><target><bpt id="p1">**</bpt>VNET-Isolationseinstellungen anzeigen<ept id="p1">**</ept> Nicht ausgewählt</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Use the existing resource group where you provisioned your Azure OpenAI resource</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account<ept id="p1">**</ept>: Create a new storage account with a unique name</source><target><bpt id="p1">**</bpt>Speicherkonto<ept id="p1">**</ept>: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>File share<ept id="p1">**</ept>: Create a new file share with a unique name</source><target><bpt id="p1">**</bpt>Dateifreigabe<ept id="p1">**</ept>: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source>Then wait a minute or so for the storage to be created.</source><target>Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: If you already have a cloud shell set up in your Azure subscription, you may need to use the <bpt id="p2">**</bpt>Reset user settings<ept id="p2">**</ept> option in the ⚙️ menu to ensure the latest versions of Python and the .NET Framework are installed.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option <bpt id="p2">**</bpt>Benutzereinstellungen zurücksetzen<ept id="p2">**</ept> im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.</target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source>Make sure the type of shell indicated on the top left of the Cloud Shell pane is <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept>.</source><target>Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> lautet.</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>If it's <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept>, switch to <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept> by using the drop-down menu.</source><target>Sollte <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept> angezeigt werden, wechseln Sie über das Dropdownmenü zu <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>Once the terminal starts, enter the following command to download the application code you are going to work with.</source><target>Sobald das Terminal gestartet wird, geben Sie den folgenden Befehl ein, um den Anwendungscode herunterzuladen, mit dem Sie arbeiten möchten.</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source>The files are downloaded to a folder named <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept>.</source><target>Die Dateien werden in einen Ordner namens <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept> heruntergeladen.</target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source>Applications for both C# and Python have been provided.</source><target>Anwendungen für C# und Python wurden bereitgestellt.</target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source>Both apps feature the same functionality.</source><target>Beide Apps verfügen über die gleiche Funktionalität.</target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source>Navigate to the folder for the language you want to use by running the appropriate command.</source><target>Navigieren Sie zum Ordner für die Sprache, die Sie verwenden möchten, indem Sie den entsprechenden Befehl ausführen.</target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source>Use the following command to open the built-in code editor and see the code files you will be working with.</source><target>Verwenden Sie den folgenden Befehl, um den integrierten Code-Editor zu öffnen und die Codedateien anzuzeigen, mit denen Sie arbeiten werden.</target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Consult the <bpt id="p2">[</bpt>documentation for the Azure cloud shell code editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept> for more details about using it to work with files in the Azure cloud shell environment.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der <bpt id="p2">[</bpt>Dokumentation für den Azure Cloud Shell-Code-Editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept>.</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source>Configure your application</source><target>Konfigurieren der Anwendung</target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source>The application uses a configuration file to store the details needed to connect to your Azure OpenAI service account.</source><target>Die Anwendung verwendet eine Konfigurationsdatei, um die Details zu speichern, die zum Herstellen einer Verbindung mit Ihrem Azure OpenAI Service-Konto erforderlich sind.</target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source>In the code editor, select the configuration file for your app - depending on your language preference.</source><target>Wählen Sie im Code-Editor die Konfigurationsdatei für Ihre App aus – je nach der von Ihnen bevorzugten Sprache.</target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source>C#: <ph id="ph1">`appsettings.json`</ph></source><target>C#: <ph id="ph1">`appsettings.json`</ph></target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source>Python: <ph id="ph1">`.env`</ph></source><target>Python: <ph id="ph1">`.env`</ph></target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source>Update the configuration values to include the <bpt id="p1">**</bpt>Endpoint<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Key1<ept id="p2">**</ept> for your Azure OpenAI service and then save the file.</source><target>Aktualisieren Sie die Konfigurationswerte, um den <bpt id="p1">**</bpt>Endpunkt<ept id="p1">**</ept> und <bpt id="p2">**</bpt>Key1<ept id="p2">**</ept> für Ihre Azure OpenAI Service-Instanz einzuschließen, und speichern Sie dann die Datei.</target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: You can adjust the split at the top of the cloud shell pane to see the Azure portal, and get the endpoint and key values from the <bpt id="p2">**</bpt>Keys and Endpoint<ept id="p2">**</ept> page for your Azure OpenAI service.</source><target><bpt id="p1">**</bpt>Tipp<ept id="p1">**</ept>: Sie können die Aufteilung oben im Cloud Shell-Bereich anpassen, um das Azure-Portal anzuzeigen und die Endpunkt- und Schlüsselwerte auf der Seite <bpt id="p2">**</bpt>Schlüssel und Endpunkt<ept id="p2">**</ept> für Ihren Azure OpenAI-Dienst abzurufen.</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>If you are using <bpt id="p1">**</bpt>Python<ept id="p1">**</ept>, you'll also need to install the <bpt id="p2">**</bpt>python-dotenv<ept id="p2">**</ept> package used to read the configuration file.</source><target>Wenn Sie <bpt id="p1">**</bpt>Python<ept id="p1">**</ept> verwenden, müssen Sie auch das Paket <bpt id="p2">**</bpt>python-dotenv<ept id="p2">**</ept> installieren, das zum Lesen der Konfigurationsdatei verwendet wird.</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>In the console prompt pane, ensure the current folder is <bpt id="p1">**</bpt>~/azure-openai/Labfiles/05-image-generation/Python<ept id="p1">**</ept>.</source><target>Stellen Sie im Konsoleneingabeaufforderungsbereich sicher, dass der aktuelle Ordner <bpt id="p1">**</bpt>~/azure-openai/Labfiles/05-image-generation/Python<ept id="p1">**</ept> ist.</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source>Then enter this command:</source><target>Geben Sie dann den folgenden Befehl ein:</target>
        </trans-unit></group></group>
        <group id="p177-PARA"><group id="s177-PARA"><trans-unit id="177" translate="yes" xml:space="preserve">
          <source>View application code</source><target>Anzeigen des Anwendungscodes</target>
        </trans-unit></group></group>
        <group id="p178-PARA"><group id="s178-PARA"><trans-unit id="178" translate="yes" xml:space="preserve">
          <source>Now you're ready to explore the code used to call the REST API and generate an image.</source><target>Jetzt können Sie den Code untersuchen, der zum Aufrufen der REST-API und zum Generieren eines Bilds verwendet wird.</target>
        </trans-unit></group></group>
        <group id="p179-PARA"><group id="s179-PARA"><trans-unit id="179" translate="yes" xml:space="preserve">
          <source>In the code editor pane, select the main code file for your application:</source><target>Wählen Sie im Code-Editor-Bereich die Hauptcodedatei für Ihre Anwendung aus:</target>
        </trans-unit></group></group>
        <group id="p180-PARA"><group id="s180-PARA"><trans-unit id="180" translate="yes" xml:space="preserve">
          <source>C#: <ph id="ph1">`Program.cs`</ph></source><target>C#: <ph id="ph1">`Program.cs`</ph></target>
        </trans-unit></group></group>
        <group id="p181-PARA"><group id="s181-PARA"><trans-unit id="181" translate="yes" xml:space="preserve">
          <source>Python: <ph id="ph1">`generate-image.py`</ph></source><target>Python: <ph id="ph1">`generate-image.py`</ph></target>
        </trans-unit></group></group>
        <group id="p182-PARA"><group id="s182-PARA"><trans-unit id="182" translate="yes" xml:space="preserve">
          <source>Review the code that the file contains, noting the following key features:</source><target>Überprüfen Sie den Code, der in der Datei enthalten ist, und beachten Sie dabei die folgenden wichtigen Features:</target>
        </trans-unit></group></group>
        <group id="p183-PARA"><group id="s183-PARA"><trans-unit id="183" translate="yes" xml:space="preserve">
          <source>The code makes https requests to the endpoint for your service, including the key for your service in the header.</source><target>Der Code sendet HTTPS-Anforderungen an den Endpunkt für Ihren Dienst und fügt den Schlüssel für Ihren Dienst in den Header ein.</target>
        </trans-unit></group></group>
        <group id="p184-PARA"><group id="s184-PARA"><trans-unit id="184" translate="yes" xml:space="preserve">
          <source>Both of these values are obtained from the configuration file.</source><target>Beide Werte werden aus der Konfigurationsdatei abgerufen.</target>
        </trans-unit></group></group>
        <group id="p185-PARA"><group id="s185-PARA"><trans-unit id="185" translate="yes" xml:space="preserve">
          <source>The process consists of <bpt id="p1">&lt;u&gt;</bpt>two<ept id="p1">&lt;/u&gt;</ept> REST requests: One to initiate the image-generation request, and another to retrieve the results.</source><target>Der Prozess besteht aus <bpt id="p1">&lt;u&gt;</bpt>zwei<ept id="p1">&lt;/u&gt;</ept> REST-Anforderungen: eine zum Initiieren der Bildgenerierungsanforderung und eine zum Abrufen der Ergebnisse.</target>
        </trans-unit></group></group>
        <group id="p186-PARA"><group id="s186-PARA"><trans-unit id="186" translate="yes" xml:space="preserve">
          <source>The initial request includes the following data:</source><target>Die anfängliche Anforderung enthält die folgenden Daten:</target>
        </trans-unit></group></group>
        <group id="p187-PARA"><group id="s187-PARA"><trans-unit id="187" translate="yes" xml:space="preserve">
          <source>The user-provided prompt that describes the image to be generated</source><target>Die von dem*der Benutzer*in bereitgestellte Eingabeaufforderung, die das zu generierende Bild beschreibt.</target>
        </trans-unit></group></group>
        <group id="p188-PARA"><group id="s188-PARA"><trans-unit id="188" translate="yes" xml:space="preserve">
          <source>The number of images to be generated (in this case, 1)</source><target>Die Anzahl der zu generierenden Bilder (in diesem Fall 1)</target>
        </trans-unit></group></group>
        <group id="p189-PARA"><group id="s189-PARA"><trans-unit id="189" translate="yes" xml:space="preserve">
          <source>The resolution (size) of the image to be generated.</source><target>Die Auflösung (Größe) des zu generierenden Bilds.</target>
        </trans-unit></group></group>
        <group id="p190-PARA"><group id="s190-PARA"><trans-unit id="190" translate="yes" xml:space="preserve">
          <source>The response header from the initial request includes an <bpt id="p1">**</bpt>operation-location<ept id="p1">**</ept> value that is used for the subsequent callback to get the results.</source><target>Der Antwortheader der anfänglichen Anforderung enthält einen Wert vom Typ <bpt id="p1">**</bpt>operation-location<ept id="p1">**</ept>, der für den nachfolgenden Rückruf zum Abrufen der Ergebnisse verwendet wird.</target>
        </trans-unit></group></group>
        <group id="p191-PARA"><group id="s191-PARA"><trans-unit id="191" translate="yes" xml:space="preserve">
          <source>The code polls the callback URL until the status of the image-generation task is <bpt id="p1">*</bpt>succeeded<ept id="p1">*</ept>, and then extracts and displays a URL for the generated image.</source><target>Der Code ruft die Rückruf-URL ab, bis der Status des Bildgenerierungstasks <bpt id="p1">*</bpt>Erfolgreich<ept id="p1">*</ept> ist. Anschließend wird eine URL für das generierte Bild extrahiert und angezeigt.</target>
        </trans-unit></group></group>
        <group id="p192-PARA"><group id="s192-PARA"><trans-unit id="192" translate="yes" xml:space="preserve">
          <source>Run the app</source><target>Ausführen der App</target>
        </trans-unit></group></group>
        <group id="p193-PARA"><group id="s193-PARA"><trans-unit id="193" translate="yes" xml:space="preserve">
          <source>Now that you've reviewed the code, it's time to run it and generate some images.</source><target>Nachdem Sie den Code überprüft haben, ist es an der Zeit, ihn auszuführen und einige Bilder zu generieren.</target>
        </trans-unit></group></group>
        <group id="p194-PARA"><group id="s194-PARA"><trans-unit id="194" translate="yes" xml:space="preserve">
          <source>In the console prompt pane, enter the appropriate command to run your application:</source><target>Geben Sie im Konsoleneingabeaufforderungsbereich den entsprechenden Befehl ein, um Ihre Anwendung auszuführen:</target>
        </trans-unit></group></group>
        <group id="p195-PARA"><group id="s195-PARA"><trans-unit id="195" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p196-PARA"><group id="s196-PARA"><trans-unit id="196" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p197-PARA"><group id="s197-PARA"><trans-unit id="197" translate="yes" xml:space="preserve">
          <source>When prompted, enter a description for an image.</source><target>Wenn Sie dazu aufgefordert werden, geben Sie eine Beschreibung für ein Bild ein.</target>
        </trans-unit></group></group>
        <group id="p198-PARA"><group id="s198-PARA"><trans-unit id="198" translate="yes" xml:space="preserve">
          <source>For example, <bpt id="p1">*</bpt>A giraffe flying a kite<ept id="p1">*</ept>.</source><target>Beispiel: <bpt id="p1">*</bpt>Eine Giraffe, die einen Drachen fliegt<ept id="p1">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p199-PARA"><group id="s199-PARA"><trans-unit id="199" translate="yes" xml:space="preserve">
          <source>Wait for the image to be generated - a hyperlink will be displayed in the console pane.</source><target>Warten Sie, bis das Bild generiert wurde. Im Konsolenbereich wird ein Link angezeigt.</target>
        </trans-unit></group></group>
        <group id="p200-PARA"><group id="s200-PARA"><trans-unit id="200" translate="yes" xml:space="preserve">
          <source>Then select the hyperlink to open a new browser tab and review the image that was generated.</source><target>Wählen Sie dann den Link aus, um eine neue Browserregisterkarte zu öffnen und das generierte Bild zu überprüfen.</target>
        </trans-unit></group></group>
        <group id="p201-PARA"><group id="s201-PARA"><trans-unit id="201" translate="yes" xml:space="preserve">
          <source>Close the tab containing the generated image and re-run the app to generate a new image with a different prompt.</source><target>Schließen Sie die Registerkarte mit dem generierten Bild, und führen Sie die App erneut aus, um ein neues Bild mit einer anderen Eingabeaufforderung zu generieren.</target>
        </trans-unit></group></group>
        <group id="p202-PARA"><group id="s202-PARA"><trans-unit id="202" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigung</target>
        </trans-unit></group></group>
        <group id="p203-PARA"><group id="s203-PARA"><trans-unit id="203" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept> zu löschen.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>