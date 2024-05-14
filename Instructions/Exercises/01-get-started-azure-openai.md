<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" original="markdown" source-language="en-US" target-language="de-DE">
    <header>
      <tool tool-id="JunoTransformer" tool-name="JunoTransformer" tool-version="1.0.0" tool-company="Microsoft"><transformer-options xmlns="urn:microsoft:content:juno:1.0"><option name="TargetXliffVersion" value="V1"/><option name="ArtToXliff" value="False"/><option name="UseParagraphMarker" value="False"/><option name="ExposeLinkTitleText" value="False"/><option name="ReplaceNewlineWithWhitespace" value="False"/><option name="LockAtSign" value="False"/><option name="ExposeImageTitleText" value="True"/><option name="LockBackslashEscapeChars" value="False"/><option name="PairHtmlTags" value="False"/><option name="TrimBoundingPhTags" value="False"/><option name="MergeAdjacentPhTags" value="False"/><option name="LinkifyHeaders" value="False"/></transformer-options></tool>
    </header>
    <body>
      <group id="content" extype="content">
        <group id="p101-PARA"><group id="s101-PARA"><trans-unit id="101" translate="yes" xml:space="preserve" restype="x-metadata">
          <source>Get started with Azure OpenAI</source><target>Erste Schritte mit Azure OpenAI</target>
        </trans-unit></group></group>
        <group id="p102-PARA"><group id="s102-PARA"><trans-unit id="102" translate="yes" xml:space="preserve">
          <source>Get started with Azure OpenAI Service</source><target>Erste Schritte mit Azure OpenAI Service</target>
        </trans-unit></group></group>
        <group id="p103-PARA"><group id="s103-PARA"><trans-unit id="103" translate="yes" xml:space="preserve">
          <source>Azure OpenAI Service brings the generative AI models developed by OpenAI to the Azure platform, enabling you to develop powerful AI solutions that benefit from the security, scalability, and integration of services provided by the Azure cloud platform.</source><target>Azure OpenAI Service bringt die von OpenAI entwickelten generativen KI-Modelle auf die Azure-Plattform und ermöglicht Ihnen die Entwicklung leistungsstarker KI-Lösungen, die von der Sicherheit, Skalierbarkeit und Integration anderer Dienste der Azure-Cloudplattform profitieren.</target>
        </trans-unit></group></group>
        <group id="p104-PARA"><group id="s104-PARA"><trans-unit id="104" translate="yes" xml:space="preserve">
          <source>In this exercise, you'll learn how to get started with Azure OpenAI by provisioning the service as an Azure resource and using Azure OpenAI Studio to deploy and explore OpenAI models.</source><target>In dieser Übung erfahren Sie, wie Sie die Arbeit mit Azure OpenAI beginnen, indem Sie den Dienst als Azure-Ressource bereitstellen und Azure OpenAI Studio verwenden, um OpenAI-Modelle bereitzustellen und zu untersuchen.</target>
        </trans-unit></group></group>
        <group id="p105-PARA"><group id="s105-PARA"><trans-unit id="105" translate="yes" xml:space="preserve">
          <source>This exercise takes approximately <bpt id="p1">**</bpt>30<ept id="p1">**</ept> minutes.</source><target>Diese Übung dauert ca. <bpt id="p1">**</bpt>30<ept id="p1">**</ept> Minuten.</target>
        </trans-unit></group></group>
        <group id="p106-PARA"><group id="s106-PARA"><trans-unit id="106" translate="yes" xml:space="preserve">
          <source>Before you start</source><target>Vorbereitung</target>
        </trans-unit></group></group>
        <group id="p107-PARA"><group id="s107-PARA"><trans-unit id="107" translate="yes" xml:space="preserve">
          <source>You'll need an Azure subscription that has been approved for access to the Azure OpenAI service.</source><target>Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.</target>
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
          <source>Deploy a model</source><target>Bereitstellen eines Modells</target>
        </trans-unit></group></group>
        <group id="p122-PARA"><group id="s122-PARA"><trans-unit id="122" translate="yes" xml:space="preserve">
          <source>Azure OpenAI provides a web-based portal named <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>, that you can use to deploy, manage, and explore models.</source><target>Azure OpenAI bietet ein webbasiertes Portal namens <bpt id="p1">**</bpt>Azure OpenAI Studio<ept id="p1">**</ept>, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können.</target>
        </trans-unit></group></group>
        <group id="p123-PARA"><group id="s123-PARA"><trans-unit id="123" translate="yes" xml:space="preserve">
          <source>You'll start your exploration of Azure OpenAI by using Azure OpenAI Studio to deploy a model.</source><target>Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.</target>
        </trans-unit></group></group>
        <group id="p124-PARA"><group id="s124-PARA"><trans-unit id="124" translate="yes" xml:space="preserve">
          <source>On the <bpt id="p1">**</bpt>Overview<ept id="p1">**</ept> page for your Azure OpenAI resource, use the <bpt id="p2">**</bpt>Go to Azure OpenAI Studio<ept id="p2">**</ept> button to open Azure OpenAI Studio in a new browser tab.</source><target>Verwenden Sie auf der Seite <bpt id="p1">**</bpt>Übersicht<ept id="p1">**</ept> für Ihre Azure OpenAI-Ressource die Schaltfläche <bpt id="p2">**</bpt>Zu Azure OpenAI Studio wechseln<ept id="p2">**</ept>, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.</target>
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
          <source><bpt id="p1">**</bpt>Deployment name<ept id="p1">**</ept>: <bpt id="p2">*</bpt>A unique name of your choice<ept id="p2">*</ept></source><target><bpt id="p1">**</bpt>Bereitstellungsname<ept id="p1">**</ept>: <bpt id="p2">*</bpt>Wählen Sie einen Namen Ihrer Wahl aus<ept id="p2">*</ept></target>
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
          <source>In this case, don't worry and continue without setting the option.</source><target>Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen</target>
        </trans-unit></group></group>
        <group id="p137-PARA"><group id="s137-PARA"><trans-unit id="137" translate="yes" xml:space="preserve">
          <source>Use the Chat playground</source><target>Verwenden des Chat-Playgrounds</target>
        </trans-unit></group></group>
        <group id="p138-PARA"><group id="s138-PARA"><trans-unit id="138" translate="yes" xml:space="preserve">
          <source>The <bpt id="p1">*</bpt>Chat<ept id="p1">*</ept> playground provides a chatbot interface for GPT 3.5 and higher models.</source><target>Der <bpt id="p1">*</bpt>Chat<ept id="p1">*</ept>-Playground bietet eine Chatbotschnittstelle für GPT 3.5 und höhere Modelle.</target>
        </trans-unit></group></group>
        <group id="p139-PARA"><group id="s139-PARA"><trans-unit id="139" translate="yes" xml:space="preserve">
          <source>It uses the <bpt id="p1">*</bpt>ChatCompletions<ept id="p1">*</ept> API rather than the older <bpt id="p2">*</bpt>Completions<ept id="p2">*</ept> API.</source><target>Er verwendet die <bpt id="p1">*</bpt>ChatCompletions<ept id="p1">*</ept>-API anstelle der älteren <bpt id="p2">*</bpt>Completions<ept id="p2">*</ept>-API.</target>
        </trans-unit></group></group>
        <group id="p140-PARA"><group id="s140-PARA"><trans-unit id="140" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Playground<ept id="p1">**</ept> section, select the <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept> page, and ensure that your model is selected in the configuration pane.</source><target>Wählen Sie im Bereich <bpt id="p1">**</bpt>Playground<ept id="p1">**</ept> die Seite <bpt id="p2">**</bpt>Chat<ept id="p2">**</ept> und vergewissern Sie sich, dass Ihr Modell im Konfigurationsbereich ausgewählt ist.</target>
        </trans-unit></group></group>
        <group id="p141-PARA"><group id="s141-PARA"><trans-unit id="141" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> section, in the <bpt id="p2">**</bpt>System message<ept id="p2">**</ept> box, replace the current text with the following statement: <ph id="ph1">`The system is an AI teacher that helps people learn about AI`</ph>.</source><target>Ersetzen Sie im Abschnitt <bpt id="p1">**</bpt>Assistenteneinrichtung<ept id="p1">**</ept> im Feld <bpt id="p2">**</bpt>Systemmeldung<ept id="p2">**</ept> den aktuellen Text durch folgende Anweisung: <ph id="ph1">`The system is an AI teacher that helps people learn about AI`</ph>.</target>
        </trans-unit></group></group>
        <group id="p142-PARA"><group id="s142-PARA"><trans-unit id="142" translate="yes" xml:space="preserve">
          <source>Below the <bpt id="p1">**</bpt>System message<ept id="p1">**</ept> box, click on <bpt id="p2">**</bpt>Add few-shot examples<ept id="p2">**</ept>, and enter the following message and response in the designated boxes:</source><target>Klicken Sie unterhalb des Felds <bpt id="p1">**</bpt>Systemmeldung<ept id="p1">**</ept> auf <bpt id="p2">**</bpt>Beispiele hinzufügen<ept id="p2">**</ept>, und geben Sie die folgende Nachricht und Antwort in die entsprechenden Felder ein:</target>
        </trans-unit></group></group>
        <group id="p143-PARA"><group id="s143-PARA"><trans-unit id="143" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>User<ept id="p1">**</ept>: <ph id="ph1">`What are different types of artificial intelligence?`</ph></source><target><bpt id="p1">**</bpt>Benutzer:<ept id="p1">**</ept> <ph id="ph1">`What are different types of artificial intelligence?`</ph></target>
        </trans-unit></group></group>
        <group id="p144-PARA"><group id="s144-PARA"><trans-unit id="144" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Assistant<ept id="p1">**</ept>: <ph id="ph1">`There are three main types of artificial intelligence: Narrow or Weak AI (such as virtual assistants like Siri or Alexa, image recognition software, and spam filters), General or Strong AI (AI designed to be as intelligent as a human being. This type of AI does not currently exist and is purely theoretical), and Artificial Superintelligence (AI that is more intelligent than any human being and can perform tasks that are beyond human comprehension. This type of AI is also purely theoretical and has not yet been developed).`</ph></source><target><bpt id="p1">**</bpt>Assistent:<ept id="p1">**</ept> <ph id="ph1">`There are three main types of artificial intelligence: Narrow or Weak AI (such as virtual assistants like Siri or Alexa, image recognition software, and spam filters), General or Strong AI (AI designed to be as intelligent as a human being. This type of AI does not currently exist and is purely theoretical), and Artificial Superintelligence (AI that is more intelligent than any human being and can perform tasks that are beyond human comprehension. This type of AI is also purely theoretical and has not yet been developed).`</ph></target>
        </trans-unit></group></group>
        <group id="p145-PARA"><group id="s145-PARA"><trans-unit id="145" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: Few-shot examples are used to provide the model with examples of the types of responses that are expected.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Einige wenige Beispiele werden verwendet, um dem Modell Beispiele für die zu erwartenden Antworttypen zu geben.</target>
        </trans-unit></group></group>
        <group id="p146-PARA"><group id="s146-PARA"><trans-unit id="146" translate="yes" xml:space="preserve">
          <source>The model will attempt to reflect the tone and style of the examples in its own responses.</source><target>Das Modell versucht, den Ton und den Stil der Beispiele in seinen eigenen Antworten wiederzugeben.</target>
        </trans-unit></group></group>
        <group id="p147-PARA"><group id="s147-PARA"><trans-unit id="147" translate="yes" xml:space="preserve">
          <source>Save the changes to start a new session and set the behavioral context of the chat system.</source><target>Speichern Sie die Änderungen, um eine neue Sitzung zu starten, und legen Sie den Verhaltenskontext des Chatsystems fest.</target>
        </trans-unit></group></group>
        <group id="p148-PARA"><group id="s148-PARA"><trans-unit id="148" translate="yes" xml:space="preserve">
          <source>In the query box at the bottom of the page, enter the text <ph id="ph1">`What is artificial intelligence?`</ph></source><target>Geben Sie im Abfragefeld unten auf der Seite den Text <ph id="ph1">`What is artificial intelligence?`</ph> ein.</target>
        </trans-unit></group></group>
        <group id="p149-PARA"><group id="s149-PARA"><trans-unit id="149" translate="yes" xml:space="preserve">
          <source>Use the <bpt id="p1">**</bpt>Send<ept id="p1">**</ept> button to submit the message and view the response.</source><target>Verwenden Sie die Schaltfläche <bpt id="p1">**</bpt>Senden<ept id="p1">**</ept>, um die Nachricht zu übermitteln und die Antwort anzuzeigen.</target>
        </trans-unit></group></group>
        <group id="p150-PARA"><group id="s150-PARA"><trans-unit id="150" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Note<ept id="p1">**</ept>: You may receive a response that the API deployment is not yet ready.</source><target><bpt id="p1">**</bpt>Hinweis<ept id="p1">**</ept>: Sie erhalten möglicherweise die Antwort, dass die API-Bereitstellung noch nicht abgeschlossen ist.</target>
        </trans-unit></group></group>
        <group id="p151-PARA"><group id="s151-PARA"><trans-unit id="151" translate="yes" xml:space="preserve">
          <source>If so, wait for a few minutes and try again.</source><target>Wenn dies der Fall ist, warten Sie ein paar Minuten, und versuchen Sie es erneut.</target>
        </trans-unit></group></group>
        <group id="p152-PARA"><group id="s152-PARA"><trans-unit id="152" translate="yes" xml:space="preserve">
          <source>Review the response and then submit the following message to continue the conversation: <ph id="ph1">`How is it related to machine learning?`</ph></source><target>Überprüfen Sie die Antwort, und senden Sie dann die folgende Nachricht, um die Unterhaltung fortzusetzen: <ph id="ph1">`How is it related to machine learning?`</ph></target>
        </trans-unit></group></group>
        <group id="p153-PARA"><group id="s153-PARA"><trans-unit id="153" translate="yes" xml:space="preserve">
          <source>Review the response, noting that context from the previous interaction is retained (so the model understands that "it" refers to artificial intelligence).</source><target>Überprüfen Sie die Antwort, und achten Sie darauf, dass der Kontext der vorherigen Interaktion erhalten bleibt (damit das Modell versteht, dass sich „sie“ auf die künstliche Intelligenz bezieht).</target>
        </trans-unit></group></group>
        <group id="p154-PARA"><group id="s154-PARA"><trans-unit id="154" translate="yes" xml:space="preserve">
          <source>Use the <bpt id="p1">**</bpt>View Code<ept id="p1">**</ept> button to view the code for the interaction.</source><target>Verwenden Sie die Schaltfläche <bpt id="p1">**</bpt>Code anzeigen<ept id="p1">**</ept>, um den Code für die Interaktion anzuzeigen.</target>
        </trans-unit></group></group>
        <group id="p155-PARA"><group id="s155-PARA"><trans-unit id="155" translate="yes" xml:space="preserve">
          <source>The prompt consists of the <bpt id="p1">*</bpt>system<ept id="p1">*</ept> message, the few-shot examples of <bpt id="p2">*</bpt>user<ept id="p2">*</ept> and <bpt id="p3">*</bpt>assistant<ept id="p3">*</ept> messages, and the sequence of <bpt id="p4">*</bpt>user<ept id="p4">*</ept> and <bpt id="p5">*</bpt>assistant<ept id="p5">*</ept> messages in the chat session so far.</source><target>Die Eingabeaufforderung besteht aus der <bpt id="p1">*</bpt>Systemnachricht<ept id="p1">*</ept>, den wenigen Beispielen der <bpt id="p2">*</bpt>Benutzer<ept id="p2">*</ept>- und <bpt id="p3">*</bpt>Assistentnachrichten<ept id="p3">*</ept> und der Sequenz von <bpt id="p4">*</bpt>Benutzer<ept id="p4">*</ept>- und <bpt id="p5">*</bpt>Assistentnachrichten<ept id="p5">*</ept> in der bisherigen Chatsitzung.</target>
        </trans-unit></group></group>
        <group id="p156-PARA"><group id="s156-PARA"><trans-unit id="156" translate="yes" xml:space="preserve">
          <source>Explore prompts and parameters</source><target>Untersuchen von Eingabeaufforderungen und Parametern</target>
        </trans-unit></group></group>
        <group id="p157-PARA"><group id="s157-PARA"><trans-unit id="157" translate="yes" xml:space="preserve">
          <source>You can use the prompt and parameters to maximize the likelihood of generating the response you need.</source><target>Sie können die Eingabeaufforderung und die Parameter verwenden, um die Wahrscheinlichkeit zu maximieren, dass die benötigte Antwort generiert wird.</target>
        </trans-unit></group></group>
        <group id="p158-PARA"><group id="s158-PARA"><trans-unit id="158" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Parameters<ept id="p1">**</ept> pane, set the following parameter values:</source><target>Legen Sie im Bereich <bpt id="p1">**</bpt>Parameter<ept id="p1">**</ept> die folgenden Parameterwerte fest:</target>
        </trans-unit></group></group>
        <group id="p159-PARA"><group id="s159-PARA"><trans-unit id="159" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Temperature<ept id="p1">**</ept>: 0</source><target><bpt id="p1">**</bpt>Temperatur<ept id="p1">**</ept>: 0</target>
        </trans-unit></group></group>
        <group id="p160-PARA"><group id="s160-PARA"><trans-unit id="160" translate="yes" xml:space="preserve">
          <source><bpt id="p1">**</bpt>Max response<ept id="p1">**</ept>: 500</source><target><bpt id="p1">**</bpt>Maximale Antwort<ept id="p1">**</ept>: 500</target>
        </trans-unit></group></group>
        <group id="p161-PARA"><group id="s161-PARA"><trans-unit id="161" translate="yes" xml:space="preserve">
          <source>Submit the following message</source><target>Übermitteln Sie folgende Nachricht:</target>
        </trans-unit></group></group>
        <group id="p162-PARA"><group id="s162-PARA"><trans-unit id="162" translate="yes" xml:space="preserve">
          <source>Review the results, which should consist of multiple-choice questions that a teacher could use to test students on the computer vision topics in the prompt.</source><target>Überprüfen Sie die Ergebnisse, die aus Multiple-Choice-Fragen bestehen sollten, die eine Lehrkraft verwenden kann, um Schüler*innen oder Student*innen zu Themen zu maschinellem Sehen in der Eingabeaufforderung zu testen.</target>
        </trans-unit></group></group>
        <group id="p163-PARA"><group id="s163-PARA"><trans-unit id="163" translate="yes" xml:space="preserve">
          <source>The total response should be smaller than the maximum length you specified as a parameter.</source><target>Die Gesamtantwort sollte kleiner sein als die maximale Länge, die Sie als Parameter angegeben haben.</target>
        </trans-unit></group></group>
        <group id="p164-PARA"><group id="s164-PARA"><trans-unit id="164" translate="yes" xml:space="preserve">
          <source>Observe the following about the prompt and parameters you used:</source><target>Beachten Sie die folgenden Informationen zu den verwendeten Eingabeaufforderungen und Parametern:</target>
        </trans-unit></group></group>
        <group id="p165-PARA"><group id="s165-PARA"><trans-unit id="165" translate="yes" xml:space="preserve">
          <source>The prompt specifically states that the desired output should be three multiple choice questions.</source><target>Die Eingabeaufforderung gibt ausdrücklich an, dass die gewünschte Ausgabe drei Multiple-Choice-Fragen enthalten sollte.</target>
        </trans-unit></group></group>
        <group id="p166-PARA"><group id="s166-PARA"><trans-unit id="166" translate="yes" xml:space="preserve">
          <source>The parameters include <bpt id="p1">*</bpt>Temperature<ept id="p1">*</ept>, which controls the degree to which response generation includes an element of randomness.</source><target>Zu den Parametern gehört <bpt id="p1">*</bpt>Temperature<ept id="p1">*</ept>, der den Grad steuert, in dem die Antwortgenerierung ein Element der Zufälligkeit enthält.</target>
        </trans-unit></group></group>
        <group id="p167-PARA"><group id="s167-PARA"><trans-unit id="167" translate="yes" xml:space="preserve">
          <source>The value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> used in your submission minimizes randomness, resulting in stable, predictable responses.</source><target>Der in Ihrer Übermittlung verwendete Wert von <bpt id="p1">**</bpt>0<ept id="p1">**</ept> minimiert die Zufälligkeit, was zu stabilen, vorhersehbaren Antworten führt.</target>
        </trans-unit></group></group>
        <group id="p168-PARA"><group id="s168-PARA"><trans-unit id="168" translate="yes" xml:space="preserve">
          <source>Explore code-generation</source><target>Erkunden der Codegenerierung</target>
        </trans-unit></group></group>
        <group id="p169-PARA"><group id="s169-PARA"><trans-unit id="169" translate="yes" xml:space="preserve">
          <source>In addition to generating natural language responses, you can use GPT models to generate code.</source><target>Zusätzlich zum Generieren natürlicher Sprachantworten können Sie GPT-Modelle verwenden, um Code zu generieren.</target>
        </trans-unit></group></group>
        <group id="p170-PARA"><group id="s170-PARA"><trans-unit id="170" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Assistant setup<ept id="p1">**</ept> pane, select the <bpt id="p2">**</bpt>Empty Example<ept id="p2">**</ept> template to reset the system message.</source><target>Wählen Sie im Bereich <bpt id="p1">**</bpt>Assistenteneinrichtung<ept id="p1">**</ept> die Vorlage <bpt id="p2">**</bpt>Leeres Beispiel<ept id="p2">**</ept> aus, um die Systemmeldung zurückzusetzen.</target>
        </trans-unit></group></group>
        <group id="p171-PARA"><group id="s171-PARA"><trans-unit id="171" translate="yes" xml:space="preserve">
          <source>Enter the system message: <ph id="ph1">`You are a Python developer.`</ph> and save the changes.</source><target>Geben Sie die Systemmeldung <ph id="ph1">`You are a Python developer.`</ph> ein, und speichern Sie die Änderungen.</target>
        </trans-unit></group></group>
        <group id="p172-PARA"><group id="s172-PARA"><trans-unit id="172" translate="yes" xml:space="preserve">
          <source>In the <bpt id="p1">**</bpt>Chat session<ept id="p1">**</ept> pane, select <bpt id="p2">**</bpt>Clear chat<ept id="p2">**</ept> to clear the chat history and start a new session.</source><target>Wählen Sie im Bereich <bpt id="p1">**</bpt>Chatsitzung<ept id="p1">**</ept> die Option <bpt id="p2">**</bpt>Chat löschen<ept id="p2">**</ept> aus, um den Chatverlauf zu löschen und eine neue Sitzung zu starten.</target>
        </trans-unit></group></group>
        <group id="p173-PARA"><group id="s173-PARA"><trans-unit id="173" translate="yes" xml:space="preserve">
          <source>Submit the following user message:</source><target>Übermitteln Sie die folgende Benutzernachricht:</target>
        </trans-unit></group></group>
        <group id="p174-PARA"><group id="s174-PARA"><trans-unit id="174" translate="yes" xml:space="preserve">
          <source>Review the response, which should include sample Python code that meets the requirement in the prompt.</source><target>Überprüfen Sie die Antwort, die Python-Beispielcode enthalten sollte, der die Anforderung in der Eingabeaufforderung erfüllt.</target>
        </trans-unit></group></group>
        <group id="p175-PARA"><group id="s175-PARA"><trans-unit id="175" translate="yes" xml:space="preserve">
          <source>Clean up</source><target>Bereinigung</target>
        </trans-unit></group></group>
        <group id="p176-PARA"><group id="s176-PARA"><trans-unit id="176" translate="yes" xml:space="preserve">
          <source>When you're done with your Azure OpenAI resource, remember to delete the deployment or the entire resource in the <bpt id="p1">[</bpt>Azure portal<ept id="p1">](https://portal.azure.com)</ept>.</source><target>Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im <bpt id="p1">[</bpt>Azure-Portal<ept id="p1">](https://portal.azure.com)</ept> zu löschen.</target>
        </trans-unit></group></group>
      </group>
    </body>
  </file>
</xliff>