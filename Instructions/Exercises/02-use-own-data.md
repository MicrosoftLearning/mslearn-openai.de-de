---
lab:
  title: Implementieren von Retrieval Augmented Generation (RAG) mit Azure OpenAI Service
  status: new
---

# Implementieren von Retrieval Augmented Generation (RAG) mit Azure OpenAI Service

Mit Azure OpenAI Service können Sie Ihre eigenen Daten mit der Intelligenz der zugrunde liegenden Large Language Models (LLMs) verwenden. Sie können das Modell so einschränken, dass Ihre Daten nur für relevante Themen verwendet werden, oder Sie können sie mit Ergebnissen aus dem vortrainierten Modell kombinieren.

Im Szenario für diese Übung sind Sie ein Softwareentwickler, der für Marias Reisebüro arbeitet. Sie werden erfahren, wie Sie Azure AI Search zur Indexierung Ihrer eigenen Daten verwenden und diese mit Azure OpenAI zur Erweiterung von Eingabeaufforderungen nutzen können.

Diese Übung dauert ungefähr **30** Minuten.

## Bereitstellen von Azure-Ressourcen

Für diese Übung benötigen Sie Folgendes:

- Eine Azure OpenAI-Ressource
- Eine Azure KI-Suche-Ressource:
- Eine Azure-Speicherkonto-Ressource.

1. Melden Sie sich beim **Azure-Portal** unter `https://portal.azure.com` an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
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

3. Während die Azure OpenAI-Ressource bereitgestellt wird, erstellen Sie eine **Azure AI Search**-Ressource mit den folgenden Einstellungen:
    - **Abonnement**: *Das Abonnement, in dem Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Ressourcengruppe:** *Die Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Dienstname**: *Ein eindeutiger Name Ihrer Wahl*
    - **Ort**: *Die Region, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Tarif**: Basic
4. Während die Azure-KI-Suchressource bereitgestellt wird, erstellen Sie eine **Speicherkonto**-Ressource mit den folgenden Einstellungen:
    - **Abonnement**: *Das Abonnement, in dem Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Ressourcengruppe:** *Die Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Name des Speicherkontos**: *Ein eindeutiger Name Ihrer Wahl*
    - **Region**: *Die Region, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Primärer Dienst**: Azure Blob Storage oder Azure Data Lake Storage Gen 2
    - **Leistung**: Standard
    - **Redundanz**: Lokal redundanter Speicher (LRS)
5. Nachdem alle drei Ressourcen erfolgreich in Ihrem Azure-Abonnement bereitgestellt wurden, überprüfen Sie sie im Azure-Portal und sammeln Sie die folgenden Informationen (die Sie später in der Übung benötigen):
    - Den **Endpunkt** und einen **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
    - Der Endpunkt für Ihren Azure KI-Suchdienst (der **URL**-Wert auf der Übersichtsseite für Ihre Azure KI-Suche-Ressource im Azure-Portal).
    - Ein **primärer Administrationsschlüssel** für Ihre Azure AI Search-Ressource (verfügbar auf der Seite "**Schlüssel"** für Ihre Azure AI Search-Ressource im Azure-Portal).

## Hochladen Ihrer Daten

Sie werden die von Ihnen verwendeten Eingabeaufforderungen mit einem generativen KI-Modell verknüpfen, indem Sie Ihre eigenen Daten verwenden. In dieser Übung bestehen die Daten aus einer Sammlung von Reisekatalogen des fiktiven Unternehmens *Margies Travel*.

1. Laden Sie auf einer neuen Browserregisterkarte ein Archiv mit Broschürendaten von `https://aka.ms/own-data-brochures` herunter. Extrahieren Sie die Broschüren in einen Ordner auf Ihrem PC.
1. Navigieren Sie im Azure-Portal zu Ihrem Speicherkonto und rufen Sie die Seite "**Speicherbrowser"** auf.
1. Wählen Sie **Blob-Container** aus und fügen Sie dann einen neuen Container mit dem Namen `margies-travel` hinzu.
1. Wählen Sie den Container **margies-travel** aus und laden Sie dann die zuvor extrahierten PDF-Broschüren in den Stammordner des Blob-Containers hoch.

## KI-Modelle bereitstellen

In dieser Übung werden Sie zwei KI-Modelle verwenden:

- Ein Text-Einbettungsmodell zur *Vektorisierung* des Textes in den Broschüren, damit dieser effizient für die Verwendung in Eingabeaufforderungen indiziert werden kann.
- Ein GPT-Modell, das Ihre Anwendung verwenden kann, um Antworten auf Eingabeaufforderungen zu generieren, die auf Ihren Daten basieren.

