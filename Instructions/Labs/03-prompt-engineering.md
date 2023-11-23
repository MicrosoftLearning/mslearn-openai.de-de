---
lab:
  title: Verwenden von Prompt Engineering in Ihrer App
---

# Verwenden von Prompt Engineering in Ihrer App

Mit Azure OpenAI Service können Entwickler*innen Chatbots, Sprachmodelle und andere Anwendungen erstellen, die die natürliche menschliche Sprache besonders gut verstehen. Azure OpenAI bietet Zugriff auf vortrainierte KI-Modelle sowie eine Suite von APIs und Tools zum Anpassen und Optimieren dieser Modelle, um die spezifischen Anforderungen Ihrer Anwendung zu erfüllen. In dieser Übung erfahren Sie, wie Sie ein Modell in Azure OpenAI bereitstellen und es in Ihrer eigenen Anwendung verwenden, um Text zusammenzufassen.

Bei der Arbeit mit Azure OpenAI Service wirkt sich die Gestaltung der Eingabeaufforderung durch Entwickler*innen erheblich darauf aus, wie das generative KI-Modell reagiert. Azure OpenAI-Modelle können Inhalte auf klare und präzise Weise anpassen und formatieren. In dieser Übung erfahren Sie, wie unterschiedliche Eingabeaufforderungen für ähnliche Inhalte dazu beitragen, die Antwort des KI-Modells so zu gestalten, dass Ihre Anforderungen besser erfüllt werden.

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

Um die Azure OpenAI-API verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verweisen wir in unserer App auf dieses Modell.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) navigieren.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungsname**: text-turbo

> **Hinweis**: Jedes Azure OpenAI-Modell ist für ein anderes Verhältnis von Funktionen und Leistung optimiert. In dieser Übung verwenden wir die Modellreihe **3.5 Turbo** in der Modellfamilie **GPT-3**, die für das Sprachverständnis sehr gut geeignet ist. In dieser Übung wird nur ein einzelnes Modell verwendet. Die Bereitstellung und Verwendung anderer von Ihnen bereitgestellter Modelle funktionieren jedoch auf die gleiche Weise.

## Anwenden von Prompt Engineering in Chatplaygrounds

Bevor Sie Ihre App verwenden, überprüfen Sie, wie das Prompt Engineering die Modellantwort im Playground verbessert. In diesem ersten Beispiel stellen Sie sich vor, dass Sie versuchen, eine Python-App mit Tieren mit lustigen Namen zu schreiben.

1. Navigieren Sie in [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) im linken Bereich zum Playground **Chat**.
1. Geben Sie im Abschnitt **Assistenteneinrichtung** `You are a helpful AI assistant` als Systemmeldung ein.
1. Geben Sie im Abschnitt **Chatsitzung** die folgende Eingabeaufforderung ein, und drücken Sie die *EINGABETASTE*.

    ```code
   1. Create a list of animals
   2. Create a list of whimsical names for those animals
   3. Combine them randomly into a list of 25 animal and name pairs
    ```

1. Das Modell liefert wahrscheinlich eine Antwort auf die Eingabeaufforderung, aufgeteilt in eine nummerierte Liste. Das ist eine gute Antwort, aber nicht das, wonach wir suchen.
1. Aktualisieren Sie dann die Systemmeldung, um die Anweisungen `You are an AI assistant helping write python code. Complete the app based on provided comments` aufzunehmen. Klicken Sie auf **Änderungen speichern**
1. Formatieren Sie die Anweisungen als Python-Kommentare. Senden Sie die folgende Eingabeaufforderung an das Modell.

    ```code
   # 1. Create a list of animals
   # 2. Create a list of whimsical names for those animals
   # 3. Combine them randomly into a list of 25 animal and name pairs
    ```

