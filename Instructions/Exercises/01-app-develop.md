---
lab:
  title: App-Entwicklung mit Azure OpenAI-Service
---

# App-Entwicklung mit Azure OpenAI-Service

Mit dem Azure OpenAI Service können Entwickelnde Chatbots und andere Anwendungen erstellen, die durch die Verwendung von REST-APIs oder sprachspezifischen SDKs die natürliche menschliche Sprache hervorragend verstehen. Bei der Arbeit mit diesen Sprachmodellen hat die Art und Weise, wie Entwickelnde ihre Eingabe gestalten, großen Einfluss darauf, wie das generative KI-Modell reagiert. Azure OpenAI-Modelle können Inhalte auf klare und präzise Weise anpassen und formatieren. In dieser Übung lernen Sie, wie Sie Ihre Anwendung mit Azure OpenAI verbinden und wie verschiedene Eingabeaufforderungen für ähnliche Inhalte dazu beitragen, die Antwort des KI-Modells so zu gestalten, dass sie Ihren Anforderungen besser entspricht.

Im Szenario für diese Übung sind Sie ein Softwareentwickler, der für eine Wildlife-Marketingkampagne arbeitet. Sie untersuchen, wie Sie generative KI verwenden können, um Werbe-E-Mails zu verbessern und Artikel zu kategorisieren, für Ihr Team relevant sein könnten. Die in der Übung verwendeten Prompt Engineering-Techniken können für eine Vielzahl von Anwendungsfällen genutzt werden.

Diese Übung dauert ungefähr **30** Minuten.

## Bereitstellen einer Azure OpenAI-Ressource

Wenn Sie noch keine Azure OpenAI-Ressource haben, stellen Sie eine in Ihrem Azure-Abonnement bereit.

1. Melden Sie sich beim **Azure-Portal** unter `https://portal.azure.com` an.

1. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement:** *Wählen Sie ein Azure-Abonnement aus, das für den Zugriff auf den Azure OpenAI-Dienst freigegeben wurde.*
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine*.
    - **Region:** *Treffen Sie eine **zufällige** Auswahl aus einer der folgenden Regionen*\*
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

Als Nächstes stellen Sie eine Azure OpenAI-Modellressource aus der CLI bereit. Verwenden Sie dieses Beispiel und ersetzen Sie die folgenden Variablen durch Ihre eigenen Werte von oben:

```dotnetcli
az cognitiveservices account deployment create \
   -g *Your resource group* \
   -n *Name of your OpenAI service* \
   --deployment-name gpt-35-turbo \
   --model-name gpt-35-turbo \
   --model-version 0125  \
   --model-format OpenAI \
   --sku-name "Standard" \
   --sku-capacity 5
```

    > \* Sku-capacity is measured in thousands of tokens per minute. A rate limit of 5,000 tokens per minute is more than adequate to complete this exercise while leaving capacity for other people using the same subscription.

> [!NOTE]
> Wenn Sie eine Warnung sehen, dass das Net7.0-Framework nicht mehr unterstützt wird, können Sie diese für diese Übung ignorieren.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt, und beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource mit asynchronen API-Aufrufen nutzen zu können.

1. Navigieren Sie in Visual Studio Code im Bereich **„Explorer“** zum Ordner **„Labfiles/01-app-develop**“ und erweitern Sie den Ordner **„CSharp“** oder **„Python“**, je nachdem, welche Sprache Sie bevorzugen. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, in die Sie Azure OpenAI-Funktionen integrieren möchten.
2. Klicken Sie mit der rechten Maustaste auf den Ordner **CSharp** oder **Python**, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Installieren Sie dann das SDK-Paket von Azure OpenAI, indem Sie den entsprechenden Befehl für Ihre bevorzugte Sprache ausführen:

    **C#:**

    ```
    dotnet add package Azure.AI.OpenAI --version 2.0.0
    ```

    **Python**:

    ```
    pip install openai==1.54.3
    ```

3. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Konfigurationsdatei für Ihre bevorzugte Sprache.

    - **C#**: appsettings.json
    - **Python**: .env
    
4. Aktualisieren Sie die Konfigurationswerte, um Folgendes einzuschließen:
    - Den **Endpunkt** und einen **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
    - Der **Bereitstellungsname**, den Sie für Ihre Modellbereitstellung angegeben haben.
5. Speichern Sie die Konfigurationsdatei.

