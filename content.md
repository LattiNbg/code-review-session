# Code Reviews

by Latti

## Motivation

Frank Sons bei der SoCraTes 2017.
Frontalunterricht vermeiden.
Methode Working out Loud.

3-5 Leute treffen sich 12 Mal für eine Stunde (1-2 wöchentlich).
Ziel festlegen.
Leute kennen sich nicht und haben divergierende Ziele.
Vernetzung und andere Ideen im Fokus.

Kleine Übungen. Z.B. explizit Bedanken. Durch das Lautmachen 
teilst du Informationen.

The richest man in Babylon. Weg von "ich habe keine Zeit".
Sich Zeitscheiben geben und 

## Gründe warum wir das machen

* externer Zwang
* 4-Augen-Prinzip
* Code verbessern
* Weg von **W**issens**inseln**
* Andere Wege kennenlernen
* Know-How im Team besser verteilen (technisch und fachlich)
* Im Team lernen, wie man miteinander reden kann
* Besser schätzen durch gemeinsames Verständnis
* Dinge hinterfragen (lernen)
* Sich selbst hinterfragen
* Training für seinen Lernweg. Wissen von anderen Aufsaugen
* Änderung am Code

## Grundprämisse

* Kein Code ist sicher.
* Alles kann verbessert werden ;-).

## Vermeiden vs. Verhindern 

* Best Practices vs harte Regeln
* Error vs Warnings
* Problem ist, Warnings zu ignorieren
  * Broken Window Theory. Sobald der erste Defekt da ist, 
    kommt es auf einen weiteren nicht an.
  * Zero-Tolerance Strategy: es darf keinen weiteren Defekt geben!

## Was hilft uns dabei?

* Code-Coverage ~= 100%

## Wer führt Code-Reviews aus?

* externer Dienstleister. z.B. Zukunftsfähigkeit antizipieren. "Der Prophet gilt nichts im eigenen Lande". 
  Vorteil ist die Unvoreingenommenheit. Keine Vorgesetzte in der Firma, die man politisch beachten müsste.
  "Was viel Geld kostet, taugt auch was!"
* myself
* eigene Gruppe

## Trennung von fachliche Änderung vs. Verbesserung

