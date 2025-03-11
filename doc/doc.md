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

### Auftrag 4 - Analyse Preisrecherche.
• Welche Preismodelle stehen zur Verfügung (Bsp. Subscription, Flat Rate, Pay-per-Use)?
Simplerweise gibt es nur 3 Subscription-Pläne, "Hobby" für 5$/Monat, "Pro" für 20$/Monat und "Enterprise" für einen custom Betrag im Monat welcher nicht genau deklariert wurde.
Die Pläne bieten folgende limitationen:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/750f2003-9e27-4a7b-9f01-8d8ac5d28984" />

Zusätzlich zu den Subscription Kosten gibt es noch Kosten anhand der Nutzung:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/a3e3f52c-014c-41cd-848c-e188340cb12e" />


Zuletzt ist es auch möglich anstelle einer Subscription ein "Commited Spending" zu beziehen welches viel höhere Monatliche Kosten hat, jedoch keine weiteren dynamischen Kosten, solange man im Rahmen des Pakets bleibt:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/373ec80e-8ebb-44cc-b188-ed9d9a3c5ba0" />


• Wie kann bezahlt werden (Kreditkarte, Rechnung, ...)?
Wenn man die Subscription ändern möchte muss man dazu die Kreditkarte angeben, wobei andere Zahlungsmethoden nicht möglich sind. Angeblich soll jedoch für die Zusätzlichen Kosten die Zahlung auch per Rechnung begleichbar sein.

• Gibt es ein Gratis-Angebot für Einsteiger (falls ja: was sind die Einschränkungen)?
Ja es gibt eine "Full" und eine "Limited" Trial-Version. Der einzige unterschied zwischen den beiden ist, dass die Limited-Version keinen Code deployen kann sondern nur Datenbanken. Wenn man seinen Account verifiziert wird man von der Limited- zu der Full-Version heraufgestuft. Die Einschränkungen sind bereits in der vorherigen Fragen ersichtlich mit 0.5GB RAM, 2 vCPU, 1GB Ephemeral Storage und 0.5GB Volume Storage.

• Welche Ressourcen werden abgerechnet?
Es werden als Dynamische Kosten zusätzlich zur Subscription immer RAM, CPU, Network Egress und falls man noch zusätzlichen Volume Storage möchte auch der Storage abgerechnet.

• Was kostet Sie das Hosting der Anwendung aus der Ausgangslage über drei Jahre?


• Welche Schwierigkeiten treten bei dem Vergleich auf (z.B. unterschiedliche Servicemodelle
oder Qualitätseigenschaften, versteckte Kosten, widersprüchliche Angaben)?
Der Vergleich zwischen einer normalen Subscription und den "Committed Spend Tiers" ist etwas schwierig. Weil man genau berechnen muss wieviele Kosten anfallen könnten und wie konsistent die Belastung ist. Ansonsten sind die Subscriptions und die dynamischen Kosten sehr simpel. In der Dokumentation steht noch: "Cost of the plan you're on: [cost per seat] x [purchased seats] Cost of the resources you've consumed: [cost per unit] x [used units]"


## tmpdoc

- Logged into railway with github account
- looked at nextjs example
- created github repo and copied files from previous java exercise into repo
- created railway project and selected github repo as source
- building and deploying went automatic, zero input and configuration required, WTF
- created a domain so app is now accessible from web

