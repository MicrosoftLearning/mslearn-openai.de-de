---
lab:
  title: Erste Schritte mit Azure OpenAI
---

# Erste Schritte mit Azure OpenAI Service

Azure OpenAI Service bringt die von OpenAI entwickelten generativen KI-Modelle auf die Azure-Plattform und ermöglicht Ihnen die Entwicklung leistungsstarker KI-Lösungen, die von der Sicherheit, Skalierbarkeit und Integration anderer Dienste der Azure-Cloudplattform profitieren. In dieser Übung erfahren Sie, wie Sie die Arbeit mit Azure OpenAI beginnen, indem Sie den Dienst als Azure-Ressource bereitstellen und Azure OpenAI Studio verwenden, um OpenAI-Modelle bereitzustellen und zu untersuchen.

Diese Übung dauert ca. **30** Minuten.

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

## Bereitstellen eines Modells

Azure OpenAI bietet ein webbasiertes Portal namens **Azure OpenAI Studio**, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können. Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Erkunden**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modellname**: text-davinci-003
    - **Bereitstellungsname**: text-davinci

> **Hinweis**: Azure OpenAI umfasst mehrere Modelle, die jeweils für ein anderes Verhältnis von Funktionen und Leistung optimiert sind. In dieser Übung beginnen Sie mit dem **Davinci-Modell** aus der **GPT-3-Familie** von Textgenerierungsmodellen. **text-davinci-003** ist ein gutes allgemeines Modell zum Zusammenfassen und Generieren natürlicher Sprache. Weitere Informationen zu den verfügbaren Modellen in Azure OpenAI finden Sie unter [Modelle](https://learn.microsoft.com/azure/cognitive-services/openai/concepts/models) in der Azure OpenAI-Dokumentation.

## Erkunden eines Modells im Playground „Vervollständigungen“

*Playgrounds* sind nützliche Oberflächen in Azure OpenAI Studio, auf denen Sie mit Ihren bereitgestellten Modellen experimentieren können, ohne eine eigene Clientanwendung entwickeln zu müssen.

1. Wählen Sie in Azure OpenAI Studio im linken Bereich unter **Playground** die Option **Vervollständigungen** aus.
2. Stellen Sie auf der Seite **Vervollständigungen** sicher, dass die Bereitstellung **text-davinci** ausgewählt ist, und wählen Sie dann in der Liste **Beispiele** die Option **Artikel zusammenfassen (abstrakt)** aus.

    Das Beispiel mit dem Zusammenfassungstext besteht aus einer *Eingabeaufforderung*, die einen Text enthält, der mit **Zusammenfassung des folgenden Texts angeben...** beginnt. Die Eingabeaufforderung, die mit diesem Satz beginnt, weist das Modell an, den folgenden Textblock zusammenzufassen.

3. Notieren Sie sich unten auf der Seite die Anzahl der im Text erkannten *Token*. Token sind die grundlegenden Einheiten einer Eingabeaufforderung, vergleichbar mit Wörtern oder Wortteilen im Text.
4. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung an das Modell zu übermitteln und eine Antwort abzurufen.

    Die Antwort besteht aus einer Zusammenfassung des ursprünglichen Texts. Die Zusammenfassung sollte die wichtigsten Punkte aus dem ursprünglichen Text weniger ausführlich wiedergeben.

5. Verwenden Sie die Schaltfläche **Erneut generieren**, um die Eingabeaufforderung erneut zu übermitteln. Beachten Sie, dass die Antwort von der ursprünglichen abweichen kann. Ein generatives KI-Modell kann bei jedem Aufruf eine neue Sprache erzeugen.
6. Fügen Sie unter der zusammengefassten Antwort eine neue Zeile hinzu, und geben Sie den folgenden Text ein:

    *Wie hat sich KI entwickelt?*

7. Verwenden Sie die Schaltfläche **Generieren**, um die neue Eingabeaufforderung zu übermitteln und die Antwort zu überprüfen. Die vorherige Eingabeaufforderung und die dazugehörige Antwort stellen Kontext in einem laufenden Dialog mit dem Modell bereit, sodass das Modell eine geeignete Antwort auf Ihre Frage generieren kann.
8. Ersetzen Sie den gesamten Inhalt der Eingabeaufforderungen durch den folgenden Text:

    *Fassen Sie den folgenden Text so zusammen, dass der Hauptgedanke wiedergegeben wird.* 
    
    *Azure OpenAI Service bietet REST-API-Zugriff auf die leistungsstarken Sprachmodelle von OpenAI, einschließlich der Modellreihen GPT-4, Codex und Embeddings. Diese Modelle können leicht an Ihre spezifische Aufgabe angepasst werden, einschließlich, aber nicht beschränkt auf Inhaltsgenerierung, Zusammenfassung, semantische Suche und die Übersetzung natürlicher Sprache in Code. Benutzer*innen können über REST-APIs, das Python-SDK oder unsere webbasierte Benutzeroberfläche in Azure OpenAI Studio auf den Dienst zugreifen.*

9. Verwenden Sie die Schaltfläche **Generieren**, um die neue Eingabeaufforderung zu übermitteln und zu überprüfen, ob das Modell den Text ordnungsgemäß zusammenfasst.

## Verwenden eines Modells zum Klassifizieren von Text

Bisher haben Sie erfahren, wie Sie ein Modell verwenden, um Text zusammenzufassen. Die generativen Modelle in Azure OpenAI können für mehrere Arten von Aufgaben verwendet werden. Sehen wir uns ein anderes Beispiel an, nämlich die *Textklassifizierung*.

1. Stellen Sie auf der Seite **Vervollständigungen** sicher, dass die Bereitstellung **text-davinci** ausgewählt ist, und wählen Sie dann in der Liste **Beispiele** die Option **Text klassifizieren** aus.

    Die Eingabeaufforderung zum Klassifizieren von Textbeispielen beschreibt den Kontext für das Modell in Form einer Anweisung zum Klassifizieren eines Nachrichtenartikels in eine Kategorie aus einer Auswahl von Kategorien. Anschließend wird der Text für den Nachrichtenartikel (mit dem Präfix *News arcticle:* ) angegeben und endet mit *Classified Category:* . Das Modell soll die letzte Zeile der Eingabeaufforderung „vervollständigen“, indem die entsprechende Kategorie vorhergesagt wird.

2. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung an das Modell zu übermitteln und eine Antwort abzurufen. Das Modell sollte eine geeignete Kategorie für den Nachrichtenartikel vorhersagen.
3. Fügen Sie unter der vorhergesagten Kategorie den folgenden Text hinzu:

    *Nachrichtenartikel: Microsoft veröffentlicht Azure OpenAI-Dienst. Die Microsoft Corporation hat einen Azure-Dienst veröffentlicht, der OpenAI-Modelle für Anwendungsentwickler*innen verfügbar macht, die Apps und Dienste in der Azure-Cloud erstellen.*

    *Klassifizierte Kategorie:*

4. Verwenden Sie die Schaltfläche **Generieren**, um den Dialog mit dem Modell fortzusetzen und eine geeignete Kategorisierung für den neuen Nachrichtenartikel zu generieren.

## Untersuchen von Eingabeaufforderungen und Parametern

Bis jetzt haben Sie sich bei der Eingabeaufforderung an den Beispielen orientiert, die in Azure OpenAI Studio bereitgestellt werden. Lassen Sie uns etwas anderes ausprobieren.

1. Ersetzen Sie den gesamten Text im Eingabeaufforderungsbereich durch den folgenden Text:

    *Sie sind eine Lehrkraft, die einen Test für Lernende erstellt.*

    *Schreiben Sie drei Multiple-Choice-Fragen auf der Grundlage des folgenden Texts.*

    *Die meisten Lösungen für maschinelles Sehen basieren auf Modellen für maschinelles Lernen, die auf visuelle Eingaben von Kameras, Videos oder Bildern angewendet werden können.*

    *\- Bei der Bildklassifizierung wird ein Modell für maschinelles Lernen trainiert, Bilder anhand ihres Inhalts zu klassifizieren. Beispielsweise können Sie in einer Verkehrsüberwachungslösung ein Bildklassifizierungsmodell verwenden, um Bilder basierend auf dem darin enthaltenen Fahrzeugtyp zu klassifizieren (z. B. Taxis, Busse, Radfahrer usw.).*

    *\- Objekterkennungsmodelle für maschinelles Lernen werden so trainiert, dass sie einzelne Objekte in einem Bild klassifizieren und ihre Position durch ein umgebendes Feld kenntlich machen. Beispielsweise kann eine Verkehrsüberwachungslösung die Objekterkennung verwenden, um die Positionen verschiedener Fahrzeugklassen zu erkennen.*

    *\- Die semantische Segmentierung ist eine fortschrittliche Technik für maschinelles Lernen, bei der einzelne Pixel im Bild anhand des Objekt klassifiziert werden, dem sie zugeordnet werden können. Beispielsweise kann eine Verkehrsüberwachungslösung Verkehrsbilder mit sogenannten Maskenschichten überlagern, um mit bestimmten Farben verschiedene Fahrzeuge hervorzuheben.*

2. Legen Sie im Bereich **Parameter** die folgenden Parameterwerte fest:
    - **Temperatur**: 0
    - **Maximale Länge (Token)** : 500
    - **Vorabantworttext**: Automatisch generierte Fragen Führen Sie vor der Verwendung in einem Test eine Überprüfung durch:
3. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung zu übermitteln und die Ergebnisse zu überprüfen. Dies sollte aus dem Wert im Parameter *Vorabantworttext* bestehen, gefolgt von Multiple-Choice-Fragen, die eine Lehrkraft verwenden kann, um die Lernenden zum maschinellen Sehen in der Eingabeaufforderung zu testen. Die Gesamtantwort sollte kleiner sein als die maximale Länge, die Sie als Parameter angegeben haben.

    Beachten Sie die folgenden Informationen zu den verwendeten Eingabeaufforderungen und Parametern:

    - Die Eingabeaufforderung enthält Kontextinformationen in natürlicher Sprache, die dem Modell vorgeben, wie es sich zu verhalten hat. Konkret heißt es, dass das Modell die Rolle einer Lehrkraft einnehmen sollte, die einen Test für Lernende erstellt.
    - Zu den Parametern gehört *Temperature*, der den Grad steuert, in dem die Antwortgenerierung ein Element der Zufälligkeit enthält. Der in Ihrer Übermittlung verwendete Wert von **0** minimiert die Zufälligkeit, was zu stabilen, vorhersehbaren Antworten führt.

4. Verwenden Sie die Schaltfläche **Erneut generieren**, um die Antwort erneut zu generieren. Sie sollte der vorherigen Antwort ähneln.
5. Ändern Sie den **Temperaturparameterwert** in **0,9**, und verwenden Sie dann die Schaltfläche **Erneut generieren**, um die Antwort erneut zu generieren. Dieses Mal sollte der erhöhte Grad an Zufälligkeit zu einer anderen Reaktion führen. Es ist jedoch wahrscheinlicher, dass die Fragen Ungenauigkeiten enthalten als die in der zuvor erstellten Antwort.

## Erkunden der Codegenerierung

Das von Ihnen bereitgestellte **text-davinci**-Modell ist ein gutes allgemeines Modell, das die meisten Aufgaben gut verarbeiten kann. In einigen Fällen ist es jedoch besser, ein Modell auszuwählen, das für eine bestimmte Art von Aufgabe optimiert ist. Beispielsweise können Azure OpenAI-Modelle verwendet werden, um Computercode anstelle von Text in natürlicher Sprache zu generieren, und einige Modelle wurden für diese Aufgabe optimiert.

1. Zeigen Sie in Azure OpenAI Studio die Seite **Modelle** an, auf der alle verfügbaren Modelle in Ihrer Azure OpenAI Service-Ressource aufgelistet werden.
2. Wählen Sie das Modell **code-davinci-002** aus, und verwenden Sie die Schaltfläche **Modell bereitstellen**, um es mit dem Bereitstellungsnamen **code-davinci** bereitzustellen.
3. Nachdem die Bereitstellung abgeschlossen ist, zeigen Sie in Azure OpenAI Studio die Seite **Bereitstellungen** an, auf der die von Ihnen bereitgestellten Modelle aufgeführt sind.
4. Wählen Sie die Modellimplementierung **code-davinci** aus, und verwenden Sie die Schaltfläche **In Playground öffnen**, um sie im Playground zu öffnen.
5. Stellen Sie auf der Seite **Vervollständigungen** sicher, dass die Bereitstellung **code-davinci** ausgewählt ist, und wählen Sie dann in der Liste **Beispiele** die Option **Natürliche Sprache zu SQL**.

    Die Beispieleingabeaufforderung für SQL in natürlicher Sprache enthält Details zu Tabellen in einer Datenbank und eine Beschreibung der erforderlichen Abfrage, gefolgt von dem `SELECT`-Schlüsselwort. Das Modell soll die `SELECT`-Anweisung vervollständigen, um eine Abfrage zu erstellen, die die Anforderung erfüllt.

6. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung an das Modell zu übermitteln und eine Antwort abzurufen, die aus einer `SELECT`-SQL-Abfrage besteht.
7. Ersetzen Sie die gesamte Eingabeaufforderung und Antwort durch die folgende neue Eingabeaufforderung:

    *# Python 3*

    *# Erstellen einer Funktion zum Ausgeben von „Hello“ und einer angegebenen Zeichenfolge*

    *def print_hello(s):*

8. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung zu übermitteln und den generierten Code anzuzeigen. Die Eingabeaufforderung enthielt einen Hinweis auf die zu generierende Programmiersprache (Python 3), einen Kommentar, der die gewünschte Funktionalität beschreibt, und den ersten Teil der Funktionsdefinition. Das **code-davinci**-Modell sollte die Funktion mit entsprechendem Python-Code vervollständigt haben.

## Erkunden von Modellen für Chats

ChatGPT ist ein von OpenAI entwickelter Chatbot, der in einem Konversationsszenario eine Vielzahl von Antworten in natürlicher Sprache geben kann. Das von ChatGPT und APIs für die Verwendung verwendete Modell ist in Azure OpenAI enthalten.

1. Zeigen Sie in Azure OpenAI Studio die Seite **Modelle** an, auf der alle verfügbaren Modelle in Ihrer Azure OpenAI Service-Ressource aufgelistet werden.
2. Wählen Sie das Modell **gpt-35-turbo** aus, und verwenden Sie die Schaltfläche **Modell bereitstellen**, um es mit dem Bereitstellungsnamen **gpt-chat** bereitzustellen.
3. Nachdem das Modell bereitgestellt wurde, wählen Sie im Abschnitt **Playground** die Seite **Chat** aus, und stellen Sie sicher, dass das **gpt-chat**-Modell im Bereich auf der rechten Seite ausgewählt ist.
4. Ersetzen Sie im Abschnitt **Assistenteneinrichtung** im Feld **Systemmeldung** den aktuellen Text durch Folgendes:

    *Das System ist eine KI-Lehrkraft, die Menschen hilft, mehr über KI zu lernen.*

5. Klicken Sie unterhalb des Felds **Systemmeldung** auf **Beispiele hinzufügen**, und geben Sie die folgende Nachricht und Antwort in die entsprechenden Felder ein:

    Benutzer*in: *Was sind verschiedene Arten von künstlicher Intelligenz?*

    Assistent: *Es gibt drei Hauptarten von künstlicher Intelligenz: Schwache KI (z. B. virtuelle Assistenten wie Siri oder Alexa, Bilderkennungssoftware und Spamfilter), starke KI (KI, die so intelligent wie ein Mensch sein soll – diese Art von KI existiert derzeit nicht und ist ein rein theoretisches Konzept) und künstliche Superintelligenz (KI, die intelligenter ist als jeder Mensch und Aufgaben erfüllen kann, die das menschliche Verständnis übersteigen – auch diese Art von KI ist ein rein theoretisches Konzept und wurde noch nicht entwickelt).*

    > **Hinweis**: Einige wenige Beispiele werden verwendet, um dem Modell Beispiele für die zu erwartenden Antworttypen zu geben. Das Modell versucht, den Ton und den Stil der Beispiele in seinen eigenen Antworten wiederzugeben.

6. Speichern Sie die Änderungen, um eine neue Sitzung zu starten, und legen Sie den Verhaltenskontext des Chatsystems fest.

7. Geben Sie im Textfeld unten auf der Seite den folgenden Text ein:

    *Was ist künstliche Intelligenz?*

8. Verwenden Sie die Schaltfläche **Senden**, um die Nachricht zu übermitteln und die Antwort anzuzeigen.

    > **Hinweis**: Sie erhalten möglicherweise die Antwort, dass die API-Bereitstellung noch nicht abgeschlossen ist. Wenn dies der Fall ist, warten Sie ein paar Minuten, und versuchen Sie es erneut.

9. Überprüfen Sie die Antwort, und senden Sie dann die folgende Nachricht, um die Unterhaltung fortzusetzen:

    *Wie hängt sie mit dem maschinellen Lernen zusammen?*

10. Überprüfen Sie die Antwort, und achten Sie darauf, dass der Kontext der vorherigen Interaktion erhalten bleibt (damit das Modell versteht, dass sich „sie“ auf die künstliche Intelligenz bezieht).

In dieser Übung haben Sie erfahren, wie Sie Azure OpenAI Service in einem Azure-Abonnement bereitstellen und Azure OpenAI Studio zum Bereitstellen und Erkunden von Modellen verwenden.

Als Entwickler*in können Sie die REST-Schnittstelle und sprachspezifische APIs verwenden, um Apps und Dienste zu erstellen, die Azure OpenAI-Modelle nutzen. Dadurch können Sie generative KI-Modelle in Ihren eigenen Anwendungen nutzen. Die Codierung für Azure OpenAI wird in anderen Übungen behandelt.
