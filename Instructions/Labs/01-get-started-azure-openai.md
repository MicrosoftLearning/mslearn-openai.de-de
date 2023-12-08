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
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits bestehende Ressourcengruppe, oder erstellen Sie eine neue Ressourcengruppe mit einem beliebigen Namen.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Azure OpenAI bietet ein webbasiertes Portal namens **Azure OpenAI Studio**, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können. Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Zu Azure OpenAI Studio wechseln**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Ihre vorhandenen Modellbereitstellungen finden Sie in Azure OpenAI Studio auf der Seite **Bereitstellungen**. Falls noch nicht vorhanden, erstellen Sie eine neue Bereitstellung des **gpt-35-turbo-16k**-Modells mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo-16k
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: *Wählen Sie einen Namen Ihrer Wahl aus*
    - **Erweiterte Optionen**
        - **Inhaltsfilter**: Standard
        - **Ratenlimit für Token pro Minute**: 5K\*
        - **Dynamisches Kontingent aktivieren**: Aktiviert

    > \* Ein Ratenlimit von 5.000 Token pro Minute ist mehr als ausreichend, um diese Aufgabe zu erfüllen und gleichzeitig Kapazität für andere Personen zu schaffen, die das gleiche Abonnement nutzen.

> **Hinweis**: In einigen Regionen zeigt die Schnittstelle zur Bereitstellung des neuen Modells die Option **Modellversion** nicht an. Lassen Sie sich in diesem Fall nicht beunruhigen und fahren Sie fort, ohne die Option festzulegen

## Verwenden des Chat-Playgrounds

Der *Chat*-Playground bietet eine Chatbotschnittstelle für GPT 3.5 und höhere Modelle. Er verwendet die *ChatCompletions*-API anstelle der älteren *Completions*-API.

1. Wählen Sie im Bereich **Playground** die Seite **Chat** und vergewissern Sie sich, dass Ihr Modell im Konfigurationsbereich ausgewählt ist.
2. Ersetzen Sie im Abschnitt **Assistenteneinrichtung** im Feld **Systemmeldung** den aktuellen Text durch folgende Anweisung: `The system is an AI teacher that helps people learn about AI`.

3. Klicken Sie unterhalb des Felds **Systemmeldung** auf **Beispiele hinzufügen**, und geben Sie die folgende Nachricht und Antwort in die entsprechenden Felder ein:

    - **Benutzer:** `What are different types of artificial intelligence?`
    - **Assistent:** `There are three main types of artificial intelligence: Narrow or Weak AI (such as virtual assistants like Siri or Alexa, image recognition software, and spam filters), General or Strong AI (AI designed to be as intelligent as a human being. This type of AI does not currently exist and is purely theoretical), and Artificial Superintelligence (AI that is more intelligent than any human being and can perform tasks that are beyond human comprehension. This type of AI is also purely theoretical and has not yet been developed).`

    > **Hinweis**: Einige wenige Beispiele werden verwendet, um dem Modell Beispiele für die zu erwartenden Antworttypen zu geben. Das Modell versucht, den Ton und den Stil der Beispiele in seinen eigenen Antworten wiederzugeben.

4. Speichern Sie die Änderungen, um eine neue Sitzung zu starten, und legen Sie den Verhaltenskontext des Chatsystems fest.
5. Geben Sie im Abfragefeld unten auf der Seite den Text `What is artificial intelligence?` ein.
6. Verwenden Sie die Schaltfläche **Senden**, um die Nachricht zu übermitteln und die Antwort anzuzeigen.

    > **Hinweis**: Sie erhalten möglicherweise die Antwort, dass die API-Bereitstellung noch nicht abgeschlossen ist. Wenn dies der Fall ist, warten Sie ein paar Minuten, und versuchen Sie es erneut.