* VCS-History ist da absolut überfordert :-(
* Auto-Format + Fachliche Änderungen bitte trennen!
* Boy-Scout-Rule ist gut, aber
  * Bitte nicht Auto-Format nicht mit fachlichem Commit mischen

## Anti-Patterns Code Reviews

* Syntax-Nazis (die Klammer hier fehlt fei). Geht an der Motivation komplett
  vorbei.
* Nur auf die Form, aber nicht auf den Inhalt eingehen.
* Reviews durch *ivory-tower-architects*. Will überall mitreden. Sieht Produkte als
  Kreise und Pfeile dazwischen. Hat seit 20 Jahren keinen produktiven Code mehr geschrieben.
  Alles bestimmen, aber für nichts verantwortlich sein.

## Braucht der Reviewer Verständnis von der Fachdomäne?

* Contra: Ein Fachfremder versteht das technische Glossar womöglich nicht.
* Pro: Test wie selbsterklärend der Code ist.
  
## Arten von Code-Reviews

* Klassisch mit Moderator. Anti-Eskalator.
  Moderator greift ein und achtet auf Umgangston.
  Hat keinen Bezug vom eigentlichen Code und Problemdomäne.
* Ad-hoc-Methode. Hey, schau mal drüber ob es funktioniert.
* Pair Programming ist auch eine Art von Review!
* Tool-Basiert. Pull Request. Z.B. mit GitHub / GitLab.
* Word-Basiert (*eek!*)
* Code Walkthrough. 
    * Der Entwickler erklärt einem anderen den Code.
    * Der Entwickler lässt sich von einem anderen den Code erklären.
* Penetration: mit unmöglichen Daten füttern (Fuzzy Tests)
* Murphy's Law: das Unmögliche vorausdenken.
* Automatisierung
    
## Was würdet ihr alles reviewen?

* Alles
* Auch Konfigurationsdateien können Teil des Codes sein! Wenn sie
  das Programm kaputt machen können.
* Was für den Programmablauf wichtig ist.
* Architektur. Architektur ist die Idee hinter dem Programm!
  Vielleicht auch eine alte Idee, die mittlerweile ein Hindernis sein kann
  (Legacy).
* Fachlich. Passt die Business Logic? Ist der Code richtig oder ist es der richtige Code?
* Clean Code. Code Conventions, SOLID, Sprechende Konstrukte, sinnvolle Kommentare.
  Benennung ist wichtig! Vgl. a, b, c für Identifier für Klassen, Vars, Funktionen.
* Security. Ist der Code frei von Security Issues? Statische Code Analyse kann da eine Hilfe sein?
* Prozess: SCRUM oder Ähnliches mit Hilfe von Retros immer weiter optimieren und Schwachpunkte kompensieren.
  Nicht klassisch Code, aber trägt zur Schaffung von Code bei!
* Lizenzen: Passt mein Geschäftsmodell zu den verwendeten APIs (z.B. GPL).
* API-Check: not invented here syndrom vermeiden (insbesondere Krypto, ORM, Logging! 

## Zeitpunkte für Review?

* Post-Mortem: wenn schon die Kacke am Dampfen ist.
* Frühzeitig: vor Release Penetrationstest. Geld kann auch eine endliche Resource sein ;-).
* Iteratives Vorgehen: während der Entwicklungsphase kleine Reviews, so dass der Aufwand vor dem
  Release kleiner wird. Und Änderungen hinterher sind per se teurer je weiter weg von der Entwicklungsphase.
  Vorteil ist, dass die Entwickler geschult werden, frühzeitig auf Security-Themen zu berücksichtigen.
  
## Tools

### Prozess 

* Gated Check-in. 
* Ohne Code-Review kein Merge auf Master.
* Wenn es einfacher ist, eine Regel zu befolgen als sie zu verletzen, werden sich die Leute daran halten!
  Hürden schaffen bei der Verletzung. Empfohlenen Pfad vereinfachen.
  
### Statische Code-Analyse

* Automatisiertes Linting (Code Conventions via CheckStyle, ESLint, StyleCop).
* Statische Code-Analyse (FindBugs, SonarQube, FxCop, Fortify)
* Weitere automatisierte Tools wie z.B. Boundschecker. 
* Kann nicht alles finden. Siehe Halteproblem.

## Guide

* Problem im klassischem Umfeld (Waterfall): 
  * Alles 3-4 Wochen diskutieren und dann erst festlegen
* Starte wo du bist. Knapper Guide. Kurze Checkliste. Längere Diskussionen vermeiden.
* Kontinuierliche Verbesserungen.
* Scope für ein Review:
  * Zeit, Umfang in LoC
  * Was können wir effektiv bei einer Session wirklich reviewen?
* Ausnahmen sind okay! 
  * Guide als Richtwert und nicht als Gesetz verstehen! 
  
## Fragen

* Toolgläubigkeit: 
  * 99.9% aller Fehler sind draußen
  * Auto-Format mit Tools sinnvoll
  * Ein Tool kann kein gutes Review ersetzen! Mensch vs. Maschine.
    Verweis auf ein mögliches Problem und nicht ein sicherer Treffer.
  * False Negatives / False Positives
    * Auch Tools haben Bugs!
    * Issue einbringen, wenn etwas komisch aussieht (z.B. in SonarQube)
  * FindBugs hat "immer" recht. Selbst wenn ein False Negative ist, ist ein Aspekt anders.
    Vielleicht ist es besser, dem Tool gegenüber konformer zu programmieren als immer zu suppressen.
  * False Positives aufgrund von neuen APIs z.B. wie Junit5 Bindings. Annotations wie UsedImplicitly oder
    Suppress-Kommentare zur Vermeidung.
  * Fachliche Probleme aufgrund von Issue-Solving möglich!
  * Erfahrung und Best Practices sind wichtig, um sichere Tool-Findings von Problematischen zu unterscheiden!
* Inwiefern ist Review Coverage nahe an 100% wichtig?
  * getter und setter: wenig hilfreich. 
  * Trennung Logic und Value Objects.
  * Wert für Kunden von dem Code ist wichtig. Kritikalität des Codes bewerten.
  * Legacy Code ohne Testabdeckung, der zuverlässig läuft und keine Änderungsnotwendigkeit hat,
    ist okay!
    * Markterfahrung ist auch eine Form von Tests.
    * Nicht dem Tool wegen reviewen!
* Cargo Cult durch Automatisierung
  * "Das Tool wird schon recht haben"
  * Formularisierung durchführen, aber nicht das "Warum" verstehen
  * Sklavisch einem Prozess folgen

## Leicht OT

auch für Reviews relevant

* Per Remote: 
  * Telefonkonferenz alle legen den Hörer weg.
  * Geschriebenes Wort kann sinnvoller sein.
  * Gesicht sehen!
  * Mehrere Kommunikationskanäle für Mimik, Ton, Aussage (z.B. Videokonferenz)
  * Unsymmetrisch funktioniert schlecht (einer Remote, der Rest local)
    "Die und wir"
  * Permanente Liveschaltung in Küche und Board (wir haben immerhin schnelle Internetverbindungen und 
    hochauflösende Videos).
   
## Abschlusssatz

*Leave your ego at the door*
  
