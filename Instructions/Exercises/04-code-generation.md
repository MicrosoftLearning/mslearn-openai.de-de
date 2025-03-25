---
lab:
  title: Generieren und Verbessern von Code mit Azure OpenAI Service
  status: stale
---

# Generieren und Verbessern von Code mit Azure OpenAI Service

Die Azure OpenAI Service-Modelle können Code für Sie generieren, indem Sie Eingabeaufforderungen in natürlicher Sprache verwenden, Fehler in fertigem Code beheben und Codekommentare bereitstellen. Diese Modelle können auch vorhandenen Code erklären und vereinfachen, damit Sie verstehen, was er tut und wie man ihn verbessern kann.

Im Szenario für diese Übung führen Sie die Rolle eines Softwareentwicklers aus, der untersucht, wie generative KI verwendet werden kann, um Codierungsaufgaben einfacher und effizienter zu gestalten. Die in der Übung verwendeten Techniken können auch für andere Codedateien, Programmiersprachen und Anwendungsfälle genutzt werden.

Diese Übung dauert ungefähr **25** Minuten.

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

Azure bietet ein webbasiertes Portal mit dem Namen **Azure KI Foundry Portal**, das Sie zur Bereitstellung, Verwaltung und Untersuchung von Modellen verwenden können. Sie beginnen Ihre Erkundung von Azure OpenAI, indem Sie das Azure KI Foundry-Portal verwenden, um ein Modell bereitzustellen.

> **Hinweis**: Während Sie Azure KI Studio verwenden, werden möglicherweise Meldungsfelder mit Vorschlägen für auszuführende Aufgaben angezeigt. Sie können diese schließen und die Schritte in dieser Übung ausführen.

1. Scrollen Sie im Azure-Portal auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource nach unten zum Abschnitt **Erste Schritte** und wählen Sie die Schaltfläche aus, um zum **KI Foundry-Portal** (zuvor KI-Studio) zu gelangen.
1. Wählen Sie im Azure KI Foundry-Portal im linken Bereich die Seite „**Deployments**“ aus und sehen Sie sich Ihre vorhandenen Modellbereitstellungen an. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Bereitstellungsname**: *Ein eindeutiger Name Ihrer Wahl*
    - **Modell**: gpt-35-turbo-16k *(wenn das 16k-Modell nicht verfügbar ist, wählen Sie gpt-35-turbo)*
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungstyp**: Standard
    - **Ratenlimit für Token pro Minute**: 5K\*
    - **Inhaltsfilter**: Standard
    - **Dynamische Quote aktivieren**: Deaktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Generieren von Code im Playground für Chats

Überprüfen Sie vor der Verwendung in Ihrer App, wie Azure OpenAI Code im Playground für Chats generieren und erklären kann.

1. Wählen Sie im Abschnitt **Playground** die Seite **Chat** aus. Die Seite "**Chat** Playground" besteht aus einer Reihe von Schaltflächen und zwei Hauptbereichen (die je nach Bildschirmauflösung horizontal von rechts nach links oder vertikal von oben nach unten angeordnet werden können):
    - **Konfiguration** – wird verwendet, um Ihre Bereitstellung auszuwählen, Systemmeldungen zu definieren und Parameter für die Interaktion mit Ihrer Bereitstellung festzulegen.
    - **Chatsitzung**: wird zum Senden von Chat-Nachrichten und Ansehen von Antworten verwendet
1. Stellen Sie unter **Bereitstellungen** sicher, dass Ihre Modellbereitstellung ausgewählt ist.
1. Legen Sie im Bereich "**System message**" die Systemmeldung auf `You are a programming assistant helping write code` fest und übernehmen Sie die Änderungen.
1. Senden Sie in der **Chatsitzung** die folgende Abfrage:

    ```
    Write a function in python that takes a character and a string as input, and returns how many times the character appears in the string
    ```

    Das Modell antwortet wahrscheinlich mit einer Funktion, mit einer Erklärung, was die Funktion tut und wie sie aufgerufen werden kann.

1. Senden Sie als Nächstes die Eingabeaufforderung `Do the same thing, but this time write it in C#`.

    Das Modell reagierte wahrscheinlich sehr ähnlich wie beim ersten Mal, diesmal jedoch in C#. Sie können es erneut nach einer anderen Sprache Ihrer Wahl oder einer Funktion fragen, um eine andere Aufgabe zu erfüllen, wie z. B. das Umkehren einer Eingabezeichenfolge.

1. Als Nächstes erkunden wir den Einsatz von KI, um Code zu verstehen. Senden Sie die folgende Eingabeaufforderung als Benutzernachricht.

    ```
    What does the following function do?  
    ---  
    def multiply(a, b):  
        result = 0  
        negative = False  
        if a < 0 and b > 0:  
            a = -a  
            negative = True  
        elif a > 0 and b < 0:  
            b = -b  
            negative = True  
        elif a < 0 and b < 0:  
            a = -a  
            b = -b  
        while b > 0:  
            result += a  
            b -= 1      
        if negative:  
            return -result  
        else:  
            return result  
    ```

    Das Modell sollte beschreiben, was die Funktion bewirkt, und zwar zwei Zahlen mithilfe einer Schleife zu multiplizieren.

