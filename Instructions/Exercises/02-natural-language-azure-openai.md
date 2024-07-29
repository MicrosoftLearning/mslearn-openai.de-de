---
lab:
  title: Verwenden von Azure OpenAI SDKs in Ihrer App
---

# Verwenden von Azure OpenAI APIs in Ihrer App

Mit Azure OpenAI Service können Entwickler*innen Chatbots, Sprachmodelle und andere Anwendungen erstellen, die die natürliche menschliche Sprache besonders gut verstehen. Azure OpenAI bietet Zugriff auf vortrainierte KI-Modelle sowie eine Suite von APIs und Tools zum Anpassen und Optimieren dieser Modelle, um die spezifischen Anforderungen Ihrer Anwendung zu erfüllen. In dieser Übung erfahren Sie, wie Sie ein Modell in Azure OpenAI bereitstellen und es in Ihrer eigenen Anwendung verwenden.

Im Szenario für diese Übung führen Sie die Rolle eines Softwareentwicklers aus, der beauftragt wurde, eine App zu implementieren, die generative KI verwenden kann, um Wanderempfehlungen bereitzustellen. Die in der Übung verwendeten Techniken können auf jede App angewendet werden, für die Azure OpenAI-APIs verwendet werden sollen.

Diese Übung dauert ungefähr **30** Minuten.

## Bereitstellen einer Azure OpenAI-Ressource

Wenn Sie noch keine Azure OpenAI-Ressource haben, stellen Sie eine in Ihrem Azure-Abonnement bereit.

1. Melden Sie sich beim **Azure-Portal** unter `https://portal.azure.com` an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement:** *Wählen Sie ein Azure-Abonnement aus, das für den Zugriff auf den Azure OpenAI-Dienst freigegeben wurde.*
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine*.
    - **Region:** *Treffen Sie eine **zufällige** Auswahl aus einer der folgenden Regionen*\*
        - Australien (Osten)
        - Kanada, Osten
        - East US
        - USA (Ost) 2
        - Frankreich, Mitte
        - Japan, Osten
        - USA Nord Mitte
        - Schweden, Mitte
        - Schweiz, Norden
        - UK, Süden
    - **Name:** *Wählen Sie einen Namen Ihrer Wahl aus.*
    - **Tarif**: Standard S0.

    > \* Azure OpenAI-Ressourcen werden durch regionale Kontingente eingeschränkt. Die aufgeführten Regionen enthalten das Standardkontingent für die in dieser Übung verwendeten Modelltypen. Durch die zufällige Auswahl einer Region wird das Risiko reduziert, dass eine einzelne Region ihr Kontingentlimit in Szenarien erreicht, in denen Sie ein Abonnement für andere Benutzer freigeben. Wenn später in der Übung ein Kontingentlimit erreicht wird, besteht eventuell die Möglichkeit, eine andere Ressource in einer anderen Region zu erstellen.

3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Azure OpenAI bietet ein webbasiertes Portal namens **Azure OpenAI Studio**, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können. Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Zu Azure OpenAI Studio wechseln**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite **Bereitstellungen**. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Bereitstellungsname**: *Ein eindeutiger Name Ihrer Wahl*
    - **Modell**: gpt-35-turbo-16k *(wenn das 16k-Modell nicht verfügbar ist, wählen Sie gpt-35-turbo)*
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungstyp**: Standard
    - **Ratenlimit für Token pro Minute**: 5K\*
    - **Inhaltsfilter**: Standard
    - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sie entwickeln Ihre Azure OpenAI-App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P), und führen Sie einen **Git: Clone**-Befehl aus, um das Repository `https://github.com/MicrosoftLearning/mslearn-openai` in einen lokalen Ordner zu klonen (der Ordner ist beliebig).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource nutzen zu können.

1. Wechseln Sie in Visual Studio Code im **Explorer**-Bereich zum Ordner **Labfiles/02-azure-openai-api**, und erweitern Sie je nach Ihrer bevorzugten Sprache den Ordner **CSharp** oder **Python**. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, mit der Sie Azure OpenAI-Funktionen integrieren.
2. Klicken Sie mit der rechten Maustaste auf den Ordner **CSharp** oder **Python**, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Installieren Sie dann das SDK-Paket von Azure OpenAI, indem Sie den entsprechenden Befehl für Ihre bevorzugte Sprache ausführen:

    **C#:**

    ```
    dotnet add package Azure.AI.OpenAI --version 1.0.0-beta.14
    ```

    **Python**:

    ```
    pip install openai==1.13.3
    ```

3. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Konfigurationsdatei für Ihre bevorzugte Sprache.

    - **C#**: appsettings.json
    - **Python**: .env
    
4. Aktualisieren Sie die Konfigurationswerte, um Folgendes einzuschließen:
    - Den **Endpunkt** und einen **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
    - Der **Bereitstellungsname**, den Sie für die Modellbereitstellung angegeben haben, verfügbar auf der Seite **Bereitstellungen** in Azure OpenAI Studio
5. Speichern Sie die Konfigurationsdatei.

## Hinzufügen von Code zum Verwenden des Azure OpenAI-Diensts

