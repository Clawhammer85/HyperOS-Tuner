<div align="center">

# HYPER⚡OS Privacy Tuner

**Mehr Privatsphäre, Sicherheit und Tempo für dein Android-Handy – Schritt für Schritt, ohne Root.**

[![APK bauen](https://github.com/Clawhammer85/HyperOS-Tuner/actions/workflows/apk.yml/badge.svg)](https://github.com/Clawhammer85/HyperOS-Tuner/actions/workflows/apk.yml)
![Version](https://img.shields.io/badge/Version-1.3-2DD4BF)
![Android](https://img.shields.io/badge/Android-10%2B-3DDC84?logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-Jetpack%20Compose-7F52FF?logo=kotlin&logoColor=white)
![Ohne Internet](https://img.shields.io/badge/Internet--Berechtigung-keine-blue)

Deutsch · [English](README.en.md)

</div>

---

Der **HyperOS Privacy Tuner** zeigt dir, welche Einstellungen dein Handy privater, sicherer und schneller machen – und bringt dich mit einem Fingertipp direkt an die richtige Stelle. Vieles erkennt die App selbst und hakt es ab, sobald du zurückkommst. Gemacht für **Xiaomi, Redmi und POCO mit HyperOS**, angepasst auch für **Samsung (One UI)** und andere Android-Geräte.

> [!NOTE]
> Die App ändert nichts ohne dich, und jede Einstellung lässt sich zurückdrehen. Sie hat **keine Internet-Berechtigung** und kann deshalb keine Daten senden.

## Inhalt

- [Funktionen](#funktionen)
- [Unterstützte Geräte](#unterstützte-geräte)
- [Installation](#installation)
- [Erweitert: Automatik und Freischaltung](#erweitert-automatik-und-freischaltung)
- [Berechtigungen](#berechtigungen)
- [Häufige Fragen](#häufige-fragen)
- [Selbst bauen](#selbst-bauen)
- [Projektstruktur](#projektstruktur)
- [Quellen](#quellen)
- [Lizenz und Hinweise](#lizenz-und-hinweise)

## Funktionen

### Für Einsteiger

- **Einführung beim ersten Start** – fünf kurze Seiten, jederzeit überspringbar und später erneut aufrufbar.
- **„Das Wichtigste“** – zum Start nur rund zehn Punkte statt der kompletten Liste.
- **Assistent „Nächster Schritt“** – zeigt immer genau einen offenen Punkt mit Erklärung und großem „Jetzt einstellen“-Knopf. Was dir nicht geheuer ist, schiebst du mit „Später“ auf.

### Checkliste

- **Über 40 recherchierte Empfehlungen** in fünf Kategorien: Datenschutz, Sicherheit, Netzwerk, Werbung, Geschwindigkeit.
- **Direktsprung** in das passende Menü, der Weg steht immer dabei.
- **Automatische Erkennung** von Bildschirmsperre, Sicherheitsupdate, Bildschirm-Timeout, USB-Debugging, WLAN-/Bluetooth-Suche, Privatem DNS, Sperrbildschirm-Inhalten, Zwischenablage-Hinweis, Passwort-Anzeige, Animationen, Helligkeit und freiem Speicher.
- Nicht installierte Apps werden übersprungen, die Speichererweiterungs-Empfehlung passt sich an den Arbeitsspeicher an.

### Automatik lite – ohne PC, ohne Passwort

Mit einer einzigen Erlaubnis („Systemeinstellungen ändern“) setzt die App:
- Bildschirmsperre nach 1 Minute
- Passwörter beim Tippen verbergen
- automatische Helligkeit (optional)

### Werbefilter per Privatem DNS

Anbieter wählen, „Kopieren und Einstellungen öffnen“, einfügen – fertig. Alle Anbieter sind kostenlos und ohne Konto nutzbar:

| Rang | Anbieter | Hostname | Filtert |
|:---:|---|---|---|
| 1 | **AdGuard DNS** (empfohlen) | `dns.adguard-dns.com` | Werbung, Tracker, Schadsoftware |
| 2 | **DNS4EU** – ohne Werbung | `noads.joindns4.eu` | Werbung, Schadsoftware · EU-Initiative, DSGVO |
| 3 | **HaGeZi DNS** | `root.hagezi.org` | Werbung, Tracker, Telemetrie · Server in Deutschland |
| 4 | **Control D** – ohne Werbung | `p2.freedns.controld.com` | Werbung, Tracker, Schadsoftware |
| 5 | **Quad9** | `dns.quad9.net` | nur Schadsoftware · gemeinnützig |

> [!WARNING]
> Mullvad stellt seinen öffentlichen DNS-Dienst am **2. November 2026** ein. Die App erkennt einen eingetragenen Mullvad-Server und bittet um einen Wechsel.

### Bedienung

- **Deutsch und Englisch**, folgt der Systemsprache oder wird oben rechts umgestellt
- **Glas-Design im Dark Mode** mit sechs Farbdesigns: Lagune, Polarlicht, Amethyst, Glut, Ozean, Graphit
- Aufklappbare Karten, Filter je Kategorie, dezentes haptisches Feedback

## Unterstützte Geräte

Die App erkennt den Hersteller selbst und passt Menüpfade, Empfehlungen und den Schriftzug an. Über den Schriftzug oben links lässt sich die Oberfläche auch von Hand wechseln.

| Hersteller | Schriftzug | Besonderheiten |
|---|---|---|
| Xiaomi, Redmi, POCO | HYPER⚡OS (ältere: MI⚡UI) | msa, Werbedienste, Empfehlungen in Xiaomi-Apps, App Vault, Autostart, Speichererweiterung |
| Samsung | ONE⚡UI | Automatische Sperre, Anpassungsdienst, Werbe-Blockierung (One UI 8.5), Push Service, Galaxy Store, RAM Plus, Sicherer Ordner |
| OnePlus, Oppo, realme, Nothing, Motorola | OXYGEN⚡OS, COLOR⚡OS … | Standard-Android-Pfade |
| alle anderen | ANDROID⚡16 | Standard-Android-Pfade |

Voraussetzung: **Android 10 oder neuer**. Für die Freischaltung per Shizuku: Android 11 oder neuer.

## Installation

1. Die neueste APK unter **[Releases](https://github.com/Clawhammer85/HyperOS-Tuner/releases)** herunterladen – oder, mit GitHub-Konto, aus dem letzten erfolgreichen Lauf unter **[Actions](https://github.com/Clawhammer85/HyperOS-Tuner/actions)** › *Artifacts*.
2. APK auf dem Handy antippen und einmalig „Unbekannte Apps installieren“ erlauben.
3. App öffnen – die Einführung führt durch den Rest.

> [!TIP]
> Die Erlaubnis „Unbekannte Apps installieren“ danach wieder entziehen – das ist sogar ein Punkt der Checkliste. Bei Samsung muss die „Automatische Sperre“ für die Installation kurz aus sein.

Updates lassen sich direkt über die vorhandene Version installieren; Haken und Einstellungen bleiben erhalten.

## Erweitert: Automatik und Freischaltung

Alles in diesem Abschnitt ist **optional**. Die Checkliste funktioniert komplett ohne.

### Automatischer Durchlauf

Setzt alle Systemwerte auf einmal – Animationen, WLAN-/Bluetooth-Suche, Sperrbildschirm-Inhalte, Zwischenablage-Hinweis, Bildschirm-Timeout, verborgene Passwörter und auf Wunsch Privates DNS. Vorher bestätigst du mit Fingerabdruck, Gesicht oder PIN. Danach zeigt die App ein Ergebnis je Punkt; „Alles rückgängig machen“ nimmt die Änderungen wieder zurück.

Dafür braucht die App einmalig erweiterte Rechte. **Die Bestätigung per Fingerabdruck verschafft diese Rechte nicht** – sie verhindert nur, dass jemand anderes den Durchlauf an deinem Handy startet.

### Freischaltung ohne PC – mit Shizuku

Im Reiter **„Erweitert“** führt die App in vier Schritten durch:

1. [Shizuku](https://github.com/thedjchi/Shizuku/releases) installieren (empfohlen: Fork von thedjchi)
2. Shizuku über „Kabelloses Debugging“ starten
3. Der App den Zugriff erlauben
4. „Jetzt freischalten“

Danach kann Shizuku wieder deinstalliert werden – **die Freischaltung bleibt erhalten**. Solange Shizuku läuft, entfernt die App gefundene Werbe- und Tracking-Pakete auf Knopfdruck und stellt sie bei Bedarf wieder her.

### Freischaltung per PC

Mit den [Android SDK Platform-Tools](https://developer.android.com/tools/releases/platform-tools):

```bash
adb devices
adb shell pm grant de.hyperos.tuner android.permission.WRITE_SECURE_SETTINGS
adb shell appops set de.hyperos.tuner WRITE_SETTINGS allow
```

> [!IMPORTANT]
> **Xiaomi:** In den Entwickleroptionen zusätzlich „USB-Debugging (Sicherheitseinstellungen)“ einschalten (Xiaomi-Konto nötig), sonst lehnt HyperOS die Befehle ab.
> **Samsung:** Die „Automatische Sperre“ vorübergehend ausschalten – sie blockiert Befehle über USB.

Die passenden Befehle zum Entfernen und Wiederherstellen von Werbediensten zeigt die App im Reiter „Erweitert“ zum Kopieren an. Entfernt wird nur für den eigenen Benutzer (`pm uninstall -k --user 0`); ein Werksreset oder `cmd package install-existing` holt alles zurück.

## Berechtigungen

| Berechtigung | Wofür | Wann aktiv |
|---|---|---|
| `QUERY_ALL_PACKAGES` | Erkennen, welche vorinstallierten Apps vorhanden sind | ab Installation |
| `WRITE_SETTINGS` | Automatik lite: Bildschirm-Timeout, Passwort-Anzeige, Helligkeit | nur nach deiner Zustimmung |
| `WRITE_SECURE_SETTINGS` | Automatischer Durchlauf, „Automatisch setzen“ | nur nach Freischaltung per Shizuku oder PC |
| `USE_BIOMETRIC` | Bestätigung vor dem Durchlauf und vor dem Entfernen von Apps | bei Bedarf |
| Shizuku-Provider | Verbindung zu Shizuku | nur wenn Shizuku läuft und du zustimmst |
| ~~`INTERNET`~~ | – | **wird nicht angefordert** |

Gesicherte Originalwerte und deine Haken liegen nur lokal auf dem Gerät. Die App ist von Android-Backups ausgenommen.

## Häufige Fragen

<details>
<summary><b>Braucht die App Root?</b></summary>

Nein. Die Checkliste funktioniert ohne Sonderrechte. Für den automatischen Durchlauf reicht eine einmalige Freischaltung per Shizuku oder PC.
</details>

<details>
<summary><b>Play Protect warnt bei der Installation – ist die App gefährlich?</b></summary>

Play Protect warnt grundsätzlich vorsichtig bei Apps außerhalb des Play Stores, die es noch nicht kennt. Der Quellcode liegt hier offen, und die App hat keine Internet-Berechtigung. Lass die App ruhig von Play Protect prüfen.
</details>

<details>
<summary><b>Nach dem Einrichten von Privatem DNS habe ich in einem WLAN kein Internet.</b></summary>

Manche Firmen- oder Hotel-WLANs sperren den nötigen Port 853. Stelle Privates DNS dort auf „Automatisch“ zurück. Einen eigenen DNS-Filter im Heimnetz (z. B. Pi-hole) umgeht Privates DNS übrigens.
</details>

<details>
<summary><b>Eine App funktioniert nach dem Werbefilter nicht mehr richtig.</b></summary>

Sehr gründliche Filter blockieren gelegentlich etwas Legitimes. Der schnellste Test: zu AdGuard DNS wechseln oder Privates DNS kurz ausschalten.
</details>

<details>
<summary><b>Meine Banking-App startet nicht mehr.</b></summary>

Manche Banking-Apps verweigern den Dienst, solange Shizuku installiert ist. Nach der Freischaltung kannst du Shizuku deinstallieren – die Rechte der App bleiben erhalten.
</details>

<details>
<summary><b>Nach einem großen Update sind Punkte wieder offen.</b></summary>

Große HyperOS- oder One-UI-Updates setzen einzelne Werte zurück. Außerdem schaltet der Scan der Xiaomi-Sicherheits-App manchmal die Entwickleroptionen ab – dann gehen die Animationswerte verloren. Die Checkliste zeigt betroffene Punkte wieder als offen an.
</details>

<details>
<summary><b>Ein Menüpfad stimmt auf meinem Gerät nicht.</b></summary>

Menünamen unterscheiden sich je nach Version leicht. Bitte ein [Issue](https://github.com/Clawhammer85/HyperOS-Tuner/issues) mit Gerät, Android- bzw. HyperOS-/One-UI-Version und dem richtigen Pfad anlegen.
</details>

## Selbst bauen

**Mit GitHub Actions:** Jeder Push startet den Workflow [`apk.yml`](.github/workflows/apk.yml); die APK liegt danach unter *Actions* › *Artifacts*. Alternativ lässt sich das Projekt als `HyperOSTuner.zip` hochladen – der Workflow entpackt es automatisch.

**Mit Android Studio:** Projekt öffnen und *Build › Build APK(s)* wählen.

**Per Kommandozeile:**

```bash
gradle assembleDebug   # APK: app/build/outputs/apk/debug/app-debug.apk
```

Alle Builds werden mit `app/debug.keystore` signiert, damit Updates über ältere Versionen installiert werden können. Für eine öffentliche Verteilung empfiehlt sich ein eigener Release-Schlüssel.

| | |
|---|---|
| Sprache | Kotlin, Jetpack Compose, Material 3 |
| minSdk / targetSdk | 29 (Android 10) / 35 |
| Abhängigkeiten | AndroidX, Shizuku-API 13.1.5 |
| App-ID | `de.hyperos.tuner` |

## Projektstruktur

```
app/src/main/java/de/hyperos/tuner/
├── MainActivity.kt    Oberfläche: Einführung, Checkliste, Erweitert
├── ManualSteps.kt     Alle Empfehlungen je Hersteller (Deutsch/Englisch)
├── Platform.kt        Herstellererkennung, Schriftzug, Debloat-Listen
├── Model.kt           Systemwerte, DNS-Anbieter, Kategorien
├── Detectors.kt       Automatische Erkennung erledigter Punkte
├── SettingsRepo.kt    Lesen, Sichern, Setzen, Zurücksetzen von Systemwerten
├── ShizukuBridge.kt   Optionale Freischaltung ohne PC
├── Auth.kt            Bestätigung per Fingerabdruck, Gesicht oder PIN
├── L10n.kt            Texte der Oberfläche
├── Glass.kt           Glas-Design, Haptik, Bedienelemente
├── Palettes.kt        Farbdesigns
└── Launcher.kt        Sprünge in Einstellungen und Apps
```

**Neue Sprache:** In `L10n.kt` die Klasse `T` um ein Feld erweitern und die Texte in `L10n.kt` und `ManualSteps.kt` ergänzen.

## Quellen

Die Empfehlungen stützen sich auf aktuelle Anleitungen und Projekte (Stand Oktober 2026): smartzone.de und Notebookcheck (Werbung in HyperOS), techbone.de (HyperOS- und One-UI-Pfade), netzwelt.de (One UI 8.5, Automatische Sperre), Samsung Community, SamMobile und Android Authority, Android Central, die Debloat-Projekte [ovsky/hyperos-debloater](https://github.com/ovsky/hyperos-debloater) und [BloodBlinker/hyperos-debloat](https://github.com/BloodBlinker/hyperos-debloat), das [Shizuku-Wiki](https://github.com/thedjchi/Shizuku/wiki) sowie die Seiten der DNS-Anbieter ([AdGuard](https://adguard-dns.io), [DNS4EU](https://www.joindns4.eu), [HaGeZi](https://github.com/hagezi/dns-servers), [Control D](https://controld.com/free-dns), [Quad9](https://quad9.net)) und [Mullvad](https://mullvad.net/en/blog/2026/9/3/shutting-down-our-public-encrypted-dns-servers-and-sponsoring-quad9-instead) zur Abschaltung des DNS-Dienstes.

## Lizenz und Hinweise

**Lizenz:** noch nicht festgelegt.

Dieses Projekt steht in keiner Verbindung zu Xiaomi, Samsung oder Google. HyperOS, MIUI, One UI, Galaxy und Android sind Marken der jeweiligen Inhaber. Die Nutzung erfolgt auf eigene Verantwortung – entfernte Pakete lassen sich jederzeit wiederherstellen, ein Werksreset stellt den Auslieferungszustand her.
