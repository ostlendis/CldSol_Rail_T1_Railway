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



## Arbeitsauftrag 2
### OSSM-Analyse
#### On-Demand
Der On-Demand Aspekt ist auf Railway klar gewährleistet. Nach dem Anmelden oder registrieren kann man direkt loslegen indem ein Template gestartet wird oder ein Github-Repo verknüpft. Kurze Zeit später (bis zu 2 Minuten) ist die Applikation funktionsfähig.  
Zum Beispiel lässt sich jederzeit das Wordpress Template starten:  
![image](images/wordpress-lauch-activity.png)  
Innerhalb Sekunden und ohne warten lässt sich ein Service starten. Es wurde zuerst von einem leeren Projekt gestartet und schliesslich sind alle Services funktionsfähig.  
![image](images/wordpress-instances-launched.png)  

#### Self-Service
Bei Rawilway lassen sich alle On-Demand Services via Self-Service selbst managen. Man hat gewisse Einschränkungen wenn man sich auf dem Trial-Plan befindet im Gegensatz zu einem bezahlten Plan befindet. Man müsste also zuerst seinen Plan upgraden, will man einen Service vom bezahlten Plan nutzen. Allerdings lässt sich auch dies innerthalb von kurzer Zeit ohne direkte Kommunikation mit Railway machen. Man kann also beliebig Services starten, ohne sich mit dem Provider absprechen zu müssen.  
Dies lässt sich ebenfalls aus den obigen Bildern entnehmen, da innert kurzer zeit ein neues Projekt angelegt wurde, und danach Datenbank- und Webserver hochgefahren wurden welche kurze zeit später vollständig funktionieren.