1. Das Modell sollte ordnungsgemäß mit vollständigem Python-Code antworten und das tun, was in den Kommentaren angefordert wurde.
1. Als Nächstes sehen wir die Auswirkungen einiger Eingabeaufforderungen beim Versuch, Artikel zu klassifizieren. Kehren Sie zur Systemmeldung zurück, geben Sie erneut `You are a helpful AI assistant` ein, und speichern Sie Ihre Änderungen. Dadurch wird eine neue Chatsitzung erstellt.
1. Senden Sie die folgende Eingabeaufforderung an das Modell.

    ```code
   Severe drought likely in California

   Millions of California residents are bracing for less water and dry lawns as drought threatens to leave a large swath of the region with a growing water shortage.
   
   In a remarkable indication of drought severity, officials in Southern California have declared a first-of-its-kind action limiting outdoor water use to one day a week for nearly 8 million residents.
   
   Much remains to be determined about how daily life will change as people adjust to a drier normal. But officials are warning the situation is dire and could lead to even more severe limits later in the year.
    ```

1. Die Antwort besteht wahrscheinlich aus einigen Informationen über die Dürre in Kalifornien. Obwohl es keine schlechte Antwort ist, ist es nicht die Klassifizierung, nach der wir suchen.
1. Wählen Sie im Abschnitt **Assistenteneinrichtung** in der Nähe der Systemmeldung die Schaltfläche **Beispiel hinzufügen** aus. Fügen Sie das folgende Beispiel hinzu.

    **Benutzer:**

    ```code
   New York Baseballers Wins Big Against Chicago
   
   New York Baseballers mounted a big 5-0 shutout against the Chicago Cyclones last night, solidifying their win with a 3 run homerun late in the bottom of the 7th inning.
   
   Pitcher Mario Rogers threw 96 pitches with only two hits for New York, marking his best performance this year.
   
   The Chicago Cyclones' two hits came in the 2nd and the 5th innings, but were unable to get the runner home to score.
    ```

    **Assistent:**

    ```code
   Sports
    ```

1. Fügen Sie ein weiteres Beispiel mit dem folgenden Text hinzu.

    **Benutzer:**

    ```code
   Joyous moments at the Oscars

   The Oscars this past week where quite something!
   
   Though a certain scandal might have stolen the show, this year's Academy Awards were full of moments that filled us with joy and even moved us to tears.
   These actors and actresses delivered some truly emotional performances, along with some great laughs, to get us through the winter.
   
   From Robin Kline's history-making win to a full performance by none other than Casey Jensen herself, don't miss tomorrows rerun of all the festivities.
    ```

    **Assistent:**

    ```code
   Entertainment
    ```

1. Speichern Sie diese Änderungen in der Assistenteneinrichtung, und senden Sie die gleiche Eingabeaufforderung über die Dürre in Kalifornien, die hier aus Gründen der Einfachheit noch einmal bereitgestellt wird.

    ```code
   Severe drought likely in California

   Millions of California residents are bracing for less water and dry lawns as drought threatens to leave a large swath of the region with a growing water shortage.
   
   In a remarkable indication of drought severity, officials in Southern California have declared a first-of-its-kind action limiting outdoor water use to one day a week for nearly 8 million residents.
   
   Much remains to be determined about how daily life will change as people adjust to a drier normal. But officials are warning the situation is dire and could lead to even more severe limits later in the year.
    ```

