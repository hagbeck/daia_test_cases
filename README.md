# Testfälle DAIA nach Umstellung auf Alma

Es wird jeweils ein Link zum aktuellen Ergebnis des "hbz-DAIA" sowie die Datei mit dem erwarteten JSON angegeben. Ferner werden die offenen Punkte durch Anmerkungen erläutert.

## LOCAL:991012201282806445 - case: electronic portfolio

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991012201282806445
* expected: LOCAL_991012201282806445.json

Offene Frage in der UB Dortmund: Wie kennzeichnen wir den "Zugriff nur im Hochschulnetz"?

## LOCAL:991003557889706445 - case: public note

Bei diesem Bestand ist die Ausgabe der `public_note` aus dem `item_data` sehr relevant. Diese Information sollte als `limitation` zu den `service`s 
angegeben werden:

```
{
   "id": "...",
   "items": [
      {
         "id": "...",
         "available": [
            {
               "service": "presentation",
               "limitation": [
                  {
                     "content": "FootNoteExt: Medienschrank"
                  }
               ]
            },
            {
               "service": "loan",
               "limitation": [
                  {
                     "content": "FootNoteExt: Medienschrank"
                  }
               ]
            }
         ]
      }
   ]
}
```

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003557889706445
* expected: LOCAL_991003557889706445.json



## LOCAL:991003731929706445 - case: physical item

aka HT016599403

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003731929706445
* expected: LOCAL_991003731929706445.json

Anmerkungen:

* Es fehlt: `unavailable.queue`
* `item.label`: "Abteilung" des Standorts in der Signatur anstatt in `storage`
* `item.storage.href`: Der Link zum Lageplan wird so wohl nicht mehr funktionieren, da er passend aus Sunrise geliefert wurde. Das gibt es in Alma wohl so nur noch für Primo-Kunden. Wir verzichten daher auf `item.storage.href`
* `item.department`: soll die Daten für `library` in Alma liefern
  * auf `item.department.href` wird ebenfalls verzichtet
* `item.storage`: soll die Daten für `location` in Alma liefern

## HBZ:HT002135652 - case: physical item

aka 991007110519706445

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=HBZ%3AHT002135652
* expected: HBZ_HT002135652.json

Anmerkungen:

* `item.label`: liefert falsche Signatur "Freihand @"; erwartet: "Freihand A 6931"
* `item.storage.href`: Der Link zum Lageplan wird so wohl nicht mehr funktionieren, da er passend aus Sunrise geliefert wurde. Das gibt es in Alma wohl so nur noch für Primo-Kunden. Wir verzichten daher auf `item.storage.href`
* `item.department`: soll die Daten für `library` in Alma liefern
  * auf `item.department.href` wird ebenfalls verzichtet
* `item.storage`: soll die Daten für `location` in Alma liefern
