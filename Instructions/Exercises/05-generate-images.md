---
lab:
  title: Erstellen Sie Bilder mit einem DALL-E-Modell
  status: stale
---

# Erstellen Sie Bilder mit einem DALL-E-Modell

Der Azure OpenAI Service enthält ein Bildgenerierungsmodell mit dem Namen DALL-E. Sie können dieses Modell verwenden, um Eingabeaufforderungen in natürlicher Sprache zu übermitteln, die ein gewünschtes Bild beschreiben, und das Modell generiert ein Originalbild basierend auf der von Ihnen angegebenen Beschreibung.

In dieser Übung verwenden Sie ein DALL-E Version 3-Modell, um Bilder basierend auf Aufforderungen in natürlicher Sprache zu generieren.

Diese Übung dauert ungefähr **25** Minuten.

## Bereitstellen einer Azure OpenAI-Ressource

Bevor Sie Azure OpenAI verwenden können, um Bilder zu generieren, müssen Sie eine Azure OpenAI-Ressource in Ihrem Azure-Abonnement bereitstellen. Die Ressource muss sich in einer Region befinden, in der DALL-E-Modelle unterstützt werden.

1. Melden Sie sich beim **Azure-Portal** unter `https://portal.azure.com` an.
1. Erstellen Sie eine **Azure OpenAI-Ressource** mit den folgenden Einstellungen:
    - **Abonnement:** *Wählen Sie ein Azure-Abonnement aus, das für den Zugriff auf den Azure OpenAI-Dienst genehmigt wurde, einschließlich DALL-E*
    - **Ressourcengruppe**: *Wählen Sie eine Ressourcengruppe aus, oder erstellen Sie eine*.
    - **Region**: *Wählen Sie entweder **USA, Osten** oder **Schweden, Mitte*** aus\*
    - **Name:** *Wählen Sie einen Namen Ihrer Wahl aus.*
    - **Tarif**: Standard S0.

    > \* DALL-E 3-Modelle sind nur in Azure OpenAI-Dienstressourcen in den Regionen **USA, Osten** und **Schweden, Mitte** verfügbar.

1. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.
1. Scrollen Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource nach unten zum Abschnitt **Erste Schritte** und klicken Sie auf die Schaltfläche, um zum **AI Foundry-Portal** (zuvor KI-Studio) zu gelangen.
1. Wählen Sie im Azure KI Foundry-Portal im linken Bereich die Seite „**Deployments**“ aus und sehen Sie sich Ihre vorhandenen Modellbereitstellungen an. Wenn Sie noch kein DALL-E 3 haben, erstellen Sie eine neue Bereitstellung des **dall-e-3**-Modells mit den folgenden Einstellungen:
    - **Name der Bereitstellung**: dalle3
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungstyp**: Standard
    - **Kapazitätseinheiten**: 1.000
    - **Inhaltsfilter**: Standard
    - **Dynamische Quote aktivieren**: Deaktiviert
1. Navigieren Sie nach dem Einsatz zurück zur Seite "**Bilder**" im linken Fensterbereich.

## Erkunden Sie die Bilderzeugung im Playground für Bilder

Sie können den Playground "Images" im **Azure AI Foundry-Portal** verwenden, um mit der Bilderzeugung zu experimentieren.

1. Im Abschnitt "**Images Playground**" sollte Ihr Einsatz von DALL-E 3 automatisch ausgewählt werden. Falls nicht, wählen Sie es aus der Dropdown-Liste "Bereitstellung" aus.
1. Geben Sie im Feld **Eingabeaufforderung** eine Beschreibung eines Bilds ein, das Sie generieren möchten. Wählen Sie beispielsweise `An elephant on a skateboard` Wählen Sie dann **Generieren** aus, und zeigen Sie das generierte Bild an.

1. Ändern Sie die Eingabeaufforderung, um eine spezifischere Beschreibung bereitzustellen. Beispiel: `An elephant on a skateboard in the style of Picasso`. Generieren Sie dann das neue Bild, und überprüfen Sie die Ergebnisse.

    ![Der Playground "Images" im Azure AI Foundry-Portal mit zwei generierten Bildern.](../media/images-playground-new-style.png)

## Verwenden der REST-API zum Generieren von Bildern

Der Azure OpenAI Service stellt eine REST-API bereit, die Sie verwenden können, um Eingabeaufforderungen zur Inhaltsgenerierung zu übermitteln, einschließlich der Bilder, die von einem DALL-E-Modell generiert wurden.

### Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sehen wir uns nun an, wie Sie eine benutzerdefinierte App erstellen können, die Azure OpenAI Service verwendet, um Bilder zu generieren. Sie entwickeln Ihre App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P), und führen Sie einen **Git: Clone**-Befehl aus, um das Repository `https://github.com/MicrosoftLearning/mslearn-openai` in einen lokalen Ordner zu klonen (der Ordner ist beliebig).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

### Konfigurieren der Anwendung

Anwendungen für C# und Python wurden bereitgestellt. Beide Apps verfügen über die gleiche Funktionalität. Zuerst fügen Sie den Endpunkt und den Schlüssel für Ihre Azure OpenAI-Ressource zur Konfigurationsdatei der App hinzu.

1. Wechseln Sie in Visual Studio Code im **Explorer** -Bereich zum Ordner **Labfiles/05-image-generation**, und erweitern Sie je nach Ihrer bevorzugten Sprache den Ordner **CSharp** oder **Python**. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, in die Sie Azure OpenAI-Funktionen integrieren möchten.
2. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Konfigurationsdatei für Ihre bevorzugte Sprache

    - **C#**: appsettings.json
    - **Python**: .env
    
3. Aktualisieren Sie die Konfigurationswerte so, dass sie den **Endpunkt** und **Schlüssel** aus der Azure OpenAI-Ressource enthalten, die Sie erstellt haben (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
4. Speichern Sie die Konfigurationsdatei.

### Anzeigen des Anwendungscodes

Jetzt können Sie den Code untersuchen, der zum Aufrufen der REST-API und zum Generieren eines Bilds verwendet wird.

1. Wählen Sie im Bereich **Explorer** die Hauptcodedatei für Ihre Anwendung aus:

    - C#: `Program.cs`
    - Python: `generate-image.py`

2. Überprüfen Sie den Code, der in der Datei enthalten ist, und beachten Sie dabei die folgenden wichtigen Features:
    - Der Code sendet eine HTTPS-Anforderung an den Endpunkt für Ihren Dienst, einschließlich des Schlüssels für Ihren Dienst im Header. Beide Werte werden aus der Konfigurationsdatei abgerufen.
    - Die Anforderung enthält einige Parameter, einschließlich der Eingabeaufforderung auf dem Bild, die Anzahl der zu generierenden Bilder und die Größe der generierten Bilder.
    - Die Antwort enthält eine überarbeitete Eingabeaufforderung, die das DALL-E-Modell von der vom Benutzer bereitgestellten Eingabeaufforderung extrapoliert hat, um es aussagekräftiger zu machen, und die URL für das generierte Bild.
    
    > **Wichtig**: Wenn Sie Ihrer Bereitstellung einen anderen Namen als den empfohlenen *dalle3* gegeben haben, müssen Sie den Code aktualisieren, um den Namen Ihrer Bereitstellung zu verwenden.

### Ausführen der App

Nachdem Sie den Code überprüft haben, ist es an der Zeit, ihn auszuführen und einige Bilder zu generieren.

1. Klicken Sie mit der rechten Maustaste auf den **CSharp-** oder **Python-** Ordner, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Geben Sie dann den entsprechenden Befehl ein, um Ihre Anwendung auszuführen:

   **C#**
   ```
   dotnet run
   ```
   
   **Python**
   ```
   pip install requests
   python generate-image.py
   ```

3. Wenn Sie dazu aufgefordert werden, geben Sie eine Beschreibung für ein Bild ein. Beispiel: *Eine Giraffe, die einen Drachen fliegt*.

4. Warten Sie, bis das Bild generiert wurde. Im Konsolenbereich wird ein Link angezeigt. Wählen Sie dann den Link aus, um eine neue Browserregisterkarte zu öffnen und das generierte Bild zu überprüfen.

   > **TIPP**: Wenn die App keine Antwort zurückgibt, warten Sie eine Minute, und versuchen Sie es erneut. Neu bereitgestellte Ressourcen können bis zu 5 Minuten in Anspruch nehmen, bis sie verfügbar sind.

5. Schließen Sie die Registerkarte mit dem generierten Bild, und führen Sie die App erneut aus, um ein neues Bild mit einer anderen Eingabeaufforderung zu generieren.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im **Azure-Portal** unter `https://portal.azure.com` zu löschen.
