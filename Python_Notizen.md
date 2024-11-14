### Mehrere Python Versionen

Es ist möglich mehrere Versionen von Python im gleichen System gleichzeitig installiert zu haben.

Eine der Versionen ist die *default* Version und wird ausgeführt wenn die Befehle `python` bzw. `python3` aufgerufen werden.

**Die aktuelle Version herausfinden**

`python --version`

**Eine spezifische Version von Python installieren**

```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.9
sudo apt install python3.9-venv
```

Die pyhton Version 3.9 wird aus dem `ppa` *deadsnakes* heruntergeladen.

+ Was ist dieses `ppa` *deadsnakes*? https://github.com/deadsnakes
+ Ist das sicher? https://youtu.be/Xe40amojaXE

**Überprüfen, dass 3.9 installiert wurde**

`python3.9 --version`

**Virtuelle Umgebung mit spezifischer python Version**

Nachdem die Version 3.9 installiert wurde, können wir eine virtuelle Umgebung erstellen, die diese spezifische python Version verwendet.

Wir navigieren zu unserem Projektverzeichnis, z.B. `cd ~/Projekt`

Erstellen eines Untervezeichnisses, das die virtuelle Umgebung beinhalten wird (eine gute Idee!)

`python3.9 -m venv ./myvenv`

Wir aktivieren die virtuelle Umgebung:

`source ./myvenv/bin/activate`

Jetzt überprüfen wir, dass die *default* Version von python innerhalb dieser virtuellen Umgebung die gewünschte ist:

`python --version`

Die Ausgabe sollte `Python 3.9.x` sein.

Jetzt können wir mit dieser Version weiter arbeiten. Zum Beispiel `jupyter notebooks` bzw. `jupyter Lab` installieren.


venv deaktivieren wenn wir fertig sind.

`deactivate`


**Eine virtuelle Umgebung löschen**

Es könnte sein, dass wir eine virtuelle Umgebung mit der falschen Python-Version erstellt haben und jetzt möchten wir diese Umgebung löschen, um möglicherweise eine neue Umgebung mit der richtigen Python-Version zu erstellen.

Falls die Umgebung aktiv ist, sollten wir diese zuerst deaktivieren

`deactivate`

Wir sollten das alles deinstallieren, was wir in der falschen Umgebung installiert haben, z.B. jupyter notebook bzw. jupiterLab.

`python -m pip uninstall jupyter`

oder 

`python -m pip uninstall jupyterlab`

Jetzt haben wir zwei Optionen

**1. Es gibt ein Unterverzeichnis, das die virtuelle Umgebung beinhaltet:**

+ Das Verzeichnis in dem die virtuelle Umgebung enthalten ist einfach löschen. Möglicherweise `venv` oder `myenv`

**2. Die virtuelle Umgebung und die weiteren Projektdateien sind zusammen im gleichen Verzeichnis**

+ Die spezifische Verzeichnisse der virtuellen Umgebung löschen. Übliche Verzeichnisse sind: `bin/` `lib/` `include/` `lib64/` `pyvenv.cfg`
+ In Windows noch: `Scripts/` `Lib/`