Jetzt können Sie das Azure OpenAI-SDK verwenden, um Ihr bereitgestelltes Modell zu nutzen.

1. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Codedatei für Ihre bevorzugte Sprache, und ersetzen Sie den Kommentar ***Hinzufügen des Azure OpenAI-Pakets*** durch Code, um die Azure OpenAI-SDK-Bibliothek hinzuzufügen:

    **C#** : Program.cs

    ```csharp
    // Add Azure OpenAI package
    using Azure.AI.OpenAI;
    ```
    
    **Python**: test-openai-model.py
    
    ```python
    # Add Azure OpenAI package
    from openai import AzureOpenAI
    ```

1. Ersetzen Sie im Anwendungscode für Ihre Sprache den Kommentar ***Initialisieren des Azure OpenAI-Clients...*** durch den folgenden Code, um den Client zu initialisieren und unsere Systemnachricht zu definieren.

    **C#** : Program.cs

    ```csharp
    // Initialize the Azure OpenAI client
    OpenAIClient client = new OpenAIClient(new Uri(oaiEndpoint), new AzureKeyCredential(oaiKey));
    
    // System message to provide context to the model
    string systemMessage = "I am a hiking enthusiast named Forest who helps people discover hikes in their area. If no area is specified, I will default to near Rainier National Park. I will then provide three suggestions for nearby hikes that vary in length. I will also share an interesting fact about the local nature on the hikes when making a recommendation.";
    ```

    **Python**: test-openai-model.py

    ```python
    # Initialize the Azure OpenAI client
    client = AzureOpenAI(
            azure_endpoint = azure_oai_endpoint, 
            api_key=azure_oai_key,  
            api_version="2024-02-15-preview"
            )
    
    # Create a system message
    system_message = """I am a hiking enthusiast named Forest who helps people discover hikes in their area. 
        If no area is specified, I will default to near Rainier National Park. 
        I will then provide three suggestions for nearby hikes that vary in length. 
        I will also share an interesting fact about the local nature on the hikes when making a recommendation.
        """
    ```

1. Ersetzen Sie den Kommentar ***Hinzufügen von Code zum Senden der Anforderung*** durch den erforderlichen Code zum Erstellen der Anforderung; geben Sie dabei die verschiedenen Parameter für Ihr Modell an, z. B. `messages` und `temperature`.

    **C#** : Program.cs

    ```csharp
    // Add code to send request...
    // Build completion options object
    ChatCompletionsOptions chatCompletionsOptions = new ChatCompletionsOptions()
    {
        Messages =
        {
            new ChatRequestSystemMessage(systemMessage),
            new ChatRequestUserMessage(inputText),
        },
        MaxTokens = 400,
        Temperature = 0.7f,
        DeploymentName = oaiDeploymentName
    };

    // Send request to Azure OpenAI model
    ChatCompletions response = client.GetChatCompletions(chatCompletionsOptions);

    // Print the response
    string completion = response.Choices[0].Message.Content;
    Console.WriteLine("Response: " + completion + "\n");
    ```

    **Python**: test-openai-model.py

    ```python
    # Add code to send request...
    # Send request to Azure OpenAI model
    response = client.chat.completions.create(
        model=azure_oai_deployment,
        temperature=0.7,
        max_tokens=400,
        messages=[
            {"role": "system", "content": system_message},
            {"role": "user", "content": input_text}
        ]
    )
    generated_text = response.choices[0].message.content

    # Print the response
    print("Response: " + generated_text + "\n")
    ```

1. Speichern Sie die Änderungen an der Codedatei.

## Testen Ihrer Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten.

1. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python test-openai-model.py`

    > **Tipp**: Sie können das Symbol **Maximize panel size** (Panelgröße maximieren) (**^**) in der Terminalsymbolleiste verwenden, um mehr des Konsolentexts anzuzeigen.

1. Wenn Sie dazu aufgefordert werden, geben Sie den Text `What hike should I do near Rainier?` ein.
1. Beobachten Sie die Ausgabe und achten Sie darauf, dass die Antwort den Richtlinien der Systemmeldung entspricht, die Sie dem *Nachrichten*-Array hinzugefügt haben.
1. Stellen Sie die Eingabeaufforderung `Where should I hike near Boise? I'm looking for something of easy difficulty, between 2 to 3 miles, with moderate elevation gain.` bereit, und beobachten Sie die Ausgabe.
1. Ändern Sie in der Codedatei für Ihre bevorzugte Sprache den *Temperatur*-Parameterwert in Ihrer Anforderung auf **1,0** und speichern Sie die Datei.
1. Führen Sie die Anwendung erneut mit den oben aufgeführten Eingabeaufforderungen aus, und beobachten Sie die Ausgabe.

Eine Erhöhung der Temperatur führt häufig dazu, dass die Antworten variieren, selbst wenn der gleiche Text bereitgestellt wird, was auf die erhöhte Zufälligkeit zurückzuführen ist. Sie können sie mehrmals ausführen, um zu sehen, wie sich die Ausgabe ändern kann. Versuchen Sie, verschiedene Werte für Ihre Temperatur mit derselben Eingabe zu verwenden.

