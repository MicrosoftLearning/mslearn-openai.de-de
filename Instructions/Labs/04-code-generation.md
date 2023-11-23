---
lab:
  title: Generieren und Verbessern von Code mit Azure OpenAI Service
---

# Generieren und Verbessern von Code mit Azure OpenAI Service

Die Azure OpenAI Service-Modelle können Code für Sie generieren, indem Sie Eingabeaufforderungen in natürlicher Sprache verwenden, Fehler in fertigem Code beheben und Codekommentare bereitstellen. Diese Modelle können auch vorhandenen Code erklären und vereinfachen, damit Sie verstehen, was er tut und wie man ihn verbessern kann.

Diese Übung dauert ungefähr **25** Minuten.

## Vorbereitung

Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.

- Besuchen Sie [https://azure.microsoft.com/free](https://azure.microsoft.com/free), um sich für ein kostenloses Azure-Abonnement zu registrieren.
- Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Bereitstellen einer Azure OpenAI-Ressource

Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement**: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits vorhandene Ressourcengruppe, oder erstellen Sie eine Ressourcengruppe mit einem beliebigen Namen.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.
4. Navigieren Sie zur Seite **Schlüssel und Endpunkt**, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.

## Bereitstellen eines Modells

Um die Azure OpenAI-API zur Codegenerierung verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verwenden wir das Modell mit dem Playground und verweisen in unserer App auf dieses Modell.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) navigieren.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungsname**: 35turbo

> **Hinweis**: Jedes Azure OpenAI-Modell ist für ein anderes Verhältnis von Funktionen und Leistung optimiert. In dieser Übung verwenden wir die Modellreihe **3.5 Turbo** in der Modellfamilie **GPT-3**, die sowohl für das Sprach- als auch für das Codeverständnis sehr gut geeignet ist.

## Generieren von Code im Playground für Chats

Überprüfen Sie vor der Verwendung in Ihrer App, wie Azure OpenAI Code im Playground für Chats generieren und erklären kann.

1. Navigieren Sie in [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) im linken Bereich zum Playground **Chat**.
1. Wählen Sie oben im Abschnitt **Assistenteneinrichtung** die Vorlage **Standardsystemmeldung** aus.
1. Geben Sie im Abschnitt **Chatsitzung** die folgende Eingabeaufforderung ein, und drücken Sie die *EINGABETASTE*.

    ```code
   Write a function in python that takes a character and string as input, and returns how many times that character appears in the string
    ```

1. Das Modell antwortet wahrscheinlich mit einer Funktion, mit einer Erklärung, was die Funktion tut und wie sie aufgerufen werden kann.
1. Senden Sie als Nächstes die Eingabeaufforderung `Do the same thing, but this time write it in C#`.
1. Beobachten Sie die Ausgabe. Das Modell reagierte wahrscheinlich sehr ähnlich wie beim ersten Mal, diesmal jedoch in C#. Sie können es erneut nach einer anderen Sprache Ihrer Wahl oder einer Funktion fragen, um eine andere Aufgabe zu erfüllen, wie z. B. das Umkehren einer Eingabezeichenfolge.
1. Als Nächstes untersuchen wir die Verwendung von KI zum Verständnis von Code anhand dieses Beispiels einer Zufallsfunktion, die Sie in Ruby geschrieben haben. Senden Sie die folgende Eingabeaufforderung als Benutzernachricht.

    ```code
    What does the following function do?  
    ---  
    def random_func(n)
      start = [0, 1]
      (n - 2).times do
        start << start[-1] + start[-2]
      end
      start.shuffle.each do |num|
        puts num
      end
    end
    ```

1. Beobachten Sie die Ausgabe, die erklärt, was die Funktion in natürlicher Sprache ausführt. Fordern Sie das Modell auf, sie in einer Sprache neu zu schreiben, mit der Sie vertraut sind.

## Einrichten einer Anwendung in Cloud Shell

Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird. Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.