7. Senden Sie die Eingabeaufforderung `Can you simplify the function?`.

    Das Modell sollte eine einfachere Version der Funktion schreiben.

8. Senden Sie die Eingabeaufforderung: `Add some comments to the function.`

    Das Modell fügt dem Code Kommentare hinzu.

## Vorbereitung auf das Entwickeln einer App in Visual Studio Code

Sehen wir uns nun an, wie Sie eine benutzerdefinierte App erstellen können, die Azure OpenAI Service verwendet, um Bilder zu generieren. Sie entwickeln Ihre App mit Visual Studio Code. Die Codedateien für Ihre App wurden in einem GitHub-Repository bereitgestellt.

> **Tipp**: Wenn Sie das **mslearn-openai**-Repository bereits geklont haben, öffnen Sie es in Visual Studio Code. Führen Sie andernfalls die folgenden Schritte aus, um es in Ihrer Entwicklungsumgebung zu klonen.

1. Starten Sie Visual Studio Code.
2. Öffnen Sie die Palette (UMSCHALT+STRG+P), und führen Sie einen **Git: Clone**-Befehl aus, um das Repository `https://github.com/MicrosoftLearning/mslearn-openai` in einen lokalen Ordner zu klonen (der Ordner ist beliebig).
3. Nachdem das Repository geklont wurde, öffnen Sie den Ordner in Visual Studio Code.

    > **Hinweis:** Wenn Visual Studio Code eine Popupnachricht anzeigt, in der Sie aufgefordert werden, dem geöffneten Code zu vertrauen, klicken Sie auf die Option **Ja, ich vertraue den Autoren** im Popupfenster.

4. Warten Sie, während zusätzliche Dateien zur Unterstützung der C#-Codeprojekte im Repository installiert werden.

    > **Hinweis**: Wenn Sie aufgefordert werden, erforderliche Ressourcen zum Erstellen und Debuggen hinzuzufügen, wählen Sie **Not now** (Jetzt nicht) aus.

## Konfigurieren der Anwendung

Es werden Anwendungen für C# und Python bereitgestellt sowie eine Beispieltextdatei, mit der Sie die Zusammenfassung testen können. Beide Apps verfügen über die gleiche Funktionalität. Zuerst vervollständigen Sie einige wichtige Teile der Anwendung, um Ihre Azure OpenAI-Ressource nutzen zu können.

1. Wechseln Sie in Visual Studio Code im **Explorer** -Bereich zum Ordner **Labfiles/04-code-generation**, und erweitern Sie je nach Ihrer bevorzugten Sprache den Ordner **CSharp** oder **Python**. Jeder Ordner enthält die sprachspezifischen Dateien für eine App, in die Sie Azure OpenAI-Funktionen integrieren möchten.
2. Klicken Sie mit der rechten Maustaste auf den Ordner **CSharp** oder **Python**, der Ihre Codedateien enthält, und öffnen Sie ein integriertes Terminal. Installieren Sie dann das SDK-Paket von Azure OpenAI, indem Sie den entsprechenden Befehl für Ihre bevorzugte Sprache ausführen:

    **C#:**

    ```
    dotnet add package Azure.AI.OpenAI --version 1.0.0-beta.14
    ```

    **Python**:

    ```
    pip install openai==1.55.3
    ```

3. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Konfigurationsdatei für Ihre bevorzugte Sprache.

    - **C#**: appsettings.json
    - **Python**: .env
    
4. Aktualisieren Sie die Konfigurationswerte, um Folgendes einzuschließen:
    - Den **Endpunkt** und einen **Schlüssel** aus der von Ihnen erstellten Azure OpenAI-Ressource (verfügbar auf der Seite **Schlüssel und Endpunkt** für Ihre Azure OpenAI-Ressource im Azure-Portal).
    - Der **Bereitstellungsname**, den Sie für Ihre Modellbereitstellung angegeben haben (verfügbar auf der Seite „**Bereitstellungen“** im Azure KI Foundry-Portal).
5. Speichern Sie die Konfigurationsdatei.

## Hinzufügen von Code zum Verwenden Ihres Azure OpenAI-Dienstmodells

Jetzt können Sie das Azure OpenAI-SDK verwenden, um Ihr bereitgestelltes Modell zu nutzen.

1. Öffnen Sie im Bereich **Explorer** im Ordner **CSharp** oder **Python** die Codedatei für Ihre bevorzugte Sprache. Fügen Sie in der Funktion, die das Azure OpenAI-Modell aufruft, unter dem Kommentar ***Formatieren und Senden der Anforderung an das Modell***, den Code zum Formatieren hinzu, und senden Sie die Anforderung an das Modell.

    **C#** : Program.cs

    ```csharp
    // Format and send the request to the model
    var chatCompletionsOptions = new ChatCompletionsOptions()
    {
        Messages =
        {
            new ChatRequestSystemMessage(systemPrompt),
            new ChatRequestUserMessage(userPrompt)
        },
        Temperature = 0.7f,
        MaxTokens = 1000,
        DeploymentName = oaiDeploymentName
    };

    // Get response from Azure OpenAI
    Response<ChatCompletions> response = await client.GetChatCompletionsAsync(chatCompletionsOptions);

    ChatCompletions completions = response.Value;
    string completion = completions.Choices[0].Message.Content;
    ```

    **Python**: code-generation.py

    ```python
    # Format and send the request to the model
    messages =[
        {"role": "system", "content": system_message},
        {"role": "user", "content": user_message},
    ]
    
    # Call the Azure OpenAI model
    response = client.chat.completions.create(
        model=model,
        messages=messages,
        temperature=0.7,
        max_tokens=1000
    )
    ```

