![Logo](https://github.com/GuideOS/things-and-stuff/blob/main/artikel_photos/guideos_header.png?raw=true)

Im Oktober 2024 schrieb der Admin (@Stardenver) der LinuxGuides-Community einen Kommentar unter einen News-Post, der ungefähr so klang: „Ich hatte ja auch mal echt Bock, eine eigene Distro zu bauen!“

Nachdem die Idee im Moderatoren-Team abgesegnet wurde, ging es an die Umsetzung.

### Gemeinsam statt einsam

Die Rahmenbedingungen wurden abgesteckt. Es soll ein Projekt werden, das ein ganzes Forum einbeziehen soll. Es entstanden hitzige Debatten über die Basis, am Ende wurde sich für Debian entschieden. Diese Entscheidung war langwierig und nur Teil des groben Umrisses. Die eigentlich Mammutaufgabe besteht darin die einzelnen Fähigkeiten der Forums-Nutzer zu bündeln, die Schwelle um zu partizipieren soll so niedrig wie möglich sein. Von einfachen Gedankenspielen, Ideen und Bildschnipsel bis hin zu Code und Expertise in IT-Infrastruktur ist alles erlaubt.    
    
![Desktop](https://github.com/GuideOS/things-and-stuff/blob/main/img/Bild1.png?raw=true)    
    
### Das Schöne: Alles ist von Anfang an dokumentiert!

[Community Projekt: Bestände Interesse am Bau/Modifizierung einer eigenen Distro?](https://forum.linuxguides.de/index.php?thread/7487-community-projekt-best%C3%A4nde-interesse-am-bau-modifizierung-einer-eigenen-distro/&pageNo=1)


### Infrastruktur und Kommunikation

Der große Vorteil des Projektes ist das Forum. Man kennt sich, schreibt oft mit den selben Nutzern und weiß wie man den Anderen "zu nehmen hat". Auf dieser Basis ist es eine tolle Erfahrung gemeinsam etwas aus dem Nichts zu erschaffen. Kleine Anmerkungen aus dem Forum werden im Code-Team genaustens diskutiert. Am Ende steht eine direkte Umsetzung oder ein Voting zum Thema in der Community. Während der Beta-Phase entwickelte das Team ein Tool, das direkt aus GuideOS heraus Bug-Reports in das Forum postet, sodass unmittelbar darüber diskutiert und gemeinsam eine Lösung gefunden werden konnte.

Schon in der Ideen-Sammelphase beschloss das Mod-Team auf die Vote-Funktion des Forum zu setzen. So konnten Meinungen und Stimmungen sehr gut von Beginn an abgegriffen werden. Voting kann aber schief gehen. Nachdem die Community beschlossen hatte, dass die Firewall ab Installation eingeschaltet sein soll, kam es bei den Testern vermehrt zu Problem, teilweiße so gravierend, dass nicht mal mehr APT funktionierte und die Entscheidung revidiert werden musste.

### Das Core-Team

Zunächst bestand das Team ausschließlich aus Moderatoren des Forums, welche Know-How zum Distro-Bau, Paket-Bau, APT, DPKG, Python und BASH mitbrachten. Schnell wurde aber klar, dass Grafiker und Webdesigner gebraucht werden. So erweiterte sich das Team über das Jahr hinweg mit normalen (Nicht-Moderatoren) Nutzers des Forums, die sich besonders engagierten.

#### @Stardenver     
Software-Entwicklung, Webinhalte, Koordination, Testing, Bug-Management

#### @evilware666    
Software-Entwicklung, Bug-Management, ISO-Build
    
#### @Actionschnitzel    
Software-Entwicklung, Bug-Management, Package-Maintainer
    
#### @StephanR    
Webinhalte; Art-Design; Projekt-Koordination; Forums-Bereich    
    
#### @KTT76    
Software-Entwicklung, Testing, Bug-Management
    
@Nighworker    
Software-Entwicklung, Testing, Bug-Management
     
### Die Basis

Natürlich wurde auch lebhaft darüber diskutiert, welcher Distribution GuideOS zu Grunde liegen soll. Erste Experimente, die niemals an die Öffentlichkeit kamen, basierten auf Ubuntu Cinnamon. Diese wurden aber schnell wieder verworfen, da es nicht wirklich sicher war, was ein neuer Release mit den GuideOS-Konfigurationen anstellen könnte. Offiziell wurde dann verkündet, dass die erste Beta (Closed-Beta) mit Debian als Basis an den Start geht. Für die ersten Gehversuche wurde noch ein modifiziertes Debian-Live-ISO genutzt - später wurden eine alternative Version mit Spiral-Linux als Basis getestet. Die aktuelle GuideOS-Version ist immer noch an die Konfigurationen von Spiral angelehnt, wird aber mit sehr vielen Anpassungen über live-build/lb config und lb build aufgesetzt.

#### Die Software

Einstimmig war die Community schon zu Beginn dafür, dass ProjectGuideOS (Arbeitstitel) für Anfänger geeignet sein soll. Das bedeutete sehr wenig Terminal und viele Buttons zum klicken. Daraus entwickelte sich später ein ganzes Repository, voll mit kleinen Helfer-Tools aus der Community.

![GOS-Tools](https://github.com/GuideOS/things-and-stuff/blob/main/artikel_photos/GuideOS1.png?raw=true)

Den Anfang machte das Tool Primo, welches bewusst an Yast angelehnt sein sollte und viele Funktionen vereint und die Cinnamon-Settings ersetzt.

![Primo](https://github.com/GuideOS/things-and-stuff/blob/main/artikel_photos/Primo1.png?raw=true)

### Die erste Idee

![Ein First Run Wizard](https://github.com/GuideOS/things-and-stuff/blob/main/img/erste-idee.png?raw=true)

### Pakete Management

Die definition "Distribution" kann weit ausgelegt werden. Für das Team bedeutet es ganz klar, ein eigenes Repository zu pflegen. Neben dem Debian-Repo existieren noch eigene GuideOS-Repos die eigene Software enthalten, sowie Software die in Eigenregie portiert wurde. Die Anbindung an APT erfolgt über den OpenBuildService.

### Dein Wunsch ist mir Befehl

In einem Thema im Forum zu zukünftige Funktionen kam die Idee eines Nutzers auf, einen Layout-Changer a la ZorinOS zu entwickeln. Die Idee fand sofort Anklang und wurde von Entwickler @Actionschnitzel mit den Worten "Ach, das ist ja nur ein bisschen JSON-File-Geschubse" also schnell zu erledigen abgetan. In Wahrheit hat die Entwicklung dann ein halbes Jahr gedauert und bis wenigstens 80% der Bugs verschwunden waren, wurden dutzende Wikis rauf und runter gelesen. Am Ende (ent)stand das:
![Layouter](https://github.com/GuideOS/things-and-stuff/blob/main/img/primo-layout.png?raw=true)
    
### Die menschliche Komponente

Wir wollen natürlich nah am Nutzer sein. Um schnell Rückmeldungen zu bekommen, haben wir ein GUI geschrieben, welches ohne Anmeldung einen Bug an unsere Redmine-Instanz sendet. Ein Bot überträgt das Ganze dann ins Forum. Ob das bei einer großen Nutzerschaft immer noch praktikabel sein wird, muss sich allerdings noch zeigen. 

Menschen übersehen gerne etwas und machen auch Fehler. Als die ersten Bugreports eintrudelten, war das ganze Team am rotieren und bemüht, alles auszubügeln. In diesem einen Jahr kam es aber auch vor, dass einige von uns nicht schlafen konnten oder neben ihrer Frau im Bett lagen und vor dem geistigen Auge Python-Code geschrieben haben, der denn sogar wirklich funktionierte. Der Satz: "Als, ich mich darauf eingelassen hab', hatte ich mir das einfacher vorgestellt!", ist auch des öfteren gefallen. 

Die große Erkenntnis ist aber, das hinter jeder Distro Menschen stecken, die eine Leistung vollbracht haben. Man schreibt nicht einfach mal so Code - auch nicht in Zeiten von ChatGPT. Alles muss manuell angepasst werden, ob das nun GuideOS, Ubuntu oder CachyOS heißt. 

### Wohin die Reise führt

Jetzt im Spätsommer 2025 ist schon klar, dass GuideOS langfristig auf Trixie zur finalen Version vorangetrieben werden soll. Damit bleiben wir auf Debian und schauen gemeinsam, dass wir die finale Version 1.0 noch in diesem Jahr an den User bringen können.

Natürlich soll GuideOS eine funktionierende Distro sein. Im Fokus steht aber auch das Lernen. Unbestreitbar kann jeder, der zum Core-Team gehört, mit absoluter Sicherheit sagen, dass er mehr über Linux gelernt hat. Das ist auch eine Grundvoraussetzung: Lernen und über seinen Schatten springen. Man muss nicht Programmieren können um bei GuideOS dabei zu sein. Aber es ist auch mehr als einmal passiert, dass Team-Mitglieder, die eigentlich nur einen kleinen Teil mit vorhandenem Wissen beitragen wollten, sich plötzlich umfangreiche Handbücher bestellt haben, weil sie noch mehr wissen und leisten wollten.

Vieles ist offen und neben den ernormen Möglichkeiten und der Chance, gemeinsam etwas zu schaffen, ist da natürlich auch immer die Angst, dass man mit einem solchen Projekt scheitern könnte. Wie wir uns die Angst nehmen? Hier wird es jetzt ganz prakmatisch und vielleicht sogar klischeehaft: Der Weg ist das Ziel. Wir sind aus der Community enstanden und diese ist der Stützpfeiler und das Herz von GuideOS. Egal wie der Weg verläuft und egal wohin er uns führt - wir gehen ihn gemeinsam als Community. Auf diesem Weg haben wir viel Spaß, lernen viel Neues, wachsen über uns hinaus und wir machen einfach etwas ganz tolles als Gemeinschaft. Das kann uns niemand mehr nehmen und egal was kommt, wir erleben es gmeinsam. Danke an die gesamte Community.
