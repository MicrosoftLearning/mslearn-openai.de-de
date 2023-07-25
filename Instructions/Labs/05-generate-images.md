---
lab:
  title: Generieren von Bildern mit einem DALL-E-Modell
---

# Generieren von Bildern mit einem DALL-E-Modell

Der Azure OpenAI Service enthält ein Bildgenerierungsmodell mit dem Namen DALL-E. Sie können dieses Modell verwenden, um Eingabeaufforderungen in natürlicher Sprache zu übermitteln, die ein gewünschtes Bild beschreiben, und das Modell generiert ein Originalbild basierend auf der von Ihnen angegebenen Beschreibung.

Diese Übung dauert ungefähr **25** Minuten.

## Vorbereitung

Sie benötigen ein Azure-Abonnement, das für den Zugriff auf Azure OpenAI Service genehmigt wurde, einschließlich DALL-E. Wenn Sie zuvor Zugriff auf den Azure OpenAI Service beantragt haben, müssen Sie möglicherweise einen anderen Antrag stellen, um Zugriff auf DALL-E zu erhalten.

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
4. Navigieren Sie zur Seite **Schlüssel und Endpunkt**. Sie können den eindeutigen Endpunkt und die Authentifizierungsschlüssel für Ihren Dienst von hier abrufen. Sie benötigen diese später.

## Erkunden der Bildgenerierung im DALL-E-Playground

Sie können den DALL-E-Playground in **Azure OpenAI Studio** verwenden, um mit der Bildgenerierung zu experimentieren.

1. Verwenden Sie im Azure-Portal auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) navigieren.
2. Wählen Sie den **DALL-E-Playground** aus.
3. Geben Sie im Feld **Eingabeaufforderung** eine Beschreibung eines Bilds ein, das Sie generieren möchten. Beispiel: *Ein Elefant auf einem Skateboard*. Wählen Sie dann **Generieren** aus, und zeigen Sie das generierte Bild an.

    ![Der DALL-E-Playground in Azure OpenAI Studio mit einem generierten Bild.](../media/dall-e-playground.png)

4. Ändern Sie die Eingabeaufforderung, um eine spezifischere Beschreibung bereitzustellen. Zum Beispiel: *Ein Elefant auf einem Skateboard im Stil von Picasso*. Generieren Sie dann das neue Bild, und überprüfen Sie die Ergebnisse.

    ![Der DALL-E-Playground in Azure OpenAI Studio mit zwei generierten Bildern.](../media/dall-e-playground-new-image.png)

## Verwenden der REST-API zum Generieren von Bildern

Der Azure OpenAI Service stellt eine REST-API bereit, die Sie verwenden können, um Eingabeaufforderungen zur Inhaltsgenerierung zu übermitteln, einschließlich der Bilder, die von einem DALL-E-Modell generiert wurden.

### Vorbereiten der App-Umgebung

In dieser Übung verwenden Sie eine einfache Python- oder Microsoft-C#-App, um Bilder zu generieren, indem Sie die REST-API aufrufen. Sie führen den Code in der Cloud Shell-Konsolenschnittstelle im Azure-Portal aus.

