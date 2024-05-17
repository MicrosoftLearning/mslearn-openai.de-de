---
lab:
  title: Implementieren von Retrieval Augmented Generation (RAG) mit Azure OpenAI Service
---

# Implementieren von Retrieval Augmented Generation (RAG) mit Azure OpenAI Service

Mit Azure OpenAI Service können Sie Ihre eigenen Daten mit der Intelligenz der zugrunde liegenden Large Language Models (LLMs) verwenden. Sie können das Modell so einschränken, dass Ihre Daten nur für relevante Themen verwendet werden, oder Sie können sie mit Ergebnissen aus dem vortrainierten Modell kombinieren.

Im Szenario für diese Übung sind Sie ein Softwareentwickler, der für Marias Reisebüro arbeitet. Sie erfahren, wie Sie generative KI verwenden, um Programmieraufgaben einfacher und effizienter zu gestalten. Die in der Übung verwendeten Techniken können auch für andere Codedateien, Programmiersprachen und Anwendungsfälle genutzt werden.

Diese Übung dauert ungefähr **20** Minuten.

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
    - **Modell**: gpt-35-turbo-16k *Es muss dieses Modell sein, um die Features in dieser Übung verwenden zu können.*
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Wählen Sie einen Namen für Ihre Wahl aus. Sie verwenden diesen Namen später im Lab.*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Bereitstellungstyp**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Beobachten des normalen Chatverhaltens ohne Hinzufügen eigener Daten

Bevor Sie Azure OpenAI mit Ihren Daten verknüpfen, sollten Sie zunächst herausfinden, wie das Basismodell auf Abfragen ohne Groundingdaten reagiert.

1. Wählen Sie in **Azure OpenAI Studio** unter `https://oai.azure.com` im Abschnitt **Playground** die Seite **Chat** aus. Die Playground-Seite **Chat** besteht aus drei Hauptabschnitten:
    - **Setup**: wird zum Festlegen des Kontexts für die Antworten des Modells verwendet
    - **Chatsitzung**: wird zum Senden von Chat-Nachrichten und Ansehen von Antworten verwendet
    - **Konfiguration**: wird zum Konfigurieren von Einstellungen für die Modellbereitstellung verwendet
2. Stellen Sie im Bereich **Konfiguration** sicher, dass Ihre Modellbereitstellung ausgewählt ist.
3. Wählen Sie im Bereich **Setup** die Standardvorlage für Systemnachrichten aus, um den Kontext für die Chatsitzung festzulegen. Die Standardsystemnachricht lautet *Sie sind ein KI-Assistent, der Personen hilft, Informationen zu finden*.
4. Senden Sie in der **Chatsitzung** die folgenden Abfragen, und überprüfen Sie die Antworten:

    ```
    I'd like to take a trip to New York. Where should I stay?
    ```

    ```
    What are some facts about New York?
    ```

    Probieren Sie ähnliche Fragen zu Tourismus und Aufenthaltsmöglichkeiten für andere Orte aus, die in unseren Basisdaten enthalten sind, z. B. London oder San Francisco. Es werden wahrscheinlich vollständige Antworten zu Gebieten oder Stadtvierteln sowie allgemeine Fakten über die Stadt zurückgegeben.

## Verknüpfen Ihrer Daten im Chat-Playground

Jetzt fügen Sie Daten für ein fiktives Reisebüro namens *Marias Reisebüro* hinzu. Dann sehen Sie, wie das Azure OpenAI-Modell reagiert, wenn Sie die Broschüren von Marias Reisebüro als Groundingdaten verwenden.

1. Laden Sie auf einer neuen Browserregisterkarte ein Archiv mit Broschürendaten von `https://aka.ms/own-data-brochures` herunter. Extrahieren Sie die Broschüren in einen Ordner auf Ihrem PC.
1. Wählen Sie in Azure OpenAI Studio im **Chat**-Playground im Abschnitt **Setup** **Ihre Daten hinzufügen** aus.
1. Wählen Sie **Datenquelle hinzufügen** und dann **Datei hochladen** aus.
1. Sie müssen ein Speicherkonto und eine Azure KI Search-Ressource erstellen. Wählen Sie in der Dropdownliste für die Speicherressource die Option **Neue Azure Blob Storage-Ressource erstellen** aus, und erstellen Sie ein Speicherkonto mit den folgenden Einstellungen. Alles, was nicht angegeben ist, wird als Standard beibehalten.

    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe:** *Wählen Sie dieselbe Ressourcengruppe aus wie für Ihre Azure OpenAI-Ressource.*
    - **Speicherkontoname:** *Geben Sie einen eindeutigen Namen ein.*
    - **Region:** *Wählen Sie dieselbe Region aus wie für Ihre Azure OpenAI-Ressource.*
    - **Redundanz**: Lokal redundanter Speicher (LRS)

