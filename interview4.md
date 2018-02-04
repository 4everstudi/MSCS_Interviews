# Anonimous Interview 4

"A" for Interviewer statements

"B" for Interviewee answers

Interview was made on 16.08.2017, phone interview

===

A: Noch mal vielen dan fuer Ihre Hilfsbereitschaft. Koennen Sie zu anfang ein bisschen erzyehlen was fuer Projekte Sie bei <companyName1> machen? Wie weit sind Sie gekommen und so... allgemeine Informationen.

B: Genau. Ich bin bei der <companyName2> ingestellt, das ist ein IT-Dienstleister fuer <companyName1> und wir haben dort den Auftrag den Marketingauftritt der <companyName1> inhalltlich technisch zu betreue und weiterzuentwickeln. Das sind die Projekte das wir machen.

A: Okay.

B: Das sind so 16 Webseiten, eine App. In Summe ein Paar grosse und ein Paar kleinere Projekte. Und die Teiles sich so auf der Basis der Technologiestamm(?) und so... genau... Ich ich designe.. entwickle zusammen mit der Fachanforderungen eine Loesung, eine Designarchitektur mit Schnittstellen, Qualitätskriterien um dann die technologische Basis... [inaudible].. genau.

A: Ok. Aber wird das ganze neu, "from scratch" entwickelt oder werden die Altsysteme dabei überführt?

B: Wir haben bestehende Systeme wie, zum Beispiel, <companyName1>-Webseite. Die wird [inaudible] weiterentwickelt. Und es gibt noch mal neue Projekte wie Ausbildung.<companyName1>. Und das ist ein Ausbildungsportal fuer Ausbildungsberufe, genau, für Schulabsolventen. Das ist eine Neuentwicklung, die dann auf etablierten Technologien oder neuen Technologien aufgebaut wird. Wir machen beides.

A: Okay. Aber das was neuimplementiert wird wird als microservices umgesetzt oder?

B: Genau. Bei jeder neuen Anforderung gucken wir ob wir dort eine Chance haben die innerhalb unseres Microservice-Architektur umzusetzen.

A: Gut. Wie wird die Datenintegrität über alle Microservices bei Ihnen gewährleistet?

B: Da muss ich fragen was genau meinen Sie mit Datenintegrität?

A: Zum Beispiel, wenn wir von mehreren Microservices sprechen, die über Event Streams miteinender kommunizieren, dann kann man natüerlich nicht mehr von ACID-Transaktionen mehr reden, ja. Die eventuelle Konsistenz. Wie gehen Sie bei diesem Problem vor?

B: Also, z.B. fuer die Entitäten(?) "Märkte" und "Standorte" gibt es eine führende(?) System zukükftig, was die Marktinformationen findet(?), was sind seine Attribute, wenn ich einen Konsumenten habe zieht er sich ein Subset an informationen und speichert es ein seinem eigenen Microservice ab. Also, es wird zum Teil mit Datenduplizierung gearbeitet, aber nicht mit 100%-ger Datenduplizierung.

A: Ok. Aber sobald eine neue Instanz von einem Microservice deployt und hochgefahren wird, wie wird die Datenbank von dem Service gefüllt?

B: Wenn ich ein komplett neuen Service baue?

A: Nein. Ich meine eine neue Kopie von einem existierenden Microservice.

B: Wenn ich bei einem relationalen Datenbankschema bin, dann nehme ich die Datenbankversionierungswerkzeuge, um sicherzustellen dass sowohl altes als auch neues Service weiterhin funktionieren koennen. Fuer die Datenbankversionierung setzen wir FlyWay ein. Der wird dann idealerweise in eine Deploymennt-Pipeline mit reingenommen und integriert. Also wir haben dann ein Paar Integrationstests, die dann gucken ob ein SQL-Statement immer noch funktioniert auch mit dem neuen Datenbankschema. Also wir versuchen ganz viel über Tests abzudecken. Im Rahmen automatischen Build&Release-Pipeline.

A: Aber ist die Aussage, das jede Microservice eigene Datenbank bzw. eigene Datenschema haben soll, wahr?

B: Ja.

A: Okay. Aber wird dann bei Ihnen für jedes Microservice auch wirklich ein separates Datenbankmanagementsystem installiert, oder greifen mehrere microservices auf ein DBMS bzw. ein DBMS-Cluster?

B: Gute Frage... Wenn ich jetzt mit Virtualisierungstechniken arbeite, weiss ich gar nicht wieviele Datenbanken in der Tat im hintergrund sind.

A: Okay

B: Sagen wir es mal so. Jedes Microservice kriegt auf jeden Fall eine eigene Schema, die unabhängig von einem anderen Service, eine andere Fachlichkeit funktioniert.

