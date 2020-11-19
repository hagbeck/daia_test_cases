# Testfälle DAIA nach Umstellung auf Alma

Es wird jeweils ein Link zum aktuellen Ergebnis des "hbz-DAIA" sowie die Datei mit dem erwarteten JSON angegeben. Ferner werden die offenen Punkte durch Anmerkungen erläutert.

## LOCAL:991003884029706445

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=LOCAL%3A991003884029706445
* expected: LOCAL_991003884029706445.json

Anmerkungen:

* leere `queue` bei `unavailable`
* `label`: "Abteilung" des Standorts in der Signatur anstatt in `storage`
* `storage.href`: Der Link zum Lageplan wird so wohl nicht mehr funktionieren. Bisher wurde Link für das Exemplar passend aus Sunrise geliefert. Das gibt es in Alma wohl so nur noch für Primo-Kunden. Suche nach einer Lösung läuft ...

## HBZ:HT002135652

* current: https://tub-dortmundalma--daia-paia.devel.digibib.net/daia?id=HBZ%3AHT002135652
* expected: HBZ_HT002135652.json

Anmerkungen:

* `label`: liefert falsche Signatur "Freihand @"; erwartet: "Freihand A 6931"
* `storage.href`: Der Link zum Lageplan wird so wohl nicht mehr funktionieren. Bisher wurde Link für das Exemplar passend aus Sunrise geliefert. Das gibt es in Alma wohl so nur noch für Primo-Kunden. Suche nach einer Lösung läuft ...
