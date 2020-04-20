  
  
  
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
  
  
  
###  Ordnerstruktur verstehen
  
  
  
  
Um nachzuvollziehen, was während der Installation von Jupyter und generell bei der Arbeit in der Kommandozeile passiert, hier ein kurzer Überblick der Strukturierung im Dateisystem.
Es ist notwendig, zu verstehen, wie Pfadangaben zum Beispiel mit graphischen Dateimanagern zusammenhängen.
  
  
  
<img src="img/Windows-Explorer.png?0.5116763107787441"  width="600px"  alt="Windows Explorer" >
  
  
  
  
  
  
  
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
Dieser befindet sich in `C:\Users\%USER%\Desktop` in Windows und `/home/<username>/Desktop` ^[Je nach Linuxdistribution kann der Ort auch anders, z. B. `Schreibtisch` heißen].
  
Dabei fällt auf, dass sich in den Pfadangaben von Windows `\` und Linux `/` unterscheiden. Dies führt gerne zu Problemen.
  
####  Verzeichnis/Ordner wechseln
  
  
Möchte man in den übergeordneten Ordner `C:\Users\%USER%\` oder `/home/<username>/` wechseln, gibt man `cd ..`^[change directory] ein. Durch `cd Dokumente` wechselt man vom übergeordneten Ordner eine Ebene tiefer nach Dokumente. Es ist sehr wichtig, sich das klarzumachen.
  
####  Absolute und relative Pfadangaben
  
  
Um zwischen verschiedenen Orten zu navigieren kann man relative Pfadangaben (vom Ort aus, *an dem man sich befindet*) oder absolute Pfadangaben verwenden.
Vom Ort `C:\Users\%USER%\Dokumente` oder `/home/<username>/Dokumente` aus gibt es zwei Wege, um in den Ordner `Bilder` zu wechseln:
+ `cd..`, vom relativen Pfad aus eine Ebene höher zu steigen und dann `cd Bilder`, um eine Ebene tiefer, in den gewünschten Ort zu wechseln
+ `cd C:\Users\%USER%\Bilder` oder `cd /home/<username>/Bilder`, um, egal, wo man sich befindet, direkt in den absoluten Ordner zu wechseln.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
###  Kommandozeile / Terminal
  
<img src="img/Open_CMD.jpg?0.5318762809857345"  width="600px"  alt="Kommandozeile" >
  
Die Kommandozeile ist eine der ersten Möglichkeiten, mit einem Programm (oder dem Betriebssystem) zu interagieren[^noteC1]. Zwar wirkt der Umgang mit der Kommandozeile oft kompliziert, da dieser im Folgenden aber unumgänglich ist, hier einige kurze einleitende Worte. Man wird schnell merken, das jede Angst der Benutzung unbegründet ist und die Nutzung der Kommandozeile für alltägliche Arbeiten oft der effizienteste Weg.
Die Kommandozeile gibt es auf jedem Betriebssystem und sie funktioniert auch überall ziemlich ähnlich.
Unter Windows startet man sie durch Drücken von *Windowstaste + R* und der Eingabe von `CMD`.
Unter Linux benutzt man dafür das *Terminal*, auf einigen Distributionen drückt man *ALT + CTRL + T*.
Es öffnet sich ein meist schwarz oder weiß hinterlegtes Fenster. Zu sehen ist ein meist blinkender Cursor. Dort wird die Eingabe erwartet.
Der Cursor steht hinter einem `>` (Windows) oder einem `$` (Linux). Vor diesen Zeichen, die anzeigen, dass eine Eingabe erwartet wird, ist der aktuelle Pfad, in der sich die Kommandozeile gerade befindet. Standardmäßig öffnet sich diese im entsprechenden Benutzerverzeichnis, `C:\Users\%USER%` (Windows) und `/home/<username>`[^noteC2], wobei dieser Standardpfad in Linux mit `~` abgekürzt ist[^noteC3]. In diesem Zusammenhang ist es hilfreich, sich noch einmal klarzumachen, was im Abchnitt [Ordnerstruktur](folderstructure.md#Ordnerstruktur ) beschrieben wurde.
Auf weiterführende Erklärungen bezüglich verschiedener Benutzer- und Rechteverwaltung wird hier bewusst verzichtet.
  
[^noteC1]: [Erklärung](https://tutorial.djangogirls.org/de/intro_to_command_line/ ) für alle Betriebssysteme
[^noteC2]:`%USER%` und `<username>` sind natürlich Platzhalter für die jeweiligen Benutzernamen. Vor allem unter Windows findet man immer wieder auch `%APPDATA%`, um auf (versteckte) Benutzerdaten zugreifen zu können. Diese sind standardmäßig versteckt.
[^noteC3]:Ein Wechsel in das eigene Homeverzeichnis ist unter Linux mit der Eingabe `cd ~` möglich
  
In der Kommandozeile kann im Dateisystem navigiert werden, Dateien und Ordner können aufgelistet und manipuliert werden (Erstellen, Umbenennen, Löschen, Kopieren, etc.). Alles was in einer grafischen Benutzeroberfläche meist mit der Maus gemacht wird und noch mehr ist hier möglich. Die vielen Befehle wirken sicher zunächst abschreckend, werden aber schon nach weniger Zeit des Umgangs ganz automatisch von der Hand gehen.
  
Einige der am häufigsten gebrauchten Befehle sind in der Tabelle unten zu finden.
  
  
  
  
  
  
####  Einige Entsprechungen von wichtigen Windows- und Unix-Kommandos
  
  
  
  
  
  
  
  
  
|    CMD Command    | UNIX Command |   PowerShell Command  | PowerShell Alias |                  Erklärung                 |
|-------------------|--------------|-----------------------|------------------|--------------------------------------------|
| dir               | ls           | Get-ChildItem         | gci              | Ordnerinhalt anzeigen (`directory`, `list`)|
| cls               | clear        | Clear-Host (function) | cls              | Konsole leeren                             |
| del, erase, rmdir | rm           | Remove-Item           | ri               | Lösche-Befehl (`delete`, `remove`)         |
| copy              | cp           | Copy-Item             | ci               | Kopieren                                   |
| move              | mv           | Move-Item             | mi               | Verschieben (`move`)                       |
| rename            | mv           | Rename-Item           | rni              | Umbenennen (unter Linux wird Umbenannt durch Verschieben)|
| type              | cat          | Get-Content           | gc               | Inhalt von (einer) Datei(en) anzeigen (`concatenate`)|
| cd                | cd           | Set-Location          | sl               | Ort (Ordner) wechseln (`change directory`)[^noteC4]  |
| md                | mkdir        | New-Item              | ni               | Ordner anlegen (`make directory`)[^noteC5]|
  
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
  
  
  
  
  
Auf [Google Colab](https://colab.research.google.com/ ) kann man - sofern ein Google-Konto vorhanden ist, Jupyter-Notebooks ausprobieren, ohne etwas installieren zu müssen. Jedoch: (Später vielleicht) Sensible Daten werden so aus der Hand gegeben; dies gilt es im Hinterkopf zu behalten.
  
###  Installation
  
####  Anaconda
  
Zur Installation von Jupyter empfiehlt sich, dies zusammen mit der Anaconda-Distribution zu tun. Jupyter über `pip` zu installieren ist eher fortgeschrittenen Benutzern zu empfehlen[^note4].
[^note4]: https://jupyter.readthedocs.io/en/latest/install.html
  
  + Was ist Anaconda
  
  Anaconda ist <!--sozusagen--> ein Softwarepaket, dass sich nicht nur um die richtige Installation von Python (und R) kümmert, sondern auch dafür sorgt, dass Abhängigkeiten von (Python-)Paketen richtig aufgelöst werden.
  Das verhindert nicht nur Fehler durch Inkompabilität sondern möglicherweise auch durch Änderungen in den Paketen selbst, die sich mitunter auf Ausgeben von selbstentwickelten Programmen auswirken.
  Dabei und dafür bringt Anaconda die Entwicklungsumgebung Spyder mit und beinhaltet eine umfangreiche Paketsammlung[^note5] für Python, sodass zunächst mit keiner anderen Paketverwaltung gearbeitet werden muss.
  So erklärt sich die Downloadgröße von Anaconda.
  Vom Anaconda Navigator, der "Benutzeroberfläche" von Anaconda aus sind alle Tools wie Jupyter, Spyder, Paketverwaltung aber auch Installation und Update von Paketen erreichbar; so können viele Aufgaben von einem Ort und zunächst ohne [Kommandozeile](commandline.md ) erledigt werden.
  <!--
  + Warum Anaconda/so ein Riesenpaket?
  + Spyder
+ Python 3 != Anaconda 3(?)-->
  
Bei der Auswahl der richtigen Anaconda-Distribution kommt es auf folgende Punkte an:
+ welches Betriebssystem: Windows - Linux - macOS
+ 32bit - 64bit: zu finden in den Systeminformationen, neuere Geräte sind vermutlich mit 64bit-Software ausgestattet
Für Linux und macOS nur 64bit
+ Python-Version 3 (Python 2 wird in Zukunft nicht mehr weiterentwickelt)
  
[Anaconda-Download-Seite](https://www.anaconda.com/distribution/#download-section )
[^note5]: Häufig verwendete Pakete wie numpy, pandas, matplotlib, SciPy und viele weiter sind bereits enthalten
  
+ Die Installation unter Linux und macOS sollte relativ ähnlich sein
  
Weil die Installation von Anaconda auf Linux und macOS sehr ähnlich sein sollten, wird bei den folgenden Hinweisen nur auf Windows und Linux eingegangen.
Ein wichtiger Hinweis, der in beiden Fällen gilt: Soll Anaconda installiert werden, so ist es sehr wichtig bestehende Pythoninstallationen (auch IDLE oder Ähnliches) restlos vom System zu entfernen. Dies betrifft auch schon eingerichtete Umgebungsvariablen. Sollte Anaconda parallel installiert werden kann (und wird) es zu Vermischungen und Fehlern kommen, die nur sehr aufwändig behoben werden können.
  
####  Windows
  
+ **Erst alle anderen Python-Installationen deinstallieren und vorhandene PATH- und Umgebungsvariablen zu entfernen**
  
  
  
  
  
+ Pfade ohne Leerzeichen! → Fehlerquelle
  + `"C:\Users\My Name"`
  + `"C:\Users\My\ Name"`?`"C:\\Users\\My\ Name"`
  + Besser: `"C:\Users\My_Name"` oder `C:\Users\MyName`
  + Achtung: Windows `"C:\Users"` vs. Unix: `"/home/users"` → Rückstrich vs. Schrägstrich
+ Pfad(e) merken (für alle OS) → für spätere Installationen/Problemlösungen
+ Für alle Nutzer/All Users
  
Windows vs. Linux
+ PATH
  
####  Linux
  
  
####  macOS
  
  
  
  
####  Häufige Probleme
  
+ Passwortabfrage
  + token aus Kommandozeilenausgabe kopieren und einfügen
  
  
  
  
  
####  Links:
  
+ [Better Medium Installation Guide](https://medium.com/@neuralnets/beginners-quick-guide-for-handling-issues-launching-jupyter-notebook-for-python-using-anaconda-8be3d57a209b )
  
+ [Einrichten von Anaconda (TU Harburg)](https://fizban05.rz.tu-harburg.de/itbh-inf-wise201718/veranstaltungsskript-inf-wise201718/material/sitzungsmaterial/einrichtung-byod-python.html )
  
+ [Einführung zu und Benutzung der Kommandozeile](https://tutorial.djangogirls.org/de/intro_to_command_line/ )
  
  