1. Dieses Mal sollte das Modell mit einer entsprechenden Klassifizierung reagieren, auch ohne Anweisungen.

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
   cd azure-openai/Labfiles/03-prompt-engineering
    ```

    Es werden Anwendungen für C# und Python sowie Textdateien für die Eingabeaufforderungen bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität.

    Öffnen Sie den integrierten Code-Editor, und Sie können die Eingabeaufforderungsdateien beobachten, die Sie in `prompts` verwenden. Verwenden Sie den folgenden Befehl, um die Labdateien im Code-Editor zu öffnen.

    ```bash
   code .
    ```

## Konfigurieren der Anwendung

In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.

1. Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner **CSharp** oder **Python**.

2. Öffnen Sie die Konfigurationsdatei für Ihre Sprache.

    - C#: `appsettings.json`
    - Python: `.env`
    
3. Aktualisieren Sie die Konfigurationswerte so, dass sie den **Endpunkt** und **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen enthalten (`text-turbo`). Speichern Sie die Datei .

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

5. Navigieren Sie zu Ihrem bevorzugten Sprachordner, wählen Sie die Codedatei aus, und fügen Sie die erforderlichen Bibliotheken hinzu.

    **C#**

    ```csharp
   // Add Azure OpenAI package
   using Azure.AI.OpenAI;
    ```

    **Python**

    ```python
   # Add OpenAI import
   import openai
    ```

5. Öffnen Sie den Anwendungscode für Ihre Sprache, und fügen Sie den erforderlichen Code zum Konfigurieren des Clients hinzu.

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
   openai.api_version = "2023-03-15-preview"
   openai.api_key = azure_oai_key
    ```

6. Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.

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
       MaxTokens = 800,
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
       max_tokens=800
   )
    ```

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten. Sie werden feststellen, dass der einzige Unterschied zwischen den verschiedenen Optionen der Inhalt der Eingabeaufforderung ist. Alle anderen Parameter (z. B. Tokenanzahl und Temperatur) bleiben für jede Anforderung gleich.

Jede Eingabeaufforderung wird während des Sendevorgangs in der Konsole angezeigt, damit Sie sehen können, wie unterschiedliche Eingabeaufforderungen verschiedene Antworten erzeugen.

1. Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.
1. Führen Sie die Anwendung aus, und erweitern Sie das Terminal, um den größten Teil Ihres Browserfensters zu nutzen.

    - **C#** : `dotnet run`
    - **Python**: `python prompt-engineering.py`

1. Wählen Sie Option **1** für die einfachste Eingabeaufforderung aus.
1. Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe. Das KI-Modell wird wahrscheinlich eine gute allgemeine Einführung in die Rettung von Wildtieren liefern.
1. Wählen Sie als Nächstes Option **2** aus, um eine Eingabeaufforderung für eine Vorstellungs-E-Mail mit einigen Details über die Wildtierrettung zu erhalten.
1. Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe. Dieses Mal werden Sie wahrscheinlich das Format einer E-Mail sehen, in der die Tiere und der Spendenaufruf enthalten sind.
1. Wählen Sie als Nächstes Option **3** aus, um eine E-Mail ähnlich der obigen zu erhalten, jedoch mit einer formatierten Tabelle mit zusätzlichen Tieren.
1. Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe. Dieses Mal sehen Sie wahrscheinlich eine ähnliche E-Mail mit speziell formatiertem Text (in diesem Fall eine Tabelle am Ende), die zeigt, wie die generativen KI-Modelle die Ausgabe bei Bedarf formatieren können.
1. Wählen Sie als Nächstes Option **4** aus, um eine ähnliche E-Mail anzufordern, aber dieses Mal mit einem anderen Ton in der Systemmeldung.
1. Beobachten Sie die Eingabeaufforderungseingabe und die generierte Ausgabe. Diesmal werden Sie die E-Mail wahrscheinlich in einem ähnlichen Format sehen, aber in einem viel informelleren Ton. Wahrscheinlich werden sogar Witze enthalten sein!

Eine Erhöhung der Temperatur führt häufig dazu, dass die Antworten variieren, selbst wenn die gleiche Eingabeaufforderung bereitgestellt wird, was auf die erhöhte Zufälligkeit zurückzuführen ist. Sie können sie mehrmals mit unterschiedlichen Temperatur- oder top_p-Werten ausführen, um zu sehen, wie sich dies auf die Antwort auf dieselbe Eingabeaufforderung auswirkt.

Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die `printFullResponse`-Variable auf `True` festlegen und die App erneut ausführen.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen.
