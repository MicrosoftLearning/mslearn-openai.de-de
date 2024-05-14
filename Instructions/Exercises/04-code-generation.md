<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Generate and improve code with Azure OpenAI Service</source><target>Generieren und Verbessern von Code mit Azure OpenAI Service</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Generate and improve code with Azure OpenAI Service</source><target>Generieren und Verbessern von Code mit Azure OpenAI Service</target>
        </trans-unit></group></group>
        <group id="p103-PARA"><group id="s103-PARA"><trans-unit id="103" translate="yes" xml:space="preserve">
          <source>The Azure OpenAI Service models can generate code for you using natural language prompts, fixing bugs in completed code, and providing code comments.</source><target>Die Azure OpenAI Service-Modelle können Code für Sie generieren, indem Sie Eingabeaufforderungen in natürlicher Sprache verwenden, Fehler in fertigem Code beheben und Codekommentare bereitstellen.</target>
        </trans-unit></group></group>
        <group id="p104-PARA"><group id="s104-PARA"><trans-unit id="104" translate="yes" xml:space="preserve">
          <source>These models can also explain and simplify existing code to help you understand what it does and how to improve it.</source><target>Diese Modelle können auch vorhandenen Code erklären und vereinfachen, damit Sie verstehen, was er tut und wie man ihn verbessern kann.</target>
        </trans-unit></group></group>
        <group id="p105-PARA"><group id="s105-PARA"><trans-unit id="105" translate="yes" xml:space="preserve">
          <source>This exercise will take approximately <bpt id="p1">**</bpt>25<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ungefähr <bpt id="p1">**</bpt>25<ept id="p1">**</ept> Minuten.</target>
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
          <source>Sign into the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com)</ept>.</source><target>Melden Sie sich beim <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com)</ept> an.</target>
        </trans-unit></group></group>
        <group id="p113-PARA"><group id="s113-PARA"><trans-unit id="113" translate="yes" xml:space="preserve">
          <source>Create an <bpt id="p1">**</bpt>Azure OpenAI<ept id="p1">**</ept> resource with the following settings:</source><target>Erstellen Sie eine <bpt id="p1">**</bpt>Azure OpenAI-Ressource<ept id="p1">**</ept> mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p114-PARA"><group id="s114-PARA"><trans-unit id="114" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: An Azure subscription that has been approved for access to the Azure OpenAI service.</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
        </trans-unit></group></group>
        <group id="p115-PARA"><group id="s115-PARA"><trans-unit id="115" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Choose an existing resource group, or create a new one with a name of your choice.</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie entweder eine bereits bestehende Ressourcengruppe, oder erstellen Sie eine neue Ressourcengruppe mit einem beliebigen Namen.</target>
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
          <source>Navigate to <bpt id="p1">**</bpt>Keys and Endpoint<ept id="p1">**</ept> page, and save those to a text file to use later.</source><target>Navigieren Sie zur Seite <bpt id="p1">**</bpt>Schlüssel und Endpunkt<ept id="p1">**</ept>, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.</target>
        </trans-unit></group></group>
        <group id="p122-PARA"><group id="s122-PARA"><trans-unit id="122" translate="yes" xml:space="preserve">
          <source>Deploy a model</source><target>Bereitstellen eines Modells</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>To use the Azure OpenAI API for code generation, you must first deploy a model to use through the <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>.</source><target>Um die Azure OpenAI-API zur Codegenerierung verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept> verwendet werden kann.</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>Once deployed, we will use the model with the playground and reference that model in our app.</source><target>Nach der Bereitstellung verwenden wir das Modell mit dem Playground und verweisen in unserer App auf dieses Modell.</target>
        </trans-unit></group></group>
        <group id="p125-PARA"><group id="s125-PARA"><trans-unit id="125" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Explore<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab. Alternatively, navigate to <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> directly.</source><target>Verwenden Sie auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressourcen die Schaltfläche <bpt id="p2">**</bpt>Erkunden<ept id="p2">**</ept>, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu <bpt id="p3">[</bpt>Azure OpenAI Studio<ept id="p3">](https://oai.azure.com/?azure-portal=true)</ept> navigieren.</target>
        </trans-unit></group></group>
        <group id="p126-PARA"><group id="s126-PARA"><trans-unit id="126" translate="yes" xml:space="preserve">
          <source>In Azure OpenAI Studio, on the <bpt id="p1">**</bpt>Deployments<ept id="p1">**</ept> page, view your existing model deployments.</source><target>Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite <bpt id="p1">**</bpt>Bereitstellungen<ept id="p1">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p127-PARA"><group id="s127-PARA"><trans-unit id="127" translate="yes" xml:space="preserve">
          <source>If you don't already have one, create a new deployment of the <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept> model with the following settings:</source><target>Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des <bpt id="p1">**</bpt>gpt-35-turbo-16k<ept id="p1">**</ept>-Modells mit den folgenden Einstellungen:</target>
        </trans-unit></group></group>
        <group id="p128-PARA"><group id="s128-PARA"><trans-unit id="128" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model<ept id="p1">**</ept>: gpt-35-turbo-16k</source><target><bpt id="p1">**</bpt>Modell<ept id="p1">**</ept>: gpt-35-turbo-16k</target>
        </trans-unit></group></group>
        <group id="p129-PARA"><group id="s129-PARA"><trans-unit id="129" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Model version<ept id="p1">**</ept>: Auto-update to default</source><target><bpt id="p1">**</bpt>Modellversion<ept id="p1">**</ept>: Automatische Aktualisierung auf die Standardeinstellung</target>
        </trans-unit></group></group>
        <group id="p130-PARA"><group id="s130-PARA"><trans-unit id="130" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Deployment name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>A unique name of your choice<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Bereitstellungsname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Wählen Sie einen Namen Ihrer Wahl aus<ept id="p2">*</ept></target>
        </trans-unit></group></group>
        <group id="p131-PARA"><group id="s131-PARA"><trans-unit id="131" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Advanced options<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Erweiterte Optionen<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p132-PARA"><group id="s132-PARA"><trans-unit id="132" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Content filter<ept id="p1">**</ept>: Default</source><target><bpt id="p1">**</bpt>Inhaltsfilter<ept id="p1">**</ept>: Standard</target>
        </trans-unit></group></group>
        <group id="p133-PARA"><group id="s133-PARA"><trans-unit id="133" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tokens per minute rate limit<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></source><target><bpt id="p1">**</bpt>Ratenlimit für Token pro Minute<ept id="p1">**</ept>: 5K<ph id="ph1">\*</ph></target>
        </trans-unit></group></group>
        <group id="p134-PARA"><group id="s134-PARA"><trans-unit id="134" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Enable dynamic quota<ept id="p1">**</ept>: Enabled</source><target><bpt id="p1">**</bpt>Dynamisches Kontingent aktivieren<ept id="p1">**</ept>: Aktiviert</target>
        </trans-unit></group></group>
        <group id="p135-PARA"><group id="s135-PARA"><trans-unit id="135" translate="yes" xml:space="preserve">
          <source><ph id="ph1">\*</ph> A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.</source><target><ph id="ph1">\*</ph> Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.</target>
        </trans-unit></group></group>
        <group id="p136-PARA"><group id="s136-PARA"><trans-unit id="136" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: In some regions, the new model deployment interface doesn't show the <bpt id="p2">**</bpt>Model version<ept id="p2">**</ept> option.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option <bpt id="p2">**</bpt>Modellversion<ept id="p2">**</ept> nicht an.</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source>In this case, don't worry and continue without setting the option</source><target>Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen</target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source>Generate code in chat playground</source><target>Generieren von Code im Playground für Chats</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source>Before using in your app, examine how Azure OpenAI can generate and explain code in the chat playground.</source><target>Überprüfen Sie vor der Verwendung in Ihrer App, wie Azure OpenAI Code im Playground für Chats generieren und erklären kann.</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source>In <bpt id="p1">[</bpt>Azure OpenAI Studio<ept id="p1">](https://oai.azure.com/?azure-portal=true)</ept>, navigate to the <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept> playground in the left pane.</source><target>Navigieren Sie in <bpt id="p1">[</bpt>Azure OpenAI Studio<ept id="p1">](https://oai.azure.com/?azure-portal=true)</ept> im linken Bereich zum Playground <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept>.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Configuration<ept id="p1">**</ept>, nsure your model deployment is selected.</source><target>Stellen Sie unter <bpt id="p1">**</bpt>Konfiguration<ept id="p1">**</ept> sicher, dass Ihre Modellbereitstellung ausgewählt ist.</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> section at the top, select the <bpt id="p2">**</bpt>Default<ept id="p2">**</ept> system message template.</source><target>Wählen Sie oben im Abschnitt <bpt id="p1">**</bpt>Assistenteneinrichtung<ept id="p1">**</ept> die Vorlage <bpt id="p2">**</bpt>Standardsystemmeldung<ept id="p2">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Chat session<ept id="p1">**</ept> section, enter the following prompt and press <bpt id="p2">*</bpt>Enter<ept id="p2">*</ept>.</source><target>Geben Sie im Abschnitt <bpt id="p1">**</bpt>Chatsitzung<ept id="p1">**</ept> die folgende Eingabeaufforderung ein, und drücken Sie die <bpt id="p2">*</bpt>EINGABETASTE<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source>The model will likely respond with a function, with some explanation of what the function does and how to call it.</source><target>Das Modell antwortet wahrscheinlich mit einer Funktion, mit einer Erklärung, was die Funktion tut und wie sie aufgerufen werden kann.</target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source>Next, send the prompt <ph id="ph1">`Do the same thing, but this time write it in C#`</ph>.</source><target>Senden Sie als Nächstes die Eingabeaufforderung <ph id="ph1">`Do the same thing, but this time write it in C#`</ph>.</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>Observe the output.</source><target>Beobachten Sie die Ausgabe.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>The model likely responded very similarly as the first time, but this time coding in C#.</source><target>Das Modell reagierte wahrscheinlich sehr ähnlich wie beim ersten Mal, diesmal jedoch in C#.</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source>You can ask it again for a different language of your choice, or a function to complete a different task such as reversing the input string.</source><target>Sie können es erneut nach einer anderen Sprache Ihrer Wahl oder einer Funktion fragen, um eine andere Aufgabe zu erfüllen, wie z. B. das Umkehren einer Eingabezeichenfolge.</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source>Next, let's explore using AI to understand code with this example of a random function you saw written in Ruby.</source><target>Als Nächstes untersuchen wir die Verwendung von KI zum Verständnis von Code anhand dieses Beispiels einer Zufallsfunktion, die Sie in Ruby geschrieben haben.</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source>Send the following prompt as the user message.</source><target>Senden Sie die folgende Eingabeaufforderung als Benutzernachricht.</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source>Observe the output, which explains what the function does in natural language.</source><target>Beobachten Sie die Ausgabe, die erklärt, was die Funktion in natürlicher Sprache ausführt.</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source>Try asking the model to rewrite it in a language you are familiar with.</source><target>Fordern Sie das Modell auf, sie in einer Sprache neu zu schreiben, mit der Sie vertraut sind.</target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source>Set up an application in Cloud Shell</source><target>Einrichten einer Anwendung in Cloud Shell</target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source>To show how to integrate with an Azure OpenAI model, we'll use a short command-line application that runs in Cloud Shell on Azure.</source><target>Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird.</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source>Open up a new browser tab to work with Cloud Shell.</source><target>Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.</target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept>, select the <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>) button at the top of the page to the right of the search box.</source><target>Klicken Sie im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com?azure-portal=true)</ept> oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche <bpt id="p2">**</bpt>[&gt;_]<ept id="p2">**</ept> (<bpt id="p3">*</bpt>Cloud Shell<ept id="p3">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>A Cloud Shell pane will open at the bottom of the portal.</source><target>Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>Screenshot of starting Cloud Shell by clicking on the icon to the right of the top search box.</source><target>Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source>The first time you open the Cloud Shell, you may be prompted to choose the type of shell you want to use (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> or <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</source><target>Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (<bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> oder <bpt id="p2">*</bpt>PowerShell<ept id="p2">*</ept>).</target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source>Select <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept>.</source><target>Wählen Sie <bpt id="p1">**</bpt>Bash<ept id="p1">**</ept> aus.</target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source>If you don't see this option, skip the step.</source><target>Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.</target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source>If you're prompted to create storage for your Cloud Shell, select <bpt id="p1">**</bpt>Show advanced settings<ept id="p1">**</ept> and select the following settings:</source><target>Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie <bpt id="p1">**</bpt>Erweiterte Einstellungen anzeigen<ept id="p1">**</ept> und dann die folgenden Einstellungen aus:</target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Subscription<ept id="p1">**</ept>: Your subscription</source><target><bpt id="p1">**</bpt>Abonnement<ept id="p1">**</ept>: Ihr Abonnement</target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Cloud shell regions<ept id="p1">**</ept>: Choose any available region</source><target><bpt id="p1">**</bpt>Cloud Shell-Regionen<ept id="p1">**</ept>: Wählen Sie eine beliebige verfügbare Region</target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Show VNET isolation setings<ept id="p1">**</ept> Unselected</source><target><bpt id="p1">**</bpt>VNET-Isolationseinstellungen anzeigen<ept id="p1">**</ept> Nicht ausgewählt</target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Resource group<ept id="p1">**</ept>: Use the existing resource group where you provisioned your Azure OpenAI resource</source><target><bpt id="p1">**</bpt>Ressourcengruppe<ept id="p1">**</ept>: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Storage account<ept id="p1">**</ept>: Create a new storage account with a unique name</source><target><bpt id="p1">**</bpt>Speicherkonto<ept id="p1">**</ept>: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>File share<ept id="p1">**</ept>: Create a new file share with a unique name</source><target><bpt id="p1">**</bpt>Dateifreigabe<ept id="p1">**</ept>: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen</target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source>Then wait a minute or so for the storage to be created.</source><target>Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.</target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: If you already have a cloud shell set up in your Azure subscription, you may need to use the <bpt id="p2">**</bpt>Reset user settings<ept id="p2">**</ept> option in the ⚙️ menu to ensure the latest versions of Python and the .NET Framework are installed.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option <bpt id="p2">**</bpt>Benutzereinstellungen zurücksetzen<ept id="p2">**</ept> im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.</target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source>Make sure the type of shell indicated on the top left of the Cloud Shell pane is <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept>.</source><target>Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ <bpt id="p1">*</bpt>Bash<ept id="p1">*</ept> lautet.</target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source>If it's <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept>, switch to <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept> by using the drop-down menu.</source><target>Sollte <bpt id="p1">*</bpt>PowerShell<ept id="p1">*</ept> angezeigt werden, wechseln Sie über das Dropdownmenü zu <bpt id="p2">*</bpt>Bash<ept id="p2">*</ept>.</target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source>Once the terminal starts, enter the following command to download the sample application and save it to a folder called <ph id="ph1">`azure-openai`</ph>.</source><target>Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens <ph id="ph1">`azure-openai`</ph> zu speichern.</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>The files are downloaded to a folder named <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept>.</source><target>Die Dateien werden in einen Ordner namens <bpt id="p1">**</bpt>azure-openai<ept id="p1">**</ept> heruntergeladen.</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>Navigate to the lab files for this exercise using the following command.</source><target>Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source>Open the built-in code editor by running the following command:</source><target>Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:</target>
        </trans-unit></group></group>
        <group id="p177-PARA"><group id="s177-PARA"><trans-unit id="177" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <bpt id="p1">**</bpt>sample-code<ept id="p1">**</ept> folder and review the code files that your application will use the model to improve.</source><target>Erweitern Sie im Code-Editor den Ordner <bpt id="p1">**</bpt>Beispielcode<ept id="p1">**</ept> und überprüfen Sie die Codedateien, die Ihre Anwendung mithilfe des Modells optimiert.</target>
        </trans-unit></group></group>
        <group id="p178-PARA"><group id="s178-PARA"><trans-unit id="178" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Tip<ept id="p1">**</ept>: Consult the <bpt id="p2">[</bpt>documentation for the Azure cloud shell code editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept> for more details about using it to work with files in the Azure cloud shell environment.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der <bpt id="p2">[</bpt>Dokumentation für den Azure Cloud Shell-Code-Editor<ept id="p2">](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor)</ept>.</target>
        </trans-unit></group></group>
        <group id="p179-PARA"><group id="s179-PARA"><trans-unit id="179" translate="yes" xml:space="preserve">
          <source>Configure your application</source><target>Konfigurieren der Anwendung</target>
        </trans-unit></group></group>
        <group id="p180-PARA"><group id="s180-PARA"><trans-unit id="180" translate="yes" xml:space="preserve">
          <source>For this exercise, you'll complete some key parts of the application to enable using your Azure OpenAI resource.</source><target>In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.</target>
        </trans-unit></group></group>
        <group id="p181-PARA"><group id="s181-PARA"><trans-unit id="181" translate="yes" xml:space="preserve">
          <source>Applications for both C# and Python have been provided.</source><target>Anwendungen für C# und Python wurden bereitgestellt.</target>
        </trans-unit></group></group>
        <group id="p182-PARA"><group id="s182-PARA"><trans-unit id="182" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the language folder for your preferred language.</source><target>Erweitern Sie im Code-Editor den Sprachordner für Ihre bevorzugte Sprache.</target>
        </trans-unit></group></group>
        <group id="p183-PARA"><group id="s183-PARA"><trans-unit id="183" translate="yes" xml:space="preserve">
          <source>Open the configuration file for your language.</source><target>Öffnen Sie die Konfigurationsdatei für Ihre Sprache.</target>
        </trans-unit></group></group>
        <group id="p184-PARA"><group id="s184-PARA"><trans-unit id="184" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: <ph id="ph1">`appsettings.json`</ph></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : <ph id="ph1">`appsettings.json`</ph></target>
        </trans-unit></group></group>
        <group id="p185-PARA"><group id="s185-PARA"><trans-unit id="185" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`.env`</ph></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`.env`</ph></target>
        </trans-unit></group></group>
        <group id="p186-PARA"><group id="s186-PARA"><trans-unit id="186" translate="yes" xml:space="preserve">
          <source>Update the configuration values to include the <bpt id="p1">**</bpt>endpoint<ept id="p1">**</ept> and <bpt id="p2">**</bpt>key<ept id="p2">**</ept> from the Azure OpenAI resource you created, as well as the name of your deployment.</source><target>Aktualisieren Sie die Konfigurationswerte, um den <bpt id="p1">**</bpt>Endpunkt<ept id="p1">**</ept> und den <bpt id="p2">**</bpt>Schlüssel<ept id="p2">**</ept> aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen hinzuzufügen.</target>
        </trans-unit></group></group>
        <group id="p187-PARA"><group id="s187-PARA"><trans-unit id="187" translate="yes" xml:space="preserve">
          <source>Save the file.</source><target>Speichern Sie die Datei .</target>
        </trans-unit></group></group>
        <group id="p188-PARA"><group id="s188-PARA"><trans-unit id="188" translate="yes" xml:space="preserve">
          <source>In the console pane, enter the following commands to navigate to the folder for your preferred language and install the necessary packages.</source><target>Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.</target>
        </trans-unit></group></group>
        <group id="p189-PARA"><group id="s189-PARA"><trans-unit id="189" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p190-PARA"><group id="s190-PARA"><trans-unit id="190" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept></target>
        </trans-unit></group></group>
        <group id="p191-PARA"><group id="s191-PARA"><trans-unit id="191" translate="yes" xml:space="preserve">
          <source>Select the code file in this folder for your language and add the necessary libraries.</source><target>Wählen Sie die Codedatei in diesem Ordner für Ihre Sprache aus, und fügen Sie die erforderlichen Bibliotheken hinzu.</target>
        </trans-unit></group></group>
        <group id="p192-PARA"><group id="s192-PARA"><trans-unit id="192" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: Program.cs</source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : Program.cs</target>
        </trans-unit></group></group>
        <group id="p193-PARA"><group id="s193-PARA"><trans-unit id="193" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</target>
        </trans-unit></group></group>
        <group id="p194-PARA"><group id="s194-PARA"><trans-unit id="194" translate="yes" xml:space="preserve">
          <source>Add the necessary code for configuring the client.</source><target>Fügen Sie den erforderlichen Code zum Konfigurieren des Clients hinzu.</target>
        </trans-unit></group></group>
        <group id="p195-PARA"><group id="s195-PARA"><trans-unit id="195" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: Program.cs</source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : Program.cs</target>
        </trans-unit></group></group>
        <group id="p196-PARA"><group id="s196-PARA"><trans-unit id="196" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</target>
        </trans-unit></group></group>
        <group id="p197-PARA"><group id="s197-PARA"><trans-unit id="197" translate="yes" xml:space="preserve">
          <source>In the function that calls the Azure OpenAI model, add the code to format and send the request to the model.</source><target>Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.</target>
        </trans-unit></group></group>
        <group id="p198-PARA"><group id="s198-PARA"><trans-unit id="198" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: Program.cs</source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : Program.cs</target>
        </trans-unit></group></group>
        <group id="p199-PARA"><group id="s199-PARA"><trans-unit id="199" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: code-generation.py</target>
        </trans-unit></group></group>
        <group id="p200-PARA"><group id="s200-PARA"><trans-unit id="200" translate="yes" xml:space="preserve">
          <source>Run your application</source><target>Ausführen der Anwendung</target>
        </trans-unit></group></group>
        <group id="p201-PARA"><group id="s201-PARA"><trans-unit id="201" translate="yes" xml:space="preserve">
          <source>Now that your app has been configured, run it to try generating code for each use case.</source><target>Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Code für jeden Anwendungsfall zu generieren.</target>
        </trans-unit></group></group>
        <group id="p202-PARA"><group id="s202-PARA"><trans-unit id="202" translate="yes" xml:space="preserve">
          <source>The use case is numbered in the app, and can be run in any order.</source><target>Die Anwendungsfälle sind in der App nummeriert und können in beliebiger Reihenfolge ausgeführt werden.</target>
        </trans-unit></group></group>
        <group id="p203-PARA"><group id="s203-PARA"><trans-unit id="203" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Some users may experience rate limiting if calling the model too frequently.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Bei einigen Benutzer*innen kann es zu einer Ratenbegrenzung kommen, wenn sie das Modell zu häufig aufrufen.</target>
        </trans-unit></group></group>
        <group id="p204-PARA"><group id="s204-PARA"><trans-unit id="204" translate="yes" xml:space="preserve">
          <source>If you hit an error about a token rate limit, wait for a minute then try again.</source><target>Wenn Sie eine Fehlermeldung über eine Tokenratenbegrenzung erhalten, warten Sie eine Minute, und versuchen Sie es dann erneut.</target>
        </trans-unit></group></group>
        <group id="p205-PARA"><group id="s205-PARA"><trans-unit id="205" translate="yes" xml:space="preserve">
          <source>In the code editor, expand the <ph id="ph1">`sample-code`</ph> folder and briefly observe the function and the app for your language.</source><target>Erweitern Sie im Code-Editor den <ph id="ph1">`sample-code`</ph>-Ordner, und beobachten Sie kurz die Funktion und die App für Ihre Sprache.</target>
        </trans-unit></group></group>
        <group id="p206-PARA"><group id="s206-PARA"><trans-unit id="206" translate="yes" xml:space="preserve">
          <source>These files will be used for the tasks in the app.</source><target>Diese Dateien werden für die Aufgaben in der App verwendet.</target>
        </trans-unit></group></group>
        <group id="p207-PARA"><group id="s207-PARA"><trans-unit id="207" translate="yes" xml:space="preserve">
          <source>In the Cloud Shell bash terminal, navigate to the folder for your preferred language.</source><target>Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.</target>
        </trans-unit></group></group>
        <group id="p208-PARA"><group id="s208-PARA"><trans-unit id="208" translate="yes" xml:space="preserve">
          <source>Run the application.</source><target>Führen Sie die Anwendung aus.</target>
        </trans-unit></group></group>
        <group id="p209-PARA"><group id="s209-PARA"><trans-unit id="209" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: <ph id="ph1">`dotnet run`</ph></source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : <ph id="ph1">`dotnet run`</ph></target>
        </trans-unit></group></group>
        <group id="p210-PARA"><group id="s210-PARA"><trans-unit id="210" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python code-generation.py`</ph></source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: <ph id="ph1">`python code-generation.py`</ph></target>
        </trans-unit></group></group>
        <group id="p211-PARA"><group id="s211-PARA"><trans-unit id="211" translate="yes" xml:space="preserve">
          <source>Choose option <bpt id="p1">**</bpt>1<ept id="p1">**</ept> to add comments to your code.</source><target>Wählen Sie Option <bpt id="p1">**</bpt>1<ept id="p1">**</ept> aus, um Ihrem Code Kommentare hinzuzufügen.</target>
        </trans-unit></group></group>
        <group id="p212-PARA"><group id="s212-PARA"><trans-unit id="212" translate="yes" xml:space="preserve">
          <source>Note, the response might take a few seconds for each of these tasks.</source><target>Beachten Sie, dass die Beantwortung jeder dieser Aufgaben einige Sekunden dauern kann.</target>
        </trans-unit></group></group>
        <group id="p213-PARA"><group id="s213-PARA"><trans-unit id="213" translate="yes" xml:space="preserve">
          <source>The results will be put into <ph id="ph1">`result/app.txt`</ph>.</source><target>Die Ergebnisse werden in <ph id="ph1">`result/app.txt`</ph> eingefügt.</target>
        </trans-unit></group></group>
        <group id="p214-PARA"><group id="s214-PARA"><trans-unit id="214" translate="yes" xml:space="preserve">
          <source>Open that file up, and compare it to the function file in <ph id="ph1">`sample-code`</ph>.</source><target>Öffnen Sie diese Datei, und vergleichen Sie sie mit der Funktionsdatei in <ph id="ph1">`sample-code`</ph>.</target>
        </trans-unit></group></group>
        <group id="p215-PARA"><group id="s215-PARA"><trans-unit id="215" translate="yes" xml:space="preserve">
          <source>Next, choose option <bpt id="p1">**</bpt>2<ept id="p1">**</ept> to write unit tests for that same function.</source><target>Wählen Sie als Nächstes Option <bpt id="p1">**</bpt>2<ept id="p1">**</ept> aus, um Komponententests für dieselbe Funktion zu schreiben.</target>
        </trans-unit></group></group>
        <group id="p216-PARA"><group id="s216-PARA"><trans-unit id="216" translate="yes" xml:space="preserve">
          <source>The results will replace what was in <ph id="ph1">`result/app.txt`</ph>, and details four unit tests for that function.</source><target>Die Ergebnisse ersetzen das, was in <ph id="ph1">`result/app.txt`</ph> stand, und enthalten vier Komponententests für diese Funktion.</target>
        </trans-unit></group></group>
        <group id="p217-PARA"><group id="s217-PARA"><trans-unit id="217" translate="yes" xml:space="preserve">
          <source>Next, choose option <bpt id="p1">**</bpt>3<ept id="p1">**</ept> to fix bugs in an app for playing Go Fish.</source><target>Wählen Sie als Nächstes Option <bpt id="p1">**</bpt>3<ept id="p1">**</ept> aus, um Fehler in einer App für die Wiedergabe von Go Fish zu beheben.</target>
        </trans-unit></group></group>
        <group id="p218-PARA"><group id="s218-PARA"><trans-unit id="218" translate="yes" xml:space="preserve">
          <source>The results will replace what was in <ph id="ph1">`result/app.txt`</ph>, and should have very similar code with a few things corrected.</source><target>Die Ergebnisse ersetzen das, was in <ph id="ph1">`result/app.txt`</ph> stand, und sollten einen sehr ähnlichen Code haben, wobei einige Dinge korrigiert wurden.</target>
        </trans-unit></group></group>
        <group id="p219-PARA"><group id="s219-PARA"><trans-unit id="219" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>C#<ept id="p1">**</ept>: Fixes are made on line 30 and 59</source><target><bpt id="p1">**</bpt>C#<ept id="p1">**</ept> : Korrekturen werden in Zeile 30 und 59 vorgenommen.</target>
        </trans-unit></group></group>
        <group id="p220-PARA"><group id="s220-PARA"><trans-unit id="220" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: Fixes are made on line 18 and 31</source><target><bpt id="p1">**</bpt>Python<ept id="p1">**</ept>: Korrekturen werden in Zeile 18 und 31 vorgenommen.</target>
        </trans-unit></group></group>
        <group id="p221-PARA"><group id="s221-PARA"><trans-unit id="221" translate="yes" xml:space="preserve">
          <source>The app for Go Fish in <ph id="ph1">`sample-code`</ph> can be run, if you replace the lines with bugs with the response from Azure OpenAI.</source><target>Die App für Go Fish in <ph id="ph1">`sample-code`</ph> kann ausgeführt werden, wenn man die Zeilen mit Fehlern durch die Antwort von Azure OpenAI ersetzt.</target>
        </trans-unit></group></group>
        <group id="p222-PARA"><group id="s222-PARA"><trans-unit id="222" translate="yes" xml:space="preserve">
          <source>If you run it without the fixes, it will not work correctly.</source><target>Wenn Sie sie ohne die Korrekturen ausführen, wird sie nicht richtig funktionieren.</target>
        </trans-unit></group></group>
        <group id="p223-PARA"><group id="s223-PARA"><trans-unit id="223" translate="yes" xml:space="preserve">
          <source>It's important to note that even though the code for this Go Fish app was corrected for some syntax, it's not a strictly accurate representation of the game.</source><target>Es ist wichtig zu beachten, dass der Code für diese Go Fish-App zwar um einige Syntaxfehler korrigiert wurde, es sich jedoch nicht um eine genaue Darstellung des Spiels handelt.</target>
        </trans-unit></group></group>
        <group id="p224-PARA"><group id="s224-PARA"><trans-unit id="224" translate="yes" xml:space="preserve">
          <source>If you look closely, there are issues with not checking if the deck is empty when drawing cards, not removing pairs from the players hand when they get a pair, and a few other bugs that require understanding of card games to realize.</source><target>Wenn Sie genau hinsehen, treten Probleme dadurch auf, dass beim Ziehen von Karten nicht geprüft wird, ob das Deck leer ist, dass Paare nicht aus der Hand des Spielers bzw. der Spielerin entfernt werden, wenn er*sie ein Paar erhält, und einige andere Fehler, die ein Verständnis von Kartenspielen erfordern, um sie zu erkennen.</target>
        </trans-unit></group></group>
        <group id="p225-PARA"><group id="s225-PARA"><trans-unit id="225" translate="yes" xml:space="preserve">
          <source>This is a great example of how useful generative AI models can be to assist with code generation, but can't be trusted as correct and need to be verified by the developer.</source><target>Dies ist ein großartiges Beispiel dafür, wie nützlich generative KI-Modelle sein können, um die Codegenerierung zu unterstützen. Sie sollten jedoch nicht als absolut zuverlässig angesehen werden und müssen von dem*der Entwickler*in überprüft werden.</target>
        </trans-unit></group></group>
        <group id="p226-PARA"><group id="s226-PARA"><trans-unit id="226" translate="yes" xml:space="preserve">
          <source>If you would like to see the full response from Azure OpenAI, you can set the <ph id="ph1">`printFullResponse`</ph> variable to <ph id="ph2">`True`</ph>, and rerun the app.</source><target>Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die <ph id="ph1">`printFullResponse`</ph>-Variable auf <ph id="ph2">`True`</ph> festlegen und die App erneut ausführen.</target>
        </trans-unit></group></group>
        <group id="p227-PARA"><group id="s227-PARA"><trans-unit id="227" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigung</target>
        </trans-unit></group></group>
        <group id="p228-PARA"><group id="s228-PARA"><trans-unit id="228" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the deployment or the entire resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com/?azure-portal=true)</ept> zu löschen.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>