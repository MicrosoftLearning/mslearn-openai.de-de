---
lab:
  title: Verwenden von Prompt Engineering in Ihrer App
---

# Verwenden von Prompt Engineering in Ihrer App

Bei der Arbeit mit Azure OpenAI Service wirkt sich die Gestaltung der Eingabeaufforderung durch Entwickler*innen erheblich darauf aus, wie das generative KI-Modell reagiert. Azure OpenAI-Modelle können Inhalte auf klare und präzise Weise anpassen und formatieren. In dieser Übung erfahren Sie, wie unterschiedliche Eingabeaufforderungen für ähnliche Inhalte dazu beitragen, die Antwort des KI-Modells so zu gestalten, dass Ihre Anforderungen besser erfüllt werden.

Im Szenario für diese Übung sind Sie ein Softwareentwickler, der für eine Wildlife-Marketingkampagne arbeitet. Sie untersuchen, wie Sie generative KI verwenden können, um Werbe-E-Mails zu verbessern und Artikel zu kategorisieren, für Ihr Team relevant sein könnten. Die in der Übung verwendeten Prompt Engineering-Techniken können für eine Vielzahl von Anwendungsfällen genutzt werden.

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
    - **Modell**: gpt-35-turbo-16k *(wenn das 16k-Modell nicht verfügbar ist, wählen Sie gpt-35-turbo)*
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Wählen Sie einen Namen für Ihre Wahl aus. Sie verwenden diesen Namen später im Lab.*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Bereitstellungstyp**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Erkunden von Prompt-Engineering-Techniken

Beginnen wir mit der Erkundung einiger Prompt Engineering-Technik im Chat-Playground.

1. Wählen Sie in **Azure OpenAI Studio** unter `https://oai.azure.com` im Abschnitt **Playground** die Seite **Chat** aus. Die Playground-Seite **Chat** besteht aus drei Hauptabschnitten:
    - **Setup**: wird zum Festlegen des Kontexts für die Antworten des Modells verwendet
    - **Chatsitzung**: wird zum Senden von Chat-Nachrichten und Ansehen von Antworten verwendet
    - **Konfiguration**: wird zum Konfigurieren von Einstellungen für die Modellbereitstellung verwendet
2. Stellen Sie im Bereich **Konfiguration** sicher, dass Ihre Modellbereitstellung ausgewählt ist.
3. Wählen Sie im Bereich **Setup** die Standardvorlage für Systemnachrichten aus, um den Kontext für die Chatsitzung festzulegen. Die Standardsystemnachricht lautet *Sie sind ein KI-Assistent, der Personen hilft, Informationen zu finden*.
4. Senden Sie in der **Chatsitzung** die folgende Abfrage:

    ```
    What kind of article is this?
    ---
    Severe drought likely in California
    
    Millions of California residents are bracing for less water and dry lawns as drought threatens to leave a large swath of the region with a growing water shortage.
    
    In a remarkable indication of drought severity, officials in Southern California have declared a first-of-its-kind action limiting outdoor water use to one day a week for nearly 8 million residents.
    
    Much remains to be determined about how daily life will change as people adjust to a drier normal. But officials are warning the situation is dire and could lead to even more severe limits later in the year.
    ```

    Die Antwort enthält eine Beschreibung des Artikels. Nehmen wir an, Sie möchten ein spezielleres Format für die Artikelkategorisierung.

5. Ändern Sie im Abschnitt **Setup** die Systemmeldung in `You are a news aggregator that categorizes news articles.`.

6. Wählen Sie unter der neuen Systemmeldung im Abschnitt **Beispiele** die Schaltfläche **Hinzufügen** aus. Fügen Sie anschließend das folgende Beispiel hinzu.

    **Benutzer**:
    
    ```
    What kind of article is this?
    ---
    New York Baseballers Wins Big Against Chicago
    
    New York Baseballers mounted a big 5-0 shutout against the Chicago Cyclones last night, solidifying their win with a 3 run homerun late in the bottom of the 7th inning.
    
    Pitcher Mario Rogers threw 96 pitches with only two hits for New York, marking his best performance this year.
    
    The Chicago Cyclones' two hits came in the 2nd and the 5th innings but were unable to get the runner home to score.
    ```
    
    **Assistent:**
    
    ```
    Sports
      ```

7. Fügen Sie ein weiteres Beispiel mit dem folgenden Text hinzu.

    **Benutzer:**
    
    ```
    Categorize this article:
    ---
    Joyous moments at the Oscars
    
    The Oscars this past week where quite something!
    
    Though a certain scandal might have stolen the show, this year's Academy Awards were full of moments that filled us with joy and even moved us to tears.
    These actors and actresses delivered some truly emotional performances, along with some great laughs, to get us through the winter.
    
    From Robin Kline's history-making win to a full performance by none other than Casey Jensen herself, don't miss tomorrows rerun of all the festivities.
    ```
    
    **Assistent:**
    
    ```
    Entertainment
    ```

8. Verwenden Sie die Schaltfläche **Änderungen anwenden** oben im Abschnitt **Setup**, um die Systemmeldung zu aktualisieren.

