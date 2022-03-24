<h1>Streamstation</h1>

In diesen Docker Services handelt es sich um eine Streamingstation, die es ermöglicht, einen Audiostream an Icecast2 zu senden. 
Dieser Stream kann dann dann z.B. auf einer Website eingebunden werden oder aber, über eine Sipgate Telefonanlage mitgehört werden. 

Telerix wurde von Benjamin Hedert entwickelt und ist als standalone Applikation für die native Installation auf z.B. Ubuntu hier auf GitHub erhältlich:
[Telerix](https://github.com/beni1993/Telerix)

<h2>Vorraussetzungen für die Installation</h2>

Docker für Windows, MacOS oder Linux, Git

<h2>Installationsanleitung</h2>

1. Nach der Installation und Start von Docker muss dieses Repository herunter geladen werden. Dafür verwenden wir git.
2. Wechseln in ein beliebiges Verzeichnis: 
```bash
cd /
```
3. Herunterladen des Repositorys:
```bash
git clone https://github.com/Fill205/streamstation.git
```
4. Wechsel in das heruntergeladene Verzeichnis:
```bash
cd streamstation
```
5. Docker Services installieren: 
```bash
docker-compose up -d
```
<h2></h2>
<p>Docker hat nun Telerix und Icecast als Container installiert.<br>
Telerix ist eine Frontend für die Asterisk Telefonanlage und Icecast, wie bereits erwähnt, die Streamingplattform.<br>
<br>
Über den lokalen Browser kannst du nun auf die beiden Applikationen zugreifen:<br>
Telerix: http://localhost:9000 <br>
Icecast: Http://localhost:8000 <br></p>

<h2>Anmeldung</h2>
<p>
Für die Anmeldung in Icecast: <br>
  User: admin <br>
  Passwort: set here your password <br>
  (ja, es ist wirklich das Passwort, inkl. Leerzeichen zwischen den Wörtern :) ) <br>
  <br>
  Für Telerix könnt ihr nun selbst die Daten wählen...
</p>

<h2>Icecast Zugangsdaten ändern</h2>

1. Über die Kommandozeile in den Container wechseln:
```bash
docker exec -it icecast bash
```
2. Konfigurationsdatei öffnen
```bash
vim /etc/icecast2/icecast.xml
```
3. Zum Bereich der Passwörter und User springen: 
```bash
:37
```
4. In den Editirmodus wechseln:
```bash
i
```
5. Die zwischen den beiden Tags > und < das bekannte Passwort ändern, auch in den nächsten Zeilen. In Summe drei mal. 
6. Editiermodus verlassen mit Escape Taste
7. Datei speichern und schließen:
```bash
:wq
```
8. Den Icecast Dienst neu starten: 
```bash
service icecast2 restart
```
9. Falls denkbar wäre auch den Container neu zu starten. Dazu auf dem Hostsystem das Kommandozeilenprogramm öffnen und folgenden Befehl absetzen:
```bash
docker restart icecast
```
10. Nun den Browserverlauf leeren und die Seite neu laden.

<h2>Stream einrichten</h2>
<p>
Dazu einen verwendest du auf dem Computer, von dem aus gestreamt werden soll z.B. das Programm Butt welches es zum Download gibt. <br>
https://danielnoethen.de/butt/ <br>
<br>
Richte in Butt den Stream ein und beginne den Stream an den Icecast zu senden. <br>
<br>
Telerix einrichten: <br>
Hierfür gibst du die Streamurl an z.b. icecast:8000/stream.mp3 <br>
Wenn du auf Sipgate einen Account hast, hinterlege die Zugangsdaten in Telerix
  


