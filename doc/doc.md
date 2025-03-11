# Arbeit 1: Evaluation eines Cloud-Providers

## Inhaltsverzeichnis
TODO

## Arbeitsauftrag 1

### Vorstellung Railway
Railway ist eine Cloud-Platform die einem erlaubt vereinfacht Applikationen zu bauen, deployen und zu skalieren. Services lassen sich über Docker-images starten oder aber auch über source code aus einem Github Repository. Ebenso lassen sich mit wenigen Klicks Datenbanken hochfahren und mit Services vernetzen.  
Railway bietet einen modernen, intuitiven visuellen Canvas welcher Übersicht über die Services bietet und gleichzeitig die Oberfläche bereitstellt seine Services zu konfigurieren.

TODO

### Fragen

Frage: Können alle Teammitglieder die Applikation deployen?  
Antwort: Ja, alle Teammitglieder können die Applikation starten, entfernen und auch bearbeiten.

Frage: Können Sie Benutzer und Zugriffsrechte fürs Deployment verwalten?  
Antwort: Nein. Man kann User zum Projekt einladen welche entweder read-only oder read-write access haben.
Eine granulare einstellung ist nicht möglich

Frage: Bietet der Provider die Möglichkeit z.B. ein GitHub-/GitLab-Repository zu verbinden und dieses automatisch zu deployen?  
Antwort: Ja, das ist mehr oder weniger der hauptaspekt von Railway

Frage: Weshalb haben Sie diesen Provider für die Evaluation ausgewählt?  
Antwort: Railway ist sehr einfach zu bedienen und schnell auf zu setzen, zumindest beim Deployment eines Github Projektes. Weiter gibt es eine relativ grosszügige "Free Trial" bei der man 500MB RAM und geteilte VCPUs benutzen kann. Zuletzt war uns beiden dieser Cloud-Provider unbekannt welches die Arbeit spannender gestaltete. 

Frage: Welche Möglichkeiten haben Sie, die Applikation zu starten und zu stoppen?  
Antwort: Auf der Website railway.com hat man die Möglichkeit das Deployment einer Applikation zu entfernen und wieder zurück zu laden. Dies ist sehr unschön und die Webseite bietet ansonsten keine weiteren Möglichkeiten in der Trial-Version. Wenn man allerdings das CLI für eine lokale Instanz verwendet kann man mit "railway up" für Start und "railway down" für Stop die Kontrolle etwas besser übernehmen.


Frage: Gibt es die Möglichkeit, das Deployment zu automatisieren? Welche Schritte wären dazu
nötig?  
Antwort: Ja, out of the box wird Railway ein GitHub-Projekt sofort deployen und mit automatisierte Deployments konfigurieren. Railway kann automatisch Änderungen im Repository erkennen (z.B. bei einem neuen commit) und die Applikation neu deployen.


Frage: Wo können Sie das Log der Applikation betrachten? Sehen Sie auch die einzelnen HTTP
Requests und Responses?  
Antwort: Wenn man auf dem Dashboard auf der Railway Webseite das deployte Projekt anklickt, kann man die laufende Instanz anklicken und sieht da nebst weiteren Details einen Tab für je Build-, Deploy- und HTTP-Logs.

Frage: Worin sehen Sie die Vor- und Nachteile Ihres Providers verglichen mit a9s?  
Antwort: Die Vorteile sind: 
Benutzerfreundlichkeit - Applikation lässt sich einfach und schnell aufsetzen und überwachen.
Automatisierung - Projekte sind von Anfang an automatisiert.
Logs - Die Logdateien sind übersichtlich und einfach einsehbar im Web-Portal.
Kosten - Für kleine Projekte ist die Verwendung absolut kostenlos.

Die Nachteile sind:
Einstellungsmöglichkeiten im "Backend" - Railway ist eine Managed Platform, die die Infrastruktur komplett abstrahiert und bietet keine Möglichkeit, unterliegende Instanzen oder Netzwerkeinstellungen direkt zu konfigurieren.

## tmpdoc

- Logged into railway with github account
- looked at nextjs example
- created github repo and copied files from previous java exercise into repo
- created railway project and selected github repo as source
- building and deploying went automatic, zero input and configuration required, WTF
- created a domain so app is now accessible from web

