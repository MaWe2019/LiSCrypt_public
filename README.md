# LiSCrypt 0.9.6
LiSCrypt ist ein Programm zur symmetrischen Verschlüsselung von Einzeldateien unter Verwendung von AES-GCM-256 bzw. einer Kombination von ChaCha20 und HMAC für sehr große Dateien.

Es wurde ursprünglich von der Qualitäts- und UnterstützungsAgentur - Landesinstitut für Schule in Nordrhein-Westfalen entwickelt.

## Prozedere
Die folgenden Ausführungen sollen Ihnen helfen, eine lokale Kopie von LiSCrypt auf Ihrem Rechner zu starten, die Sie für eigene Weiterentlickungen oder zu Testzwecken verwenden wollen. Falls Sie LiSCrypt in Ihrer Umgebung als ausführbares Programm ausrollen möchten, berücksichtigen Sie bitte die Hinweise unter "Ausrollen".

### Voraussetzungen
Voraussetzungen für die Verwendung von LiSCrypt

* Python 3.6.x
* Windows, macOS oder Linux

### Benötigte Bibliotheken
LiSCrypt 0.9.6 wurde u.a. mit den im Folgenden angegebenen Versionen getestet. Möglicherweise funktionieren insb. neuere Versionen ebenfalls.

* [base91, Version 1.0.1](https://github.com/aberaud/base91-python) - Base91-Kodiere/-Dekodierer
* [pyca/cryptography, Version 2.6.1](https://cryptography.io/en/latest/) - Kryptografie-Backend
* [psutil, Version 5.6.1](https://psutil.readthedocs.io) - Bibliothek für die Ermittlung von Systeminformationen
* [PyQt 5, Version 5.12](https://riverbankcomputing.com/software/pyqt/intro) - Python-Schnittstelle zum GUI-Framework Qt 5
* Unter Windows: [pywin32, Version 224](https://github.com/mhammond/pywin32) - Bibliothek für Zugriff auf die Windows API
* [PyYAML, Version 5.1](https://pyyaml.org/) - Bibliothek für Im- und Export von YAML-Dateien

Nähere Informationen zu den benötigten Fremdquellen finden sich in der Dokumentation.

### Installation und erster Start
1. Herunterladen und Installieren von [Python 3.6.x](https://www.python.org/).

    Entsprechend des persönlichen Bedarfs können Schritte 2, 3 und 4 entweder systemweit oder alternativ unter Verwendung von *virtualenv* durchgeführt werden.

2. Update von pip:
    ```
    python3 -m pip install --upgrade pip
    ```
    
3. Installieren der benötigten Abhängigkeiten (in den Versionen, mit denen LiSCrypt 0.9 getestet wurde):
    ```
    pip3 install base91==1.0.1 cryptography==2.6.1 psutil==5.6.1 PyQt5==5.12 PyYAML==5.1 pywin32==224  
    ```
 
3. Herunterladen des LiSCrypt-Quelltextes von https://github.com/MaWe2019/LiSCrypt_public/releases

4. Starten des Programms:
    ```
    python3 -m Steuerung.LiSCrypt
    ```
    oder Import in eine beliebige Python-IDE. Entwickelt wurde Python mit der Community-Variante von [PyCharm](https://www.jetbrains.com/pycharm/download/).
    
5. Test aller Programmfunktionen (Verschlüsseln, Entschlüsseln, Vernichten) mit Dummy-Dateien.

### Ausrollen

Zum Ausrollen von LiSCrypt in ausführbarer Form kann [PyInstaller](https://www.pyinstaller.org/) verwendet werden. Dabei ist insbesondere auf *hidden imports* und die Einbeziehung der [Visual C++ Runtime-Biblitoheken](https://support.microsoft.com/de-de/help/2977003/the-latest-supported-visual-c-downloads) zu achten. Unter macOS muss aktuell ein [Fork der Development-Version](https://github.com/pyinstaller/pyinstaller/pull/3832) von PyInstaller verwendet werden, damit Apple-Events unterstützt werden.

## Beiträge zur Weiterentwicklung

Sie möchten uns bei der Weiterentwicklung von LiSCrypt unterstützen? Wenden Sie sich an Martin Weise bei [QUA-LiS NRW](https://www.qua-lis.nrw.de)

### Quelltext-Formatierung

* Weitestgehende Verwendung von camelCase (entgegen der PEP8-Spezifikation)
* Einrückungen mit Tabs (entgegen der PEP8-Spezifikation)
* Modul- und Klassennamen beginnen mit einem Großbuchstaben
* Konstanten und globale Variablen werden komplett in Großbuchstaben geschrieben
* Methodennamen beginnen mit einem Kleinbuchstaben und beschreiben sematisch eine Tätigkeit
* Modulnamen beginnen mit 'LiS'
* Klassennamen beginnen mit 'Q', Klassennamen für GUI-Komponenten beginnen mit 'Ui_'
* Verwendung von Präfixen zur Unterscheidung von Attributen/Bezugsobjekten ('s'), Parametern ('p') und lokalen Variablen ('l')
* Attribute/Bezugsobjekte, Parameter und lokale Varaiblen enden mit einer Typangabe (z.B. lNachrichtString)
* Bezeichner und Kommentare in deutscher Sprache (ohne Umlaute)
* Ansätze des MVC-Prinzips

## Versionierung und Updates

Die Versionierung von LiSCrypt folgt dem [SemVer](http://semver.org/)-Schema. Der [Quelltext zu den verschiedenen Versionen](https://github.com/MaWe2019/LiSCrypt_public/releases) wird in Form von zip-Archiven in diesem Repository zur Verfügung gestellt.

## Copyright

* [QUA-LiS NRW](https://www.qua-lis.nrw.de), **Projektleitung:** Martin Weise

## Lizenz

LiSCrypt ist lizenziert unter der GNU General Public License Version 3 (GNU GPL v3). Den Lizenztext finden Sie in der Datei [COPYING](COPYING).

## Mitwirkende

* Dr. Albert Kapune, Tests
* Arbeitsbereich 5 von [QUA-LiS NRW](https://www.qua-lis.nrw.de), Verbesserungsvorschläge

## ToDo

* Fertigstellung der (derzeit veralteten und lückenhaften) API-Dokumentation.