A: Okay. Und wie sieht der Entwicklungsprozess bei Ihnen aus? Wie fängt die Entwicklung eines Microservices an? Wie werden die Rahmen gesetzt? Wie wird entschiede welche Date soll ein Microservice bei sich speichern? Und so weiter.

B: Klar. Es gibt eine entsprechende Fachanforderung, wo schon eine längere Konzeptionsphase vor[inaudible] gehen kann. Sagen wir es mal so. Wenn wir die Marktinformation neustrukturieren wollen, dann gucken wir erst mal welche fachlichen Informationen muss das Service erfüllen, dann wird es auf Attributebene runtergeschrieben, dann gucken wir auch welche Kommunikationswege zum Aussenwelt gibt es, ob dabei noch weitere Attribute benötigt werden. Bei Marktinformationen müssen vielleich irgendwelche API von Google (z.B. Landkarten) angesprochen werden. Das müssen wir uns angucken und dann gibt es erst mal ein Fachdesign. Ein grobes Domaindesign, so gesagt. Anhand desse kann ich dan entscheiden ob ich dann eine relationale Datenbank nehme un die wird dann auch modelliert. In Rahmen eines agilen Entwicklungsprozesses wir können sagen, dass im 1. Sprint muss ich erst mal eine Fachanalyse durchführen, die Fachmodellierung für die Domäne und wenn die dann steht und die Entwickler, Datenbankarchitekten und Anwendungsarchitekten draufgeguckt haben mit den Kunden kann man sagen aus [inaudible] ergibt es Sinn und dann wird es implementiert. Im naechsten Sprint.

A: Die Implimentierung, genau. Womit fängt es an? Mit einem API-Design? Wie werden die APIs beschrieben? Anbere organisationen haben so eine Art von API-Gilden, wo die API-Spezifikationen erst mal reviewt werden muessen. Damit werden Unstimmichkeiten abgegeliechen und API-Richtlinien umgesetzt.

B: Wir arbeiten mit Swagger. Das benutzen wir um unsere APIs zu beschreiben. Für clients. In der Tat, haben wir so eine Wiki-Seite wo wir die best practices beschrieben haben und jeder kann sowas da nachschlagen. Die APIs an sich werden dann inkrementell erweitert. Sprich, in einem sprint kann zu einem existirenden API-Endpunkt ein neuer Kontoller mit neue Funktionalität hinzugefügt werden.

A: Die nächste Frage. Wo und wie wird das Ganze demployt?

B: Wir fahren ein hybrides Rechenzentrumsmodell. Das heisst dass wir bei allen, vor allem bei klassischen Hostingdienstleister die Webanwendungen und die erste generation von Microservices laufen haben. Dann suchen wir uns einen Clouddienstleister aus wo wird dann Dinge auch hindeployen koennen um da [inaudible]effekte zu haben. Und wir habe in dem eigenen <companyName2>-Rechenzentrum die ganzen Stammdaten. Da werden wir auch demnächst auch die Microservices deployen und die den beiden anderen Rechenzentren zur Verfügung zu stellen, über die Schnittstellen... Also, ein hybrider Ansatz.

A: Was der Clouddienstleister angeht gibt es aktuell nicht so viel zur Auswahl... Amazon vielleicht nicht in Ihren Fall, das es mit <companyName1> konkurriert...

B: Genau. Das ist aus strategischen sich so. Aber technisch gesehen gibt es da keine Hürde. Wir haben bereit ein proof-of-concept implementiert, von dem wir überzeugt sind. Müssen wir gucken das wir da aus Wettbewerbsicht nicht Amazon irgendwelche Informationen freigeben die dann gegen uns verwendet werden können. Aber so einfache Dinge wie Marktinformationen die sowieso öffentlich sind, die können wir auch, meiner Meinung nach, in AWS deployen. Da spielt die Datensicherheitsproblematik nicht so eine wichtige Rolle.

A: Und wie sieht es mit Google Cloud aus? Stand Google auch auf Ihre Auswahlliste?

B: Nein, Google haben wir uns nicht angeguckt. 

A: Ich frage weil Google Cloud unterstützt dieses Kubernetes-Werkzeug, der momentan in aller Munde ist. Und von vielen habe ich bereits gehört, das die Goodle momentan fast besser einschätzen wurden was das Deployment und das Management von Microservices angeht.

B: Wir habe da noch kein Vergleich gemacht. Wir haben mit IBM Bluemix angefangen. Das haben wir vor einem Jahr angefangen, weil IBM schon ein Partner der <companyName2> ist. Deswegen bot sich das an da den ersten proof-of-concept zu machen. Und das hat... uns nicht gefallen, sagen wir erst mal so. Weil wir das Deployment mit Docker machen wollten und die Docker-Unterstützung bei Bluemix war damals noch nicht ausreichend.

A: Und Microsoft, glaube ich, ist auch noch nicht so weit...