#### Skalierbarkeit
Bei Railway lässt sich sowohl horizontal als auch vertikal skalieren. Vertikale skalierbarkeit ist durch die anzahlt CPU-Kerne und die Menge an Arbeitsspeicher erreichbar, ist aber eingeschränkt, auf welchem Zahl-Plan man momentan fährt. Ist man gratis unterwegs, hat man keine Möglichkeit vertikal zu skalieren. Beim Hobby und Pro Plan sind 8GB Arbeisspeicher und 8 CPU's respektive 32GB Arebeitsspeicher und 32 CPU's pro Service verfügbar.
Siehe [Pläne](https://railway.com/workspace/plans)  
Die Hrizontale Skalierbarkeit im Vergleich zu grösseren Anbietern auch minimalistisch. Ist kein Dateisystem am Service angehängt und es sind keine Cronjobs definiert, lassen sich die Services manuell um eine gewünschte Anzahl replizieren und somit Skalieren. 
Gleichzeitg gibt es die Möglichkeit, einen Service in den Serverless-Mode zu schalten. Bei diesem Modus werden anhand von verschiedenen Kriterien die Aktivität am service gemessen und je nach Last die Anzahl Replikas hoch und hinunter gefahren.  
Siehe [Scaling](https://docs.railway.com/reference/scaling)

#### Messbarkeit
Die mit dem Hosten verbundenen Kosten sind sehr transparent und einfach gestaltet. Bei Arbeitsspeicher, Prozessorkernen und Festplattenspeicher zahlt man pro Menge mal die Zeit. Ausgehender traffic bezahlt man pro Kilobyte.  
Siehe [Pricing](https://docs.railway.com/reference/pricing/plans)

## Auftrag 4 - Analyse Preisrecherche.
### • Welche Preismodelle stehen zur Verfügung?

Simplerweise gibt es nur 3 Subscription-Pläne, "Hobby" für 5$/Monat, "Pro" für 20$/Monat und "Enterprise" für einen custom Betrag im Monat welcher nicht genau deklariert wurde.
Die Pläne bieten folgende limitationen:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/750f2003-9e27-4a7b-9f01-8d8ac5d28984" />

Zusätzlich zu den Subscription Kosten gibt es noch Kosten anhand der Nutzung:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/a3e3f52c-014c-41cd-848c-e188340cb12e" />


Zuletzt ist es auch möglich anstelle einer Subscription ein "Commited Spending" zu beziehen welches viel höhere Monatliche Kosten hat, jedoch keine weiteren dynamischen Kosten, solange man im Rahmen des Pakets bleibt:
<img width="642" alt="image" src="https://github.com/user-attachments/assets/373ec80e-8ebb-44cc-b188-ed9d9a3c5ba0" />


### • Wie kann bezahlt werden?

Wenn man die Subscription ändern möchte muss man dazu die Kreditkarte angeben, wobei andere Zahlungsmethoden nicht möglich sind. Angeblich soll jedoch für die Zusätzlichen Kosten die Zahlung auch per Rechnung begleichbar sein.

### • Gibt es ein Gratis-Angebot für Einsteiger?

Ja es gibt eine "Full" und eine "Limited" Trial-Version. Der einzige unterschied zwischen den beiden ist, dass die Limited-Version keinen Code deployen kann sondern nur Datenbanken. Wenn man seinen Account verifiziert wird man von der Limited- zu der Full-Version heraufgestuft. Die Einschränkungen sind bereits in der vorherigen Fragen ersichtlich mit 0.5GB RAM, 2 vCPU, 1GB Ephemeral Storage und 0.5GB Volume Storage.

### • Welche Ressourcen werden abgerechnet?

Es werden als Dynamische Kosten zusätzlich zur Subscription immer RAM, CPU, Network Egress und falls man noch zusätzlichen Volume Storage möchte auch der Storage abgerechnet.

### • Was kostet Sie das Hosting der Anwendung aus der Ausgangslage über drei Jahre?

500$ * 12 für 1sten jedes Monats (Enterprise minimum monatlicher Preis) 

Eigentlich wäre die Hobby Subscription genug aber bei einem Downgrade (zweiter Tag jedes Monats) werden die Änderungen erst nächsten Monat angepasst, somit muss man bei der Enterprise Version bleiben. Die Enterprise Version hat auf der Webseite keinen Preis und muss durch die Besprechung des optimalen Plans mit einem Mitarbeiter der Railway Firma per E-Mail herausgefunden werden.

Es sollte kein zusätzlicher Speicher benötigt sein allerdings ist dies ebenfalls nicht auf der Webseite deklariert wieviel beim Mindestangebot der Enterprise Version dabei ist.

10$ * 8 * 12 für RAM

20$ * 4 * 12 || 20$ * 8 * 12 für CPU Cores wobei nicht genau beschrieben steht wieviele Cores ein vCPU hat und sein kann, dass es nur ein halber Core eines phyischen CPUs ist. Bei der finalen Rechnung gehe ich davon aus, dass ein vCPU ein Core eines physischen CPUs ist.

0.05$ * 1000 für Netzwerk Traffic

Somit wäre der Gesamtpreis 2140$ im Jahr, was für die Ausgangslage von 3 Jahren 6420$ bedeutet.


### • Welche Schwierigkeiten treten bei dem Vergleich auf?

Der Vergleich zwischen einer normalen Subscription und den "Committed Spend Tiers" ist schwierig da bei diesen Tiers sowie bei der Enterprise Version die genauen Kosten und was alles enthalten ist nicht beschrieben wird. Wenn man etwas grösseres in die Cloud stellen möchte muss man mit einer solchen personalisierten Lösung arbeiten. Weiter ist es mühsam, dass man beim Downgrade der Subscription die teurere bis ende Monat behält. Somit muss man schlussendlich viel zu viel für eine kleine Applikation mit kurzen Peaks bezahlen.

## Arbeitsauftrag 5



## tmpdoc

- Logged into railway with github account
- looked at nextjs example
- created github repo and copied files from previous java exercise into repo
- created railway project and selected github repo as source
- building and deploying went automatic, zero input and configuration required, WTF
- created a domain so app is now accessible from web

