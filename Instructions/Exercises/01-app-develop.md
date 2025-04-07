---
lab:
  title: App-Entwicklung mit Azure OpenAI-Service
  status: new
---

# App-Entwicklung mit Azure OpenAI-Service

Mit dem Azure OpenAI Service können Entwickelnde Chatbots und andere Anwendungen erstellen, die durch die Verwendung von REST-APIs oder sprachspezifischen SDKs die natürliche menschliche Sprache hervorragend verstehen. Bei der Arbeit mit diesen Sprachmodellen hat die Art und Weise, wie Entwickelnde ihre Eingabe gestalten, großen Einfluss darauf, wie das generative KI-Modell reagiert. Azure OpenAI-Modelle können Inhalte auf klare und präzise Weise anpassen und formatieren. In dieser Übung lernen Sie, wie Sie Ihre Anwendung mit Azure OpenAI verbinden und wie verschiedene Eingabeaufforderungen für ähnliche Inhalte dazu beitragen, die Antwort des KI-Modells so zu gestalten, dass sie Ihren Anforderungen besser entspricht.

Im Szenario für diese Übung sind Sie ein Softwareentwickler, der für eine Wildlife-Marketingkampagne arbeitet. Sie untersuchen, wie Sie generative KI verwenden können, um Werbe-E-Mails zu verbessern und Artikel zu kategorisieren, für Ihr Team relevant sein könnten. Die in der Übung verwendeten Prompt Engineering-Techniken können für eine Vielzahl von Anwendungsfällen genutzt werden.

Diese Übung dauert ungefähr **30** Minuten.

## Klonen des Repositorys für diesen Kurs

Wenn Sie das noch nicht erledigt haben, müssen Sie das Coderepository für diesen Kurs klonen:

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Befehlspalette (UMSCHALT+STRG+P oder **Ansicht** > **Befehlspalette …**) und führen Sie den Befehl **Git: Clone** aus, um das `https://github.com/MicrosoftLearning/mslearn-openai`-Repository in einen lokalen Ordner zu klonen (es spielt keine Rolle, in welchen Ordner).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.
4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

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

1. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Als Nächstes stellen Sie eine Azure OpenAI-Modellressource aus der CLI bereit. Verwenden Sie dieses Beispiel und ersetzen Sie die folgenden Variablen durch Ihre eigenen Werte von oben:

```dotnetcli
az cognitiveservices account deployment create \
   -g <your_resource_group> \
   -n <your_OpenAI_service> \
   --deployment-name gpt-4o \
   --model-name gpt-4o \
   --model-version 2024-05-13 \
   --model-format OpenAI \
   --sku-name "Standard" \
   --sku-capacity 5
```

> **Hinweis:** Die Sku-Kapazität wird in Tausend Token pro Minute gemessen. Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt, und beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource mit asynchronen API-Aufrufen nutzen zu können.

