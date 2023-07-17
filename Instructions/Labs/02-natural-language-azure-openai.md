---
lab:
  title: Integrieren von Azure OpenAI mit Ihrer App
---

# Integrieren von Azure OpenAI mit Ihrer App

Mit Azure OpenAI Service können Entwickler*innen Chatbots, Sprachmodelle und andere Anwendungen erstellen, die die natürliche menschliche Sprache besonders gut verstehen. Azure OpenAI bietet Zugriff auf vortrainierte KI-Modelle sowie eine Suite von APIs und Tools zum Anpassen und Optimieren dieser Modelle, um die spezifischen Anforderungen Ihrer Anwendung zu erfüllen. In dieser Übung erfahren Sie, wie Sie ein Modell in Azure OpenAI bereitstellen und es in Ihrer eigenen Anwendung verwenden, um Text zusammenzufassen.

Diese Übung dauert ungefähr **30** Minuten.

## Vorbereitung

Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.

- Besuchen Sie [https://azure.microsoft.com/free](https://azure.microsoft.com/free), um sich für ein kostenloses Azure-Abonnement zu registrieren.
- Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Bereitstellen einer Azure OpenAI-Ressource

Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement**: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.
    - **Ressourcengruppe**: Erstellen Sie eine neue Ressourcengruppe mit einem Namen Ihrer Wahl.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.
4. Navigieren Sie zur Seite **Schlüssel und Endpunkt**, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.

## Bereitstellen eines Modells

Um die Azure OpenAI-API verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verweisen wir in unserer App auf dieses Modell.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Erkunden**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungsname**: text-turbo

> **Hinweis**: Jedes Azure OpenAI-Modell ist für ein anderes Verhältnis von Funktionen und Leistung optimiert. In dieser Übung verwenden wir die Modellreihe **3.5 Turbo** in der Modellfamilie **GPT-3**, die für das Sprachverständnis sehr gut geeignet ist. In dieser Übung wird nur ein einzelnes Modell verwendet. Die Bereitstellung und Verwendung anderer von Ihnen bereitgestellter Modelle funktionieren jedoch auf die gleiche Weise.

## Einrichten einer Anwendung in Cloud Shell

Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird. Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.

1. Klicken Sie im [Azure-Portal](https://portal.azure.com?azure-portal=true) oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche **[>_]** (*Cloud Shell*). Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.

    ![Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld](../media/cloudshell-launch-portal.png#lightbox)

2. Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (*Bash* oder *PowerShell*). Wählen Sie **Bash** aus. Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.  

3. Wenn Sie aufgefordert werden, Speicher für Cloud Shell zu erstellen, überprüfen Sie, ob Ihr Abonnement korrekt angegeben ist, und klicken Sie auf **Speicher erstellen**. Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.

4. Vergewissern Sie sich, dass links oben im Cloud Shell-Bereich der Shelltyp auf *Bash* umgestellt wurde. Sollte *PowerShell* angezeigt werden, wechseln Sie über das Dropdownmenü zu *Bash*.

5. Sobald das Terminal gestartet ist, geben Sie den folgenden Befehl ein, um die Beispielanwendung herunterzuladen und in einem Ordner namens `azure-openai` zu speichern.

    ```bash
   rm -r azure-openai -f
   git clone https://github.com/MicrosoftLearning/mslearn-openai azure-openai
    ```
  
6. Die Dateien werden in einen Ordner namens **azure-openai** heruntergeladen. Navigieren Sie mit dem folgenden Befehl zu den Labdateien für diese Übung.

    ```bash
   cd azure-openai/Labfiles/02-nlp-azure-openai
    ```

Es werden Anwendungen für C# und Python bereitgestellt sowie eine Beispieltextdatei, mit der Sie die Zusammenfassung testen können. Beide Apps verfügen über die gleiche Funktionalität.

Öffnen Sie den integrierten Code-Editor, und beachten Sie die Textdatei, die Sie mit Ihrem Modell zusammenfassen werden, die sich unter `text-files/sample-text.txt` befindet. Verwenden Sie den folgenden Befehl, um die Labdateien im Code-Editor zu öffnen.

```bash
code .
```

## Konfigurieren der Anwendung

In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren.

1. Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner **CSharp** oder **Python**.

2. Öffnen der Konfigurationsdatei für Ihre Sprache

    - C#: `appsettings.json`
    - Python: `.env`
    
3. Aktualisieren Sie die Konfigurationswerte so, dass sie den **Endpunkt** und **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen enthalten (`text-turbo`). Speichern Sie die Datei .

4. Navigieren zum Ordner für Ihre bevorzugte Sprache und Installieren der benötigten Pakete

    **C#**

    ```bash
   cd CSharp
   dotnet add package Azure.AI.OpenAI --prerelease
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

5. Öffnen Sie den Anwendungscode für Ihre Sprache, und fügen Sie den erforderlichen Code für die Erstellung der Anforderung hinzu, in dem die verschiedenen Parameter für Ihr Modell wie `prompt` und `temperature` angegeben sind.

    **C#**

    ```csharp
   // Initialize the Azure OpenAI client
   OpenAIClient client = new OpenAIClient(new Uri(oaiEndpoint), new AzureKeyCredential(oaiKey));

   // Build completion options object
   ChatCompletionsOptions chatCompletionsOptions = new ChatCompletionsOptions()
   {
       Messages =
       {
          new ChatMessage(ChatRole.System, "You are a helpful assistant. Summarize the following text in 60 words or less."),
          new ChatMessage(ChatRole.User, text),
       },
       MaxTokens = 120,
       Temperature = 0.7f,
   };

   // Send request to Azure OpenAI model
   ChatCompletions response = client.GetChatCompletions(
       deploymentOrModelName: oaiModelName, 
       chatCompletionsOptions);
   string completion = response.Choices[0].Message.Content;

   Console.WriteLine("Summary: " + completion + "\n");
    ```

    **Python**

    ```python
   # Set OpenAI configuration settings
   openai.api_type = "azure"
   openai.api_base = azure_oai_endpoint
   openai.api_version = "2023-03-15-preview"
   openai.api_key = azure_oai_key

   # Send request to Azure OpenAI model
   print("Sending request for summary to Azure OpenAI endpoint...\n\n")
   response = openai.ChatCompletion.create(
       engine=azure_oai_model,
       temperature=0.7,
       max_tokens=120,
       messages=[
          {"role": "system", "content": "You are a helpful assistant. Summarize the following text in 60 words or less."},
           {"role": "user", "content": text}
       ]
   )

   print("Summary: " + response.choices[0].message.content + "\n")
    ```

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten.

1. Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.
1. Führen Sie die Anwendung aus.

    - **C#** : `dotnet run`
    - **Python**: `python test-openai-model.py`

1. Sehen Sie sich die Zusammenfassung der Beispieltextdatei an.
1. Navigieren Sie zu Ihrer Codedatei für Ihre bevorzugte Sprache, und ändern Sie den *Temperaturwert* in `1`. Speichern Sie die Datei .
1. Führen Sie die Anwendung erneut aus, und sehen Sie sich die Ausgabe an.

Eine Erhöhung der Temperatur führt häufig dazu, dass die Zusammenfassung variiert, selbst wenn der gleiche Text bereitgestellt wird, was auf die erhöhte Zufälligkeit zurückzuführen ist. Sie können sie mehrmals ausführen, um zu sehen, wie sich die Ausgabe ändern kann. Versuchen Sie, verschiedene Werte für Ihre Temperatur mit derselben Eingabe zu verwenden.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im [Azure-Portal](https://portal.azure.com?azure-portal=true) zu löschen.
