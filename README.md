# Testfälle DAIA nach Umstellung auf Alma

Es wird jeweils ein Link zum aktuellen Ergebnis des "hbz-DAIA" sowie die Datei mit dem erwarteten JSON angegeben. Ferner werden die offenen Punkte durch Anmerkungen erläutert.


### :x: LOCAL:991000024009706445 (EFB)

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991000024009706445

Anmerkungen:

* Es fehlen: `unavailable.queue` und `unavailable.exprected`
* `item.storage.href`: Wir verzichten daher auf `item.storage.href`


### :x: LOCAL:991000015419706445 (ZB)

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991000015419706445

Anmerkungen:

* Es fehlen: `unavailable.queue` und `unavailable.exprected`
* :heavy_check_mark: `item.storage.href`: Wir verzichten daher auf `item.storage.href`
* Abfrage dauert recht lange, sind aber auch ein paar "items" ;-)

## ... - case: Überordnung eines mehrbändigen Werks

...

## LOCAL:991012208459206445 - eine Vormerkung

**Problem:** Es fehlt `unavailable.queue=1` und was ist mit "Process Types" in Alma? Kommt - wie hier - "Acquisition technical services (Katalogisierung)" von der API zurück?

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991012208459206445
* expected: LOCAL_991012208459206445.json


## LOCAL:991012208459106445 - zwei Vormerkungen

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991012208459106445
* expected: LOCAL_991012208459106445.json


## LOCAL:991007227919706445 - case: print holdings for journal

Ziel ist hier, die Bestandsinformationen zu gedruckten Zeitschriften aus Alma zu holen. Der Grund dafür liegt darin, dass mit dem Umstieg auf Alma, die Bestandsinformationen in der ZDB und damit auch in "Journals Online & Print" bis auf Weiteres nicht mehr aktuell sein werden. 

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991007227919706445
* expected: ...

Offene Frage:

* Wie bilden wir den Bestand ab?


## :x: LOCAL:991012201282806445 - case: electronic portfolio (1)

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991012201282806445
* expected: LOCAL_991012201282806445.json

**Probleme:** 

* keine ID
* keine Angabe zur zugehörigen Kollektionen (als `storage`); die API liefert zwar die Service- und Collection-ID, aber keine weiteren Angaben.


## :x: LOCAL:991011172459706445 - case: electronic portfolio (2)

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991011172459706445
* expected: LOCAL_991011172459706445.json

**Probleme:** 

* keine ID
* keine URL
* keine Angabe zur zugehörigen Kollektionen (als `storage`); die API liefert zwar die Service- und Collection-ID, aber keine weiteren Angaben.


## :x: LOCAL:991003557889706445 - case: public note

**Problem:** Bei diesem Bestand ist die Ausgabe der `public_note` aus dem `item_data` sehr relevant. Diese Information sollte als `limitation` zu den `service`s 
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

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003557889706445
* expected: LOCAL_991003557889706445.json



## :x: LOCAL:991003731929706445 - case: physical item

aka HT016599403

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003731929706445
* expected: LOCAL_991003731929706445.json

Anmerkungen:

* Es fehlen: `unavailable.queue` und `unavailable.exprected`
* :heavy_check_mark: `item.storage.href`: Wir verzichten daher auf `item.storage.href`


## :heavy_check_mark: HBZ:HT002135652 - case: physical item

aka 991007110519706445

* current: https://tub-dortmund--daia-paia.devel.digibib.net/daia?id=HBZ%3AHT002135652
* expected: HBZ_HT002135652.json

Anmerkungen:

* `item.storage.href`: Der Link zum Lageplan wird so wohl nicht mehr funktionieren, da er passend aus Sunrise geliefert wurde. Das gibt es in Alma wohl so nur noch für Primo-Kunden. Wir verzichten daher auf `item.storage.href`