1. Klicken Sie im [Azure-Portal](https://portal.azure.com?azure-portal=true) oben auf der Seite rechts neben dem Suchfeld auf die Schaltfläche **[>_]** (*Cloud Shell*). Am unteren Rand des Portals wird ein Cloud Shell-Bereich geöffnet. 

    ![Screenshot: Starten von Cloud Shell durch das Klicken auf das Symbol rechts neben dem oberen Suchfeld](../media/cloudshell-launch-portal.png#lightbox)

2. Wenn Sie die Cloud Shell zum ersten Mal öffnen, werden Sie möglicherweise aufgefordert, die Art der Shell zu wählen, die Sie verwenden möchten (*Bash* oder *PowerShell*). Wählen Sie **Bash** aus. Wenn Sie diese Option nicht sehen, überspringen Sie den Schritt.  

3. Wenn Sie aufgefordert werden, Speicher für Cloud Shell zu erstellen, überprüfen Sie, ob Ihr Abonnement korrekt angegeben ist, und klicken Sie auf **Speicher erstellen**. Warten Sie dann etwa eine Minute, bis der Speicher erstellt ist.

    > **Hinweis**: Wenn Sie bereits eine Cloud Shell in Ihrem Azure-Abonnement eingerichtet haben, müssen Sie möglicherweise die Option **Benutzereinstellungen zurücksetzen** im ⚙️-Menü verwenden, um sicherzustellen, dass die neuesten Versionen von Python und .NET Framework installiert sind.

4. Vergewissern Sie sich, dass links oben im Cloud Shell-Bereich der Shelltyp auf *Bash* umgestellt wurde. Sollte *PowerShell* angezeigt werden, wechseln Sie über das Dropdownmenü zu *Bash*.

5. Sobald das Terminal gestartet wird, geben Sie den folgenden Befehl ein, um den Anwendungscode herunterzuladen, mit dem Sie arbeiten möchten.

    ```bash
   rm -r azure-openai -f
   git clone https://github.com/MicrosoftLearning/mslearn-openai azure-openai
    ```

    Die Dateien werden in einen Ordner namens **azure-openai** heruntergeladen. Anwendungen für C# und Python wurden bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität.

6. Navigieren Sie zum Ordner für die Sprache, die Sie verwenden möchten, indem Sie den entsprechenden Befehl ausführen.

    **Python**

    ```bash
   cd azure-openai/Labfiles/05-image-generation/Python
    ```

    **C#**

    ```bash
   cd azure-openai/Labfiles/05-image-generation/CSharp
    ```

7. Verwenden Sie den folgenden Befehl, um den integrierten Code-Editor zu öffnen und die Codedateien anzuzeigen, mit denen Sie arbeiten werden.

    ```bash
   code .
    ```

### Konfigurieren der Anwendung

Die Anwendung verwendet eine Konfigurationsdatei, um die Details zu speichern, die zum Herstellen einer Verbindung mit Ihrem Azure OpenAI Service-Konto erforderlich sind.

1. Wählen Sie im Code-Editor die Konfigurationsdatei für Ihre App aus – je nach der von Ihnen bevorzugten Sprache.

    - C#: `appsettings.json`
    - Python: `.env`
    
2. Aktualisieren Sie die Konfigurationswerte, um den **Endpunkt** und **Key1** für Ihre Azure OpenAI Service-Instanz einzuschließen, und speichern Sie dann die Datei.

    > **Tipp**: Sie können die Aufteilung oben im Cloud Shell-Bereich anpassen, um das Azure-Portal anzuzeigen und die Endpunkt- und Schlüsselwerte auf der Seite **Schlüssel und Endpunkt** für Ihren Azure OpenAI-Dienst abzurufen.

3. Wenn Sie **Python** verwenden, müssen Sie auch das Paket **python-dotenv** installieren, das zum Lesen der Konfigurationsdatei verwendet wird. Stellen Sie im Konsoleneingabeaufforderungsbereich sicher, dass der aktuelle Ordner **~/azure-openai/Labfiles/05-image-generation/Python** ist. Geben Sie dann den folgenden Befehl ein:

    ```bash
   pip install python-dotenv
    ```

### Anzeigen des Anwendungscodes

Jetzt können Sie den Code untersuchen, der zum Aufrufen der REST-API und zum Generieren eines Bilds verwendet wird.

1. Wählen Sie im Code-Editor-Bereich die Hauptcodedatei für Ihre Anwendung aus:

    - C#: `Program.cs`
    - Python: `generate-image.py`

2. Überprüfen Sie den Code, der in der Datei enthalten ist, und beachten Sie dabei die folgenden wichtigen Features:
    - Der Code sendet HTTPS-Anforderungen an den Endpunkt für Ihren Dienst und fügt den Schlüssel für Ihren Dienst in den Header ein. Beide Werte werden aus der Konfigurationsdatei abgerufen.
    - Der Prozess besteht aus <u>zwei</u> REST-Anforderungen: eine zum Initiieren der Bildgenerierungsanforderung und eine zum Abrufen der Ergebnisse.
    Die anfängliche Anforderung enthält die folgenden Daten:
        - Die von dem*der Benutzer*in bereitgestellte Eingabeaufforderung, die das zu generierende Bild beschreibt.
        - Die Anzahl der zu generierenden Bilder (in diesem Fall 1)
        - Die Auflösung (Größe) des zu generierenden Bilds.
    - Der Antwortheader der anfänglichen Anforderung enthält einen Wert vom Typ **operation-location**, der für den nachfolgenden Rückruf zum Abrufen der Ergebnisse verwendet wird.
    - Der Code ruft die Rückruf-URL ab, bis der Status des Bildgenerierungstasks *Erfolgreich* ist. Anschließend wird eine URL für das generierte Bild extrahiert und angezeigt.

### Ausführen der App

Nachdem Sie den Code überprüft haben, ist es an der Zeit, ihn auszuführen und einige Bilder zu generieren.

1. Geben Sie im Konsoleneingabeaufforderungsbereich den entsprechenden Befehl ein, um Ihre Anwendung auszuführen:

    **Python**

    ```bash
   python generate-image.py
    ```

    **C#**

    ```bash
   dotnet run
    ```

2. Wenn Sie dazu aufgefordert werden, geben Sie eine Beschreibung für ein Bild ein. Beispiel: *Eine Giraffe, die einen Drachen fliegt*.

3. Warten Sie, bis das Bild generiert wurde. Im Konsolenbereich wird ein Link angezeigt. Wählen Sie dann den Link aus, um eine neue Browserregisterkarte zu öffnen und das generierte Bild zu überprüfen.

4. Schließen Sie die Registerkarte mit dem generierten Bild, und führen Sie die App erneut aus, um ein neues Bild mit einer anderen Eingabeaufforderung zu generieren.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen.
