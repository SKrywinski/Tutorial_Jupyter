Übersicht
=========

Nicht nur im sagt Verlauf dieses Seminars werden Sie vor der Notwendigkeit stehen, Code ausführen, Codeschnipsel kombinieren oder Code selber erzeugen zu müssen.
Vor allem zur schnellen Ausführung von Code und zur Entwicklung bietet es sich an, Jupyter-Notebooks zu verwenden. Damit ist es möglich, Code zeilenweise auszuführen, um zu überprüfen, ob er tut was er soll, ohne auf eine umfangreiche und große Entwicklungsumgebung wie [PyCharm](https://www.jetbrains.com/pycharm/)[^note1] zurückgreifen zu müssen.[^note2]

[^note1]: PyCharm ist in einer kostenlosen Community- und einer für Studenten auch kostenlosen professionellen Version erhältlich
[^note2]: Hinweis auf Atom + Hydrogen?

## From zero to Jupyter

+ what is Jupyter

+ why Jupyter

Auf [Google Colab](https://colab.research.google.com/) kann man - sofern ein Google-Konto vorhanden ist, Jupyter-Notebooks ausprobieren, ohne etwas installieren zu müssen. Jedoch: (Später vielleicht) Sensible Daten werden so aus der Hand gegeben; dies gilt es im Hinterkopf zu behalten.

## Installation {install}
### Anaconda
Zur Installation von Jupyter empfiehlt sich, dies zusammen mit der Anaconda-Distribution zu tun. Jupyter über `pip` zu installieren ist eher fortgeschrittenen Benutzern zu empfehlen[^note4].
[^note4]: https://jupyter.readthedocs.io/en/latest/install.html

  + Was ist Anaconda

  Anaconda ist sozusagen ein Softwarepaket, dass sich nicht nur um die richtige Installation von Python (und R) kümmert, sondern auch dafür sorgt, dass Abhängigkeiten von (Python-)Paketen richtig aufgelöst werden.
  Das verhindert nicht nur Fehler durch Inkompabilität sondern möglicherweise auch durch Änderungen in den Paketen selbst, die sich mitunter auf Ausgeben von selbstentwickelten Programmen auswirken.
  Dabei und dafür bringt Anaconda die Entwicklungsumgebung Spyder mit und beinhaltet eine umfangreiche Paketsammlung[^note5] für Python, sodass zunächst mit keiner anderen Paketverwaltung gearbeitet werden muss.
  So erklärt sich die Downloadgröße von Anaconda.
  Vom Anaconda Navigator, der "Benutzeroberfläche" von Anaconda aus sind alle Tools wie Jupyter, Spyder, Paketverwaltung aber auch Installation und Update von Paketen erreichbar; so können viele Aufgaben von einem Ort und zunächst ohne Kommandozeile erledigt werden.
  + Warum Anaconda/so ein Riesenpaket?
  + Spyder
+ Python 3! = Anaconda 3(?)

Bei der Auswahl der richtigen Anaconda-Distribution kommt es auf folgende Punkte an:
+ welches Betriebssystem: Windows - Linux - macOS
+ 32bit - 64bit: zu finden in den Systeminformationen, neuere Geräte sind vermutlich mit 64bit-Software ausgestattet
Für Linux und macOS nur 64bit
+ Python-Version 3 (Python 2 wird in Zukunft nicht mehr weiterentwickelt)

[Anaconda-Download-Seite](https://www.anaconda.com/distribution/#download-section)
[^note5]: Häufig verwendete Pakete wie numpy, pandas, matplotlib, SciPy und viele weiter sind bereits enthalten

+ Die Installation unter Linux und macOS sollte relativ ähnlich sein

Weil die Installation von Anaconda auf Linux und macOS sehr ähnlich sein sollten, wird bei den folgenden Hinweisen nur auf Windows und Linux eingegangen.
Ein wichtiger Hinweis, der in beiden Fällen gilt: Soll Anaconda installiert werden, so ist es sehr wichtig bestehende Pythoninstallationen (auch IDLE oder Ähnliches) restlos vom System zu entfernen. Dies betrifft auch schon eingerichtete Umgebungsvariablen. Sollte Anaconda parallel installiert werden kann (und wird) es zu Vermischungen und Fehlern kommen, die nur sehr aufwändig behoben werden können.

### Windows {windows}
+ **Erst alle anderen Python-Installationen deinstallieren und vorhandene PATH- und Umgebungsvariablen zu entfernen**
→ wie Entfernt man die am Besten?

+ Pfade ohne Leerzeichen! → Fehlerquelle
  + `"C:\Users\My Name"`
  + `"C:\Users\My\ Name"`?`"C:\\Users\\My\ Name"`
  + Besser: `"C:\Users\My_Name"` oder `C:\Users\MyName`
  + Achtung: Windows `"C:\Users"` vs. Unix: `"/home/users"` → Rückstrich vs. Schrägstrich
+ Pfad(e) merken (für alle OS) → für spätere Installationen/Problemlösungen
+ Für alle Nutzer/All Users

Windows vs. Linux
+ PATH

### Linux {linux}

### macOS {mac}



### Jupyter Probleme
+ Passwortabfrage
  + token aus Kommandozeilenausgabe kopieren und einfügen


Danach:
+ conda
+ pip - pip user...
+ pyenv
+ pipenv

# Links:
+ [Better Medium Installation Guide](https://medium.com/@neuralnets/beginners-quick-guide-for-handling-issues-launching-jupyter-notebook-for-python-using-anaconda-8be3d57a209b)

+ [Einrichten von Anaconda (TU Harburg)](https://fizban05.rz.tu-harburg.de/itbh-inf-wise201718/veranstaltungsskript-inf-wise201718/material/sitzungsmaterial/einrichtung-byod-python.html)