4. Speichern Sie die Änderungen in der Codedatei.

## Ausführen der Anwendung

Nachdem Ihre App konfiguriert wurde, führen Sie sie aus, um Code für jeden Anwendungsfall zu generieren. Die Anwendungsfälle sind in der App nummeriert und können in beliebiger Reihenfolge ausgeführt werden.

> **Hinweis**: Bei einigen Benutzer*innen kann es zu einer Ratenbegrenzung kommen, wenn sie das Modell zu häufig aufrufen. Wenn Sie eine Fehlermeldung über eine Tokenratenbegrenzung erhalten, warten Sie eine Minute, und versuchen Sie es dann erneut.

1. Erweitern Sie im Bereich **Explorer** den Ordner **Labfiles/04-code-generation/sample-code**, und überprüfen Sie die Funktion und die *go-fish*-App für Ihre Sprache. Diese Dateien werden für die Aufgaben in der App verwendet.
2. Stellen Sie im interaktiven Terminalbereich sicher, dass der Ordnerkontext der Ordner für Ihre bevorzugte Sprache ist. Geben Sie dann den folgenden Befehl ein, um die Anwendung auszuführen.

    - **C#** : `dotnet run`
    - **Python**: `python code-generation.py`

    > **Tipp**: Sie können das Symbol **Maximize panel size** (Panelgröße maximieren) (**^**) in der Terminalsymbolleiste verwenden, um mehr des Konsolentexts anzuzeigen.

3. Wählen Sie die Option **1** aus, um Ihrem Code Kommentare hinzuzufügen, und geben Sie die folgende Eingabeaufforderung ein. Beachten Sie, dass die Beantwortung jeder dieser Aufgaben einige Sekunden dauern kann.

    ```prompt
    Add comments to the following function. Return only the commented code.\n---\n
    ```

    Die Ergebnisse werden in **result/app.txt** eingefügt. Öffnen Sie diese Datei, und vergleichen Sie sie mit der Funktionsdatei in **sample-code**.

4. Wählen Sie als Nächstes Option **2** aus, um Komponententests für dieselbe Funktion zu schreiben, und geben Sie die folgende Eingabeaufforderung ein.

    ```prompt
    Write four unit tests for the following function.\n---\n
    ```

    Die Ergebnisse ersetzen das, was in **result/app.txt** stand, und enthalten vier Komponententests für diese Funktion.

5. Wählen Sie als Nächstes Option **3** aus, um Fehler in einer App für die Wiedergabe von Go Fish zu beheben. Geben Sie den folgenden Prompt ein.

    ```prompt
    Fix the code below for an app to play Go Fish with the user. Return only the corrected code.\n---\n
    ```

    Die Ergebnisse ersetzen das, was in **result/app.txt** stand, und sollten einen sehr ähnlichen Code haben, wobei einige Dinge korrigiert wurden.

    - **C#** : Korrekturen werden in Zeile 30 und 59 vorgenommen.
    - **Python**: Korrekturen werden in Zeile 18 und 31 vorgenommen.

    Die App für Go Fish in **sample-code** kann ausgeführt werden, wenn man die Zeilen, die Fehler enthalten, durch die Antwort von Azure OpenAI ersetzt. Wenn Sie sie ohne die Korrekturen ausführen, wird sie nicht richtig funktionieren.
    
    > **Hinweis:** Es ist wichtig zu beachten, dass der Code für diese Go Fish-App zwar um einige Syntaxfehler korrigiert wurde, es sich jedoch nicht um eine genaue Darstellung des Spiels handelt. Wenn Sie genau hinsehen, treten Probleme dadurch auf, dass beim Ziehen von Karten nicht geprüft wird, ob das Deck leer ist, dass Paare nicht aus der Hand des Spielers bzw. der Spielerin entfernt werden, wenn er*sie ein Paar erhält, und einige andere Fehler, die ein Verständnis von Kartenspielen erfordern, um sie zu erkennen. Dies ist ein großartiges Beispiel dafür, wie nützlich generative KI-Modelle sein können, um die Codegenerierung zu unterstützen. Sie sollten jedoch nicht als absolut zuverlässig angesehen werden und müssen von dem*der Entwickler*in überprüft werden.

    Wenn Sie die vollständige Antwort von Azure OpenAI sehen möchten, können Sie die **printFullResponse**-Variable auf `True` festlegen und die App erneut ausführen.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im **Azure-Portal** auf `https://portal.azure.com` zu löschen.