9. Geben Sie im Abschnitt **Chatsitzung** erneut die folgende Eingabeaufforderung ein:

    ```
    What kind of article is this?
    ---
    Severe drought likely in California
    
    Millions of California residents are bracing for less water and dry lawns as drought threatens to leave a large swath of the region with a growing water shortage.
    
    In a remarkable indication of drought severity, officials in Southern California have declared a first-of-its-kind action limiting outdoor water use to one day a week for nearly 8 million residents.
    
    Much remains to be determined about how daily life will change as people adjust to a drier normal. But officials are warning the situation is dire and could lead to even more severe limits later in the year.
    ```

    Die Kombination aus einer spezifischeren Systemmeldung und einigen Beispielen für erwartete Abfragen und Antworten führt zu einem konsistenten Format für die Ergebnisse.

10. Ändern Sie im Abschnitt **Setup** die Systemmeldung wieder in die Standardvorlage, die `You are an AI assistant that helps people find information.` ohne Beispiele sein sollte. Übernehmen Sie dann die Änderungen.

11. Geben Sie im Abschnitt **Chatsitzung** die folgende Eingabeaufforderung ein:

    ```
    # 1. Create a list of animals
    # 2. Create a list of whimsical names for those animals
    # 3. Combine them randomly into a list of 25 animal and name pairs
    ```

    Das Modell liefert wahrscheinlich eine Antwort auf die Eingabeaufforderung, aufgeteilt in eine nummerierte Liste. Das ist eine angemessene Antwort, aber nehmen wir an, Sie wollten eigentlich, dass das Modell ein Python-Programm schreibt, das die von Ihnen beschriebenen Aufgaben ausführt.

12. Ändern Sie die Systemmeldung in `You are a coding assistant helping write python code.`, und wenden Sie die Änderungen an.
13. Senden Sie die folgende Eingabeaufforderung erneut an das Modell.

    ```
    # 1. Create a list of animals
    # 2. Create a list of whimsical names for those animals
    # 3. Combine them randomly into a list of 25 animal and name pairs
    ```

    Das Modell sollte ordnungsgemäß mit Python-Code antworten und das tun, was in den Kommentaren angefordert wurde.

## Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sehen Sie sich nun das Nutzen des Prompt Engineerings in einer App an, die das Azure OpenAI-Dienst-SDK verwendet. Sie entwickeln Ihre App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P), und führen Sie einen **Git: Clone**-Befehl aus, um das Repository `https://github.com/MicrosoftLearning/mslearn-openai` in einen lokalen Ordner zu klonen (der Ordner ist beliebig).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt, und beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource mit asynchronen API-Aufrufen nutzen zu können.

1. Wechseln Sie in Visual Studio Code im **Explorer** -Bereich zum Ordner **Labfiles/03-prompt-engineering**, und erweitern Sie je nach Ihrer bevorzugten Sprache den Ordner **CSharp** oder **Python**. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, in die Sie Azure OpenAI-Funktionen integrieren möchten.
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

    **Python**: prompt-engineering.py

    ```python
    # Add Azure OpenAI package
    from openai import AsyncAzureOpenAI
    ```

2. Suchen Sie in der Codedatei den Kommentar ***Konfigurieren des Azure OpenAI-Clients***, und fügen Sie Code zum Konfigurieren des Azure OpenAI-Clients hinzu:

    **C#** : Program.cs

    ```csharp
    // Configure the Azure OpenAI client
    OpenAIClient client = new OpenAIClient(new Uri(oaiEndpoint), new AzureKeyCredential(oaiKey));
    ```

    **Python**: prompt-engineering.py

    ```python
    # Configure the Azure OpenAI client
    client = AsyncAzureOpenAI(
        azure_endpoint = azure_oai_endpoint, 
        api_key=azure_oai_key,  
        api_version="2024-02-15-preview"
        )
    ```

3. Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, unter dem Kommentar ***Formatieren und Senden der Anforderung an das Modell***, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.

    **C#** : Program.cs

    ```csharp
    // Format and send the request to the model
    var chatCompletionsOptions = new ChatCompletionsOptions()
    {
        Messages =
        {
            new ChatRequestSystemMessage(systemMessage),
            new ChatRequestUserMessage(userMessage)
        },
        Temperature = 0.7f,
        MaxTokens = 800,
        DeploymentName = oaiDeploymentName
    };
    
    // Get response from Azure OpenAI
    Response<ChatCompletions> response = await client.GetChatCompletionsAsync(chatCompletionsOptions);
    ```

    **Python**: prompt-engineering.py

    ```python
    # Format and send the request to the model
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

1. Öffnen Sie im Ordner Ihrer bevorzugten Sprache `system.txt` in Visual Studio Code. Geben Sie für jede der Interationen die **Systemmeldung** in diese Datei ein, und speichern Sie sie. Jede Iteration wird zuerst angehalten, um die Systemmeldung zu ändern.
1. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python prompt-engineering.py`

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

    **Python**: prompt-engineering.py

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
