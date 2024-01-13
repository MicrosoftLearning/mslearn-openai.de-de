---
lab:
  title: Verwenden Ihrer eigenen Daten mit Azure OpenAI
---

# Verwenden Ihrer eigenen Daten mit Azure OpenAI

Mit Azure OpenAI Service können Sie Ihre eigenen Daten mit der Intelligenz der zugrunde liegenden Large Language Models (LLMs) verwenden. Sie können das Modell so einschränken, dass Ihre Daten nur für relevante Themen verwendet werden, oder Sie können sie mit Ergebnissen aus dem vortrainierten Modell kombinieren.

Diese Übung dauert ungefähr **20** Minuten.

## Vorbereitung

Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde. 

- Besuchen Sie [https://azure.microsoft.com/free](https://azure.microsoft.com/free), um sich für ein kostenloses Azure-Abonnement zu registrieren.
- Informationen zum Anfordern des Zugriffs auf Azure OpenAI Service finden Sie unter [https://aka.ms/oaiapply](https://aka.ms/oaiapply).

## Bereitstellen einer Azure OpenAI-Ressource

Bevor Sie Azure OpenAI-Modelle verwenden können, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen.

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com?azure-portal=true) an.
2. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement**: Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde.
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits vorhandene Ressourcengruppe, oder erstellen Sie eine Ressourcengruppe mit einem beliebigen Namen.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Um mit der Azure OpenAI-API-Instanz chatten zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verwenden wir das Modell mit dem Playground. Zudem verwenden wir unsere Daten, um eine Basis für die Antworten zu schaffen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) navigieren.
2. Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite **Bereitstellungen**. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo-16k
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Ein eindeutiger Name Ihrer Wahl*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

> **Hinweis**: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option **Modellversion** nicht an. Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen

## Beobachten des normalen Chatverhaltens ohne Hinzufügen eigener Daten

Bevor Sie Azure OpenAI mit Ihren Daten verknüpfen, sollten Sie zunächst beobachten, wie das Basismodell auf Abfragen ohne Basisdaten reagiert.

1. Navigieren Sie zum **Chat**-Playground, und stellen Sie sicher, dass das von Ihnen bereitgestellte Modell im Bereich **Konfiguration** ausgewählt ist (dies sollte die Standardeinstellung sein, wenn Sie nur über ein einziges bereitgestelltes Modell verfügen).
1. Geben Sie die folgenden Eingabeaufforderungen ein, und beobachten Sie die Ausgabe.

    ```code
    I'd like to take a trip to New York. Where should I stay?
    ```

    ```code
    What are some facts about New York?
    ```

1. Probieren Sie ähnliche Fragen zu Tourismus und Aufenthaltsmöglichkeiten für andere Orte aus, die in unseren Basisdaten enthalten sind, z. B. London oder San Francisco. Es werden wahrscheinlich vollständige Antworten zu Gebieten oder Stadtvierteln sowie allgemeine Fakten über die Stadt zurückgegeben.

## Verknüpfen Ihrer Daten im Chat-Playground

Fügen Sie als Nächstes Ihre Daten im Chat-Playground hinzu, um zu sehen, wie er mit Ihren Daten als Basis reagiert.