B: Was wir uns noch angeguckt habe war die Deutsche Telekom, was die als Cloudplatform verkaufen.

A: Und, wie sieht es bei Telekom aus?

B: Das war nichts Vergleichbares was der Funktionsumfang und die Preis anbetrifft. Die brauchen auch noch ein Paar Jahre um aufzuholen.

A: So, welche Frage nehmen wir noch mit rein.. Ganeu. Was halten Sie jetzt allgemein von der Microservice-Geschichte? Welche Herausforderungen sehen Sie, welche Problemen lassen sich am besten mit dem Einsatz lösen usw. Also, keine kannonische Definition was ein Microservice-Architektur ist, sondern rein auf Ihre Erfahrung basiert.

B: Microservices, so wie ich die hier bei uns kennen, das wir die Softwerlösungen, also einzelne Artifakten anhand ihren Fachlichkeit strukturieren können, wir können dort die Kontrolle über das gesamte Programm [inaudible] Schnittschtellenverträge einhalten müssen. Wir können viel besser skalieren, was die virtuellen Serverlandschaft anbetrifft, weil wir nicht immer Maximalskalierung [inaudible] sondern wir wollen demnächst automatische Skalierung einführen um echte Lastspitzen abzufangen. Und wir haben ein besseren Investitionsschutz weil wir die Dienste nach wenigen monaten auch wieder abschalten können wenn sie nicht mehr benötigt werden. Klar, weil wenn ich ein server kaufen muss, ihn 3 oder 4 Jahre lang betreiben... kaufe ich mir lieber die Kapazitäten in einer Cloud und schalte die Dienste wieder ab sobald ich diese nicht mehr brauche. Und das funktioniert gut. Eine Herausforderung ist tatsächlich ist dass das API-Design. Also, wie alle Microservices, die müssen eine identische API-Syntax und -Symantik aufweisen. Da muss man darauf Acht geben. Das ich das nach Aussen für die Clients [inaudible] einführt. Also die Clients dürfen gar nicht merken das die Marktabfrage ist eine andere Abfrage als die Rezeptabfrage (?). Sollte eigentlich selbe Verhalten haben. Das ist eine Herausvorderung. Und das Monitoring, wieviele virtuelle Instanzen laufen grade, wo und welche schmiert ab, das ist auch eine komplexe Geschichte. Jetzt haben wir 20+ Fachservices, die vielleicht noch im Loadbalancerbetrib, 40+ Instanzen, mit ihren Einzeldatenbanken. Das ist jets die Herausforderung die man jetzt [inaudible] muss.

A: Genau. Stimmen sie auch zu, das die Komplexität von dieser ganzen Geschichte, im Vergleich zu einem Monolith, wo die ganze Komplexität innerhelb eines Systems abgebildet ist... Bei einer Überführung zu Microservices wir diese Komplexität auf eine andere Niveau geschoben und wird zu einem Komplexität der Bezihungen zwischen einzelnen Microservices, die ganzen Event Streams, verteilte Datenbanken usw. Oder ist dieses Shift keine grosse Hürde?

B: Doch, tatsächlich bei Monolothen haben wir das Problem das Entwickler wochenlang an einem Monolith gleichzeitig schrauben können und es ist immer noch nicht Release-fähig. Weil dann wochenlang an dem selben Artefakt gearbeitet wird und man hat immer ein Schiefstand(?) denn man trotzdem Live stellen muss weill irgendwann muss man fertig sein. Oder wenn ich dann mit Git arbeite habe ich dann immer grosse Merge- und Konversationskonflikte, wenn viele Leute an einem Artefakt arbeiten. Ich glaube das Problem umgehen wir indem ich kann besser auf Teamebene skalieren indem ich sage ich habe 3 Team und 3 Microservices und arbeiten diese Teams wirklich unabhängig an getrennten Artefakten. Das hilft schon. Gespannt wird es wenn es 2 Teams gibt, die an einem Microservice arbeitem müssen. Dann haben wir wieder diese Konversationsproblem. Aber ich glaube es ist dann auch einfacher zu handeln, wenn es dann auch nicht in so einem Ausmass vorkommt, wie im Falle von einem Monolith.

A: Da kommen wir zu der Frage wie gross darf das einzelne Microservice eigentlich sein?

B: Wie gross ein Microservice sein muss? Gross genug um seine fachlichen Anforderungen zu erfüllen. Und ich hab es ganz gern dass ein Microservice alles was zum Beispiel mit dem Fachentität "Markt" zu tun hat, dass es alles in einm technischen [inaudible]. Das heisst zukünftig Stammdatenpflege, Import/Export-Schnittstellen, [inaudible] Dinge oder auch die Suchmaschinenlogik - das ist alles was wir in einen Microservice reintun

17:23