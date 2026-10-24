[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![project size](https://img.shields.io/github/repo-size/spstiger/KincoDToolsTemplate?label=project%20size)
[![Kinco DTools min. 4.4](https://img.shields.io/badge/IDE-Kinco_DTools_min._4.4-blue)](https://www.spstiger.de/moorl-dc-v2/85089e4d00614b9fb80f0dfebf415ee0/read?path=Kinco%20DTools/Kinco%20DTools%20V4.4.0.3_Build250508_250613.zip)

> **Diese Vorlage verwenden** – diesen Kasten nach dem Einrichten löschen
>
> 1. Auf GitHub **Use this template → Create a new repository** wählen und das neue Repository klonen
>    (z. B. mit GitHub Desktop).
> 2. Das DTools-Projekt (`.dpj` mit `HMI0/`, `image/`, `vg/`) in den Klon legen oder dort neu anlegen.
> 3. Im Badge oben `KincoDToolsTemplate` durch den neuen Repository-Namen ersetzen.
> 4. Die Platzhalter `<…>` unten ausfüllen, Screenshot als `assets/Beispiel.png` ablegen.
> 5. Committen. Die `.gitignore` hält alles fern, was DTools selbst erzeugt (`temp/`, `tar/`, `.pkgx`,
>    `.bak` …).

# <Projektname>

<Ein, zwei Sätze: Was zeigt dieses Beispiel, wofür ist es gut?>

* <Funktion 1>
* <Funktion 2>

![Beispiel](assets/Beispiel.png)

## Für welches HMI?

| | |
|---|---|
| Gerät | **Kinco <Modell, z. B. GT070HE>** |
| Auflösung | <1024 × 600> Pixel |
| Gespeichert mit | Kinco DTools <4.4.x> |
| SPS / Kommunikation | <z. B. keine – nur HMI-interne Adressen / Kinco K5 per Modbus RTU> |

Für ein anderes Gerät in DTools den HMI-Typ umstellen. Ändert sich die Auflösung, müssen die Bilder
angepasst werden.

## Benötigte Software

[Kinco DTools](https://www.spstiger.de/moorl-dc-v2/85089e4d00614b9fb80f0dfebf415ee0/read?path=Kinco%20DTools/Kinco%20DTools%20V4.4.0.3_Build250508_250613.zip)
ab Version 4.4.

> **Versionen nicht mischen:** DTools 4.5 speichert Projekte in einem neueren Format, das DTools 4.4
> nicht mehr öffnen kann. Wer das Projekt in 4.5 speichert und committet, sperrt alle 4.4-Nutzer aus.
> Darum oben „Gespeichert mit“ pflegen und nur mit dieser Version speichern.

## Variablen

| Adresse | Typ | Richtung | Bedeutung |
|---|---|---|---|
| <LW100> | <16 Bit ohne Vorzeichen> | <SPS → HMI> | <Istwert Drehzahl> |
| <LB10> | <Bit> | <HMI → SPS> | <Start-Taste> |

Eigene Merker und Worte nicht ab LB/LW 8900 anlegen – dieser Bereich ist für Systemregister reserviert.

## Beispiel starten

1. **Kinco DTools** herunterladen und installieren (Link oben).
2. Dieses Repository als ZIP herunterladen oder **klonen**, z. B. mit GitHub Desktop.
3. Die `.dpj`-Datei in **Kinco DTools** öffnen.
   *Bei einer neueren DTools-Version fragt die Software, ob das Projekt konvertiert werden soll –
   mit Ja bestätigen. Danach lässt es sich nicht mehr mit der älteren Version öffnen.*
4. Im Menü **Werkzeuge** das Projekt **kompilieren**.
5. Im Menü **Werkzeuge** die **Offline-Simulation** starten oder das Projekt per **Download auf das
   HMI** übertragen.

## Passwörter

Das Projekt nutzt die Kinco-Werksvorgaben für Upload-, Dekompilier- und Passwortstufen
<bzw.: Testbenutzer „…“>. Diese Werte sind öffentlich bekannt. **Vor dem Einsatz an einer Maschine in
DTools eigene Passwörter setzen.**

## Hinweise für Git

- **Änderungen nach bloßem Öffnen verwerfen.** DTools schreibt schon beim Öffnen die `.dpj` neu
  (teils unverschlüsselt statt verschlüsselt). Wer nur angesehen oder simuliert hat, verwirft das in
  GitHub Desktop (Rechtsklick → **Discard changes**).
- **Bewusst geändert und gespeichert** → alles zusammen committen: `.dpj`, geänderte `HMI0/*.whe`
  und neue Grafiken in `image/` bzw. `vg/`.
- `PLCGEDefaultProperties.xml` ist absichtlich ausgeschlossen: DTools ersetzt sie beim Öffnen durch
  die Standardvorlagen der eigenen Installation.
- Projekt nicht in DTools geöffnet lassen, während GitHub Desktop Dateien austauscht (Pull, Branch
  wechseln).

## Annahmen und offene Punkte

- <z. B. Registeradressen der SPS noch nicht am echten Gerät geprüft>

## Mehr zu Kinco-HMIs

- [Kostenlose DTools-Komponenten von spstiger](https://github.com/spstiger/Kinco-HMI-DTools-free-spstiger-components)
  – z. B. RAM-/Flash-Anzeigen, per Rechtsklick einfügbar
- Kinco-HMIs, Software und Support: [spstiger.de](https://www.spstiger.de)

## Lizenz

[MIT](LICENSE) – frei nutzbar, ohne Gewähr.
