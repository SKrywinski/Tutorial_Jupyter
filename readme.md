  
  
  
Vorbemerkungen
-------
  
Dieses Tutorial versteht sich als unterstützende Hilfestellung bei der Installation von Jupyter. Es umreißt die notwendigen Vorkehrungen und versucht, die Prozesse nachvollziehbar zu erklären, dass der Einstieg in Jupyter problemlos gelingt.
Da sich das Tutorial an Anwender - auch ganz ohne Vorkenntnisse -  richtet, ist es nicht sein Ziel, alles en detail zu beleuchten. Für weiterführende Lekture werden, wo sinnvoll, Empfehlungen gegeben. Auch können trotz sorgfältiger Vorbereitung wahrscheinlich nicht alle denkbaren (Fehler)Fälle abgedeckt werden, in denen sich Anwender Unterstützung wünschen - eingesetzte Hard- und Software und  Vorwissen sind einfach zu vielfältig.
Das Tutorial nährt sich aus Erfahrungen häufiger Probleme vorangegangener Semester und versteht sich auch als weiter im Aufbau befindlich.
  
  
  
###  Python
  
  
  
  
Ju*py*ter weißt bereits darauf hin, dass mit Python (genauer gesagt in der 3. Version) gearbeitet wird.
Python gilt als leicht erlernbare Programmiersprache, deren bereits großer Funktionsumfang mit Hilfe von Bibliotheken enorm erweitert werden kann, sodass Python sich nicht nur wachsender Beliebtheit erfreut, sondern auch in allen Bereichen von Data Science und Machine Learning eingesetzt wird.
Auch wenn Python leicht zu erlernen ist, lernt man programmieren am Besten durch programmieren. Deswegen anbei ein paar hilfreiche Links, die beim (Python) Programmierenlernen helfen.
  
