# Testfälle DAIA nach Umstellung auf Alma

This is a project including test cases for the DAIA Service of University Library Dortmund.

## LOCAL:991003884029706445

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003884029706445
* expected: LOCAL_991003884029706445.json

Anmerkungen:

* leere `queue` bei `unavailable`
* `label`: "Abteilung" des Standorts in der Signatur anstatt in `storage`

## HBZ:HT002135652

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=HBZ%3AHT002135652
* expected: HBZ_HT002135652.json

Anmerkungen:

* `label`: liefert falsche Signatur "Freihand @"; erwartet: "Freihand A 6931"