## Bereitstellen eines Modells

Als Nächstes stellen Sie eine Azure OpenAI-Modellressource aus der CLI bereit. Wählen Sie im Azure-Portal das Symbol **Cloud Shell** in der oberen Menüleiste aus und stellen Sie sicher, dass Ihr Terminal auf **Bash** eingestellt ist. Ersetzen Sie in diesem Beispiel die folgenden Variablen durch Ihre eigenen Werte:

```dotnetcli
az cognitiveservices account deployment create \
   -g <your_resource_group> \
   -n <your_OpenAI_resource> \
   --deployment-name text-embedding-ada-002 \
   --model-name text-embedding-ada-002 \
   --model-version "2"  \
   --model-format OpenAI \
   --sku-name "Standard" \
   --sku-capacity 5
```

> **Hinweis:** Die Sku-Kapazität wird in Tausend Token pro Minute gemessen. Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

Nachdem das Text-Einbettungsmodell bereitgestellt wurde, erstellen Sie eine neue Bereitstellung des **gpt-4o**-Modells mit den folgenden Einstellungen:

```dotnetcli
az cognitiveservices account deployment create \
   -g <your_resource_group> \
   -n <your_OpenAI_resource> \
   --deployment-name gpt-4o \
   --model-name gpt-4o \
   --model-version "2024-05-13" \
   --model-format OpenAI \
   --sku-name "Standard" \
   --sku-capacity 5
```

## Erstellen eines Index

Um die Verwendung Ihrer eigenen Daten in einer Eingabeaufforderung einfach zu machen, indizieren Sie sie mit Azure AI Search. Sie verwenden das Texteinbettungsmodell, um die Textdaten zu *vektorisieren* (was dazu führt, dass jedes Text-Token im Index durch numerische Vektoren dargestellt wird – wodurch es mit der Art und Weise kompatibel ist, wie ein generatives KI-Modell Text darstellt).

1. Navigieren Sie im Azure-Portal zu Ihrer Azure AI Search-Ressource.
1. Wählen Sie auf der Seite **Übersicht** die Option **Importieren und Vektorisieren von Daten** aus.
1. Wählen Sie auf der Seite "**Einrichten Ihrer Datenverbindung**" die Option "**Azure Blob Storage**" aus und legen Sie die folgenden Einstellungen für die Datenquelle fest:
    - **Abonnement**: Das Azure-Abonnement, in dem Sie Ihr Speicherkonto bereitgestellt haben.
    - **Blob-Speicherkonto**: Das Speicherkonto, das Sie zuvor erstellt haben.
    - **Blob container**: margies-travel
    - **Blob-Ordner**: *Leer lassen*
    - **Löschverfolgung aktivieren**: Nicht ausgewählt
    - **Mit verwalteter Identität authentifizieren**: Deaktiviert
1. Wählen Sie auf der Seite "**Text vektorisieren**" die folgenden Einstellungen aus:
    - **Art**: Azure OpenAI
    - **Abonnement**: Das Azure-Abonnement, in dem Sie Ihren Azure OpenAI-Dienst bereitgestellt haben.
    - **Azure OpenAI Service**: Ihre Azure OpenAI Service-Ressource
    - **Modellbereitstellung**: text-embedding-ada-002
    - **Authentifizierungstyp**: API-Schlüssel
    - **Ich bin mir bewusst, dass durch die Verbindung mit einem Azure-OpenAI-Dienst zusätzliche Kosten für mein Konto** entstehen: Ausgewählt
1. Wählen Sie auf der nächsten Seite **nicht** die Optionen zum Vektorisieren von Bildern oder zum Extrahieren von Daten mit KI-Fähigkeiten aus.
1. Aktivieren Sie auf der nächsten Seite die semantische Rangfolge und planen Sie die einmalige Ausführung des Indexers.
1. Auf der letzten Seite legen Sie den **Objektnamen-Präfix** auf `margies-index` fest und erstellen dann den Index.

## Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sehen Sie sich nun das Nutzen Ihrer eigenen Daten in einer App an, die das Azure OpenAI-Dienst-SDK verwendet. Sie entwickeln Ihre App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P oder **Ansicht** > **Befehlspalette …**) und führen Sie den Befehl **Git: Clone** aus, um das `https://github.com/MicrosoftLearning/mslearn-openai`-Repository in einen lokalen Ordner zu klonen (es spielt keine Rolle, in welchen Ordner).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt, und beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource nutzen zu können.