## Verwalten des Konversationsverlaufs

In den meisten realen Anwendungen ermöglicht das Verweisen auf frühere Teile der Unterhaltung eine realistischere Interaktion mit einem KI-Agenten. Die Azure OpenAI-API ist zustandslos, aber indem Sie einen Verlauf der Unterhaltung in Ihrer Aufforderung bereitstellen, kann das KI-Modell auf frühere Nachrichten Bezug nehmen.

1. Führen Sie die App erneut aus, und stellen Sie die Eingabeaufforderung `Where is a good hike near Boise?` bereit.
1. Beobachten Sie die Ausgabe, und verwenden Sie dann die Eingabeaufforderung `How difficult is the second hike you suggested?`.
1. Die Antwort des Modells wird wahrscheinlich darauf hindeuten, dass es die Wanderung, auf die Sie sich beziehen, nicht verstehen kann. Um dies zu beheben, können wir dem Modell die Möglichkeit bieten, frühere Unterhaltungsnachrichten als Referenz zu verwenden.
1. Fügen Sie in Ihrer Anwendung die vorherige Aufforderung und die Antwort auf die zukünftige Aufforderung, die gesendet wird, hinzu. Fügen Sie unterhalb der Definition der **Systemmeldung** den folgenden Code hinzu.

    **C#** : Program.cs

    ```csharp
    // Initialize messages list
    var messagesList = new List<ChatRequestMessage>()
    {
        new ChatRequestSystemMessage(systemMessage),
    };
    ```

    **Python**: test-openai-model.py

    ```python
    # Initialize messages array
    messages_array = [{"role": "system", "content": system_message}]
    ```

1. Ersetzen Sie unter dem Kommentar ***Hinzufügen von Code zum Senden der Anforderung...***, ersetzen Sie den gesamten Code aus dem Kommentar bis zum Ende der **while**-Schleife mit dem folgenden Code, und speichern Sie die Datei dann. Der Code ist größtenteils identisch, aber jetzt wird das Nachrichtenarray verwendet, um den Unterhaltungsverlauf zu speichern.

    **C#** : Program.cs

    ```csharp
    // Add code to send request...
    // Build completion options object
    messagesList.Add(new ChatRequestUserMessage(inputText));

    ChatCompletionsOptions chatCompletionsOptions = new ChatCompletionsOptions()
    {
        MaxTokens = 1200,
        Temperature = 0.7f,
        DeploymentName = oaiDeploymentName
    };

    // Add messages to the completion options
    foreach (ChatRequestMessage chatMessage in messagesList)
    {
        chatCompletionsOptions.Messages.Add(chatMessage);
    }

    // Send request to Azure OpenAI model
    ChatCompletions response = client.GetChatCompletions(chatCompletionsOptions);

    // Return the response
    string completion = response.Choices[0].Message.Content;

    // Add generated text to messages list
    messagesList.Add(new ChatRequestAssistantMessage(completion));

    Console.WriteLine("Response: " + completion + "\n");
    ```

    **Python**: test-openai-model.py

    ```python
    # Add code to send request...
    # Send request to Azure OpenAI model
    messages_array.append({"role": "user", "content": input_text})

    response = client.chat.completions.create(
        model=azure_oai_deployment,
        temperature=0.7,
        max_tokens=1200,
        messages=messages_array
    )
    generated_text = response.choices[0].message.content
    # Add generated text to messages array
    messages_array.append({"role": "assistant", "content": generated_text})

    # Print generated text
    print("Summary: " + generated_text + "\n")
    ```

1. Speichern Sie die Datei . Beachten Sie im hinzugefügten Code, dass wir nun die vorherige Eingabe und Antwort auf das Eingabeaufforderungsarray anfügen, mit dem das Modell den Verlauf unserer Unterhaltung verstehen kann.
1. Geben Sie den folgenden Befehl in das Terminalfenster ein, um die Anwendung auszuführen:

    - **C#** : `dotnet run`
    - **Python**: `python test-openai-model.py`

1. Führen Sie die App erneut aus, und stellen Sie die Eingabeaufforderung `Where is a good hike near Boise?` bereit.
1. Beobachten Sie die Ausgabe, und verwenden Sie dann die Eingabeaufforderung `How difficult is the second hike you suggested?`.
1. Wahrscheinlich erhalten Sie eine Antwort mit der zweiten Wanderung, die das Modell vorgeschlagen hat, was eine viel realistischere Unterhaltung bietet. Sie können zusätzliche Nachfragen stellen, die auf frühere Antworten verweisen, und jedes Mal stellt der Verlauf Kontext für das Modell zur Beantwortung bereit.

    > **Tipp**: Die Tokenanzahl ist auf lediglich 1200 festgelegt. Wenn die Unterhaltung also zu lange fortgesetzt wird, ist die Anwendung nicht mehr verfügbar, was zu einer unvollständigen Eingabeaufforderung führt. In der Produktion wird die Länge des Verlaufs auf die letzten Eingaben und Antworten beschränkt, um die Anzahl der erforderlichen Token zu steuern.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im **Azure-Portal** auf `https://portal.azure.com` zu löschen.
