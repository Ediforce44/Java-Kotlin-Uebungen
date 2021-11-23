# README

Im folgenden findest du Links zum Installieren und eine Einweisung zum Aufsetzen der Programme.

## Downloads

1. [Git](https://git-scm.com/download/win)
2. [Java RE 8](https://java.com/de/download/)
3. [Java JDK 17](https://www.oracle.com/java/technologies/downloads/#jdk17-windows)
4. [IntelliJ Edu](https://www.jetbrains.com/de-de/edu-products/download/#section=idea)

## Installation

- **Git**
    - Downloade **Git** von dem Link 
        - Folge den Installationsanweisungen und achte darauf, wenn du gefragt wirst, **git** zum *Kontextmenü* 
        hinzuzufügen (Dies solltest du ankreuzen)
    - Starte git-bash in deinem Installationsordner (an dem du Git installiert hast) und folge folgenden Befehlen:
        - ACHTUNG: Um etwas in git einzufügen funktioniert nur 'Rechtsklick' und dann 'Einfügen' 
            - `Strg` + `V` funktioniert in git nicht
        - Füge deinen Nutzernamen hinzu, indem du folgende Zeile eingibst/kopierst (vielleicht nicht *Mona Lisa* ;))
                
            ```git config --global user.name "Mona Lisa"```
                
        - Als nächstes stellst du eine Verbindung zwischen deinem GitHub-Account und git auf deinem PC her (ein Glück muss man das nur einmal machen)
            - Zunächst generierst du dir einen SSH-Schlüssel, indem du deine E-mail-Adresse benutzt, die du auch bei GitHub verwendest
                
                ```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```    
            
            - Als nächstes wird dir folgendes angezeigt: 
              ```> Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):```
              Das zeigt dir nur die Info an, wo der Schlüssel abgelegt wird (Keine Sorge du musst nichts von all dem hier 
              verstehen oder dir merken). Nun drückst du **Enter**
            - Du wirst jetzt aufgefordert ein Passwortsatz (passphrase) einzugeben. Hier kannst du irgendein Passwort 
              nehmen, es muss nichts kompliziertes sein. (Am besten etwas kurzes, was du dir gut merken kannst). **Enter**
            - Dann musst du durch nochmalige Eingebe des Passwortes es bestätigen. **Enter**
              > **Funfact:** 'ssh-keygen' generiert dir einen Schlüssel mit dem du verschlüsselt zwischen einem Server und deinem PC kommunizieren kannst.
                Die Parameter dabei sind 'rsa', das ist das Verschlüsselungsverfahren welches benutzt wird und 4096, das ist die länge des Schlüssels der generiert wird
                und somit die Sicherheit. Genauer gesagt müsste ein Angreifer 13.930.000.000.000.000.000.000.000.000.000.000.000.000.000 Rechenopreationen ausführen um die 
                Verschlüsselung zu knacken. Sicher genug?
            - Nun fügst du den Schlüssel zu **Git** hinzu. Du gibst wieder in git ein:
            
                ```eval $(ssh-agent -s)```
               
            - Und dann:
            
                ```ssh-add ~/.ssh/id_rsa```
                
            - Das war es auch schon. Nun musst du nur noch **GitHub** den Schlüssel geben. Mit dem Befehl *clip* 
              kopierst du dir den Schlüssel in die Zwischenablage.
            
                ```clip < ~/.ssh/id_rsa.pub```
            
            - Dann gehst du auf [GitHub](https://github.com/settings/profile). Mit dem Link müsstest du auf YourProfile 
              -> Settings gelangen. Dann navigierst du dich zu **SSH and GPG keys** und drückst **New SSH Key**:
            
            ![New SSH Key](/Images/GitHubEinweisung1.png)
            
            - Als Titel kannst du irgendwas eingeben. Der Titel dient nur für dich zur Identifikation, zu welchem Gerät 
              der Schlüssel gehört. Unten bei **Key** drückst du `Strg` + `v` und dann auf **Add SSH Key**
            - Damit bist du mit dem schlimmsten Teil durch.

- **Java RE**
    - Als nächstes laden wir uns Java runter. Genauer gesagt die Virtuelle Maschine von Java.
      > Java funktiert nämlich so, dass du deinen Code schreibst und dann lässt du einen Compiler darüber laufen, der alles was du geschrieben hast übersetzt in eine Sprache,
        die kein Mensch mehr versteht. Und wichtig anzumerken, auch kein Computer. Bei andere Sprachen wie C oder C++ übersetzt der Compiler deinen Code direkt in von Computern 
        verstehbaren Code. Der Java Compiler jedoch nicht und genauso funktiert das auch bei C#.
      
      > Nun stellt man sich die Frag: Wer versteht denn dann das, was der Compiler macht? Tja und genau da kommt die JVM (Java Virtual Machine) ins Spiel. Die JVM versteht alles
        was der Compiler aus deinem Code gemacht hat und kann es sehr schnell ausführen und übersetzt es während der ausführung quasi deinem Computer und gibt ihm Befehle.
      
      > **Funfact:** Java RE steht für Java Runtime Environment. Also: Java Laufzeit Umgebung. Das ist nichts anderes als eine Umschreibung der Virtuellen Maschine.
        Es ist die Umbegung, in der dein Programm, dass du programmiert hast, zur Laufzeit, wenn es ausgeführt wird, ausgeführt wird.
    - Also du gehst oben auf den Link und drückst auf den dicken, fetten, roten Knopf, auf dem **Herunterladen** steht. Dann führst du das heruntergeladene aus.
    - Du bestätigst alles und drückst immer auf **weiter**, bis du Java installiert hast. 
    - Dann kannst du das Fenster schließen und auf zum nächsten Schritt gehen.

- **Java JDK**
    - Das JDK steht für Java Development Kit. Also alles was du brauchst um ein Java Entwickler/Programmierer zu sein.
      > Mit anderen Worten gesagt beinhaltet das JDK den Java Compiler, der wie oben beschrieben deinen selbst geschriebenen Code in etwas übersetzt, was die Java VM 
        verstehen kann. Außerdem beinhaltet das JDK noch eine große Bibiliothek/API, die einem alle möglichen Grundfunktionen zum Programmieren bietet 
        (So etwas gibt es in jeder Programmiersprache, mal größer mal kleiner)
    - Jedenfalls gehst du auch hier auf den Link oben zum downloaden des Java JDKs und wählst folgenden Download wie auf dem Bild zu sehen ist aus.

    ![JDK Download](/Images/JDK17_Download.png)
    
    - Führe die heruntergeladene Datei aus.
    - Drücke immer auf **next** bis zum Ende der Installation.
    - Danach kannst du das Fenster schließen.
    
- **IntelliJ Edu**
    - JetBrains stellt einige der besten und modernsten Entwicklungsumgebungen her. Und so Benutzen auch wir eine von denen und die heißt **IntelliJ**
      > IntelliJ ist eine Programmierumbegung für Java, wie Visual Studio für C#. Wir benutzen zusätzlich die Edu (Education) Version. Diese Version bietet eine Möglichkeit 
        vorgefertigte Programmieraufgaben zu machen und gleichzeitig testen zu lassen, ob sie richtig sind.
    - Du gehst wie immer oben auf den Link und drückst auf den blauen Knopf, auf dem 'Herunterladen' steht.
    - Dann führst du die heruntergeladene Datei aus.
    - **WICHTIG: Hier drückst du nicht immer nur auf 'Next'.**
    - Im Laufe der Installation solltest du ein Kästchen ankreuzen bei dem daneben steht: ```Add "bin" folder to the PATH```
    - Du kannst auch einen Haken setzten bei ```Create Desktop Shortcut```, aber das ist dir überlassen.
    - Danach drückst du immer auf **next**, bis alles installiert ist.
    
## Einrichten
Hezlichen Glückwunsch, wenn du es soweit geschafft hast. Ab jetzt fängt es an Spaß zu machen :D
- Repository klonen
    - Zunächst suchst du dir ein Ordner aus in den unsere Projekte kommen. Diesen erstellst du und gehst in ihn.
    - Als nächstes machst du einen *Rechtsklick* in diesem Ordner und wählst **Git Bash Here** aus. Dann öffnet sich 
    **git**. (Git **nicht** schließen)
    - Du öffnest wieder [GitHub](https://github.com/). Links siehst du alle Repositories bei denen du Mitglied bist. Ein 
    Repository ist ein Platz auf einem Server auf den mehrere zugreifen können (in dem Fall). Momentan dürftest du nur 
    unseres sehen. Dort drückst du drauf.
    - Nun siehst du einen grünen **Knopf** auf dem `Clone or download` steht. Diesen drückst du.
    - Steht nun oben **`Clone with HTTPS`** drückst du auf **Use SSH**.
    ![Use SSH](/Images/GitHubEinweisung2.png)
    - Nun kannst du auf den Knopf neben dem Link drücken. Dieser kopiert dir den SSH-Link des Repositories in die 
    Zwischenablage
    - Danach wechselst du zurück auf git und gibst folgendes ein um einen Klon des Repositories bei dir auf dem Rechner 
    anzufertigen, der eine exakte Kopie ist und deine Arbeitsumgebung darstellt.
        
        ```git clone``` + 'Rechtsklick' und 'Einfügen', sodass dann ```git clone git@github...``` dasteht.
    
    - **Enter**
    > Damit hast du nun das Repository, das auf dem Server liegt gedownloadet und quasi bei dir offline auf dem PC gecloned.
      Außerdem hast du eine verschlüsselte Verbindung zwischen deinem PC und dem Server aufgebaut, auf der du jederzeit Sachen hochladen und runterladen kannst.
      Und genau das wird die erste Aufgabe sein.
    - Perfekt!!!!!!!!!!
    
- Java Pfadvariable setzen

- IntelliJ
    - Nun kannst du PyCharm öffnen. Du wählst dann `Neues Prejekt` aus und als start Ordner wählst du **Aufgaben** aus, 
    den du gerade geklont hast.
    - Dann sagst du PyCharm noch schnell wo es Python findet, indem du dich wie folgt da hinnavigierst:
    
        `File` -> `Settings` -> `Project: Aufgaben` -> `Project Interpreter`
     
    - Du kannst auf das **Zahnrad** drücken und dann auf **Add..** (die erste Option).
    - Nun wählst du links die 3. Option `System Interpreter` und dann navigierst du dich zu deinem installierten Python 
    und wählst die **python.exe** aus.
    - Dann bist du auch damit fertig und die Abenteuer können beginnen. <3