## Hinzufügen von Code zum Verwenden des Azure OpenAI-Diensts

Jetzt können Sie das Azure OpenAI-SDK verwenden, um Ihr bereitgestelltes Modell zu nutzen.

1. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Codedatei für Ihre bevorzugte Sprache, und ersetzen Sie den Kommentar ***Hinzufügen des Azure OpenAI-Pakets*** durch Code, um die Azure OpenAI-SDK-Bibliothek hinzuzufügen:

    **C#** : Program.cs

    ```csharp
    // Add Azure OpenAI packages
    using Azure.AI.OpenAI;
    using OpenAI.Chat;
    ```

    **Python**: application.py

    ```python
    # Add Azure OpenAI package
    from openai import AsyncAzureOpenAI
    ```

2. Suchen Sie in der Codedatei den Kommentar ***Konfigurieren des Azure OpenAI-Clients***, und fügen Sie Code zum Konfigurieren des Azure OpenAI-Clients hinzu:

    **C#** : Program.cs

    ```csharp
    // Configure the Azure OpenAI client
       AzureOpenAIClient azureClient = new (new Uri(oaiEndpoint), new ApiKeyCredential(oaiKey));
        ChatClient chatClient = azureClient.GetChatClient(oaiDeploymentName);
        ChatCompletion completion = chatClient.CompleteChat(
        [
        new SystemChatMessage(systemMessage),
        new UserChatMessage(userMessage),
        ]);
    ```

    **Python**: application.py

    ```python
    # Configure the Azure OpenAI client
    client = AsyncAzureOpenAI(
        azure_endpoint = azure_oai_endpoint, 
        api_key=azure_oai_key,  
        api_version="2024-02-15-preview"
        )
    ```

3. Fügen Sie in der Funktion, die das Azure OpenKI-Modell aufruft, unter dem Kommentar ***„Antwort von Azure OpenKI abrufen***“ den Code hinzu, um die Anfrage zu formatieren und an das Modell zu senden.

    **C#** : Program.cs

    ```csharp
    // Get response from Azure OpenAI
    Console.WriteLine($"{completion.Role}: {completion.Content[0].Text}");

    ```

    **Python**: application.py

    ```python
    # Get response from Azure OpenAI
    messages =[
        {"role": "system", "content": system_message},
        {"role": "user", "content": user_message},
    ]
    
    print("\nSending request to Azure OpenAI model...\n")

    # Call the Azure OpenAI model
    response = await client.chat.completions.create(
        model=model,
        messages=messages,
        temperature=0.7,
        max_tokens=800
    )
    ```

4. Speichern Sie die Änderungen in der Codedatei.

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten. Sie werden feststellen, dass der einzige Unterschied zwischen den verschiedenen Optionen der Inhalt der Eingabeaufforderung ist. Alle anderen Parameter (z. B. Tokenanzahl und Temperatur) bleiben für jede Anforderung gleich.