1. Kehren Sie während der Erstellung der Speicherkontoressource zu Azure OpenAI Studio zurück, und wählen Sie **Neue Ressource für Azure KI-Suche erstellen** mit den folgenden Einstellungen aus. Alles, was nicht angegeben ist, wird als Standard beibehalten.

    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe:** *Wählen Sie dieselbe Ressourcengruppe aus wie für Ihre Azure OpenAI-Ressource.*
    - **Dienstname:** *Geben Sie einen eindeutigen Namen ein.*
    - **Speicherort:** *Wählen Sie denselben Speicherort wie Ihre Azure OpenAI-Ressource aus.*
    - **Tarif**: Basic

1. Warten Sie, bis Ihre Suchressource bereitgestellt wurde, und wechseln Sie dann zurück zu Azure KI Studio.
1. Geben Sie im Fenster **Daten hinzufügen** die folgenden Werte für Ihre Datenquelle ein und wählen Sie dann **Weiter**.

    - **Datenquelle auswählen**: Laden Sie Dateien hoch.
    - **Abonnement**: Ihr Azure-Abonnement
    - **Wählen Sie eine Azure Blob-Speicherressource aus**: *Verwenden Sie die Schaltfläche **Aktualisieren**, um die Liste erneut aufzufüllen, und wählen Sie dann die Speicherressource aus, die Sie erstellt haben.*
        - Aktivieren Sie CORS, wenn Sie dazu aufgefordert werden.
    - **Wählen Sie eine Ressource für Azure KI-Suche aus**: *Verwenden Sie die Schaltfläche **Aktualisieren**, um die Liste erneut aufzufüllen, und wählen Sie dann die Suchressource aus, die Sie erstellt haben.*
    - **Geben Sie den Indexnamen ein**: `margiestravel`
    - **Hinzufügen der Vektorsuche zu dieser Suchressource**: deaktiviert
    - **Ich verstehe, dass die Verbindung zu einem Azure AI Search-Konto eine Nutzung meines Kontos zur Folge hat**: aktiviert

1. Laden Sie auf der Seite **Dateien hochladen** die PDFs hoch, die Sie heruntergeladen haben, und wählen Sie dann **Weiter**.
1. Wählen Sie auf der Seite **Datenverwaltung** den Suchtyp **Schlüsselwort** aus der Dropdown-Liste und wählen Sie dann **Weiter**.
1. Wählen Sie auf der Seite **Überprüfen und beenden** die Option **Speichern und schließen**, um Ihre Daten hinzuzufügen. Dieser Vorgang kann einige Minuten in Anspruch nehmen. Schließen Sie das Fenster in diesem Zeitraum nicht. Nach Abschluss des Vorgangs werden die Datenquelle, die Suchressource und der Index angezeigt, die im **Setup**-Bereich angegeben wurden.

    > **Tipp**: Gelegentlich dauert es zu lange, die Verbindung zwischen Ihrem neuen Suchindex und Azure OpenAI Studio herzustellen. Wenn Sie einige Minuten gewartet haben und die Verbindung noch nicht hergestellt wurde, überprüfen Sie Ihre KI-Suche-Ressourcen im Azure-Portal. Wenn der fertige Index angezeigt wird, können Sie die Datenverbindung in Azure OpenAI Studio trennen und erneut hinzufügen, indem Sie eine Datenquelle für Azure KI-Suche angeben und ihren neuen Index auswählen.

## Chatten mit einem Modell, das auf Ihren Daten begründet ist

Nachdem Sie Ihre Daten hinzugefügt haben, stellen Sie die gleichen Fragen wie zuvor, und beobachten Sie, wie sich die Daten verändern.

```
I'd like to take a trip to New York. Where should I stay?
```

```
What are some facts about New York?
```

Dieses Mal wird eine vollkommen andere Antwort angezeigt. Diese enthält Informationen zu bestimmten Hotels und Margie‘s Travel sowie Referenzen zur Quelle der bereitgestellten Informationen. Wenn Sie die in der Antwort aufgeführte PDF-Referenzdatei öffnen, werden dieselben Hotels wie im bereitgestellten Modell angezeigt.

Stellen Sie vielleicht Fragen zu anderen Städten, die in der Basisdatei enthalten sind, etwa zu Dubai, Las Vegas, London und San Francisco.