Tutorials
+ [W3Schools Python Tutorial](https://www.w3schools.com/python/default.asp )
+ [Python-Kurs.eu](https://www.python-kurs.eu/kurs.php )
+ [Realpython](https://realpython.com/ )
  
Live Python-Code ausprobieren und erklären lassen:
+ [Pythontutor](http://pythontutor.com/ )
  
Einfache Alltagsprobleme mit Python automatisch lösen:
+ [Automatetheboringstuff](https://automatetheboringstuff.com/ )
  
  
  
Nun folgen zwei kurze Abschnitte, in denen die Arbeit mit Ordnerstrukturen und der Kommandozeile behandelt wird. Auch wenn im Anschluss daran mit dem Softwarepaket Anaconda eine sehr einfache, vollautomatische Lösung zur Installation einer vollständigen Entwicklungsumgebung vorgestellt wird, die eine Menge Konfigurations- und Verwaltungsarbeit erspart, lohnt sich ein Verständnis von Ordnerstrukturen und der Kommandozeile spätestens bei Auftreten von Problemen. Häufig ist eine Arbeit mit der Kommandozeile die einzige Option.
Aber schon, wenn es darum geht, später kleine Skripte zu schreiben, die mit Dateien arbeiten, ist dieses Wissen unumgänglich. Die ersten eigenen Programme werden auch in der Kommandozeile laufen und kein anderes Benutzerinterface haben.
  
  
###  Ordnerstruktur verstehen
  
  
  
  
Um nachzuvollziehen, was während der Installation von Jupyter und generell bei der Arbeit in der Kommandozeile passiert, hier ein kurzer Überblick der Strukturierung im Dateisystem.
Es ist notwendig, zu verstehen, wie Pfadangaben zum Beispiel mit graphischen Dateimanagern zusammenhängen.
  
  
  
<img src="img/WindowsExplorer.png?0.20848327544747858"  width="600px"  alt="Windows Explorer" >
  
  
  
  
Exemplarisch sei hier folgende Verzeichnisstruktur vorausgesetzt:
  
Windows:
```
C:
|--Users
    |--%USER%
          |--Desktop
          |--Dokumente
          |--Bilder
```
  
Linux:
```
/
|--home
    |--<username>
          |--Desktop
          |--Dokumente
          |--Bilder
```
  
####  Wo liegen Order, die auf dem Desktop/Schreibtisch zu sehen sind?
  
  
Als kleines Beispiel dient hier der Dateiablageort "Desktop".
Dieser befindet sich in `C:\Users\%USER%\Desktop` in Windows und `/home/<username>/Desktop` [^noteF1].
  
[^noteF1]:Je nach Linuxdistribution kann der Ort auch anders, z. B. `Schreibtisch` heißen
  
Dabei fällt auf, dass sich in den Pfadangaben von Windows `\` und Linux `/` unterscheiden. Dies führt gerne zu Problemen.
  
####  Verzeichnis/Ordner wechseln
  
  
Möchte man in den übergeordneten Ordner `C:\Users\%USER%\` oder `/home/<username>/` wechseln, gibt man `cd ..`[^noteF2] ein. Durch `cd Dokumente` wechselt man vom übergeordneten Ordner eine Ebene tiefer nach Dokumente. Es ist sehr wichtig, sich das klarzumachen.
  
[^noteF2]: =change directory
  
####  Absolute und relative Pfadangaben
  
  
Um zwischen verschiedenen Orten zu navigieren kann man relative Pfadangaben (vom Ort aus, *an dem man sich befindet*) oder absolute Pfadangaben verwenden.
Vom Ort `C:\Users\%USER%\Dokumente` oder `/home/<username>/Dokumente` aus gibt es zwei Wege, um in den Ordner `Bilder` zu wechseln:
+ `cd..`, vom relativen Pfad aus eine Ebene höher zu steigen und dann `cd Bilder`, um eine Ebene tiefer, in den gewünschten Ort zu wechseln
+ `cd C:\Users\%USER%\Bilder` oder `cd /home/<username>/Bilder`, um, egal, wo man sich befindet, direkt in den absoluten Ordner zu wechseln.
  
  
####  Noch einige Hinweise zur Fehlervermeidung/-suche:
  
+ Pfade ohne Leerzeichen erstellen! → Fehlerquelle
  + Nicht so: `"C:\Users\My Name"`
  Leerzeichen in Windows müssen in Skripten (vor allem bei Betriebssystemübergreifenden Arbeiten) mit backslash escaped werden, da es sonst Fehler gibt:
  `"C:\Users\My\ Name"`
  In Zusammenhang mit Windows kann das zu folgenden Konstruktionen fürhen, in denen die Pfadbackslashes nochmal escaped werden müssen:
  `"C:\\Users\\My\ Name"`
  + Besser: `"C:\Users\My_Name"` oder `C:\Users\MyName`
  
  
+ (Installations)Pfad(e) merken (für alle OS) erleichtert spätere Installationen/Problemlösungen
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
###  Kommandozeile / Terminal
  
<img src="img/Open_CMD.jpg?0.3585709461782951"  width="600px"  alt="Kommandozeile" >
  
Die Kommandozeile ist eine der ersten Möglichkeiten, mit einem Programm (oder dem Betriebssystem) zu interagieren[^noteC1]. Zwar wirkt der Umgang mit der Kommandozeile oft kompliziert, da dieser im Folgenden aber unumgänglich ist, hier einige kurze einleitende Worte. Man wird schnell merken, das jede Angst der Benutzung unbegründet ist und die Nutzung der Kommandozeile für alltägliche Arbeiten oft der effizienteste Weg.
  
Die Kommandozeile gibt es auf jedem Betriebssystem und sie funktioniert auch überall ziemlich ähnlich.
Unter Windows startet man sie durch Drücken von *Windowstaste + R* und der Eingabe von `CMD`.
Unter Linux benutzt man dafür das *Terminal*, auf einigen Distributionen drückt man *ALT + CTRL + T*.
Ei weiterer Weg, die Kommandozeile zu öffnen ist, im Dateiexplorer per Rechtsklick ein Kontextmenü zu öffnen und dort * _was genau?_ * (Windows) oder *In Terminal öffnen* (Linux) anzuklicken.
Es öffnet sich ein meist schwarz oder weiß hinterlegtes Fenster. Zu sehen ist ein meist blinkender Cursor. Dort wird die Eingabe erwartet.
Der Cursor steht hinter einem `>` (Windows) oder einem `$` (Linux). Vor diesen Zeichen, die anzeigen, dass eine Eingabe erwartet wird, ist der aktuelle Pfad, in der sich die Kommandozeile gerade befindet. Standardmäßig öffnet sich diese im entsprechenden Benutzerverzeichnis, `C:\Users\%USER%` (Windows) und `/home/<username>`[^noteC2], wobei dieser Standardpfad in Linux mit `~` abgekürzt ist[^noteC3]. Hat man die Kommandozeile mit der Rechtsklick-Methode geöffnet, steht sie genau an dem Ort des Öffnens im Dateiverzeichnis. So eignet sich diese Methode besonders für unerfahrene Benutzer: Sie bekommen ein Gefühl dafür, das alle Aktionen in der Kommandozeile zuerst immer einen relativen Bezug zur Ordnerstruktur haben.  In diesem Zusammenhang ist es hilfreich, sich noch einmal klarzumachen, was im Abchnitt [Ordnerstruktur](folderstructure.md#Ordnerstruktur ) beschrieben wurde.
Weiterführende Erklärungen bezüglich verschiedener Benutzer- und Rechteverwaltung werden hier bewusst ausgeklammert.
  
[^noteC1]: [Erklärung](https://tutorial.djangogirls.org/de/intro_to_command_line/ ) für alle Betriebssysteme
[^noteC2]:`%USER%` und `<username>` sind natürlich Platzhalter für die jeweiligen Benutzernamen. Vor allem unter Windows findet man immer wieder auch `%APPDATA%`, um auf (versteckte) Benutzerdaten zugreifen zu können. Diese sind standardmäßig versteckt.
[^noteC3]:Ein Wechsel in das eigene Homeverzeichnis ist unter Linux mit der Eingabe `cd ~` möglich
  
In der Kommandozeile kann im Dateisystem navigiert werden, Dateien und Ordner können aufgelistet und manipuliert werden (Erstellen, Umbenennen, Löschen, Kopieren, etc.). Alles was in einer grafischen Benutzeroberfläche meist mit der Maus gemacht wird und noch mehr ist hier möglich. Die vielen Befehle wirken sicher zunächst abschreckend, werden aber schon nach weniger Zeit des Umgangs ganz automatisch von der Hand gehen.
  
Einige der am häufigsten gebrauchten Befehle sind in der Tabelle unten zu finden.
  
  
  
  
  
  
####  Einige Entsprechungen von wichtigen Windows- und Unix-Kommandos
  
  
  
  
  
  
  
  
  
|    CMD Command          | UNIX Command   |   PowerShell Command  | PowerShell Alias |                  Erklärung                               |
|-------------------------|----------------|-----------------------|------------------|----------------------------------------------------------|
| `dir`                   | `ls`           | Get-ChildItem         | gci              | Ordnerinhalt anzeigen (`directory`, `list`)              |
| `cls`                   | `clear`        | Clear-Host (function) | cls              | Konsole leeren                                           |
| `del`, `erase`, `rmdir` | `rm`           | Remove-Item           | ri               | Lösche-Befehl (`delete`, `remove`)                       |
| `copy`                  | `cp`           | Copy-Item             | ci               | Kopieren                                                 |
| `move`                  | `mv`           | Move-Item             | mi               | Verschieben (`move`)                                     |
| `rename`                | `mv`           | Rename-Item           | rni              | Umbenennen (unter Linux wird Umbenannt durch Verschieben)|
| `type`                  | `cat`          | Get-Content           | gc               | Inhalt von (einer) Datei(en) anzeigen (`concatenate`)    |
| `cd`                    | `cd`           | Set-Location          | sl               | Ort (Ordner) wechseln (`change directory`)[^noteC4]      |
| `md`                    | `mkdir`        | New-Item              | ni               | Ordner anlegen (`make directory`)[^noteC5]               |
  
> Auszug aus: [Windows To Unix Command Cheat Sheet](https://gist.github.com/jonlabelle/e8ba94cd29b8f63fd7dd3c4f95c1d210#file-windows_to_unix_command_cheat_sheet-md )
  
[^noteC4]:Vorsicht: `cd..` (Windows) vs `cd␣..` (Leerzeichen zwingend bei Linux)
[^noteC5]:Unter Linux kann mit `touch <dateiname>` eine neue, leere Datei angelegt werden
  
  
  
Jupyter
------
  
Nicht nur im Verlauf dieses Seminars wird die Notwendigkeit bestehen, Code ausführen, Codeschnipsel kombinieren oder Code selber erzeugen zu müssen.
Vor allem zur schnellen Ausführung von Code und zur Entwicklung bietet es sich an, Jupyter-Notebooks zu verwenden. Damit ist es möglich, Code zeilenweise auszuführen, um zu überprüfen, ob er tut was er soll, ohne auf eine umfangreiche und große Entwicklungsumgebung wie [PyCharm](https://www.jetbrains.com/pycharm/ )[^note1] zurückgreifen zu müssen.[^note2]
  
[^note1]: PyCharm ist in einer kostenlosen Community- und einer für Studenten auch kostenlosen professionellen Version erhältlich
[^note2]: Hinweis auf Atom + Hydrogen?
  
###  Jupyter ausprobieren
  
  
  
  
  
Um zu sehen, wie ein Jupyter-Notebook aussieht, und wie es funktioniert, ohne etwas installieren zu müssen, kann bei [JupyterLab](https://jupyterlab.readthedocs.io/en/stable/ ) ein [Beispielnotebook](https://mybinder.org/v2/gh/jupyterlab/jupyterlab-demo/master?urlpath=lab/tree/demo ) geöffnet und ausprobiert werden.  
  
Bei [Google Colab](https://colab.research.google.com/ ) können - sofern ein Google-Konto vorhanden ist, Jupyter-Notebooks mit eigenen Daten angelegt, gespeichert und ausgeführt werden. Jedoch: (Später vielleicht) Sensible Daten werden so aus der Hand gegeben; dies gilt es im Hinterkopf zu behalten.
  
####  Anaconda
  
Zur Installation von Jupyter empfiehlt sich, dies zusammen mit der Anaconda-Distribution zu tun. Jupyter über eine Paketverwaltung wie `pip` zu installieren ist eher fortgeschrittenen Benutzern zu empfehlen[^note4].
  
[^note4]: https://jupyter.readthedocs.io/en/latest/install.html
  
Anaconda ist <!--sozusagen--> ein Softwarepaket, dass sich nicht nur um die richtige Installation von Python (und R) kümmert, sondern auch dafür sorgt, dass Abhängigkeiten von (Python-)Paketen richtig aufgelöst werden.
Das verhindert nicht nur Fehler durch Inkompabilität sondern möglicherweise auch durch Änderungen in den Paketen selbst, die sich mitunter auf Ausgeben von selbstentwickelten Programmen auswirken.
Dabei und dafür bringt Anaconda die Entwicklungsumgebung Spyder mit und beinhaltet eine umfangreiche Paketsammlung[^note5] für Python, sodass zunächst mit keiner anderen Paketverwaltung gearbeitet werden muss.
Vom Anaconda Navigator, der "Benutzeroberfläche" von Anaconda aus sind alle Tools wie Jupyter, Spyder, Paketverwaltung aber auch Installation und Update von Paketen erreichbar; so können viele Aufgaben von einem Ort und zunächst ohne [Kommandozeile](commandline.md ) erledigt werden.
  
  <!--dann:
  + Warum Anaconda/so ein Riesenpaket?
  + Spyder
+ Python 3 != Anaconda 3(?)-->
  
Bei der Auswahl der richtigen Anaconda-Distribution kommt es auf folgende Punkte an:
+ welches Betriebssystem: Windows - Linux - macOS
+ 32bit - 64bit: zu finden in den Systeminformationen, neuere Geräte sind vermutlich mit 64bit-Software ausgestattet
Für Linux und macOS nur 64bit
+ Python-Version 3 (Python 2 wird in Zukunft nicht mehr weiterentwickelt)
  
[Anaconda-Download-Seite](https://www.anaconda.com/distribution/#download-section )
  
[^note5]: Häufig verwendete Pakete wie `numpy`, `pandas`, `matplotlib`, `scipy` und viele weiter sind bereits enthalten
  
Weil die Installation von Anaconda auf Linux und macOS sehr ähnlich sein sollten, wird bei den folgenden Hinweisen nur auf Windows und Linux eingegangen.
  
Ein wichtiger Hinweis, der in beiden Fällen gilt: Soll Anaconda installiert werden, so ist es sehr wichtig, bestehende Pythoninstallationen (auch IDLE oder Ähnliches) **restlos** vom System zu entfernen. Dies betrifft auch schon eingerichtete Umgebungsvariablen. Sollte Anaconda parallel installiert werden kann (und wird) es zu Fehlern kommen, die mit einigem Aufwand behoben werden können.
  
  
  
####  Exkurs: Umgebungsvariablen/Environment Variables
  
  
Normalerweise kommt man mit Umgebungsvariablen kaum in Berührung, da sie tief ins (Betriebs-)System eingreifen und der Umgang mit ihnen einiger Vorsicht bedarf. In Umgebungsvariablen werden grundsätzliche Einstellungen zum Betriebssystem gespeichert, das heißt, dass bei falschen Konfigurationen das System instabil werden kann oder es gar nicht mehr arbeitet.
Die meisten Einstellungen passieren im Hintergrund, etwa bei der Installation von neuen Programmen.
Hier ist der Anknüpfpunkt bei der Installation von Python und Anaconda: In den Umgebungsvariablen gibt es eine Variable mit Namen *PATH*. Dieser Exkurs soll sich nur auf die Beschreibung dieser beschränken.
In der PATH-Variable sind kurz gesagt Pfade abgespeichert, in denen sich Programmdateien befinden. Jedes Programm, das im Betriebssystem installiert ist, hat irgendwo eine ausführbare Datei (bei Windows zum Beispiel `.exe` oder `.bat` ufm.), die aufgerufen wird, wenn das Programm gestartet werden soll. Dabei spielt es keine Rolle, ob auf eine Verknüpfung zum Programm geklickt, es aus dem Startmenü ausgewählt oder per Befehl auf der Kommandozeile aufgerufen wird.
  
  
<img src="img/Systemvariable_path_windows.png?0.6040329102258022"  width="600px"  alt="Windows Umgebungsvariable" >
  
  
  
Ist beispielsweise auf dem Computer LibreOffice als Officepaket installiert und Writer (Word-Äquivalent) soll gestartet werden (durch eine der oben aufgeführte Methoden), dann weiß das Betriebssystem durch die PATH-Variable, wo die ausführbare Datei zu finden ist: `C:\Program Files (x86)\LibreOffice 5\program\swriter.exe` oder `usr/bin/swriter`. Gäbe es die Umgebungsvariable nicht, müsste zum entsprechenden Speicherort der Programmdatei gewechselt werden, um dann *von dort aus* gestartet zu werden. So aber kann man an jeder beliebigen Stelle im Dateisystem (die Verknüpfung kann auf dem Desktop oder irgendwo anders liegen, man kann eine Kommandozeile irgendwo starten) aus das Programm einfach durch Klick oder Eingabe von `swriter.exe` oder `swriter` starten[^note6].
Es erklärt sich von selbst, dass eine PATH-Variable aus mehreren Pfaden (jeweils ein Eintrag pro Programm) bestehen kann. Es ist eine Variable, innerhalb derer die verschiedenen Pfade durch `;` (Windows) oder durch `:` (Linux) getrennt sind.
  
  
[^note6]: Die Pfade können je nach installierter Version oder Anwendung zwar abweichen, generell finden sich Programmdateien bei Standardinstallation aber in `C:\Program Files\`, `C:\Program Files\` (Windows) oder `/usr/bin` (Linux).
  
Mit diesem Wissen ist es nun leichter, nachzuvollziehen, warum vor der Installation von Anaconda genau darauf geachtet werden muss, schon vorhandene Einträge in den Umgebungsvariablen zu entfernen. Dies geschieht eigentlich bei der Deinstallation von Programmen (z. B. Python oder IDLE) automatisch, wenn aber mehrere Programme auf die jeweilige Umgebungsvariable zugreifen, können entsprechende Variablen bestehen bleiben. Dies ist ein besonders kniffliger Fehler, wenn es bei Installationen von Programmen zu Problemen kommt.
  
Eine detaillierte Anleitung, wie auf den verschiedenen Betriebssystemen mit der PATH-Variable gearbeitet kann, soll nicht weiter Teil dieses Tutorials sein, da sich dies vor allem bei Windows aufwändiger gestaltet als bei Linux, deswegen hier nur der Hinweis auf Anleigungen:
  
* Anleitung für [Java](https://www.java.com/de/download/help/path.xml ), aber analog für andere Programme
* Allgemeinere [Anleitung](https://www.poftut.com/how-to-set-environment-variables-for-linux-windows-bsd-and-macosx/ ) für alle Betriebssysteme
  
  
  
####  Installation
  
Es ist schon viel geschafft auf dem Weg zu einer lauffähigen Jupyter-Umgebung (auf dem ganz nebenbei viel Wissen eingeflossen ist, das später sowieso gebraucht wird), sicher der größte Teil. Die Installation von Anaconda selbst besteht an sich nur aus der Ausführung des oben bereits heruntergeladenen Installers (Windows) beziehungsweise des heruntergeladenen Bash-Skripts (Linux). Bei Windows ist darauf zu achten, dass Anaconda für *alle Benutzer* installiert wird und die PATH-Variable hinzugefügt wird.
  
<img src="img/add_path_variable_win.png?0.0015490944831524356"  width="600px"  alt="PATH-Variable hinzufügen" >
  
Alle weiteren Schritte sollten weitgehend selbsterklärend sein.
Auch bei Linux ist - bei entsprechender Nachfrage - die PATH-Variable zu setzen[^note7]; den Fragen zu Lizenzvereinbarung und Installationspfad kann (mit `yes`) zugestimmt werden.
  
Der Installationsprozess sollte aufmerksam verfolgt werden und gerade der unerfahrene Benutzer sollte sich die gezeigten und abgefragten Pfade merken, um zu wissen, wo im Problemfall zu suchen ist.
  
Die umfangreiche Vorbereitungsarbeit, die investiert wurde, mag übertrieben scheinen, wenn dann hier eine Ein-Klick-Lösung angeboten wird, jedoch zeigt die Erfahrung, das Probleme wahrscheinlich sind, und zu deren Lösung brauch man oben Vermitteltes auf jeden Fall. Und spätestens - wie bereits erwähnt - wenn im eigenen Skript mit lokalen Daten gearbeitet wird, ist dieses Wissen notwendig.
  
  
[^note7]:Bei der Testweisen Installation zur Erstellung des Tutorials wurde unter Linux nicht nachgefragt, ob die Umgebungsvariable gesetzt werden soll.
  
  
####  Erste Nutzung von Anaconda/Jupyter Notebooks
  
  
  
  
<img src="img/anaconda_navigator.png?0.3630979076605716"  width="600px"  alt="Anaconda Navigator" >
  
Mit Anaconda wurde auch der Anaconda-Navigator installiert. Dies ist die zentrale grafische Benutzeroberfläche für die Verwaltung und das Starten von Programmen. Er wird über den Klick auf das entsprechende Programm-Icon oder über die Eingabe von `anaconda-navigator` in der Kommandozeile gestartet. Von dort aus kann das Jupyter-Notebook einfach per Klick auf *Launch* geöffnet werden.
Man kann Jupyter aber auch über die Eingabe von `jupyter notebook` direkt aus der Kommandozeile heraus starten.
Ein neues Notebook wird im (neuen Reiter vom) Standardbrowser. Die Adresse ist `localhost:8888/tree`. Das bedeutet nicht, dass Jupyter irgendetwas online macht, der Browser ist einfach die Oberfläche für das Programm; darauf weist *localhost* hin. Im geöffneten Fenster sind mehrere Ordner zu sehen. Da Anaconda sowohl auf Windows als auch auf Linux im Benutzerordner installiert ist, sind offensichtlich genau die Ordner zu sehen, die eben dort liegen. Auch wenn das im Moment banal erscheint, gilt es doch, Notiz davon zu nehmen.
  
  
<img src="img/jupyter_notebook.png?0.2512031623675184"  width="600px"  alt="Jupyter Notebook" >
  
Es bietet sich an, in einen Ordner wie *Dokumente* oder *Documents* zu navigieren und dort einen eigenen Ordner anzulegen, der Jupyter-Notebooks (Dateien mit der Endung `.ipynb`) enthält. Ein neues Jupyter Notebook legt man aus der Browser-Oberfläche heraus an indem man (im Screenshot ganz rechts) auf *New* und dann *Python 3* klickt.
  
Ein Beispielpfad mit Jupyter-Notebook sieht so aus:
`C:\Users\%USER%\Dokumente\Python_Projects\first_notebook.ipynb`
oder
`/home/<username>/Documents/python_projects/first_notebook.ipynb`
  
Wird Jupyter nach einer der oben genannten Methoden gestartet, müsste immer in den entsprechenden Pfad gewechselt werden, in dem die zu bearbeitende Jupyter-Datei liegt; Wesentlich leichter ist es da, entweder per grafischem Dateiverwalter zu entsprechenden Ort zu wechseln und dort - wie oben erklärt - eine Kommandozeile zu starten, oder in der Kommandozeile zu dem Ort zu wechseln, und dann in der Kommandozeile `jupyter notebook` zu starten. Idealerweise startet man im entsprechenden Ort im Beispielfall mit `jupyter notebook first_notebook.ipynb`; im Browser wird direkt das Notebook geöffnet.
  
  
  
<img src="img/first_notebook.png?0.5916801426990195"  width="600px"  alt="first_notebook" >
  
Oben ist ein kleiner Ausschnitt dargestellt, wie ein Notebook aussieht. Hier sei nur ein sehr kurzer Überblick über Jupyter Notebooks gegeben:
Man vergibt in der obersten Zeile einen Namen, unter dem das Notebook gespeichert wird. Jupyter speichert regelmäßig automatisch, doch kann mittels Klick auf das entsprechende Icon (oder mit *STRG + S*) auch manuell gespeichert werden.
Ein Notebook funktioniert, wie dem Screenshot zu entnehmen ist, mit einzelnen Zellen, die Markdown oder Pythoncode enthalten können. Nachdem die Zellen befüllt sind, müssen sie ausgeführt werden; entweder mit *SHIFT + Enter*, dann wird die Zelle ausgeführt und in die folgende Zelle gewechselt, oder mit *STRG + Enter*, dann wird nur die gewählte Zelle ausgeführt.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
####  Links:
  
+ [Anaconda unter Windows installieren](https://medium.com/@neuralnets/beginners-quick-guide-for-handling-issues-launching-jupyter-notebook-for-python-using-anaconda-8be3d57a209b )
  
+ [Anaconda (Navigator) unter Linux installieren](https://medium.com/@thecraftman/installing-anaconda-navigator-on-linux-ubuntu-18-04-d805d5a0f71a )
  
+ [Einrichten von Anaconda (TU Harburg)](https://fizban05.rz.tu-harburg.de/itbh-inf-wise201718/veranstaltungsskript-inf-wise201718/material/sitzungsmaterial/einrichtung-byod-python.html )
  
+ [Einführung zu und Benutzung der Kommandozeile](https://tutorial.djangogirls.org/de/intro_to_command_line/ )
  
  