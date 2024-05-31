---
lab:
  title: Erste Schritte mit Azure OpenAI Service
---

# Erste Schritte mit Azure OpenAI Service

Azure OpenAI Service bringt die von OpenAI entwickelten generativen KI-Modelle auf die Azure-Plattform und ermöglicht Ihnen die Entwicklung leistungsstarker KI-Lösungen, die von der Sicherheit, Skalierbarkeit und Integration anderer Dienste der Azure-Cloudplattform profitieren. In dieser Übung erfahren Sie, wie Sie die Arbeit mit Azure OpenAI beginnen, indem Sie den Dienst als Azure-Ressource bereitstellen und Azure OpenAI Studio verwenden, um generative KI-Modelle bereitzustellen und zu untersuchen.

In dem Szenario für diese Übung führen Sie die Rolle eines Softwareentwicklers aus, der beauftragt wurde, einen KI-Agent zu implementieren, der generative KI verwenden kann, um einer Marketingorganisation zu helfen, ihre Effektivität bei der Erreichung von Kunden zu verbessern und neue Produkte zu bewerben. Die in der Übung verwendeten Techniken können auf jedes Szenario angewendet werden, in dem eine Organisation generative KI-Modelle verwenden möchte, um Mitarbeitern zu helfen, effektiver und produktiver zu arbeiten.

Diese Übung dauert ca. **30** Minuten.

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

Azure OpenAI Service bietet ein webbasiertes Portal namens **Azure OpenAI Studio**, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können. Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.

> **Hinweis:** Während Sie Azure OpenAI Studio verwenden, werden möglicherweise Meldungsfelder angezeigt, die Aufgaben vorschlagen, die Sie ausführen können. Sie können diese schließen und die Schritte in dieser Übung ausführen.

1. Verwenden Sie im Azure-Portal auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Zu Azure OpenAI Studio wechseln**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.

    Nachdem die neue Registerkarte geöffnet wurde, können Sie alle Bannerbenachrichtigungen für neue Vorschaudienste schließen, die oben auf der Azure OpenAI Studio-Seite angezeigt werden.

1. Wählen Sie in Azure OpenAI Studio im Bereich auf der linken Seite die Seite **Bereitstellungen** aus, und zeigen Sie Ihre vorhandenen Modellbereitstellungen an. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo-16k *(wenn das 16k-Modell nicht verfügbar ist, wählen Sie gpt-35-turbo)*
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Ein eindeutiger Name Ihrer Wahl*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Bereitstellungstyp**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

## Verwenden des Chat-Playgrounds

Nachdem Sie ein Modell bereitgestellt haben, können Sie es verwenden, um Antworten basierend auf Aufforderungen in natürlicher Sprache zu generieren. Der *Chat*-Playground in Azure OpenAI Studio bietet eine Chatbotschnittstelle für GPT 3.5 und höhere Modelle.

> **Hinweis:** Der *Chat*-Playground verwendet die *ChatCompletions*-API anstelle der älteren *Completions*-API, die vom *Completions*-Playground verwendet wird. Der Completions-Playground wird aus Gründen der Kompatibilität mit älteren Modellen bereitgestellt.

1. Wählen Sie im Abschnitt **Playground** die Seite **Chat** aus. Die **Chat**-Playground-Seite besteht aus drei Hauptbereichen (die je nach Bildschirmauflösung horizontal von rechts nach links oder vertikal von oben nach unten angeordnet sein können):
    - **Setup**: wird zum Festlegen des Kontexts für die Antworten des Modells verwendet
    - **Chatsitzung**: wird zum Senden von Chat-Nachrichten und Ansehen von Antworten verwendet
    - **Konfiguration**: wird zum Konfigurieren von Einstellungen für die Modellbereitstellung verwendet