1. Öffnen Sie im Ordner Ihrer bevorzugten Sprache `system.txt` in Visual Studio Code. Für jede Interaktion rufen Sie die **Systemnachricht** in dieser Datei auf und speichern sie. Jede Iteration wird zuerst angehalten, um die Systemmeldung zu ändern.
1. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python application.py`

    > **Tipp**: Sie können das Symbol **Maximize panel size** (Panelgröße maximieren) (**^**) in der Terminalsymbolleiste verwenden, um mehr des Konsolentexts anzuzeigen.

1. Geben Sie für die erste Iteration die folgenden Eingabeaufforderungen ein:

    **Systemmeldung**

    ```prompt
    You are an AI assistant
    ```

    **Benutzermeldung:**

    ```prompt
    Write an intro for a new wildlife Rescue
    ```

1. Beobachten Sie die Ausgabe. Das KI-Modell wird wahrscheinlich eine gute allgemeine Einführung in die Rettung von Wildtieren liefern.
1. Geben Sie als Nächstes die folgenden Eingabeaufforderungen ein, die ein Format für die Antwort angeben:

    **Systemmeldung**

    ```prompt
    You are an AI assistant helping to write emails
    ```

    **Benutzermeldung:**

    ```prompt
    Write a promotional email for a new wildlife rescue, including the following: 
    - Rescue name is Contoso 
    - It specializes in elephants 
    - Call for donations to be given at our website
    ```

    > **Tipp**: Möglicherweise stellen Sie fest, dass die automatische Eingabe in der VM nicht gut mit mehrstufigen Eingabeaufforderungen funktioniert. Wenn dieses Problem besteht, kopieren Sie die gesamte Eingabeaufforderung und fügen Sie sie in Visual Studio Code ein.

1. Beobachten Sie die Ausgabe. Dieses Mal werden Sie wahrscheinlich das Format einer E-Mail sehen, in der die Tiere und der Spendenaufruf enthalten sind.
1. Geben Sie als Nächstes die folgenden Eingabeaufforderungen ein, die zusätzlich den Inhalt angeben:

    **Systemmeldung**

    ```prompt
    You are an AI assistant helping to write emails
    ```

    **Benutzermeldung:**

    ```prompt
    Write a promotional email for a new wildlife rescue, including the following: 
    - Rescue name is Contoso 
    - It specializes in elephants, as well as zebras and giraffes 
    - Call for donations to be given at our website 
    \n Include a list of the current animals we have at our rescue after the signature, in the form of a table. These animals include elephants, zebras, gorillas, lizards, and jackrabbits.
    ```

1. Beobachten Sie die Ausgabe, und sehen Sie, wie sich die E-Mail basierend auf Ihren klaren Anweisungen geändert hat.
1. Geben Sie als Nächstes die folgenden Eingabeaufforderungen ein, in denen Details zum Ton zur Systemmeldung hinzugefügt werden:

    **Systemmeldung**

    ```prompt
    You are an AI assistant that helps write promotional emails to generate interest in a new business. Your tone is light, chit-chat oriented and you always include at least two jokes.
    ```

    **Benutzermeldung:**

    ```prompt
    Write a promotional email for a new wildlife rescue, including the following: 
    - Rescue name is Contoso 
    - It specializes in elephants, as well as zebras and giraffes 
    - Call for donations to be given at our website 
    \n Include a list of the current animals we have at our rescue after the signature, in the form of a table. These animals include elephants, zebras, gorillas, lizards, and jackrabbits.
    ```

1. Beobachten Sie die Ausgabe. Diesmal werden Sie die E-Mail wahrscheinlich in einem ähnlichen Format sehen, aber in einem viel informelleren Ton. Wahrscheinlich werden sogar Witze enthalten sein!
1. Für die endgültige Iteration weichen wir von der E-Mail-Generierung ab und untersuchen *Grounding-Kontext*. Hier stellen Sie eine einfache Systemmeldung bereit und ändern die App so, dass der Grounding-Kontext als Beginn der Benutzeraufforderung bereitgestellt wird. Die App fügt dann die Benutzereingabe an und extrahiert Informationen aus dem Grounding-Kontext, um unsere Benutzeraufforderung zu beantworten.
1. Öffnen Sie die Datei `grounding.txt`, und lesen Sie kurz den Grounding-Kontext, den Sie einfügen möchten.
1. Fügen Sie in Ihrer App unmittelbar nach dem Kommentar ***Formatieren und Senden der Anforderung an das Modell*** und vor einem vorhandenen Code, den folgenden Codeausschnitt hinzu, um Text aus `grounding.txt` zu lesen, um die Benutzeraufforderung um den Grounding-Kontext zu erweitern.

    **C#** : Program.cs

    ```csharp
    // Format and send the request to the model
    Console.WriteLine("\nAdding grounding context from grounding.txt");
    string groundingText = System.IO.File.ReadAllText("grounding.txt");
    userMessage = groundingText + userMessage;
    ```

    **Python**: application.py

    ```python
    # Format and send the request to the model
    print("\nAdding grounding context from grounding.txt")
    grounding_text = open(file="grounding.txt", encoding="utf8").read().strip()
    user_message = grounding_text + user_message
    ```

1. Speichern Sie die Datei, und führen Sie Ihre App erneut aus.
1. Geben Sie die folgenden Eingabeaufforderungen ein (wobei die **Systemmeldung** weiterhin eingegeben und in `system.txt`gespeichert ist).

    **Systemmeldung**

    ```prompt
    You're an AI assistant who helps people find information. You'll provide answers from the text provided in the prompt, and respond concisely.
    ```

    **Benutzermeldung:**

    ```prompt
    What animal is the favorite of children at Contoso?
    ```

> **Tipp**: Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die **printFullResponse**-Variable auf `True` festlegen und die App erneut ausführen.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im **Azure-Portal** auf `https://portal.azure.com` zu löschen.