1. Navigieren Sie in Visual Studio Code im Bereich **„Explorer“** zum Ordner **„Labfiles/02-use-own-data**“ und erweitern Sie den Ordner **„CSharp“** oder **„Python“**, je nachdem, welche Sprache Sie bevorzugen. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, mit der Sie Azure OpenAI-Funktionen integrieren.
2. Klicken Sie mit der rechten Maustaste auf den Ordner **CSharp** oder **Python**, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Installieren Sie dann das SDK-Paket von Azure OpenAI, indem Sie den entsprechenden Befehl für Ihre bevorzugte Sprache ausführen:

    **C#:**

    ```powershell
    dotnet add package Azure.AI.OpenAI --version 2.1.0
    dotnet add package Azure.Search.Documents --version 11.6.0
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
    - Der **Bereitstellungsname**, den Sie für Ihre gpt-4o-Modellbereitstellung angegeben haben (sollte `gpt-4o` lauten).
    - Den Endpunkt für Ihren Suchdienst (der **URL**-Wert auf der Übersichtsseite Ihrer Search-Ressource im Azure-Portal).
    - Einen **Schlüssel** für Ihre Search-Ressource (verfügbar auf der Seite **Schlüssel** Ihrer Search-Ressource im Azure-Portal – Sie können einen der Administratorschlüssel verwenden).
    - Den Namen des Suchindexes (sollte `margies-index` sein).
5. Speichern Sie die Konfigurationsdatei.

### Hinzufügen von Code zum Verwenden des Azure OpenAI-Diensts

Jetzt können Sie das Azure OpenAI-SDK verwenden, um Ihr bereitgestelltes Modell zu nutzen.

1. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Codedatei für die von Ihnen bevorzugte Sprache und ersetzen Sie den Kommentar ***Configure your data source*** mit Code zu Ihrem Index als Datenquelle für die Chatvervollständigung:

    **C#**: ownData.cs

    ```csharp
    // Configure your data source
    // Extension methods to use data sources with options are subject to SDK surface changes. Suppress the warning to acknowledge this and use the subject-to-change AddDataSource method.
    #pragma warning disable AOAI001
    
    ChatCompletionOptions chatCompletionsOptions = new ChatCompletionOptions()
    {
        MaxOutputTokenCount = 600,
        Temperature = 0.9f,
    };
    
    chatCompletionsOptions.AddDataSource(new AzureSearchChatDataSource()
    {
        Endpoint = new Uri(azureSearchEndpoint),
        IndexName = azureSearchIndex,
        Authentication = DataSourceAuthentication.FromApiKey(azureSearchKey),
    });
    ```

    **Python**: ownData.py

    ```python
    # Configure your data source
    text = input('\nEnter a question:\n')
    
    completion = client.chat.completions.create(
        model=deployment,
        messages=[
            {
                "role": "user",
                "content": text,
            },
        ],
        extra_body={
            "data_sources":[
                {
                    "type": "azure_search",
                    "parameters": {
                        "endpoint": os.environ["AZURE_SEARCH_ENDPOINT"],
                        "index_name": os.environ["AZURE_SEARCH_INDEX"],
                        "authentication": {
                            "type": "api_key",
                            "key": os.environ["AZURE_SEARCH_KEY"],
                        }
                    }
                }
            ],
        }
    )
    ```

1. Speichern Sie die Änderungen in der Codedatei.

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten. Sie werden feststellen, dass der einzige Unterschied zwischen den verschiedenen Optionen der Inhalt der Eingabeaufforderung ist. Alle anderen Parameter (z. B. Tokenanzahl und Temperatur) bleiben für jede Anforderung gleich.

1. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python ownData.py`

    > **Tipp**: Sie können das Symbol **Maximize panel size** (Panelgröße maximieren) (**^**) in der Terminalsymbolleiste verwenden, um mehr des Konsolentexts anzuzeigen.

2. Überprüfen Sie die Antwort auf die Eingabeaufforderung `Tell me about London`, die eine Antwort sowie Details zu den verwendeten Daten enthalten sollte, die für das Grounding der Eingabeaufforderung verwendet wurden. Die Eingabeaufforderung wurde von Ihrem Suchdienst abgerufen.

    > **Tipp**: Wenn Sie die Zitate aus Ihrem Suchindex anzeigen möchten, legen Sie die Variable ***show citations*** am oben in der Codedatei auf **true** fest.

## Bereinigung

Wenn Sie Ihre Azure OpenAI-Ressource nicht mehr benötigen, denken Sie daran, die Ressourcen im **Azure-Portal** unter `https://portal.azure.com` zu löschen. Stellen Sie sicher, dass Sie auch das Speicherkonto und die Suchressource einschließen, da für diese relativ hohe Kosten entstehen können.