1. Stellen Sie im Bereich **Konfiguration** sicher, dass die gpt-35-turbo-16k-Modellimplementierung ausgewählt ist.
1. Überprüfen Sie im Bereich **Setup** die standardmäßige **Systemmeldung**, die wie folgt lauten sollte: *Sie sind ein KI-Assistent, der Benutzern dabei hilft, Informationen zu finden.* Die Systemmeldung ist in den an das Modell übermittelten Eingabeaufforderungen enthalten und stellt Kontext für die Antworten des Modells bereit. Sie legt die Erwartungen fest, wie ein KI-Agent basierend auf dem Modell mit dem Benutzer interagieren soll.
1. Geben Sie im Bereich **Chatsitzung** die Benutzerabfrage `How can I use generative AI to help me market a new product?` ein.

    > **Hinweis**: Sie erhalten möglicherweise die Antwort, dass die API-Bereitstellung noch nicht abgeschlossen ist. Wenn dies der Fall ist, warten Sie ein paar Minuten, und versuchen Sie es erneut.

1. Überprüfen Sie die Antwort, und beachten Sie, dass das Modell eine zusammenhängende Antwort in natürlicher Sprache generiert hat, die für die eingegebene Abfrage relevant ist.
1. Geben Sie die Benutzerabfrage `What skills do I need if I want to develop a solution to accomplish this?` ein.
1. Überprüfen Sie die Antwort, und beachten Sie, dass die Chatsitzung den Unterhaltungskontext beibehalten hat (daher wird „dies“ als generative KI-Lösung für Marketing interpretiert). Diese Kontextualisierung wird erreicht, indem der aktuelle Unterhaltungsverlauf in jede aufeinander folgende Eingabeaufforderungsübermittlung einbezogen wird, sodass die an das Modell für die zweite Abfrage gesendete Eingabeaufforderung die ursprüngliche Abfrage und Antwort sowie die neue Benutzereingabe enthielt.
1. Wählen Sie in der Bereichssymbolleiste **Chatsitzung** die Option **Chat löschen** aus, und bestätigen Sie, dass Sie die Chatsitzung neu starten möchten.
1. Geben Sie die Abfrage `Can you help me find resources to learn those skills?` ein, und überprüfen Sie die Antwort, die eine gültige Antwort in natürlicher Sprache sein sollte, aber da der vorherige Chatverlauf verloren gegangen ist, geht es wahrscheinlich darum, generische Fähigkeiten zu finden, anstatt sich auf die spezifischen Fähigkeiten zu beziehen, die zum Erstellen einer generativen KI-Marketinglösung erforderlich sind.

## Experimentieren mit Systemmeldungen, Eingabeaufforderungen und Few-Shot-Beispielen

Bisher haben Sie eine Chatunterhaltung mit Ihrem Modell basierend auf der Standardsystemnachricht durchgeführt. Sie können das Systemsetup anpassen, um mehr Kontrolle über die Arten von Antworten zu haben, die von Ihrem Modell generiert werden.

1. Wählen Sie im Bereich **Setup** unter **Systemnachrichtenvorlage verwenden** die Vorlage **Assistent für das Schreiben von Marketingtexten** aus, und bestätigen Sie, dass Sie die Systemmeldung aktualisieren möchten.
1. Überprüfen Sie die neue Systemmeldung, die beschreibt, wie ein KI-Agent das Modell verwenden soll, um zu antworten.
1. Geben Sie im Bereich **Chatsitzung** die Benutzerabfrage `Create an advertisement for a new scrubbing brush` ein.
1. Überprüfen Sie die Antwort, die den Werbetext für eine Scrubbing-Bürste enthalten sollte. Der Text kann recht umfangreich und kreativ sein.

    In einem echten Szenario würde ein Marketingprofi wahrscheinlich bereits den Namen der Scrubbing-Bürste kennen und einige Ideen zu wichtigen Features haben, die in einer Anzeige hervorgehoben werden sollten. Um die nützlichsten Ergebnisse eines generativen KI-Modells zu erzielen, müssen Benutzer ihre Eingabeaufforderungen so gestalten, dass sie so viele relevante Informationen wie möglich einschließen.