1. Navigieren Sie in Visual Studio Code im Bereich **„Explorer“** zum Ordner **„Labfiles/01-app-develop**“ und erweitern Sie den Ordner **„CSharp“** oder **„Python“**, je nachdem, welche Sprache Sie bevorzugen. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, in die Sie Azure OpenAI-Funktionen integrieren möchten.
2. Klicken Sie mit der rechten Maustaste auf den Ordner **CSharp** oder **Python**, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Installieren Sie dann das SDK-Paket von Azure OpenAI, indem Sie den entsprechenden Befehl für Ihre bevorzugte Sprache ausführen:

    **C#:**

    ```powershell
    dotnet add package Azure.AI.OpenAI --version 2.1.0
    ```

    **Python**:

    ```powershell
    pip install openai==1.65.2
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
    ChatCompletionOptions chatCompletionOptions = new ChatCompletionOptions()
    {
        Temperature = 0.7f,
        MaxOutputTokenCount = 800
    };

    ChatCompletion completion = chatClient.CompleteChat(
        [
            new SystemChatMessage(systemMessage),
            new UserChatMessage(userMessage)
        ],
        chatCompletionOptions
    );

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

## Verwenden des Groundingkontexts und Verwalten des Chatverlaufs

1. Für die letzte Iteration weichen wir von der E-Mail-Erstellung ab und erforschen den *Groundingkontext* und die Verwaltung des Chatverlaufs. Hier geben Sie eine einfache Systemmeldung ein und ändern die App so, dass der Kontext des Groundingkontexts als Beginn des Chatverlaufs angezeigt wird. Die App fügt dann die Benutzereingabe an und extrahiert Informationen aus dem Grounding-Kontext, um unsere Benutzeraufforderung zu beantworten.
1. Öffnen Sie die Datei `grounding.txt`, und lesen Sie kurz den Grounding-Kontext, den Sie einfügen möchten.
1. Fügen Sie in Ihrer App unmittelbar nach dem Kommentar ***Initialize messages list*** und vor jedem vorhandenen Code den folgenden Codeschnipsel hinzu, um Text aus `grounding.txt` einzulesen und den Chatverlauf mit dem Groundingkontext zu initialisieren.

    **C#** : Program.cs

    ```csharp
    // Initialize messages list
    Console.WriteLine("\nAdding grounding context from grounding.txt");
    string groundingText = System.IO.File.ReadAllText("grounding.txt");
    var messagesList = new List<ChatMessage>()
    {
        new UserChatMessage(groundingText),
    };
    ```

    **Python**: application.py

    ```python
    # Initialize messages array
    print("\nAdding grounding context from grounding.txt")
    grounding_text = open(file="grounding.txt", encoding="utf8").read().strip()
    messages_array = [{"role": "user", "content": grounding_text}]
    ```

1. Ersetzen Sie unter dem Kommentar ***Format and send the request to the model*** den Code aus dem Kommentar bis zum Ende der **while**-Schleife durch den folgenden Code. Der Code ist größtenteils derselbe, aber jetzt wird das Nachrichten-Array verwendet, um die Anfrage an das Modell zu senden.

    **C#** : Program.cs
   
    ```csharp
    // Format and send the request to the model
    messagesList.Add(new SystemChatMessage(systemMessage));
    messagesList.Add(new UserChatMessage(userMessage));
    GetResponseFromOpenAI(messagesList);
    ```

    **Python**: application.py

    ```python
    # Format and send the request to the model
    messages_array.append({"role": "system", "content": system_text})
    messages_array.append({"role": "user", "content": user_text})
    await call_openai_model(messages=messages_array, 
        model=azure_oai_deployment, 
        client=client
    )
    ```

1. Ersetzen Sie unter dem Kommentar ***Define the function that will get the response from Azure OpenAI endpoint*** die Funktionsdeklaration durch den folgenden Code, um die Chatverlaufsliste beim Aufruf der Funktion `GetResponseFromOpenAI` für C# oder `call_openai_model` für Python zu verwenden.

    **C#** : Program.cs
   
    ```csharp
    // Define the function that gets the response from Azure OpenAI endpoint
    private static void GetResponseFromOpenAI(List<ChatMessage> messagesList)
    ```

    **Python**: application.py

    ```python
    # Define the function that will get the response from Azure OpenAI endpoint
    async def call_openai_model(messages, model, client):
    ```
    
1. Ersetzen Sie schließlich den gesamten Code unter ***Get response from Azure OpenAI***. Der Code ist größtenteils identisch, aber jetzt wird das Nachrichtenarray verwendet, um den Unterhaltungsverlauf zu speichern.

    **C#** : Program.cs
   
    ```csharp
    // Get response from Azure OpenAI
    ChatCompletionOptions chatCompletionOptions = new ChatCompletionOptions()
    {
        Temperature = 0.7f,
        MaxOutputTokenCount = 800
    };

    ChatCompletion completion = chatClient.CompleteChat(
        messagesList,
        chatCompletionOptions
    );

    Console.WriteLine($"{completion.Role}: {completion.Content[0].Text}");
    messagesList.Add(new AssistantChatMessage(completion.Content[0].Text));
    ```

    **Python**: application.py

    ```python
    # Get response from Azure OpenAI
    print("\nSending request to Azure OpenAI model...\n")

    # Call the Azure OpenAI model
    response = await client.chat.completions.create(
        model=model,
        messages=messages,
        temperature=0.7,
        max_tokens=800
    )   

    print("Response:\n" + response.choices[0].message.content + "\n")
    messages.append({"role": "assistant", "content": response.choices[0].message.content})
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

   Beachten Sie, dass das Modell die Grundtextinformationen verwendet, um Ihre Frage zu beantworten.

1. Geben Sie ohne Änderung der Systemmeldung den folgenden Prompt für die Benutzermeldung ein:

    **Benutzermeldung:**

    ```prompt
    How can they interact with it at Contoso?
    ```

    Beachten Sie, dass das Modell „sie“ als untergeordnetes Element und „es“ als ihr Lieblingstier erkennt, da es nun Zugriff auf Ihre vorherige Frage im Chatverlauf hat.
   
## Bereinigen

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im **Azure-Portal** auf `https://portal.azure.com` zu löschen.
