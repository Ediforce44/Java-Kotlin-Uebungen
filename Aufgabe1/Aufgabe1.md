# Basics in Git

Hier folgt eine kleine Einführung in git und PyCharm.

## Git

1. Unsichtbare Sachen sichtbar machen :D    
    - Du dückst `Windows` +  `E` (Und neuen shortcut gelernt? Oder kanntest du das schon?)
    - Dann navigierst du dich in unseren **Java-Kotlin-Uebungen** Ordner und klickst in der obersten Leiste des Dateiexplorers auf `Ansicht` und 
    kreuzt folgendes an:
    
        - [x] Ausgeblendete Elemente 
        
    - Wenn du aufmerkam hast du gesehen wie dein Textexplorer einen neuen Ordner anzeigt. Den `.git` Ordner.
    - In diesem Ordner befinden sich alle möglichen Konfigurationsdateien für **git**.

2. Was macht **git**, kurzes Tutorial
    - Erstelle einfach mal ein neues Textdokument in dem Ordner **Aufgabe 1**.
    - Das folgende wird ab sofort immer der erste Schritt sein bzw. wir werden mit GitKraken eine schönere Lösung finden: 
        - Du gehst in deinen **Java-Kotlin-Uebungen** Ordner, machst rechtsklick auf einen freien Platz und wählst `Git Bash Here`.
        (Übrigens was das macht ist nichts anderes als **git** in dem Ordner zu öffnen in dem du bist. Du könntest auch 
        **git** über seine `.exe` öffnen und dich per Komandozeile in den Ordner navigieren, aber das ist ziemlich 
        umständlich)
    - Wenn du nun **git** einen Befehl geben willst, musst du es zuerst ansprechen durch `git`. Danach kommt ein 
    `Leerzeichen` und ein Befehl und dann irgendwelche Parameter für diesen Befehl.
    - Es gibt 7 wichtige Befehle:
        
        `clone`, `status`, `add`, `commit`, `log`, `pull`, `push`
        
        Den ersten hast du schon kennengelernt.
    - `status` zeigt dir den Status aller Datein an, die sich in diesem Repository befinden. Damit fangen wir auch an:
    
        ```git status```
     
        - Nach dieser Eingabe siehst du, dass sich *untracked fiels* in dem Ordner `Aufgabe 1` befinden. Das bedeuted du 
        hast Dateien in deinem geklonten Repository, die noch nicht von **git** erfasst wurden. Das bedeutet diese 
        Dateien existieren nur bei dir auf deinem PC und nicht auf dem Repository auf dem Server. (Und in der Tat kannst
        du das gerne mal nachschauen)
        - Aber vielleicht ist das Textdokument, dass du vorher erstellt hattest nur wichtig für dich und du willst das nicht auf den Server hochladen. 
        - Und aus diesem Grund sagen wir **git** es soll diese Datei ignorieren und nicht 'tracken'.
        - Dazu erstellst du eine Datei `.gitignore`. Unter Windows geht es nicht Dateien zu erstellen, die keinen Namen und nur eine Endung haben. Daher müssen wir das über die 
        Komandozeile machen. Du gibst also folgendes in dein offenes git-Fenster ein:
    
            ```touch .gitignore```
    
        - Nun öffnest du die `.gitignore` Datei mit irgendeinem Texteditor und gibst den namen inklusive Endung deines Textdokuments ein.
        - Du drückst speichern und nun weiß git, dass es diese Datei zu ignorieren hat.
        - Das überprüfen wir:
        
            ```git status```
        
        - Nun sagt **git**, dass nur noch die `.gitignore` Datei *untracked* ist.
        
        ![git untracked](/Images/GitEinweisung1.png)
        
        - Diese wollen wir nun zum Repository hinzufügen. Dort kann dann jeder reinschreiben, was er nicht von **git** 
        erfasst haben möchte.
    - `add` *staged* nun eine oder mehrere Dateien. Das heißt für **git** ist die Datei/Datein nicht mehr *untracked*, 
    sondern staged.
        - *untracked* Datein sind Datein, die neu erstellt oder verändert wurden
        - *staged* Datein sind Datein, die beim nächsten Commit/Protokollieren protokolliert werden von git
        - Du kannst folgendes eingeben, um alle *untracked* Datein zu *stagen*:
        
            ```git add *```     oder    ```git add .gitignore``` , um nur *.gitignore* su *stagen*
            
        - Nun kannst du dir nochmal dan Status ausgeben lassen mit `git status`
        - Du siehst es befinden sich keine *untracked* Datein mehr in **git**
        
        ![git staged](/Images/GitEinweisung2.png)
        
        - Als nächstes müssen die *staged files* noch *commited* werden, damit git die Änderungen wirklich speichert 
        (Also lass dich von dier grünen Schrifft nicht täuschen, wir sind noch nicht fertig) 
    - `commit` *commited* nun alle Datein, die in **git** *staged* sind.
        - Mit folgendem Befehl *commitest* du alle Datien mit einer von dir geschriebenen *Commit Message*:
        
            ```git commit -m "Deine Nachricht (z.B. Füge .gitignore hinzu)"```
           
            (Anführungszeichen sind Pflicht)
        - Beim Ausführen von `git status` siehst du nun, dass es nichts gibt, was **git** nicht erfasst hat.
    - `pull` ist ein Befehl mit dem du alle Änderungen des Repository auf dem Server die jemand anderes hinzugefügt hat
    auf die Kopie des Repositories auf deinem PC überträgst. Das bedeutet du bringst deine Projekt auf den neusten 
    Stand durch Eingabe von:
    
        ```git pull origin```
        
        - `origin` ist der Standardname für ein Repository und in diesem Fall dieses Repository. Dannach wirst du 
        aufgefordert dein *passphrase* einzugeben und **git** holt sich alle Sachen die sich im Repository geändert 
        haben seit deinem letzten `pull`. (z.B. Diese Datei)
    - `push` ist das Gegenteil von `pull`. Durch Ausführen dieses Befehls lädst du alle deine lokalen Änderungen auf
    das Repository hoch (allerdings nur die die du *commited* hast):
    
        ```git push origin```
        
        - Du kannst nun [GitHub](https://github.com/Ediforce44/Java-Kotlin-Uebungen) vergleichen mit dem was du geändert hast und 
        siehst, dass es hochgeladen wurde.
    - `log` mit dem Befehl kannst du dir das "Logbuch" anzeigen lassen. Also git zeigt dir die letzten `commits` an:
    
        ```git log```
         
        - Das Logbuch wird in einem internen Editor, namens *Vim*, geöffnet. Alles was du wissen musst, ist dass du das
        Logbuch verlassen kannst durch eingabe von `q` (für *quit*)