1. Geben Sie die Eingabeaufforderung `Revise the advertisement for a scrubbing brush named "Scrubadub 2000", which is made of carbon fiber and reduces cleaning times by half compared to ordinary scrubbing brushes` ein.
1. Überprüfen Sie die Antwort, die die zusätzlichen Informationen berücksichtigen sollte, die Sie über die Scrubbing-Bürste bereitgestellt haben.

    Die Antwort sollte nun nützlicher sein, aber um noch mehr Kontrolle über die Ausgabe des Modells zu erhalten, können Sie ein oder mehrere *Few-Shot*-Beispiele bereitstellen, auf denen die Antworten basieren sollen.

1. Wählen Sie im Bereich **Setup** unter **Beispiele** die Option **Hinzufügen** aus. Geben Sie dann die folgende Nachricht und Antwort in die angegebenen Felder ein:

    **Benutzer**:
    
    ```prompt
    Write an advertisement for the lightweight "Ultramop" mop, which uses patented absorbent materials to clean floors.
    ```
    
    **Assistent:**
    
    ```prompt
    Welcome to the future of cleaning!
    
    The Ultramop makes light work of even the dirtiest of floors. Thanks to its patented absorbent materials, it ensures a brilliant shine. Just look at these features:
    - Lightweight construction, making it easy to use.
    - High absorbency, enabling you to apply lots of clean soapy water to the floor.
    - Great low price.
    
    Check out this and other products on our website at www.contoso.com.
    ```

1. Verwenden Sie die Schaltfläche **Änderungen anwenden**, um die Beispiele zu speichern und eine neue Sitzung zu starten.
1. Geben Sie im Abschnitt **Chatsitzung** die Benutzerabfrage `Create an advertisement for the Scrubadub 2000 - a new scrubbing brush made of carbon fiber that reduces cleaning time by half` ein.
1. Überprüfen Sie die Antwort, die eine neue Anzeige für „Scrubadub 2000“ sein sollte, die auf dem „Ultramop“-Beispiel im Systemsetup modelliert ist.

## Experimentieren mit Parametern

Sie haben untersucht, wie Systemnachricht, Beispiele und Eingabeaufforderungen dazu beitragen können, die vom Modell zurückgegebenen Antworten zu verfeinern. Sie können auch Parameter verwenden, um das Modellverhalten zu steuern.

1. Wählen Sie im Bereich **Konfiguration** die Registerkarte **Parameter** aus, und legen Sie die folgenden Parameterwerte fest:
    - **Maximale Antwort**: 1.000
    - **Temperature**: 1

1. Verwenden Sie im Abschnitt **Chatsitzung** die Schaltfläche **Chat löschen**, um die Chatsitzung zurückzusetzen. Geben Sie dann die Benutzerabfrage `Create an advertisement for a cleaning sponge` ein, und überprüfen Sie die Antwort. Der resultierende Werbetext sollte maximal 1000 Texttoken und einige kreative Elemente enthalten, z. B. das Modell hat vielleicht einen Produktnamen für den Schwamm erfunden und einige Behauptungen über seine Eigenschaften aufgestellt.
1. Verwenden Sie die Schaltfläche **Chat löschen**, um die Chatsitzung erneut zurückzusetzen, geben Sie dann dieselbe Abfrage wie zuvor (`Create an advertisement for a cleaning sponge`) erneut ein, und überprüfen Sie die Antwort. Die Antwort kann sich von der vorherigen Antwort unterscheiden.
1. Ändern Sie im Bereich **Konfiguration** auf der Registerkarte **Parameter** den **Temperatur**-Parameterwert in 0.
1. Verwenden Sie im Abschnitt **Chatsitzung** die Schaltfläche **Chat löschen**, um die Chatsitzung erneut zurückzusetzen, geben Sie dann dieselbe Abfrage wie zuvor (`Create an advertisement for a cleaning sponge`) erneut ein, und überprüfen Sie die Antwort. Diesmal ist die Antwort vielleicht nicht ganz so kreativ.
1. Verwenden Sie die Schaltfläche **Chat löschen**, um die Chatsitzung einmal zurückzusetzen, geben Sie dann dieselbe Abfrage wie zuvor (`Create an advertisement for a cleaning sponge`) erneut ein, und überprüfen Sie die Antwort, die der vorherigen Antwort sehr ähnlich (wenn nicht identisch) sein sollte.

    Der **Temperatur**-Parameter steuert den Grad der Kreativität des Modells bei der Generierung einer Antwort. Ein niedriger Wert führt zu einer konsistenten Reaktion mit wenig zufälliger Variation, während ein hoher Wert das Modell ermutigt, kreative Elemente zur Ausgabe hinzuzufügen, was sich auf die Richtigkeit und Realität der Antwort auswirken kann.

