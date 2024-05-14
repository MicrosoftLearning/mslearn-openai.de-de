<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Utilize prompt engineering in your app</source><target>Verwenden von Prompt Engineering in Ihrer App</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Utilize prompt engineering in your app</source><target>Verwenden von Prompt Engineering in Ihrer App</target>
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
          <source>When working with the Azure OpenAI Service, how developers shape their prompt greatly impacts how the generative AI model will respond.</source><target>Bei der Arbeit mit Azure OpenAI Service wirkt sich die Gestaltung der Eingabeaufforderung durch Entwickler*innen erheblich darauf aus, wie das generative KI-Modell reagiert.</target>
        </trans-unit></group></group>
        <group id="p107-PARA"><group id="s107-PARA"><trans-unit id="107" translate="yes" xml:space="preserve">
          <source>Azure OpenAI models are able to tailor and format content, if requested in a clear and concise way.</source><target>Azure OpenAI-Modelle können Inhalte auf klare und präzise Weise anpassen und formatieren.</target>
        </trans-unit></group></group>
        <group id="p108-PARA"><group id="s108-PARA"><trans-unit id="108" translate="yes" xml:space="preserve">
          <source>In this exercise, you'll learn how different prompts for similar content help shape the AI model's response to better satisfy your requirements.</source><target>In dieser Übung erfahren Sie, wie unterschiedliche Eingabeaufforderungen für ähnliche Inhalte dazu beitragen, die Antwort des KI-Modells so zu gestalten, dass Ihre Anforderungen besser erfüllt werden.</target>
        </trans-unit></group></group>
        <group id="p109-PARA"><group id="s109-PARA"><trans-unit id="109" translate="yes" xml:space="preserve">
          <source>This exercise will take approximately <bpt id="p1">**</bpt>25<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ungefähr <bpt id="p1">**</bpt>25<ept id="p1">**</ept> Minuten.</target>
        </trans-unit></group></group>
        <group id="p110-PARA"><group id="s110-PARA"><trans-unit id="110" translate="yes" xml:space="preserve">
          <source>Before you start</source><target>Vorbereitung</target>
        </trans-unit></group></group>
        <group id="p111-PARA"><group id="s111-PARA"><trans-unit id="111" translate="yes" xml:space="preserve">
          <source>You will need an Azure subscription that has been approved for access to the Azure OpenAI service.</source><target>Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p112-PARA"><group id="s112-PARA"><trans-unit id="112" translate="yes" xml:space="preserve">
          <source>To sign up for a free Azure subscription, visit <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>.</source><target>Besuchen Sie <bpt id="p1">[</bpt><ph id="ph1">https://azure.microsoft.com/free</ph><ept id="p1">](https://azure.microsoft.com/free)</ept>, um sich für ein kostenloses Azure-Abonnement zu registrieren.</target>
        </trans-unit></group></group>
        <group id="p113-PARA"><group id="s113-PARA"><trans-unit id="113" translate="yes" xml:space="preserve">
          <source>To request access to the Azure OpenAI service, visit <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</source><target>Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter <bpt id="p1">[</bpt><ph id="ph1">https://aka.ms/oaiapply</ph><ept id="p1">](https://aka.ms/oaiapply)</ept>.</target>
        </trans-unit></group></group>
        <group id="p114-PARA"><group id="s114-PARA"><trans-unit id="114" translate="yes" xml:space="preserve">
          <source>Provision an Azure OpenAI resource</source><target>Bereitstellen einer Azure OpenAI-Ressource</target>
        </trans-unit></group></group>
        <group id="p115-PARA"><group id="s115-PARA"><trans-unit id="115" translate="yes" xml:space="preserve">
          <source>Before you can use Azure OpenAI models, you must provision an Azure OpenAI resource in your Azure subscription.</source><target>Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.</target>
        </trans-unit></group></group>
        <group id="p116-PARA"><group id="s116-PARA"><trans-unit id="116" translate="yes" xml:space="preserve">
          <source>Sign into the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com)</ept>.</source><target>Melden Sie sich beim <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com)</ept> an.</target>
        </trans-unit></group></group>
        <group id="p117-PARA"><group id="s117-PARA"><trans-unit id="117" translate="yes" xml:space="preserve">
          <source>Create an <bpt id="p1">**</bpt>Azure OpenAI<ept id="p1">**</ept> resource with the following settings:</source><target>Erstellen Sie eine <bpt id="p1">**</bpt>Azure OpenAI-Ressource<ept id="p1">**</ept> mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p118-PARA"><group id="s118-PARA"><trans-unit id="118" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: An Azure subscription that has been approved for access to the Azure OpenAI service.</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p119-PARA"><group id="s119-PARA"><trans-unit id="119" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Choose an existing resource group, or create a new one with a name of your choice.</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie entweder eine bereits bestehende Ressourcengruppe, oder erstellen Sie eine neue Ressourcengruppe mit einem beliebigen Namen.</target>
        </trans-unit></group></group>
        <group id="p120-PARA"><group id="s120-PARA"><trans-unit id="120" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Choose any available region.</source><target><bpt id="p1">**</bpt>Region<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region aus.</target>
        </trans-unit></group></group>
        <group id="p121-PARA"><group id="s121-PARA"><trans-unit id="121" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: A unique name of your choice.</source><target><bpt id="p1">**</bpt>Name<ept id="p1">**</ept>: Wählen Sie einen Namen Ihrer Wahl aus.</target>
        </trans-unit></group></group>
        <group id="p122-PARA"><group id="s122-PARA"><trans-unit id="122" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Pricing tier<ept id="p1">**</ept>: Standard S0</source><target><bpt id="p1">**</bpt>Tarif<ept id="p1">**</ept>: Standard S0.</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>Wait for deployment to complete.</source><target>Warten Sie, bis die Bereitstellung abgeschlossen ist.</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>Then go to the deployed Azure OpenAI resource in the Azure portal.</source><target>Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.</target>
        </trans-unit></group></group>
        <group id="p125-PARA"><group id="s125-PARA"><trans-unit id="125" translate="yes" xml:space="preserve">
          <source>Navigate to <bpt id="p1">**</bpt>Keys and Endpoint<ept id="p1">**</ept> page, and save those to a text file to use later.</source><target>Navigieren Sie zur Seite <bpt id="p1">**</bpt>Schlüssel und Endpunkt<ept id="p1">**</ept>, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.</target>
        </trans-unit></group></group>
        <group id="p126-PARA"><group id="s126-PARA"><trans-unit id="126" translate="yes" xml:space="preserve">
          <source>Deploy a model</source><target>Bereitstellen eines Modells</target>
        </trans-unit></group></group>
        <group id="p127-PARA"><group id="s127-PARA"><trans-unit id="127" translate="yes" xml:space="preserve">
          <source>To use the Azure OpenAI API, you must first deploy a model to use through the <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>.</source><target>Um die Azure OpenAI-API verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> verwendet werden kann.</target>
        </trans-unit></group></group>
        <group id="p128-PARA"><group id="s128-PARA"><trans-unit id="128" translate="yes" xml:space="preserve">
          <source>Once deployed, we will reference that model in our app.</source><target>Nach der Bereitstellung verweisen wir in unserer App auf dieses Modell.</target>
        </trans-unit></group></group>
        <group id="p129-PARA"><group id="s129-PARA"><trans-unit id="129" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Explore<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> directly.</source><target>Verwenden Sie auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressourcen die Schaltfläche <bpt id="p2">**</bpt>Erkunden<ept id="p2">**</ept>, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> navigieren.</target>
        </trans-unit></group></group>
        <group id="p130-PARA"><group id="s130-PARA"><trans-unit id="130" translate="yes" xml:space="preserve">
          <source>In Azure OpenAI Studio, on the <bpt id="p1">**</bpt>Deployments<ept id="p1">**</ept> page, view your existing model deployments.</source><target>Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite <bpt id="p1">**</bpt>Bereitstellungen<ept id="p1">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p131-PARA"><group id="s131-PARA"><trans-unit id="131" translate="yes" xml:space="preserve">
          <source>If you don't already have one, create a new deployment of the <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept> model with the following settings:</source><target>Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept>-Modells mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p132-PARA"><group id="s132-PARA"><trans-unit id="132" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model<ept id="p1">**</ept>: gpt-35-turbo-16k</source><target><bpt id="p1">**</bpt>Modell<ept id="p1">**</ept>: gpt-35-turbo-16k</target>
        </trans-unit></group></group>
        <group id="p133-PARA"><group id="s133-PARA"><trans-unit id="133" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model version<ept id="p1">**</ept>: Auto-update to default</source><target><bpt id="p1">**</bpt>Modellversion<ept id="p1">**</ept>: Automatische Aktualisierung auf die Standardeinstellung</target>
        </trans-unit></group></group>
        <group id="p134-PARA"><group id="s134-PARA"><trans-unit id="134" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Deployment name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>A unique name of your choice<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Bereitstellungsname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Ein eindeutiger Name Ihrer Wahl<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p135-PARA"><group id="s135-PARA"><trans-unit id="135" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Advanced options<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Erweiterte Optionen<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p136-PARA"><group id="s136-PARA"><trans-unit id="136" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Content filter<ept id="p1">**</ept>: Default</source><target><bpt id="p1">**</bpt>Inhaltsfilter<ept id="p1">**</ept>: Standard</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tokens per minute rate limit<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></source><target><bpt id="p1">**</bpt>Ratenlimit für Token pro Minute<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Enable dynamic quota<ept id="p1">**</ept>: Enabled</source><target><bpt id="p1">**</bpt>Dynamisches Kontingent aktivieren<ept id="p1">**</ept>: Aktiviert</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source><ph id="ph1">\*</ph> A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.</source><target><ph id="ph1">\*</ph> Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: In some regions, the new model deployment interface doesn't show the <bpt id="p2">**</bpt>Model version<ept id="p2">**</ept> option.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option <bpt id="p2">**</bpt>Modellversion<ept id="p2">**</ept> nicht an.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>In this case, don't worry and continue without setting the option</source><target>Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>Apply prompt engineering in chat playground</source><target>Anwenden von Prompt Engineering in Chatplaygrounds</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source>Before using your app, examine how prompt engineering improves the model response in the playground.</source><target>Bevor Sie Ihre App verwenden, überprüfen Sie, wie das Prompt Engineering die Modellantwort im Playground verbessert.</target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source>In this first example, imagine you are trying to write a python app of animals with fun names.</source><target>In diesem ersten Beispiel stellen Sie sich vor, dass Sie versuchen, eine Python-App mit Tieren mit lustigen Namen zu schreiben.</target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source>In <bpt id="p1">[</bpt>Azure OpenAI Studio<ept id="p1">](https://oai.azure.com/?azure-portal=true)</ept>, navigate to the <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept> playground in the left pane.</source><target>Navigieren Sie in <bpt id="p1">[</bpt>Azure OpenAI Studio<ept id="p1">](https://oai.azure.com/?azure-portal=true)</ept> im linken Bereich zum Playground <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Configuration<ept id="p1">**</ept>, nsure your model deployment is selected.</source><target>Stellen Sie unter <bpt id="p1">**</bpt>Konfiguration<ept id="p1">**</ept> sicher, dass Ihre Modellbereitstellung ausgewählt ist.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> section at the top, enter <ph id="ph1">`You are a helpful AI assistant`</ph> as the system message.</source><target>Geben Sie im Abschnitt <bpt id="p1">**</bpt>Assistenteneinrichtung<ept id="p1">**</ept> <ph id="ph1">`You are a helpful AI assistant`</ph> als Systemmeldung ein.</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Chat session<ept id="p1">**</ept> section, enter the following prompt and press <bpt id="p2">*</bpt>Enter<ept id="p2">*</ept>.</source><target>Geben Sie im Abschnitt <bpt id="p1">**</bpt>Chatsitzung<ept id="p1">**</ept> die folgende Eingabeaufforderung ein, und drücken Sie die <bpt id="p2">*</bpt>EINGABETASTE<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source>The model will likely respond with an answer to satisfy the prompt, split into a numbered list.</source><target>Das Modell liefert wahrscheinlich eine Antwort auf die Eingabeaufforderung, aufgeteilt in eine nummerierte Liste.</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source>This is a good response, but not what we're looking for.</source><target>Das ist eine gute Antwort, aber nicht das, wonach wir suchen.</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source>Next, update the system message to include instructions <ph id="ph1">`You are an AI assistant helping write python code. Complete the app based on provided comments`</ph>.</source><target>Aktualisieren Sie dann die Systemmeldung, um die Anweisungen <ph id="ph1">`You are an AI assistant helping write python code. Complete the app based on provided comments`</ph> aufzunehmen.</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source>Click <bpt id="p1">**</bpt>Save changes<ept id="p1">**</ept></source><target>Klicken Sie auf <bpt id="p1">**</bpt>Änderungen speichern<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source>Format the instructions as python comments.</source><target>Formatieren Sie die Anweisungen als Python-Kommentare.</target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source>Send the following prompt to the model.</source><target>Senden Sie die folgende Eingabeaufforderung an das Modell.</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source>The model should correctly respond with complete python code doing what the comments requested.</source><target>Das Modell sollte ordnungsgemäß mit vollständigem Python-Code antworten und das tun, was in den Kommentaren angefordert wurde.</target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source>Next we'll see the impact of few shot prompting when attempting to classify articles.</source><target>Als Nächstes sehen wir die Auswirkungen einiger Eingabeaufforderungen beim Versuch, Artikel zu klassifizieren.</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>Return to the system message, and enter <ph id="ph1">`You are a helpful AI assistant`</ph> again, and save your changes.</source><target>Kehren Sie zur Systemmeldung zurück, geben Sie erneut <ph id="ph1">`You are a helpful AI assistant`</ph> ein, und speichern Sie Ihre Änderungen.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>This will create a new chat session.</source><target>Dadurch wird eine neue Chatsitzung erstellt.</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source>Send the following prompt to the model.</source><target>Senden Sie die folgende Eingabeaufforderung an das Modell.</target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source>The response will likely be some information about drought in California.</source><target>Die Antwort besteht wahrscheinlich aus einigen Informationen über die Dürre in Kalifornien.</target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source>While not a bad response, it's not the classification we're looking for.</source><target>Obwohl es keine schlechte Antwort ist, ist es nicht die Klassifizierung, nach der wir suchen.</target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> section near the system message, select the <bpt id="p2">**</bpt>Add an example<ept id="p2">**</ept> button.</source><target>Wählen Sie im Abschnitt <bpt id="p1">**</bpt>Assistenteneinrichtung<ept id="p1">**</ept> in der Nähe der Systemmeldung die Schaltfläche <bpt id="p2">**</bpt>Beispiel hinzufügen<ept id="p2">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source>Add the following example.</source><target>Fügen Sie das folgende Beispiel hinzu.</target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>User:<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Benutzer:<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Assistant:<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Assistent:<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source>Add another example with the following text.</source><target>Fügen Sie ein weiteres Beispiel mit dem folgenden Text hinzu.</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>User:<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Benutzer:<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Assistant:<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Assistent:<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source>Save those changed to the assistant setup, and send the same prompt about California drought, provided here again for convenience.</source><target>Speichern Sie diese Änderungen in der Assistenteneinrichtung, und senden Sie die gleiche Eingabeaufforderung über die Dürre in Kalifornien, die hier aus Gründen der Einfachheit noch einmal bereitgestellt wird.</target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source>This time the model should respond with an appropriate classification, even without instructions.</source><target>Dieses Mal sollte das Modell mit einer entsprechenden Klassifizierung reagieren, auch ohne Anweisungen.</target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source>Set up an application in Cloud Shell</source><target>Einrichten einer Anwendung in Cloud Shell</target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source>To show how to integrate with an Azure OpenAI model, we'll use a short command-line application that runs in Cloud Shell on Azure.</source><target>Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird.</target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source>Open up a new browser tab to work with Cloud Shell.</source><target>Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>, select the <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>) button at the top of the page to the right of the search box.</source><target>Klicken Sie im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>A Cloud Shell pane will open at the bottom of the portal.</source><target>Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source>Screenshot of starting Cloud Shell by clicking on the icon to the right of the top search box.</source><target>Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld</target>
        </trans-unit></group></group>
        <group id="p177-PARA"><group id="s177-PARA"><trans-unit id="177" translate="yes" xml:space="preserve">
          <source>The first time you open the Cloud Shell, you may be prompted to choose the type of shell you want to use (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> or <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</source><target>Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> oder <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p178-PARA"><group id="s178-PARA"><trans-unit id="178" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept>.</source><target>Wählen Sie <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p179-PARA"><group id="s179-PARA"><trans-unit id="179" translate="yes" xml:space="preserve">
          <source>If you don't see this option, skip the step.</source><target>Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.</target>
        </trans-unit></group></group>
        <group id="p180-PARA"><group id="s180-PARA"><trans-unit id="180" translate="yes" xml:space="preserve">
          <source>If you're prompted to create storage for your Cloud Shell, select <bpt id="p1">**</bpt>Show advanced settings<ept id="p1">**</ept> and select the following settings:</source><target>Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie <bpt id="p1">**</bpt>Erweiterte Einstellungen anzeigen<ept id="p1">**</ept> und dann die folgenden Einstellungen aus:</target>
        </trans-unit></group></group>
        <group id="p181-PARA"><group id="s181-PARA"><trans-unit id="181" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: Your subscription</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Ihr Abonnement</target>
        </trans-unit></group></group>
        <group id="p182-PARA"><group id="s182-PARA"><trans-unit id="182" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Cloud shell regions<ept id="p1">**</ept>: Choose any available region</source><target><bpt id="p1">**</bpt>Cloud Shell-Regionen<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region</target>
        </trans-unit></group></group>
        <group id="p183-PARA"><group id="s183-PARA"><trans-unit id="183" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Show VNET isolation setings<ept id="p1">**</ept> Unselected</source><target><bpt id="p1">**</bpt>VNET-Isolationseinstellungen anzeigen<ept id="p1">**</ept> Nicht ausgewählt</target>
        </trans-unit></group></group>
        <group id="p184-PARA"><group id="s184-PARA"><trans-unit id="184" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Use the existing resource group where you provisioned your Azure OpenAI resource</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben</target>
        </trans-unit></group></group>
        <group id="p185-PARA"><group id="s185-PARA"><trans-unit id="185" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account<ept id="p1">**</ept>: Create a new storage account with a unique name</source><target><bpt id="p1">**</bpt>Speicherkonto<ept id="p1">**</ept>: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p186-PARA"><group id="s186-PARA"><trans-unit id="186" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>File share<ept id="p1">**</ept>: Create a new file share with a unique name</source><target><bpt id="p1">**</bpt>Dateifreigabe<ept id="p1">**</ept>: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p187-PARA"><group id="s187-PARA"><trans-unit id="187" translate="yes" xml:space="preserve">
          <source>Then wait a minute or so for the storage to be created.</source><target>Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.</target>
        </trans-unit></group></group>
        <group id="p188-PARA"><group id="s188-PARA"><trans-unit id="188" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: If you already have a cloud shell set up in your Azure subscription, you may need to use the <bpt id="p2">**</bpt>Reset user settings<ept id="p2">**</ept> option in the ⚙️ menu to ensure the latest versions of Python and the .NET Framework are installed.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option <bpt id="p2">**</bpt>Benutzereinstellungen zurücksetzen<ept id="p2">**</ept> im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.</target>
        </trans-unit></group></group>
        <group id="p189-PARA"><group id="s189-PARA"><trans-unit id="189" translate="yes" xml:space="preserve">
          <source>Make sure the type of shell indicated on the top left of the Cloud Shell pane is <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept>.</source><target>Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> lautet.</target>
        </trans-unit></group></group>
        <group id="p190-PARA"><group id="s190-PARA"><trans-unit id="190" translate="yes" xml:space="preserve">
          <source>If it's <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept>, switch to <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept> by using the drop-down menu.</source><target>Sollte <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept> angezeigt werden, wechseln Sie über das Dropdownmenü zu <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p191-PARA"><group id="s191-PARA"><trans-unit id="191" translate="yes" xml:space="preserve">
          <source>Once the terminal starts, enter the following command to download the sample application and save it to a folder called <ph id="ph1">`azure-openai`</ph>.</source><target>Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens <ph id="ph1">`azure-openai`</ph> zu speichern.</target>
        </trans-unit></group></group>
        <group id="p192-PARA"><group id="s192-PARA"><trans-unit id="192" translate="yes" xml:space="preserve">
          <source>The files are downloaded to a folder named <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept>.</source><target>Die Dateien werden in einen Ordner namens <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept> heruntergeladen.</target>
        </trans-unit></group></group>
        <group id="p193-PARA"><group id="s193-PARA"><trans-unit id="193" translate="yes" xml:space="preserve">
          <source>Navigate to the lab files for this exercise using the following command.</source><target>Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.</target>
        </trans-unit></group></group>
        <group id="p194-PARA"><group id="s194-PARA"><trans-unit id="194" translate="yes" xml:space="preserve">
          <source>Open the built-in code editor by running the following command:</source><target>Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:</target>
        </trans-unit></group></group>
        <group id="p195-PARA"><group id="s195-PARA"><trans-unit id="195" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>prompts<ept id="p1">**</ept> folder and review text files containing the the prompts that your application will submit to the model.</source><target>Erweitern Sie im Code-Editor den Ordner <bpt id="p1">**</bpt>Eingabeaufforderungen<ept id="p1">**</ept> und überprüfen Sie die Textdateien, die die Eingabeaufforderungen enthalten, die Ihre Anwendung an das Modell sendet.</target>
        </trans-unit></group></group>
        <group id="p196-PARA"><group id="s196-PARA"><trans-unit id="196" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Consult the <bpt id="p2">[</bpt>documentation for the Azure cloud shell code editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept> for more details about using it to work with files in the Azure cloud shell environment.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der <bpt id="p2">[</bpt>Dokumentation für den Azure Cloud Shell-Code-Editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept>.</target>
        </trans-unit></group></group>
        <group id="p197-PARA"><group id="s197-PARA"><trans-unit id="197" translate="yes" xml:space="preserve">
          <source>Configure your application</source><target>Konfigurieren der Anwendung</target>
        </trans-unit></group></group>
        <group id="p198-PARA"><group id="s198-PARA"><trans-unit id="198" translate="yes" xml:space="preserve">
          <source>For this exercise, you'll complete some key parts of the application to enable using your Azure OpenAI resource.</source><target>In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.</target>
        </trans-unit></group></group>
        <group id="p199-PARA"><group id="s199-PARA"><trans-unit id="199" translate="yes" xml:space="preserve">
          <source>Applications for both C# and Python have been provided.</source><target>Anwendungen für C# und Python wurden bereitgestellt.</target>
        </trans-unit></group></group>
        <group id="p200-PARA"><group id="s200-PARA"><trans-unit id="200" translate="yes" xml:space="preserve">
          <source>Both apps feature the same functionality.</source><target>Beide Apps verfügen über die gleiche Funktionalität.</target>
        </trans-unit></group></group>
        <group id="p201-PARA"><group id="s201-PARA"><trans-unit id="201" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> or <bpt id="p2">**</bpt>Python<ept id="p2">**</ept> folder, depending on your language preference.</source><target>Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner <bpt id="p1">**</bpt>CSharp<ept id="p1">**</ept> oder <bpt id="p2">**</bpt>Python<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p202-PARA"><group id="s202-PARA"><trans-unit id="202" translate="yes" xml:space="preserve">
          <source>Open the configuration file for your language.</source><target>Öffnen Sie die Konfigurationsdatei für Ihre Sprache.</target>
        </trans-unit></group></group>
        <group id="p203-PARA"><group id="s203-PARA"><trans-unit id="203" translate="yes" xml:space="preserve">
          <source>C#: <ph id="ph1">`appsettings.json`</ph></source><target>C#: <ph id="ph1">`appsettings.json`</ph></target>
        </trans-unit></group></group>
        <group id="p204-PARA"><group id="s204-PARA"><trans-unit id="204" translate="yes" xml:space="preserve">
          <source>Python: <ph id="ph1">`.env`</ph></source><target>Python: <ph id="ph1">`.env`</ph></target>
        </trans-unit></group></group>
        <group id="p205-PARA"><group id="s205-PARA"><trans-unit id="205" translate="yes" xml:space="preserve">
          <source>Update the configuration values to include the <bpt id="p1">**</bpt>endpoint<ept id="p1">**</ept> and <bpt id="p2">**</bpt>key<ept id="p2">**</ept> from the Azure OpenAI resource you created, as well as the model name that you deployed.</source><target>Aktualisieren Sie die Konfigurationswerte, um den <bpt id="p1">**</bpt>Endpunkt<ept id="p1">**</ept> und den <bpt id="p2">**</bpt>Schlüssel<ept id="p2">**</ept> aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen hinzuzufügen.</target>
        </trans-unit></group></group>
        <group id="p206-PARA"><group id="s206-PARA"><trans-unit id="206" translate="yes" xml:space="preserve">
          <source>Save the file.</source><target>Speichern Sie die Datei .</target>
        </trans-unit></group></group>
        <group id="p207-PARA"><group id="s207-PARA"><trans-unit id="207" translate="yes" xml:space="preserve">
          <source>In the console pane, enter the following commands to navigate to the folder for your preferred language and install the necessary packages.</source><target>Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.</target>
        </trans-unit></group></group>
        <group id="p208-PARA"><group id="s208-PARA"><trans-unit id="208" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p209-PARA"><group id="s209-PARA"><trans-unit id="209" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p210-PARA"><group id="s210-PARA"><trans-unit id="210" translate="yes" xml:space="preserve">
          <source>Navigate to your preferred language folder, select the code file, and add the necessary libraries.</source><target>Navigieren Sie zu Ihrem bevorzugten Sprachordner, wählen Sie die Codedatei aus, und fügen Sie die erforderlichen Bibliotheken hinzu.</target>
        </trans-unit></group></group>
        <group id="p211-PARA"><group id="s211-PARA"><trans-unit id="211" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p212-PARA"><group id="s212-PARA"><trans-unit id="212" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p213-PARA"><group id="s213-PARA"><trans-unit id="213" translate="yes" xml:space="preserve">
          <source>Open up the application code for your language and add the necessary code for configuring the client.</source><target>Öffnen Sie den Anwendungscode für Ihre Sprache, und fügen Sie den erforderlichen Code zum Konfigurieren des Clients hinzu.</target>
        </trans-unit></group></group>
        <group id="p214-PARA"><group id="s214-PARA"><trans-unit id="214" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p215-PARA"><group id="s215-PARA"><trans-unit id="215" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p216-PARA"><group id="s216-PARA"><trans-unit id="216" translate="yes" xml:space="preserve">
          <source>In the function that calls the Azure OpenAI model, add the code to format and send the request to the model.</source><target>Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.</target>
        </trans-unit></group></group>
        <group id="p217-PARA"><group id="s217-PARA"><trans-unit id="217" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p218-PARA"><group id="s218-PARA"><trans-unit id="218" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p219-PARA"><group id="s219-PARA"><trans-unit id="219" translate="yes" xml:space="preserve">
          <source>Run your application</source><target>Ausführen der Anwendung</target>
        </trans-unit></group></group>
        <group id="p220-PARA"><group id="s220-PARA"><trans-unit id="220" translate="yes" xml:space="preserve">
          <source>Now that your app has been configured, run it to send your request to your model and observe the response.</source><target>Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten.</target>
        </trans-unit></group></group>
        <group id="p221-PARA"><group id="s221-PARA"><trans-unit id="221" translate="yes" xml:space="preserve">
          <source>You'll notice the only difference between the different options is the content of the prompt, all other parameters (such as token count and temperature) remain the same for each request.</source><target>Sie werden feststellen, dass der einzige Unterschied zwischen den verschiedenen Optionen der Inhalt der Eingabeaufforderung ist. Alle anderen Parameter (z. B. Tokenanzahl und Temperatur) bleiben für jede Anforderung gleich.</target>
        </trans-unit></group></group>
        <group id="p222-PARA"><group id="s222-PARA"><trans-unit id="222" translate="yes" xml:space="preserve">
          <source>Each prompt is displayed in the console as it sends for you to see how differences in prompts produce different responses.</source><target>Jede Eingabeaufforderung wird während des Sendevorgangs in der Konsole angezeigt, damit Sie sehen können, wie unterschiedliche Eingabeaufforderungen verschiedene Antworten erzeugen.</target>
        </trans-unit></group></group>
        <group id="p223-PARA"><group id="s223-PARA"><trans-unit id="223" translate="yes" xml:space="preserve">
          <source>In the Cloud Shell bash terminal, navigate to the folder for your preferred language.</source><target>Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.</target>
        </trans-unit></group></group>
        <group id="p224-PARA"><group id="s224-PARA"><trans-unit id="224" translate="yes" xml:space="preserve">
          <source>Run the application, and expand the terminal to take up most of your browser window.</source><target>Führen Sie die Anwendung aus, und erweitern Sie das Terminal, um den größten Teil Ihres Browserfensters zu nutzen.</target>
        </trans-unit></group></group>
        <group id="p225-PARA"><group id="s225-PARA"><trans-unit id="225" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: <ph id="ph1">`dotnet run`</ph></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : <ph id="ph1">`dotnet run`</ph></target>
        </trans-unit></group></group>
        <group id="p226-PARA"><group id="s226-PARA"><trans-unit id="226" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python prompt-engineering.py`</ph></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python prompt-engineering.py`</ph></target>
        </trans-unit></group></group>
        <group id="p227-PARA"><group id="s227-PARA"><trans-unit id="227" translate="yes" xml:space="preserve">
          <source>Choose option <bpt id="p1">**</bpt>1<ept id="p1">**</ept> for the most basic prompt.</source><target>Wählen Sie Option <bpt id="p1">**</bpt>1<ept id="p1">**</ept> für die einfachste Eingabeaufforderung aus.</target>
        </trans-unit></group></group>
        <group id="p228-PARA"><group id="s228-PARA"><trans-unit id="228" translate="yes" xml:space="preserve">
          <source>Observe the prompt input, and generated output.</source><target>Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p229-PARA"><group id="s229-PARA"><trans-unit id="229" translate="yes" xml:space="preserve">
          <source>The AI model will likely produce a good generic introduction to a wildlife rescue.</source><target>Das KI-Modell wird wahrscheinlich eine gute allgemeine Einführung in die Rettung von Wildtieren liefern.</target>
        </trans-unit></group></group>
        <group id="p230-PARA"><group id="s230-PARA"><trans-unit id="230" translate="yes" xml:space="preserve">
          <source>Next, choose option <bpt id="p1">**</bpt>2<ept id="p1">**</ept> to give it a prompt asking for an intro email, along with some details about the wildlife rescue.</source><target>Wählen Sie als Nächstes Option <bpt id="p1">**</bpt>2<ept id="p1">**</ept> aus, um eine Eingabeaufforderung für eine Vorstellungs-E-Mail mit einigen Details über die Wildtierrettung zu erhalten.</target>
        </trans-unit></group></group>
        <group id="p231-PARA"><group id="s231-PARA"><trans-unit id="231" translate="yes" xml:space="preserve">
          <source>Observe the prompt input, and generated output.</source><target>Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p232-PARA"><group id="s232-PARA"><trans-unit id="232" translate="yes" xml:space="preserve">
          <source>This time, you'll likely see the format of an email with the specific animals included, as well as the call for donations.</source><target>Dieses Mal werden Sie wahrscheinlich das Format einer E-Mail sehen, in der die Tiere und der Spendenaufruf enthalten sind.</target>
        </trans-unit></group></group>
        <group id="p233-PARA"><group id="s233-PARA"><trans-unit id="233" translate="yes" xml:space="preserve">
          <source>Next, choose option <bpt id="p1">**</bpt>3<ept id="p1">**</ept> to ask for an email similar to above, but with a formatted table with additional animals included.</source><target>Wählen Sie als Nächstes Option <bpt id="p1">**</bpt>3<ept id="p1">**</ept> aus, um eine E-Mail ähnlich der obigen zu erhalten, jedoch mit einer formatierten Tabelle mit zusätzlichen Tieren.</target>
        </trans-unit></group></group>
        <group id="p234-PARA"><group id="s234-PARA"><trans-unit id="234" translate="yes" xml:space="preserve">
          <source>Observe the prompt input, and generated output.</source><target>Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p235-PARA"><group id="s235-PARA"><trans-unit id="235" translate="yes" xml:space="preserve">
          <source>This time, you'll likely see a similar email with text formatted in a specific way (in this case, a table near the end) demonstrating how the generative AI models can format output when requested.</source><target>Dieses Mal sehen Sie wahrscheinlich eine ähnliche E-Mail mit speziell formatiertem Text (in diesem Fall eine Tabelle am Ende), die zeigt, wie die generativen KI-Modelle die Ausgabe bei Bedarf formatieren können.</target>
        </trans-unit></group></group>
        <group id="p236-PARA"><group id="s236-PARA"><trans-unit id="236" translate="yes" xml:space="preserve">
          <source>Next, choose option <bpt id="p1">**</bpt>4<ept id="p1">**</ept> to ask for a similar email, but this time specifying different tone in the system message.</source><target>Wählen Sie als Nächstes Option <bpt id="p1">**</bpt>4<ept id="p1">**</ept> aus, um eine ähnliche E-Mail anzufordern, aber dieses Mal mit einem anderen Ton in der Systemmeldung.</target>
        </trans-unit></group></group>
        <group id="p237-PARA"><group id="s237-PARA"><trans-unit id="237" translate="yes" xml:space="preserve">
          <source>Observe the prompt input, and generated output.</source><target>Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p238-PARA"><group id="s238-PARA"><trans-unit id="238" translate="yes" xml:space="preserve">
          <source>This time you'll likely see the email in a similar format, but with a much more informal tone.</source><target>Diesmal werden Sie die E-Mail wahrscheinlich in einem ähnlichen Format sehen, aber in einem viel informelleren Ton.</target>
        </trans-unit></group></group>
        <group id="p239-PARA"><group id="s239-PARA"><trans-unit id="239" translate="yes" xml:space="preserve">
          <source>You'll likely even see jokes included!</source><target>Wahrscheinlich werden sogar Witze enthalten sein!</target>
        </trans-unit></group></group>
        <group id="p240-PARA"><group id="s240-PARA"><trans-unit id="240" translate="yes" xml:space="preserve">
          <source>Increasing the temperature often causes the response to vary, even when provided the same prompt, due to the increased randomness.</source><target>Eine Erhöhung der Temperatur führt häufig dazu, dass die Antworten variieren, selbst wenn die gleiche Eingabeaufforderung bereitgestellt wird, was auf die erhöhte Zufälligkeit zurückzuführen ist.</target>
        </trans-unit></group></group>
        <group id="p241-PARA"><group id="s241-PARA"><trans-unit id="241" translate="yes" xml:space="preserve">
          <source>You can run it multiple times with different temperature or top_p values to see how that impacts the response to the same prompt.</source><target>Sie können sie mehrmals mit unterschiedlichen Temperatur- oder top_p-Werten ausführen, um zu sehen, wie sich dies auf die Antwort auf dieselbe Eingabeaufforderung auswirkt.</target>
        </trans-unit></group></group>
        <group id="p242-PARA"><group id="s242-PARA"><trans-unit id="242" translate="yes" xml:space="preserve">
          <source>If you would like to see the full response from Azure OpenAI, you can set the <ph id="ph1">`printFullResponse`</ph> variable to <ph id="ph2">`True`</ph>, and rerun the app.</source><target>Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die <ph id="ph1">`printFullResponse`</ph>-Variable auf <ph id="ph2">`True`</ph> festlegen und die App erneut ausführen.</target>
        </trans-unit></group></group>
        <group id="p243-PARA"><group id="s243-PARA"><trans-unit id="243" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigung</target>
        </trans-unit></group></group>
        <group id="p244-PARA"><group id="s244-PARA"><trans-unit id="244" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the deployment or the entire resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept> zu löschen.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>