7. Überprüfen Sie die Antwort, und senden Sie dann die folgende Nachricht, um die Unterhaltung fortzusetzen: `How is it related to machine learning?`
8. Überprüfen Sie die Antwort, und achten Sie darauf, dass der Kontext der vorherigen Interaktion erhalten bleibt (damit das Modell versteht, dass sich „sie“ auf die künstliche Intelligenz bezieht).
9. Verwenden Sie die Schaltfläche **Code anzeigen**, um den Code für die Interaktion anzuzeigen. Die Eingabeaufforderung besteht aus der *Systemnachricht*, den wenigen Beispielen der *Benutzer*- und *Assistentnachrichten* und der Sequenz von *Benutzer*- und *Assistentnachrichten* in der bisherigen Chatsitzung.

## Untersuchen von Eingabeaufforderungen und Parametern

Sie können die Eingabeaufforderung und die Parameter verwenden, um die Wahrscheinlichkeit zu maximieren, dass die benötigte Antwort generiert wird.

1. Legen Sie im Bereich **Parameter** die folgenden Parameterwerte fest:
    - **Temperatur**: 0
    - **Maximale Antwort**: 500

2. Übermitteln Sie folgende Nachricht:

    ```
    Write three multiple choice questions based on the following text.

    Most computer vision solutions are based on machine learning models that can be applied to visual input from cameras, videos, or images.*

    - Image classification involves training a machine learning model to classify images based on their contents. For example, in a traffic monitoring solution you might use an image classification model to classify images based on the type of vehicle they contain, such as taxis, buses, cyclists, and so on.*

    - Object detection machine learning models are trained to classify individual objects within an image, and identify their location with a bounding box. For example, a traffic monitoring solution might use object detection to identify the location of different classes of vehicle.*

    - Semantic segmentation is an advanced machine learning technique in which individual pixels in the image are classified according to the object to which they belong. For example, a traffic monitoring solution might overlay traffic images with "mask" layers to highlight different vehicles using specific colors.
    ```

3. Überprüfen Sie die Ergebnisse, die aus Multiple-Choice-Fragen bestehen sollten, die eine Lehrkraft verwenden kann, um Schüler*innen oder Student*innen zu Themen zu maschinellem Sehen in der Eingabeaufforderung zu testen. Die Gesamtantwort sollte kleiner sein als die maximale Länge, die Sie als Parameter angegeben haben.

    Beachten Sie die folgenden Informationen zu den verwendeten Eingabeaufforderungen und Parametern:

    - Die Eingabeaufforderung gibt ausdrücklich an, dass die gewünschte Ausgabe drei Multiple-Choice-Fragen enthalten sollte.
    - Zu den Parametern gehört *Temperature*, der den Grad steuert, in dem die Antwortgenerierung ein Element der Zufälligkeit enthält. Der in Ihrer Übermittlung verwendete Wert von **0** minimiert die Zufälligkeit, was zu stabilen, vorhersehbaren Antworten führt.

## Erkunden der Codegenerierung

Zusätzlich zum Generieren natürlicher Sprachantworten können Sie GPT-Modelle verwenden, um Code zu generieren.

1. Wählen Sie im Bereich **Assistenteneinrichtung** die Vorlage **Leeres Beispiel** aus, um die Systemmeldung zurückzusetzen.
2. Geben Sie die Systemmeldung `You are a Python developer.` ein, und speichern Sie die Änderungen.
3. Wählen Sie im Bereich **Chatsitzung** die Option **Chat löschen** aus, um den Chatverlauf zu löschen und eine neue Sitzung zu starten.
4. Übermitteln Sie die folgende Benutzernachricht:

    ```
    Write a Python function named Multiply that multiplies two numeric parameters.
    ```

5. Überprüfen Sie die Antwort, die Python-Beispielcode enthalten sollte, der die Anforderung in der Eingabeaufforderung erfüllt.

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die Bereitstellung oder die gesamte Ressource im [Azure-Portal](https://portal.azure.com) zu löschen.
