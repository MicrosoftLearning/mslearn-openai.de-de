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
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits bestehende Ressourcengruppe, oder erstellen Sie eine neue Ressourcengruppe mit einem beliebigen Namen.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.
4. Navigieren Sie zur Seite **Schlüssel und Endpunkt**, und speichern Sie diese in einer Textdatei, die Sie später verwenden können.

## Bereitstellen eines Modells

Um die Azure OpenAI-API verwenden zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verweisen wir in unserer App auf dieses Modell.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Erkunden**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite **Bereitstellungen**. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo-16k
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Wählen Sie einen Namen Ihrer Wahl aus*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

> **Hinweis**: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option **Modellversion** nicht an. Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen

## Einrichten einer Anwendung in Cloud Shell

Um die Integration mit einem Azure OpenAI-Modell zu zeigen, verwenden wir eine kurze Befehlszeilenanwendung, die in Cloud Shell in Azure ausgeführt wird. Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.

1. Klicken Sie im [Azure-Portal](https://portal.azure.com?azure-portal=true) oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche **[>_]** (*Cloud Shell*). Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet.

    ![Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld](../media/cloudshell-launch-portal.png#lightbox)

2. Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (*Bash* oder *PowerShell*). Wählen Sie **Bash** aus. Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.  

3. Wenn Sie aufgefordert werden, Speicher für Ihre Cloud Shell zu erstellen, wählen Sie **Erweiterte Einstellungen anzeigen** und dann die folgenden Einstellungen aus:
    - **Abonnement**: Ihr Abonnement
    - **Cloud Shell-Regionen**: Wählen Sie eine beliebige verfügbare Region
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
   cd azure-openai/Labfiles/02-nlp-azure-openai
    ```

7. Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:

    ```bash
    code .
    ```

8. Erweitern Sie im Code-Editor den Ordner **Textdateien** und wählen Sie **Beispieltext.txt** aus, um den Text zu sehen, den Ihr Modell zusammenfasst.

    > **Hinweis**: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der [Dokumentation für den Azure Cloud Shell-Code-Editor](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor).

## Konfigurieren der Anwendung

In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren. Anwendungen für C# und Python wurden bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität.

1. Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner **CSharp** oder **Python**.

2. Öffnen der Konfigurationsdatei für Ihre Sprache

    - C#: `appsettings.json`
    - Python: `.env`
    
3. Aktualisieren Sie die Konfigurationswerte, um den **Endpunkt** und den **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource sowie den von Ihnen bereitgestellten Modellnamen hinzuzufügen. Speichern Sie die Datei .

4. Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.

    **C#**

    ```bash
   cd CSharp
   dotnet add package Azure.AI.OpenAI --version 1.0.0-beta.9
    ```

    **Python**

    ```bash
    cd Python
    pip install python-dotenv
    pip install openai==1.2.0
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
    from openai import AzureOpenAI
    ```

6. Öffnen Sie den Anwendungscode für Ihre Sprache, und fügen Sie den erforderlichen Code für die Erstellung der Anforderung hinzu, in dem die verschiedenen Parameter für Ihr Modell wie `prompt` und `temperature` angegeben sind.

    **C#**

    ```csharp
    // Initialize the Azure OpenAI client
    OpenAIClient client = new OpenAIClient(new Uri(oaiEndpoint), new AzureKeyCredential(oaiKey));
    
    // Build completion options object
    ChatCompletionsOptions chatCompletionsOptions = new ChatCompletionsOptions()
    {
        Messages =
        {
            new ChatMessage(ChatRole.System, "You are a helpful assistant."),
            new ChatMessage(ChatRole.User, "Summarize the following text in 20 words or less:\n" + text),
        },
        MaxTokens = 120,
        Temperature = 0.7f,
        DeploymentName = oaiModelName
    };
    
    // Send request to Azure OpenAI model
    ChatCompletions response = client.GetChatCompletions(chatCompletionsOptions);
    string completion = response.Choices[0].Message.Content;
    
    Console.WriteLine("Summary: " + completion + "\n");
    ```

    **Python**

    ```python
    # Initialize the Azure OpenAI client
    client = AzureOpenAI(
            azure_endpoint = azure_oai_endpoint, 
            api_key=azure_oai_key,  
            api_version="2023-05-15"
            )
    
    # Send request to Azure OpenAI model
    response = client.chat.completions.create(
        model=azure_oai_model,
        temperature=0.7,
        max_tokens=120,
        messages=[
            {"role": "system", "content": "You are a helpful assistant."},
            {"role": "user", "content": "Summarize the following text in 20 words or less:\n" + text}
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
