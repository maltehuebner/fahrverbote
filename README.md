# Fahrverbote

Dieses Repository enthält Informationen im GeoJSON-Format über Fahrverbote für Verbrennungsmaschinen in deutschen Großstädten.

## Mitmachen

Erstelle bitte einen Pull-Request, um einen Bereich zu korrigieren, neue Straßen zu ergänzen oder eine neue Stadt hinzuzufügen.

## Besonderheiten

Momentan ist die Anwendung unter [fahrverbote.info](https://fahrverbote.info/) noch ein bisschen hacky und erwartet zusätzliche Informationen unterhalb einer `FeatureCollection` und unterhalb eines `Feature`.

Die `FeatureCollection`, die Daten zu einer jeweiligen Stadt enthält, muss zusätzlich noch den Namen der Stadt und eine kurze Beschreibung enthalten:

    "properties": {
      "name": "Stuttgart",
      "description": "In Stuttgart könnte bereits Anfang 2019 ein großflächiges Fahrverbot für bestimmte Dieselfahrzeuge eingeführt werden, das einen Großteil des feinstaub- und stickoxidbelasteten Stadtgebietes betrifft."
    }

Ein einzelnes `Feature` enthält den Namen der Straße oder eine Bezeichnung des Fahrverbotbereiches sowie eine Beschreibung. In letzterer kann etwa die Ausdehnung des Bereiches zwischen verschiedenen Straßen oder zusätzliche Regularien beschrieben werden, etwa die betroffenen Motoren oder zeitliche Einfahrverbote:

      "properties": {
        "name": "Stadtgebiet",
        "description": "Der Stuttgarter Fahrverbotsbereich für Dieselfahrzeuge unter Euro 5 wird sich voraussichtlich über das gesamte Stadtgebiet erstrecken."
      }
      
Im Zuge der Weiterentwicklung der Fahrverbote-Webseite sollte ein technisch schönerer Weg gefunden werden, um Informationen zu den Fahrverboten abspeichern zu können.

## Editoren

Ich nutze meistens [geojson.io](http://geojson.io/) zum Editieren der GeoJSON-Daten. Allerdings muss darauf geachtet werden, dass die hineingeschmuggelten `properties` beim Speichern nicht verworfen werden.
