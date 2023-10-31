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
    - **Ressourcengruppe**: Verwenden Sie entweder eine bereits vorhandene Ressourcengruppe oder erstellen Sie eine mit einem Namen Ihrer Wahl.
    - **Region**: Wählen Sie eine beliebige verfügbare Region aus.
    - **Name**: Wählen Sie einen Namen Ihrer Wahl aus.
    - **Tarif**: Standard S0.
3. Warten Sie, bis die Bereitstellung abgeschlossen ist. Wechseln Sie dann zur bereitgestellten Azure OpenAI-Ressource im Azure-Portal.

## Bereitstellen eines Modells

Um mit der Azure OpenAI-API-Instanz chatten zu können, müssen Sie zunächst ein Modell bereitstellen, das in **Azure OpenAI Studio** verwendet werden kann. Nach der Bereitstellung verwenden wir das Modell mit dem Playground. Zudem verwenden wir unsere Daten, um eine Basis für die Antworten zu schaffen.

1. Verwenden Sie auf der Seite **Übersicht** für Ihre Azure OpenAI-Ressourcen die Schaltfläche **Erkunden**, um Azure OpenAI Studio auf einer neuen Browserregisterkarte zu öffnen. Alternativ können Sie direkt zu [Azure OpenAI Studio](https://oai.azure.com/?azure-portal=true) navigieren.
2. Erstellen Sie in Azure OpenAI Studio eine neue Bereitstellung mit den folgenden Einstellungen:
    - **Modellname**: gpt-35-turbo
    - **Modellversion**: *Standardversion verwenden*
    - **Bereitstellungsname**: text-turbo

## Beobachten des normalen Chatverhaltens ohne Hinzufügen eigener Daten

Bevor Sie Azure OpenAI mit Ihren Daten verknüpfen, sollten Sie zunächst beobachten, wie das Basismodell auf Abfragen ohne Basisdaten reagiert.

1. Navigieren Sie zum **Chat**-Playground, und stellen Sie sicher, dass das von Ihnen bereitgestellte `gpt-35-turbo`-Modell im **Konfigurationsbereich** ausgewählt ist (dies sollte die Standardeinstellung sein, wenn Sie nur über ein bereitgestelltes Modell verfügen).
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
1. Sie müssen ein Speicherkonto und eine Azure Cognitive Search-Ressource erstellen. Wählen Sie in der Dropdownliste für die Speicherressource die Option **Neue Azure Blob Storage-Ressource erstellen** aus, und erstellen Sie ein Speicherkonto mit den folgenden Einstellungen. Alles, was nicht angegeben ist, wird als Standard beibehalten.

    - **Abonnement**: *Dasselbe Abonnement wie Ihre Azure OpenAI-Ressource*
    - **Ressourcengruppe**: *Dieselbe Ressourcengruppe wie Ihre Azure OpenAI-Ressource*
    - **Speicherkontoname**: *Geben Sie einen global eindeutigen Namen ein*.
    - **Region**: *Dieselbe Region wie Ihre Azure OpenAI-Ressource*
    - **Redundanz**: Lokal redundanter Speicher (LRS)

1. Kehren Sie nach der Erstellung der Ressource zu Azure OpenAI Studio zurück, und wählen Sie **Neue Azure Cognitive Search-Ressource erstellen** mit den folgenden Einstellungen aus. Alles, was nicht angegeben ist, wird als Standard beibehalten.

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
    - **Azure Cognitive Search-Ressource auswählen:** *Wählen Sie die von Ihnen erstellte Suchressource aus.*
    - **Indexnamen eingeben:** margiestravel
    - **Hinzufügen der Vektorsuche zu dieser Suchressource**: deaktiviert
    - **Ich verstehe, dass die Verbindung zu einem Azure Cognitive Search-Konto eine Nutzung meines Kontos zur Folge hat**: aktiviert

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

## Bereinigung

Wenn Sie mit Ihrer Azure OpenAI-Ressource fertig sind, denken Sie daran, die gesamte Ressource im [Azure-Portal](https://portal.azure.com/?azure-portal=true) zu löschen. Stellen Sie sicher, dass Sie auch das Speicherkonto und die Suchressource einschließen, da für diese relativ hohe Kosten entstehen können.