1. Klicken Sie im [Azure-Portal](https://portal.azure.com?azure-portal=true) oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche **[>_]** (*Cloud Shell*). Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.

    ![Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld](../media/cloudshell-launch-portal.png#lightbox)

2. Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (*Bash* oder *PowerShell*). Wählen Sie **Bash** aus. Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.  

3. Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie **Erweiterte Einstellungen anzeigen** und wählen Sie die folgenden Einstellungen:
    - **Abonnement**: Ihr Abonnement
    - **Cloud Shell-Regionen**: Wählen Sie eine verfügbare Region
    - **VNET-Isolationseinstellungen anzeigen** Nicht ausgewählt
    - **Ressourcengruppe**: Verwenden Sie die bestehende Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben
    - **Speicherkonto**: Erstellen Sie ein neues Speicherkonto mit einem eindeutigen Namen
    - **Dateifreigabe**: Erstellen Sie eine neue Dateifreigabe mit einem eindeutigen Namen

    Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.

    > **Hinweis**: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option **Benutzereinstellungen zurücksetzen** im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.

4. Vergewissern Sie sich, dass der oben links im Bereich „Cloud Shell“ angegebene Shell-Typ *Bash* lautet. Sollte *PowerShell* angezeigt werden, wechseln Sie über das Dropdownmenü zu *Bash*.

5. Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens `azure-openai` zu speichern.

    ```bash
   rm -r azure-openai -f
   git clone https://github.com/MicrosoftLearning/mslearn-openai azure-openai
    ```

6. Die Dateien werden in einen Ordner namens **azure-openai** heruntergeladen. Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.

    ```bash
   cd azure-openai/Labfiles/04-code-generation
    ```

    Anwendungen für C# und Python sowie Beispielcode, den wir in diesem Lab verwenden werden, wurden bereitgestellt.

    Öffnen Sie den integrierten Code-Editor, und Sie können die Codedateien beobachten, die wir in `sample-code` verwenden. Verwenden Sie den folgenden Befehl, um die Labdateien im Code-Editor zu öffnen.

    ```bash
   code .
    ```

## Konfigurieren der Anwendung

In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.

1. Erweitern Sie im Code-Editor den Sprachordner für Ihre bevorzugte Sprache.

2. Öffnen Sie die Konfigurationsdatei für Ihre Sprache.

    - **C#** : `appsettings.json`
    - **Python**: `.env`

3. Aktualisieren Sie die Konfigurationswerte so, dass sie den **Endpunkt** und **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den Namen Ihrer Bereitstellung (`35turbo`) enthalten. Speichern Sie die Datei .

4. Navigieren Sie zum Ordner für Ihre bevorzugte Sprache, und installieren Sie die erforderlichen Pakete.

    **C#**

    ```bash
   cd CSharp
   dotnet add package Azure.AI.OpenAI --version 1.0.0-beta.5
    ```

    **Python**

    ```bash
   cd Python
   pip install python-dotenv
   pip install openai
    ```

5. Wählen Sie die Codedatei in diesem Ordner für Ihre Sprache aus, und fügen Sie die erforderlichen Bibliotheken hinzu.

    **C#**

    `Program.cs`

    ```csharp
   // Add Azure OpenAI package
   using Azure.AI.OpenAI;
    ```

    **Python**

    `code-generation.py`

    ```python
   # Add OpenAI import
   import openai
    ```

6. Fügen Sie den erforderlichen Code zum Konfigurieren des Clients hinzu.

    **C#**

    ```csharp
   // Initialize the Azure OpenAI client
   OpenAIClient client = new OpenAIClient(new Uri(oaiEndpoint), new AzureKeyCredential(oaiKey));
    ```

    **Python**

    ```python
   # Set OpenAI configuration settings
   openai.api_type = "azure"
   openai.api_base = azure_oai_endpoint
   openai.api_version = "2023-05-15"
   openai.api_key = azure_oai_key
    ```

7. Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.

    **C#**

    ```csharp
    // Create chat completion options
    var chatCompletionsOptions = new ChatCompletionsOptions()
    {
        Messages =
        {
            new ChatMessage(ChatRole.System, systemPrompt),
            new ChatMessage(ChatRole.User, userPrompt)
        },
        Temperature = 0.7f,
        MaxTokens = 1000,
    };

    // Get response from Azure OpenAI
    Response<ChatCompletions> response = await client.GetChatCompletionsAsync(
        oaiModelName,
        chatCompletionsOptions
    );

    ChatCompletions completions = response.Value;
    string completion = completions.Choices[0].Message.Content;
    ```

    **Python**

    ```python
   # Build the messages array
   messages =[
       {"role": "system", "content": system_message},
       {"role": "user", "content": user_message},
   ]

   # Call the Azure OpenAI model
   response = openai.ChatCompletion.create(
       engine=model,
       messages=messages,
       temperature=0.7,
       max_tokens=1000
   )
    ```

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Code für jeden Anwendungsfall zu generieren. Die Anwendungsfälle sind in der App nummeriert und können in beliebiger Reihenfolge ausgeführt werden.

> **Hinweis**: Bei einigen Benutzer*innen kann es zu einer Ratenbegrenzung kommen, wenn sie das Modell zu häufig aufrufen. Wenn Sie eine Fehlermeldung über eine Tokenratenbegrenzung erhalten, warten Sie eine Minute, und versuchen Sie es dann erneut.

1. Erweitern Sie im Code-Editor den `sample-code`-Ordner, und beobachten Sie kurz die Funktion und die App für Ihre Sprache. Diese Dateien werden für die Aufgaben in der App verwendet.
1. Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.
1. Führen Sie die Anwendung aus.

    - **C#** : `dotnet run`
    - **Python**: `python code-generation.py`

1. Wählen Sie Option **1** aus, um Ihrem Code Kommentare hinzuzufügen. Beachten Sie, dass die Beantwortung jeder dieser Aufgaben einige Sekunden dauern kann.
1. Die Ergebnisse werden in `result/app.txt` eingefügt. Öffnen Sie diese Datei, und vergleichen Sie sie mit der Funktionsdatei in `sample-code`.
1. Wählen Sie als Nächstes Option **2** aus, um Komponententests für dieselbe Funktion zu schreiben.
1. Die Ergebnisse ersetzen das, was in `result/app.txt` stand, und enthalten vier Komponententests für diese Funktion.
1. Wählen Sie als Nächstes Option **3** aus, um Fehler in einer App für die Wiedergabe von Go Fish zu beheben.
1. Die Ergebnisse ersetzen das, was in `result/app.txt` stand, und sollten einen sehr ähnlichen Code haben, wobei einige Dinge korrigiert wurden.

    - **C#** : Korrekturen werden in Zeile 30 und 59 vorgenommen.
    - **Python**: Korrekturen werden in Zeile 18 und 31 vorgenommen.

Die App für Go Fish in `sample-code` kann ausgeführt werden, wenn man die Zeilen mit Fehlern durch die Antwort von Azure OpenAI ersetzt. Wenn Sie sie ohne die Korrekturen ausführen, wird sie nicht richtig funktionieren.

Es ist wichtig zu beachten, dass der Code für diese Go Fish-App zwar um einige Syntaxfehler korrigiert wurde, es sich jedoch nicht um eine genaue Darstellung des Spiels handelt. Wenn Sie genau hinsehen, treten Probleme dadurch auf, dass beim Ziehen von Karten nicht geprüft wird, ob das Deck leer ist, dass Paare nicht aus der Hand des Spielers bzw. der Spielerin entfernt werden, wenn er*sie ein Paar erhält, und einige andere Fehler, die ein Verständnis von Kartenspielen erfordern, um sie zu erkennen. Dies ist ein großartiges Beispiel dafür, wie nützlich generative KI-Modelle sein können, um die Codegenerierung zu unterstützen. Sie sollten jedoch nicht als absolut zuverlässig angesehen werden und müssen von dem*der Entwickler*in überprüft werden.

Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die `printFullResponse`-Variable auf `True` festlegen und die App erneut ausführen.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen.