1. Laden Sie die Daten, die Sie verwenden werden, [von GitHub herunter](https://aka.ms/own-data-brochures). Extrahieren Sie die PDF-Dateien im bereitgestellten `.zip`-Ordner.
1. Navigieren Sie zum **Chat**-Playground, und wählen Sie im Bereich für die Assistenteneinrichtung die Option *Daten hinzufügen* aus.
1. Wählen Sie **Datenquelle hinzufügen** und dann *Dateien hochladen* aus der Dropdownliste aus.
1. Sie müssen ein Speicherkonto und eine Azure KI Search-Ressource erstellen. Wählen Sie in der Dropdownliste für die Speicherressource die Option **Neue Azure Blob Storage-Ressource erstellen** aus, und erstellen Sie ein Speicherkonto mit den folgenden Einstellungen. Alles, was nicht angegeben ist, wird als Standard beibehalten.

    - **Abonnement**: *Dasselbe Abonnement wie Ihre Azure OpenAI-Ressource*
    - **Ressourcengruppe**: *Dieselbe Ressourcengruppe wie Ihre Azure OpenAI-Ressource*
    - **Speicherkontoname**: *Geben Sie einen global eindeutigen Namen ein*.
    - **Region**: *Dieselbe Region wie Ihre Azure OpenAI-Ressource*
    - **Redundanz**: Lokal redundanter Speicher (LRS)

1. Kehren Sie nach der Erstellung der Ressource zu Azure OpenAI Studio zurück, und wählen Sie **Neue Azure AI Search-Ressource erstellen** mit den folgenden Einstellungen. Alles, was nicht angegeben ist, wird als Standard beibehalten.

    - **Abonnement**: *Dasselbe Abonnement wie Ihre Azure OpenAI-Ressource*
    - **Ressourcengruppe**: *Dieselbe Ressourcengruppe wie Ihre Azure OpenAI-Ressource*
    - **Dienstname**: *Geben Sie einen global eindeutigen Namen ein.*
    - **Standort**: *Derselbe Standort wie Ihre Azure OpenAI-Ressource*
    - **Tarif**: Basic

1. Warten Sie, bis Ihre Suchressource bereitgestellt wurde, wechseln Sie dann zurück zu Azure AI Studio, und aktualisieren Sie die Seite.
1. Geben Sie im Fenster **Daten hinzufügen** die folgenden Werte für Ihre Datenquelle ein und wählen Sie dann **Weiter**.

    - **Datenquelle auswählen**: Laden Sie Dateien hoch.
    - **Azure Blob Storage-Ressource auswählen:** *Wählen Sie die Speicherressource aus, die Sie erstellt haben.*
        - Aktivieren Sie CORS, wenn Sie dazu aufgefordert werden.
    - **Azure AI Search-Ressource auswählen:***Wählen Sie die von Ihnen erstellte Suchressource aus.*
    - **Indexnamen eingeben:** margiestravel
    - **Hinzufügen der Vektorsuche zu dieser Suchressource**: deaktiviert
    - **Ich verstehe, dass die Verbindung zu einem Azure AI Search-Konto eine Nutzung meines Kontos zur Folge hat**: aktiviert

1. Laden Sie auf der Seite **Dateien hochladen** die PDFs hoch, die Sie heruntergeladen haben, und wählen Sie dann **Weiter**.
1. Wählen Sie auf der Seite **Datenverwaltung** den Suchtyp **Schlüsselwort** aus der Dropdown-Liste und wählen Sie dann **Weiter**.
1. Wählen Sie auf der Seite **Überprüfen und beenden** die Option **Speichern und schließen**, um Ihre Daten hinzuzufügen. Dieser Vorgang kann einige Minuten in Anspruch nehmen. Schließen Sie das Fenster in diesem Zeitraum nicht. Nach Abschluss des Vorgangs werden die Datenquelle, die Suchressource und der Index angezeigt, die im **Setupbereich des Assistenten** angegeben sind.

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

Erfahren Sie als nächstes, wie Sie Ihre App mit Ihren eigenen Daten verbinden.

### Einrichten einer Anwendung in Cloud Shell

Zur Demonstration, wie Sie eine Azure OpenAI-App mit Ihren eigenen Daten verbinden, verwenden wir eine kurze Befehlszeilenanwendung in Azure Cloud Shell. Öffnen Sie eine neue Browserregisterkarte, um mit Cloud Shell zu arbeiten.

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
    cd azure-openai/Labfiles/06-use-own-data
    ```

7. Öffnen Sie den integrierten Code-Editor, indem Sie den folgenden Befehl ausführen:

    ```bash
    code .
    ```

    > **Hinweis**: Weitere Informationen zur Verwendung von Dateien in der Azure Cloud Shell-Umgebung finden Sie in der [Dokumentation für den Azure Cloud Shell-Code-Editor](https://learn.microsoft.com/azure/cloud-shell/using-cloud-shell-editor).

## Konfigurieren der Anwendung

In dieser Übung absolvieren Sie einige wichtige Teile der Anwendung, um die Verwendung Ihrer Azure OpenAI-Ressource zu aktivieren. Anwendungen für C# und Python wurden bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität.

1. Erweitern Sie im Code-Editor je nach Spracheinstellung den Ordner **CSharp** oder **Python**.

2. Öffnen Sie die Konfigurationsdatei für Ihre Sprache.

    - C#: `appsettings.json`
    - Python: `.env`
    
3. Aktualisieren Sie die Konfigurationswerte, um Folgendes einzuschließen:
    - Den **Endpunkt** und einen **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
    - Den Namen, den Sie für Ihre Modellbereitstellung angegeben haben (verfügbar auf der Seite **Bereitstellungen** in Azure OpenAI Studio).
    - Den Endpunkt für Ihren Suchdienst (der **URL**-Wert auf der Übersichtsseite Ihrer Search-Ressource im Azure-Portal).
    - Einen **Schlüssel** für Ihre Search-Ressource (verfügbar auf der Seite **Schlüssel** Ihrer Search-Ressource im Azure-Portal – Sie können einen der Administratorschlüssel verwenden).
    - Den Namen des Suchindexes (sollte `margiestravel` sein).
    
4. Speichern Sie die aktualisierte Konfigurationsdatei.

5. Geben Sie im Konsolenbereich die folgenden Befehle ein, um zum Ordner für Ihre bevorzugte Sprache zu navigieren und die erforderlichen Pakete zu installieren.

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

6. Navigieren Sie im Code-Editor zum Ordner Ihrer bevorzugten Sprache, wählen Sie die Codedatei aus und fügen Sie die erforderlichen Bibliotheken hinzu.

    **C#**: OwnData.cs

    ```csharp
    // Add Azure OpenAI package
    using Azure.AI.OpenAI;
    ```

    **Python**: ownData.py

    ```python
    # Add OpenAI import
    from openai import AzureOpenAI
    ```

7. Überprüfen Sie die Codedatei, insbesondere die Stelle, an der die Suchwerte bei der Angabe der Parameter für den API-Aufruf verwendet werden.

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Ihre Anforderung an Ihr Modell zu senden und die Antwort zu erhalten. Wie Sie feststellen werden, basiert die Antwort jetzt auf Ihren Daten, ähnlich wie in Studio.

1. Navigieren Sie im Cloud Shell-Bash-Terminal zum Ordner für Ihre bevorzugte Sprache.
1. Erweitern Sie das Terminal so, dass es den größten Teil Ihres Browserfensters einnimmt, und starten Sie die Anwendung.

    - **C#** : `dotnet run`
    - **Python**: `python ownData.py`

1. Übermitteln Sie die Eingabeaufforderung `Tell me about London`. Sie sollten nun eine Antwort erhalten, die sich auf Ihre Daten bezieht.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen. Stellen Sie sicher, dass Sie auch das Speicherkonto und die Suchressource einschließen, da für diese relativ hohe Kosten entstehen können.