> **Hinweis:** Die Option **Daten hinzufügen** befindet sich noch in der Vorschauphase und verhält sich für dieses Feature möglicherweise nicht immer wie erwartet. Es werden beispielsweise falsche Referenzen für eine Stadt angegeben, die nicht in den Basisdaten enthalten ist.

## Verbinden Ihrer App mit Ihren eigenen Daten

Als Nächstes erfahren Sie, wie Sie Ihre App verknüpfen, um Ihre eigenen Daten zu verwenden.

### Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sehen Sie sich nun das Nutzen Ihrer eigenen Daten in einer App an, die das Azure OpenAI-Dienst-SDK verwendet. Sie entwickeln Ihre App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P), und führen Sie einen **Git: Clone**-Befehl aus, um das Repository `https://github.com/MicrosoftLearning/mslearn-openai` in einen lokalen Ordner zu klonen (der Ordner ist beliebig).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

## Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt, und beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource nutzen zu können.

1. Wechseln Sie in Visual Studio Code im **Explorer**-Bereich zum Ordner **Labfiles/06-use-own-data**, und erweitern Sie je nach Ihrer bevorzugten Sprache den Ordner **CSharp** oder **Python**. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, mit der Sie Azure OpenAI-Funktionen integrieren.
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
    - Den Endpunkt für Ihren Suchdienst (der **URL**-Wert auf der Übersichtsseite Ihrer Search-Ressource im Azure-Portal).
    - Einen **Schlüssel** für Ihre Search-Ressource (verfügbar auf der Seite **Schlüssel** Ihrer Search-Ressource im Azure-Portal – Sie können einen der Administratorschlüssel verwenden).
    - Den Namen des Suchindexes (sollte `margiestravel` sein).
1. Speichern Sie die Konfigurationsdatei.

### Hinzufügen von Code zum Verwenden des Azure OpenAI-Diensts

Jetzt können Sie das Azure OpenAI-SDK verwenden, um Ihr bereitgestelltes Modell zu nutzen.

1. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Codedatei für Ihre bevorzugte Sprache, und ersetzen Sie den Kommentar ***Konfigurieren Ihrer Datenquelle*** durch Code, um die Azure OpenAI-SDK-Bibliothek hinzuzufügen:

    **C#**: ownData.cs

    ```csharp
    // Configure your data source
    AzureSearchChatExtensionConfiguration ownDataConfig = new()
    {
            SearchEndpoint = new Uri(azureSearchEndpoint),
            Authentication = new OnYourDataApiKeyAuthenticationOptions(azureSearchKey),
            IndexName = azureSearchIndex
    };
    ```

    **Python**: ownData.py

    ```python
    # Configure your data source
    extension_config = dict(dataSources = [  
            { 
                "type": "AzureCognitiveSearch", 
                "parameters": { 
                    "endpoint":azure_search_endpoint, 
                    "key": azure_search_key, 
                    "indexName": azure_search_index,
                }
            }]
        )
    ```

2. Überprüfen Sie den Rest des Codes, und notieren Sie die Verwendung der *Erweiterungen* im Anforderungstext, der zum Bereitstellen von Informationen zu den Datenquelleneinstellungen verwendet wird.

3. Speichern Sie die Änderungen in der Codedatei.

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten. Sie werden feststellen, dass der einzige Unterschied zwischen den verschiedenen Optionen der Inhalt der Eingabeaufforderung ist. Alle anderen Parameter (z. B. Tokenanzahl und Temperatur) bleiben für jede Anforderung gleich.

1. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python ownData.py`

    > **Tipp**: Sie können das Symbol **Maximize panel size** (Panelgröße maximieren) (**^**) in der Terminalsymbolleiste verwenden, um mehr des Konsolentexts anzuzeigen.

2. Überprüfen Sie die Antwort auf die Eingabeaufforderung `Tell me about London`, die eine Antwort sowie Details zu den verwendeten Daten enthalten sollte, die für das Grounding der Eingabeaufforderung verwendet wurden. Die Eingabeaufforderung wurde von Ihrem Suchdienst abgerufen.

    > **Tipp**: Wenn Sie die Zitate aus Ihrem Suchindex anzeigen möchten, legen Sie die Variable ***show citations*** am oben in der Codedatei auf **true** fest.

## Bereinigung

Wenn Sie Ihre Azure OpenAI-Ressource nicht mehr benötigen, löschen Sie die Ressource im **Azure-Portal** unter `https://portal.azure.com`. Stellen Sie sicher, dass Sie auch das Speicherkonto und die Suchressource einschließen, da für diese relativ hohe Kosten entstehen können.
