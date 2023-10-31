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
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits vorhandene Ressourcengruppe oder erstellen Sie eine mit einem Namen Ihrer Wahl.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Azure OpenAI bietet ein webbasiertes Portal namens **Azure OpenAI Studio**, das Sie zum Bereitstellen, Verwalten und Erkunden von Modellen verwenden können. Sie beginnen damit, Azure OpenAI kennenzulernen, indem Sie Azure OpenAI Studio verwenden, um ein Modell bereitzustellen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressource die Schaltfläche **Zu Azure OpenAI Studio wechseln**, um Azure OpenAI Studio in einer neuen Browserregisterkarte zu öffnen.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modell**: gpt-35-turbo
    - **Modellversion**: Automatische Aktualisierung auf die Standardeinstellung
    - **Bereitstellungsname**: my-gpt-model

> **Hinweis**: Azure OpenAI umfasst mehrere Modelle, die jeweils für ein anderes Verhältnis von Funktionen und Leistung optimiert sind. In dieser Übung verwenden Sie das **GPT-35-Turbo**-Modell, das ein gutes allgemeines Modell zum Zusammenfassen und Generieren natürlicher Sprache und Code ist. Weitere Informationen zu den verfügbaren Modellen in Azure OpenAI finden Sie unter [Modelle](https://learn.microsoft.com/azure/cognitive-services/openai/concepts/models) in der Azure OpenAI-Dokumentation.

## Erkunden eines Modells im Playground „Vervollständigungen“

*Playgrounds* sind nützliche Oberflächen in Azure OpenAI Studio, auf denen Sie mit Ihren bereitgestellten Modellen experimentieren können, ohne eine eigene Clientanwendung entwickeln zu müssen.

1. Wählen Sie in Azure OpenAI Studio im linken Bereich unter **Playground** die Option **Vervollständigungen** aus.
2. Stellen Sie auf der Seite **Vervollständigungen** sicher, dass die Bereitstellung **my-gpt-model** ausgewählt ist, und wählen Sie dann in der Liste **Beispiele** die Option **Quiz generieren** aus.

    Das Zusammenfassungstextbeispiel besteht aus einer *Eingabeaufforderung*, die Text bereitstellt, um dem Modell mitzuteilen, welche Art von Antwort erforderlich ist, und sie enthält einige kontextbezogene Informationen.

3. Notieren Sie sich unten auf der Seite die Anzahl der im Text erkannten *Token*. Token sind die grundlegenden Einheiten einer Eingabeaufforderung, vergleichbar mit Wörtern oder Wortteilen im Text.
4. Verwenden Sie die Schaltfläche **Generieren**, um die Eingabeaufforderung an das Modell zu übermitteln und eine Antwort abzurufen.

    Die Antwort besteht aus einem Quiz, das auf dem Beispiel in der Eingabeaufforderung basiert.

5. Verwenden Sie die Schaltfläche **Erneut generieren**, um die Eingabeaufforderung erneut zu übermitteln. Beachten Sie, dass die Antwort von der ursprünglichen abweichen kann. Ein generatives KI-Modell kann bei jedem Aufruf eine neue Sprache erzeugen.
6. Verwenden Sie die Schaltfläche **Code anzeigen**, um den Code anzuzeigen, den eine Clientanwendung zum Übermitteln der Eingabeaufforderung verwenden würde. Sie können Ihre bevorzugte Programmiersprache auswählen. Die Eingabeaufforderung enthält den Text, den Sie an das Modell übermittelt haben. Die Anforderung wird an die *Completions*-API (API für Vervollständigungen) für Ihren Azure OpenAI-Dienst gesendet.

## Verwenden des Chat-Playgrounds

Der *Chat*-Playground bietet eine Chatbotschnittstelle für GPT 3.5 und höhere Modelle. Er verwendet die *ChatCompletions*-API anstelle der älteren *Completions*-API.

1. Wählen Sie im Abschnitt **Playground** die Seite **Chat** aus, und stellen Sie sicher, dass das **my-gpt-model**-Modell im Konfigurationsbereich auf der rechten Seite ausgewählt ist.
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
    - **Maximale Länge (Token)** : 500

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