## Bereitstellen Ihres Modells in einer Web-App

Nachdem Sie nun einige der Funktionen eines generativen KI-Modells im Azure OpenAI Studio-Playground untersucht haben, können Sie eine Azure Web App bereitstellen, um eine einfache KI-Agent-Schnittstelle zu bieten, über die Benutzer mit dem Modell chatten können.

1. Wählen Sie oben rechts auf der **Chat**-Playground-Seite im Menü **Bereitstellen an** die Option **Eine neue Web-App** aus.
1. Erstellen Sie im Dialogfeld **In einer Web-App bereitstellen** eine neue Web-App mit den folgenden Einstellungen:
    - **Name**: *Ein eindeutiger Name*
    - **Abonnement:** *Geben Sie Ihr Azure-Abonnement an.*
    - **Ressourcengruppe:** *Die Ressourcengruppe, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Standorte**: *Die Region, in der Sie Ihre Azure OpenAI-Ressource bereitgestellt haben*
    - **Tarif**: Free (F1): *(Wenn diese Option nicht verfügbar ist, wählen Sie Basic (B1) aus.)*
    - **Chatverlauf in der Web-App aktivieren**: <u>Nicht</u> ausgewählt
    - **Ich erkenne an, dass Web-Apps mein Konto belasten werden**: Ausgewählt
1. Bereitstellen der neuen Web-App und Warten auf den Abschluss der Bereitstellung (dies kann 10 Minuten dauern)
1. Nachdem Ihre Web-App erfolgreich bereitgestellt wurde, verwenden Sie die Schaltfläche oben rechts auf der **Chat**-Playground-Seite, um die Web-App zu starten. Das Starten der App kann einige Minuten dauern. Wenn Sie dazu aufgefordert werden, akzeptieren Sie die Berechtigungsanforderung.
1. Geben Sie die folgende Chatnachricht in die Web-App ein:

    ```prompt
    Write an advertisement for the new "WonderWipe" cloth that attracts dust particulates and can be used to clean any household surface.
    ```

1. Überprüfen Sie die Antwort.

    > **Hinweis:** Sie haben das *Modell* in einer Web-App bereitgestellt, aber diese Bereitstellung enthält nicht die Systemeinstellungen und Parameter, die Sie im Playground festgelegt haben; daher spiegelt die Antwort möglicherweise nicht die Beispiele wider, die Sie im Playground angegeben haben. In einem echten Szenario fügen Sie Ihrer Anwendung Logik hinzu, um die Eingabeaufforderung so zu ändern, dass sie die entsprechenden Kontextdaten für die Art der Antwort enthält, die Sie generieren möchten. Diese Art von Anpassung liegt außerhalb des Umfangs dieser Einführungsübung, aber Sie können sich in anderen Übungen und Produktdokumentationen über Prompt Engineering-Techniken und Azure OpenAI-APIs informieren.

1. Wenn Sie mit dem Experimentieren mit Ihrem Modell in der Web-App fertig sind, schließen Sie die Registerkarte „Web-App“ in Ihrem Browser, um zu Azure OpenAI Studio zurückzukehren.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im **Azure-Portal** auf `https://portal.azure.com` zu löschen.
