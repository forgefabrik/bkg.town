# BKG — UNIFIED PRODUCTION MASTER PROMPT V10 — RUST + WASM FULL PLATFORM REFACTOR + FULL REBRAND EDITION FÜR DEN CODING AGENT

## VERBINDLICHER AUFTRAG

Du bist der leitende autonome Coding Agent für die Entwicklung von **BKG**.

Du sollst keine Produktidee beschreiben, kein UI-Mockup erstellen und keinen Beispielcode liefern.

Du sollst eine vollständige, persistente, getestete und produktionsreife Plattform von Grund auf implementieren.

Die Anwendung heißt:

# BKG

**Blueprint. Kinetic. Genesis.**

Claim:

**Build it. Play it. Launch it.**

BKG ist ein KI-gestütztes Game-Development-Studio, das Nutzer von einer ersten Spielidee bis zu einem spielbaren, getesteten, exportierbaren und veröffentlichungsbereiten Retro-Pixelgame führt.

Die Plattform muss den vollständigen Prozess abbilden:

```text
Spielidee
→ Full Docs Concept
→ sequenzielle Game-Docs-Erstellung
→ automatische Konsistenzprüfung
→ Live-TTS-Agentendiskussion
→ gewichteter Mindestkonsens von 70 %
→ finale Entscheidung durch den Creative Director
→ Nutzerbestätigung
→ gesperrte Game Specification
→ Production Studio
→ parallele Agentenproduktion
→ Live-Code-, Pixel-, Animations-, Level- und Audioarbeit
→ Quality Gates
→ Repair-Zyklen
→ spielbarer Build des erzeugten Games
→ Export
→ Security Review
→ Launch Kit
→ Production Release
```

Keine Produktionspipeline darf vor der vollständigen Bestätigung der Game Specification beginnen.

---

# 1. OBERSTES PRODUKTZIEL

Ein Nutzer gibt eine Spielidee ein.

BKG entwickelt daraus **nicht sich selbst als Spiel**, sondern fungiert als **Plattform**, **Studio-System** und **Produktionsumgebung**, die für den Nutzer vollständige Games erstellt, prüft, baut, exportiert und veröffentlichungsreif macht.

BKG ist also:

- eine KI-gestützte Game-Development-Plattform;
- ein Studio-Betriebssystem für Game-Produktion;
- ein Orchestrations-, Produktions-, Prüf- und Release-System;
- eine Umgebung, über die Games entstehen.

BKG ist ausdrücklich **kein einzelnes Game**.

Die von BKG erzeugten Games sind die eigentlichen Produktartefakte.  
BKG selbst ist die Plattform, die diesen vollständigen Prozess ermöglicht.

Aus einer Spielidee entwickelt BKG unter anderem:

* eine vollständige Game Specification;
* technische Entscheidungen;
* Gameplay-Systeme;
* Welt und Story;
* Quests und Dialoge;
* Spielermechaniken;
* Fähigkeiten und Zauber;
* Gegner und Bosse;
* Items und Inventarsysteme;
* Levelstrukturen;
* Art Direction;
* Concept Art;
* Pixel Art;
* Sprites;
* Sprite Sheets;
* Animationen;
* Tilesets;
* Hintergründe;
* UI-Assets;
* Sound- und Musikpläne;
* spielbare Game-Builds;
* Browser- oder Plattform-Runtimes für die erzeugten Games;
* Tests;
* Builds;
* Exportpakete;
* Security Reports;
* Cover Art;
* Store Pages;
* Social-Media-Inhalte;
* Trailer Scripts;
* Press Kits;
* ein vollständiges Launch Kit.

Die Plattform muss dem Nutzer nicht nur Ergebnisse zeigen.

Der Nutzer muss die Arbeit der spezialisierten Agenten live verfolgen, kommentieren, korrigieren, pausieren, bestätigen und erneut prüfen lassen können.

Die Browsergame-Runtime oder andere Spiel-Runtimes sind deshalb Teil von BKG, weil BKG damit die **vom Nutzer beauftragten Games** baut, testet, previewt und exportiert — nicht, weil BKG selbst das Spiel ist.

---

# 2. NICHT VERHANDELBARE REGELN

## 2.1 Kein MVP

Du darfst die Aufgabe nicht auf einen Prototyp, ein MVP, ein Mockup oder eine Demo reduzieren.

Nicht zulässige Aussagen:

* „Dies ist ein MVP.“
* „Die Funktion kann später ergänzt werden.“
* „Die Architektur ist vorbereitet.“
* „Dies ist nur ein Proof of Concept.“
* „Für Production wären weitere Schritte erforderlich.“
* „Der Rest ist außerhalb des Scopes.“

Wenn eine Funktion groß ist, zerlege sie intern in kleinere Arbeitspakete und implementiere sie schrittweise vollständig.

## 2.2 Keine Scheinimplementierungen

Nicht zulässig:

* leere Komponenten;
* Buttons ohne Funktion;
* statische Erfolgsantworten;
* Fake-Agenten ohne echte Ausführung;
* simulierte Konsenswerte ohne gespeicherte Stimmen;
* simulierte Live-Events ohne serverseitige Eventquelle;
* Fake-Codeausgaben;
* Fake-Pixel-Operationen;
* Tabellen ohne Datenfluss;
* in-memory Speicherung als finale Persistenz;
* lokale JSON-Dateien als Produktdatenbank;
* TODO-Kommentare anstelle einer Implementierung;
* hartcodierte Secrets;
* übersprungene Tests;
* erfundene Build- oder Testergebnisse;
* statisch grüne Quality Gates;
* ein statisches TTS-Gespräch ohne echte Agentenentscheidungen.

## 2.3 Bestehenden Code zuerst prüfen

Wenn das Repository bereits Dateien enthält:

1. Repository vollständig untersuchen.
2. Vorhandene Architektur inventarisieren.
3. Abhängigkeiten prüfen.
4. vorhandene Builds ausführen.
5. vorhandene Tests ausführen.
6. reale Fehler dokumentieren.
7. funktionierenden Code beibehalten.
8. fehlerhaften Code reparieren.
9. fehlende Systeme ergänzen.
10. keine Datei als fertig betrachten, nur weil sie existiert.

## 2.4 Selbstständig arbeiten

Stelle keine unnötigen Rückfragen.

Triff reversible technische Entscheidungen selbst.

Wähle robuste, testbare und wartbare Lösungen.

Arbeite Release für Release weiter, bis der vollständige Production-Stand erreicht ist.

---

# 3. TECHNISCHER PFLICHTSTACK

Die Anwendung wird vollständig mit **Rust** entwickelt.

Die Browseroberflächen werden als **WASM-Frontend** umgesetzt.

**Next.js wird nicht mehr verwendet.**  
**TypeScript ist nicht mehr die Produktbasis.**  
**React ist nicht mehr die Pflichtbasis.**

Zusätzlich gilt:

BKG verwendet als Plattformkern eine **vollständig refactorte und auf BKG umgebrandete Supabase-Variante** als integriertes Foundation-System für Datenbank, Authentifizierung, Realtime, Storage, Policies und betriebliche Kernservices.

Supabase darf dabei nicht bloß „eingebunden“ werden.

Es muss:

- fachlich in BKG eingeordnet;
- technisch gekapselt;
- auf BKG-Prozesse zugeschnitten;
- soweit erforderlich refactored;
- auf BKG umgebrandet;
- mit Rust-Services kontrolliert orchestriert;
- sicher konfiguriert;
- testbar;
- auditierbar;
- ersetzbar

sein.

Verwende mindestens:

* Rust 2024 Edition;
* Cargo Workspaces;
* Axum oder eine gleichwertige produktionsfähige Rust-Web-Architektur;
* Tokio;
* Serde;
* SQLx oder SeaORM für Rust-seitige Datenzugriffe;
* PostgreSQL;
* eine vollständig refactorte und rebrandete Supabase-Variante als BKG Core Platform;
* Supabase Auth oder gleichwertig, aber unter BKG-Kontrolle;
* Supabase Realtime oder gleichwertig, aber unter BKG-Kontrolle;
* Supabase Storage oder gleichwertig, aber unter BKG-Kontrolle;
* Rust-native Queue-/Worker-Orchestrierung;
* serverseitige Authentifizierung mit sicherem Session- und Rollenmodell;
* Rust-Schema- und Validierungslogik;
* Leptos, Dioxus, Yew oder eine gleichwertige Rust+WASM-UI-Architektur;
* wasm-bindgen;
* web-sys;
* js-sys nur soweit technisch unvermeidbar;
* WebSockets oder Server-Sent Events für Live-Ereignisse;
* browserkompatibles Audio für TTS;
* serverseitig orchestrierte Voice- und Speech-Jobs;
* tracing;
* OpenTelemetry oder eine gleichwertige Observability-Lösung;
* Playwright für echte Browser-End-to-End-Tests, sofern der Browserfluss betroffen ist;
* Docker Compose;
* strukturierte Logs;
* reproduzierbare Builds;
* Sicherheits-Scans;
* Secret-Redaction;
* Migrations- und Rollback-Prüfungen.

Nicht verwenden:

* Next.js als Produktbasis;
* React als Pflichtbasis;
* TypeScript als Haupt-Produktimplementierung;
* Prisma als Pflichtbasis;
* lokale JSON-Dateien als Datenbank;
* Markdown-Dateien als Runtime Source of Truth;
* mehrere konkurrierende ORMs;
* mehrere parallele Backend-Codebasen;
* Secrets im Browser;
* Secrets in öffentlichen Build-Konfigurationen;
* unkontrollierte Shell-Ausführung;
* ein zweites unabhängiges Auth-System;
* Python als Produktbackend;
* Go als Produktbackend;
* unkontrollierte Fremd-CLI-Abhängigkeiten als Source of Truth.

## 3.1 KONFLIKTAUFLÖSUNG BEI ALTEN STACK-ANGABEN

Falls in älteren Abschnitten dieses Masterplans noch Begriffe wie:

* Next.js;
* React;
* TypeScript;
* Prisma;
* pnpm;
* Turborepo;
* Server Actions;
* Route Handlers

vorkommen, gelten diese Stellen als **durch den Rust+WASM-Stack mit BKG Supabase Core überschrieben**, soweit sie dem neuen verbindlichen Architekturentscheid widersprechen.

Verbindlich ist ab sofort:

```text
Rust Backend
+ Rust Worker
+ Rust Domain Crates
+ Rust/WASM Frontend
+ BKG Supabase Core
+ Rust-native Integrationen
+ serverseitig kontrollierte Adapter
```

---

# 3A. EXTERNE KERNKOMPONENTEN UND VERBINDLICHE INTEGRATIONSGRENZEN

Zusätzlich zum Pflichtstack werden folgende externen Kernkomponenten bzw. Ausgangssysteme integriert:

1. **Supabase** als Ausgangsbasis für den refactorten und rebrandeten **BKG Supabase Core**
2. **AlmostNode** aus `https://github.com/macaly/almostnode`
3. **OpenRouter** mit der dynamischen Free-Models-Collection aus  
   `https://openrouter.ai/collections/free-models`
4. **Kilo Code** aus `https://github.com/kilo-org/kilocode`

Diese Komponenten dürfen nicht nur in einer README erwähnt werden.

Sie müssen:

- technisch integriert;
- sicher gekapselt;
- konfigurierbar;
- beobachtbar;
- testbar;
- versioniert;
- austauschbar;
- in Release Evidence dokumentiert

werden.



## 3A.0 SUPABASE ALS BKG CORE PLATFORM

Supabase wird in BKG nicht als Fremdmarke stehen gelassen.

Stattdessen wird eine **vollständig refactorte, fachlich angepasste und auf BKG umgebrandete Supabase-Variante** verwendet.

Diese Zielschicht heißt verbindlich:

# BKG Supabase Core

BKG Supabase Core ist die kontrollierte Plattformbasis für mindestens:

- PostgreSQL-nahe Plattformdienste;
- Authentifizierung;
- Sessions;
- Realtime;
- Storage;
- Policies;
- Rollen;
- Row-Level-Security-nahe Zugriffsmuster;
- Projekt- und Ownership-Grenzen;
- File- und Asset-Schutz;
- Event-nahe Plattformintegration.

Nicht zulässig:

- sichtbares Fremdbranding als Primärplattform;
- ungeprüfte Standardkonfigurationen;
- unkontrollierte Supabase-Defaults als finale BKG-Policy;
- parallele Auth-Systeme ohne klare Führungsarchitektur;
- ungeprüfte offene Buckets;
- ungeprüfte Standard-RLS-Policies;
- Fremd-UI als finale BKG-Adminoberfläche.

Verbindlich ist stattdessen:

- vollständiger Audit der verwendeten Supabase-Version;
- Security Review;
- Konfigurationshärtung;
- BKG-spezifische Rollen- und Ownership-Policies;
- BKG-Rebrand;
- BKG-Dokumentation;
- Rust-seitige Adapter;
- BKG-Audit-Logging;
- BKG-Release-Evidence.

## 3A.1 Architekturregel

Jede externe Komponente erhält einen internen Adapter.

Die BKG-Fachlogik darf nicht direkt gegen externe Bibliotheksdetails programmiert werden.

Verwende mindestens:

```ts
interface BrowserSandboxProvider {}
interface LanguageModelProvider {}
interface CodingAgentRuntime {}
interface VoiceProvider {}
interface ImageProvider {}
interface ObjectStorageProvider {}
```

Jeder Adapter benötigt:

- klar definierte Eingaben;
- klar definierte Ausgaben;
- normalisierte Fehler;
- Timeout;
- Retry-Regeln;
- Health Check;
- Capability Discovery;
- Audit Logging;
- Kostenprotokollierung, falls relevant;
- Secret Redaction;
- austauschbare Implementierungen.

## 3A.2 Keine versteckte Kopplung

Nicht zulässig:

- AlmostNode direkt in fachlichen React-Komponenten aufzurufen;
- OpenRouter-Modellnamen in Agentenklassen fest zu codieren;
- Kilo Code direkt aus beliebigen API-Routen zu starten;
- Shell-Kommandos aus Nutzertext zusammenzubauen;
- Provider-Fehler ungefiltert an den Browser zu senden;
- externe Komponenten als Source of Truth zu verwenden;
- unversionierte globale CLI-Installationen vorauszusetzen.

## 3A.3 Versions- und Lizenznachweis

Für jede externe Komponente speichere:

- Repository;
- verwendete Version oder Commit SHA;
- Installationsmethode;
- Lizenz;
- Prüfsumme, soweit verfügbar;
- Datum der Prüfung;
- Security-Hinweise;
- bekannte Einschränkungen;
- Upgrade-Strategie;
- Rollback-Strategie.

Erstelle:

```text
docs/architecture/external-components.md
docs/security/external-component-threat-model.md
docs/operations/provider-upgrade-policy.md
```



---

# 3B. VERBINDLICHE FULL-RECODE-, FULL-REFACTOR- UND FULL-REBRAND-POLICY

Zusätzlich zu allen bereits definierten Anforderungen gilt verbindlich:

Alle vom Nutzer ausdrücklich benannten Upstream-Apps, Tools, CLIs, Runtimes, Studios und operativen Systeme müssen vollständig analysiert, funktional zerlegt, technisch neu implementiert, in die BKG-Domänen eingeordnet, auf BKG umgebrandet und in **Rust + WASM** überführt werden.

Dies gilt mindestens für:

- Supabase;
- Gastown;
- Wasteland;
- Texel Studio;
- FalSprite;
- Kilo Code;
- Kilo CLI;
- AlmostNode-bezogene Studio- und Sandbox-Funktionen;
- OpenRouter-bezogene Routing- und Modelllogik;
- Cloudflare-Image-Worker;
- Audio2Audio-Cloudflare-Expo;
- CloudFlare-ImgBed;
- cloudflare-openai-worker;
- openai-cf-workers-ai;
- cloudflare-rag;
- vectorize-mcp-worker;
- Achsi;
- sowie alle weiteren vom Nutzer ausdrücklich benannten externen Anwendungen und Operatorflächen.

## 3B.1 KEINE OBERFLÄCHLICHE ÜBERNAHME

Nicht zulässig:

- bloße Einbettung fremder UIs;
- Iframes als finale Lösung;
- kosmetisches Umbenennen ohne echte technische Integration;
- isolierte Fremdprodukte mit eigener Produktidentität;
- Wrapper ohne Datenmodellintegration;
- statische Screens anstelle echter Funktionen;
- Placeholder;
- Mocks;
- Demo-only-Flows;
- Vaporware;
- getrennte Auth-Systeme;
- getrennte Ownership-Modelle;
- getrennte Audit-Trails;
- getrennte Produktinseln unter alten Namen.

Verbindlich ist stattdessen:

- vollständiger Audit des Ursprungsprojekts;
- Feature-Matrix;
- Lizenzprüfung;
- Security-Review;
- Architekturzuordnung zu BKG;
- Recode-Plan;
- Refactor-Plan;
- Rebrand-Plan;
- Rust-Neuimplementierung;
- WASM-UI-Neuimplementierung, soweit browserrelevant;
- Persistenz in BKG-Datenmodellen;
- zentrale Auth;
- zentrale Berechtigungen;
- zentrale Auditierung;
- zentrale Live-Events;
- zentrale Tests;
- zentrale Release Evidence.

## 3B.2 GASTOWN, WASTELAND, TEXEL STUDIO, FALSPRITE, KILO CLI, ACHSI

### Supabase
Supabase ist vollständig in einen refactorten und auf BKG umgebrandeten **BKG Supabase Core** zu überführen. Dazu gehören insbesondere Auth, Realtime, Storage, Policies, Projektgrenzen, Rollen, Session-Handling und sichere Plattformdienste unter BKG-Kontrolle.

### Gastown

Gastown ist nicht nur Referenz, Dashboard oder Admin-Fläche.

Gastown ist die fachliche Grundlage für die neue zentrale **BKG Orchestration Engine**.

Diese Engine bildet später die operative Hauptsteuerung, über die alle produktiven Arbeitsströme in BKG koordiniert werden.

Dazu gehören insbesondere:

- Pipeline-Steuerung;
- Agenten-Orchestrierung;
- Task-Verteilung;
- Workstation-Zuweisung;
- Produktionsstatus;
- Queue-Überwachung;
- Abhängigkeitssteuerung;
- Freigaben;
- Review-Punkte;
- Quality-Gate-Steuerung;
- Repair-Zyklen;
- Build- und Export-Koordination;
- Live-Produktionssicht;
- Admin- und Operator-Steuerung.

Gastown darf nicht als separates Produkt bestehen bleiben.

Gastown muss vollständig in BKG recodet, refactored und rebranded werden, sodass daraus die neue **BKG Orchestration Engine** entsteht.

Die BKG Orchestration Engine ist die zentrale operative Steuerungsebene, über die später alle produktiven Systeme arbeiten.

Dazu zählen mindestens:

- Game-Docs-Workflow;
- Live-Agentendiskussion;
- Production Studio;
- Code Studio;
- Paint Studio;
- Animation Studio;
- Level Studio;
- Audio Studio;
- Build-System;
- Export-System;
- Launch-Kit-Prozesse;
- Admin- und Monitoring-Flächen.

Nicht zulässig:

- Gastown als isolierte Nebenanwendung;
- Gastown nur als Dashboard;
- Gastown nur als UI-Hülle;
- Gastown ohne echte Orchestrierungslogik;
- getrennte Task- oder Workflow-Systeme außerhalb der zentralen Engine.

Verbindlich ist stattdessen:

Gastown wird zur einheitlichen BKG-Orchestration-Engine, über die alle produktiven Prozesse, Agentenflüsse, Freigaben und operativen Steuerungen zentral laufen.

### Wasteland
Wasteland und alle vergleichbaren Studio-/Runtime-/Builder-Komponenten sind nicht separat weiterzuführen, sondern müssen in die BKG-Systemarchitektur aufgenommen, technisch neu gebaut und unter BKG-Branding vereinheitlicht werden.

### Texel Studio
Texel Studio ist vollständig in das BKG Paint Studio zu überführen, einschließlich Pixel-Editor, Tools, Palette, Layer, Versionierung, Vergleich, Agentenfortsetzung und Asset-Export.

### FalSprite
FalSprite ist vollständig in das BKG Animation Studio zu überführen, einschließlich Timeline, Action Rows, Frames, Onion Skin, Sprite-Sheet-Export, GIF-Export, Preview und Event-Frames.

### OpenRouter
OpenRouter bleibt verpflichtender Bestandteil der BKG-Modellschicht. Es ist die zentrale externe Free-Model- und Provider-Fabric für die fachlichen Game-Agenten und muss als **BKG Model Router** gekapselt, überwacht, getestet und auditierbar integriert werden.

### Cloudflare-Image-Worker
`https://github.com/dotusmanali/Cloudflare-Image-Worker` ist als Ausgangsbasis für eine vollständig refactorte und auf BKG umgebrandete Bildgenerierungs- und Bildrender-Schicht zu behandeln.

Die Zielschicht heißt verbindlich:

**BKG Image Forge**

BKG Image Forge dient mindestens für:

- Concept-Art-Generierung;
- Asset-Varianten;
- Prompt-basierte Bildjobs;
- sichere Bild-API-Orchestrierung;
- modellabhängige Bild-Pipelines;
- agentische Bildproduktion unter BKG-Audit.

Die Quelle darf nicht als unveränderte Fremd-Worker-Lösung produktiv bestehen bleiben. Laut GitHub ist das Ursprungsrepository zudem seit dem 15. April 2026 archiviert und read-only, was den Refactor statt direkter Produktabhängigkeit zusätzlich erforderlich macht. citeturn664507search0

### Audio2Audio-Cloudflare-Expo
`https://github.com/Qloud-AI/Audio2Audio-Cloudflare-Expo` ist als Ausgangsbasis für eine vollständig refactorte und auf BKG umgebrandete Echtzeit-Voice-Schicht zu behandeln.

Die Zielschicht heißt verbindlich:

**BKG Voice Loop**

BKG Voice Loop dient mindestens für:

- Audio-zu-Audio-Agentengespräche;
- Live-TTS/STT-Pipelines;
- Voice-Diskussionen;
- Streaming-Audio-Antworten;
- Sprecherwechsel;
- Voice-Testing;
- mobile und browsernahe Voice-Clients unter BKG-Kontrolle.

Das Ursprungsrepository beschreibt eine Cloudflare-Worker-basierte Echtzeit-Audio-Pipeline mit WebSockets, Transkription, LLM-Verarbeitung und TTS. Diese Funktionen müssen fachlich in BKG übernommen, sicher refactored und vollständig umgebrandet werden. citeturn664507search1

### Kilo Code / Kilo CLI
Kilo Code und Kilo CLI dürfen nicht bloß als externe schwarze Box verbleiben. Die für BKG erforderlichen Coding-Runtime-, Session-, Policy-, MCP-, Workflow-, Mode-, Skill-, Patch-, Context- und Audit-Funktionen müssen in BKG vollständig nachvollziehbar, kontrollierbar und soweit erforderlich in Rust neu implementiert und unter BKG-Branding operationalisiert werden.

### CloudFlare-ImgBed
`https://github.com/MarSeventh/CloudFlare-ImgBed` ist vollständig zu auditieren, fachlich zu zerlegen und unter BKG neu umzusetzen.

Die Zielschicht heißt verbindlich:

**BKG Asset Core**

BKG Asset Core dient mindestens für:

- Asset-Hosting;
- sichere Dateiablage;
- Media Vault;
- Versionierung;
- signierte Zugriffe;
- Produktionsdateien;
- Export-Dateien;
- kontrollierte Sharing-Flows;
- Object-Storage-Policies;
- projektbezogene Ownership.

Die Originalquelle darf nicht unverändert als Produktbasis bestehen bleiben.

### cloudflare-openai-worker
`https://github.com/kathleenwest/cloudflare-openai-worker` ist vollständig zu auditieren, fachlich zu zerlegen und unter BKG neu umzusetzen.

Die Zielschicht heißt verbindlich:

**BKG Prompt Gateway**

BKG Prompt Gateway dient mindestens für:

- einfache generative Edge-Endpunkte;
- Text- und Bildjob-Annahme;
- OpenAI-kompatible Request-/Response-Formate;
- kontrollierte Prompt-API-Eingänge;
- leichte Agentenhilfsjobs;
- sichere Gateway-Funktionen mit Audit, Rate Limit und Kostenkontrolle.

Die demoartigen Madlib-/Beispielpfade der Quelle sind zu entfernen oder vollständig in BKG-Fachlogik umzubauen.

### openai-cf-workers-ai
`https://github.com/chand1012/openai-cf-workers-ai` ist vollständig zu auditieren, fachlich zu zerlegen und unter BKG neu umzusetzen.

Die Zielschicht heißt verbindlich:

**BKG Edge Model Bridge**

BKG Edge Model Bridge dient mindestens für:

- OpenAI-kompatible Modellendpunkte;
- Cloudflare-AI-nahe Fallbacks;
- providerneutrale Edge-Modellbrücken;
- budgetnahe oder latencynahe Modellrouten;
- kontrollierte Bridge-Funktionen zwischen BKG Model Router und Edge-Modellschichten.

### cloudflare-rag
`https://github.com/rafalwilinski/cloudflare-rag` ist vollständig zu auditieren, fachlich zu zerlegen und unter BKG neu umzusetzen.

Die Zielschicht heißt verbindlich:

**BKG RAG Core**

BKG RAG Core dient mindestens für:

- Dokumentretrieval;
- Wissenssuche;
- Game-Docs-Kontext;
- PDF- und Referenzdokument-Kontext;
- semantische Suche;
- hybride Suche;
- Retrieval-Pipelines für Agenten;
- streamingfähige Kontextlieferung.

### vectorize-mcp-worker
`https://github.com/dannwaneri/vectorize-mcp-worker` ist vollständig zu auditieren, fachlich zu zerlegen und unter BKG neu umzusetzen.

Die Zielschicht heißt verbindlich:

**BKG Knowledge Edge**

BKG Knowledge Edge dient mindestens für:

- Hybrid Search;
- Vector Search;
- BM25;
- Metadata Filtering;
- multimodale Ingestion;
- MCP-Tools;
- Query Routing;
- Query Analytics;
- Agenten-Retrieval;
- projektgebundene Wissensräume.

Die Originalquelle darf nur als Architektur- und Migrationsreferenz dienen, nicht als finale Produktbasis.

### Achsi
Achsi und alle entsprechend benannten zusätzlichen Systeme des Nutzers sind genauso als verpflichtende Audit-, Recode-, Refactor- und Rebrand-Kandidaten zu behandeln.



## 3B.2A BKG ALS PLATTFORM — NICHT ALS GAME

Alle Architektur-, UI-, Runtime-, Build- und Produktionsentscheidungen sind so zu treffen, dass BKG als Plattform arbeitet, die Games erzeugt.

Nicht zulässig sind missverständliche Formulierungen oder technische Entscheidungen, die BKG selbst wie ein einzelnes Spiel behandeln.

Verbindlich ist:

- BKG ist das Studio- und Produktionssystem;
- die vom Nutzer beauftragten Spiele sind die Produktartefakte;
- Spiel-Runtimes, Builds, Previews und Exporte beziehen sich auf die erzeugten Games;
- BKG stellt dafür die Produktionsumgebung, Orchestrierung, Editoren, Agenten, Tests, Qualitätssicherung und Release-Prozesse bereit.

## 3B.3 RUST + WASM PFLICHT FÜR DIE NEUUMSETZUNG

Alle finalen produktiven BKG-Systeme müssen in Rust und – soweit browserseitig – in WASM umgesetzt werden.

Nicht zulässig als finale Produktbasis:

- Next.js;
- React-Pflichtarchitektur;
- TypeScript-Hauptimplementierung;
- externe JS-Produktinseln;
- Go-Produktinseln;
- Python-Produktinseln.

Externe Originalprojekte dürfen höchstens dienen als:

- Analysequelle;
- Migrationsreferenz;
- Kompatibilitätsreferenz;
- Evidence-Referenz;
- Import-/Parity-Referenz.

Sie dürfen **nicht** die finale BKG-Produktbasis bleiben.

## 3B.4 FULL REBRAND

Alle übernommenen Funktionen, UIs, Studios, CLIs, Workflows und Operatorflächen müssen vollständig auf BKG umgebrandet werden.

Pflicht:

- BKG-Name;
- BKG-Terminologie;
- BKG-Routen;
- BKG-Designsystem;
- BKG-Farbsprache;
- BKG-Fehlerbilder;
- BKG-Auditbezeichnungen;
- BKG-Rollenmodell;
- BKG-Produktidentität.

Nicht zulässig:

- alte Logos;
- alte Produktnamen in produktiver UI;
- gemischte Brandings;
- sichtbare Fremd-CLI-Produktnamen als Kernoberfläche;
- parallele Produktidentitäten.

## 3B.5 RELEASE-PFLICHT FÜR FULL RECODE / FULL REBRAND

Ergänze verbindlich zusätzliche Release-Blöcke:

### Release 00C — Upstream Audit and Recode Mapping
- Supabase auditieren;
- Gastown auditieren;
- Wasteland auditieren;
- Texel Studio auditieren;
- FalSprite auditieren;
- Kilo Code / Kilo CLI auditieren;
- Achsi auditieren;
- Feature-Mapping erstellen;
- Rebrand-Plan erstellen;
- Rust/WASM-Neuimplementierungsplan erstellen;
- Security- und Lizenz-Evidence erzeugen.

### Release 02A — Supabase to BKG Supabase Core
- vollständiger Audit;
- vollständiger Refactor-Plan;
- vollständiger Rebrand-Plan;
- Auth, Realtime, Storage, Policies und Ownership-Härtung;
- Rust-Adapter;
- Tests;
- Evidence.

### Release 02B — CloudFlare-ImgBed to BKG Asset Core
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- Storage-, File-, Asset- und Media-Vault-Integration;
- Ownership- und Access-Policies;
- Tests;
- Evidence.

### Release 03A — cloudflare-openai-worker to BKG Prompt Gateway
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- generative Edge-Gateway-Funktionen;
- Auth, Audit, Rate Limit, Kostenkontrolle;
- Tests;
- Evidence.

### Release 03B — openai-cf-workers-ai to BKG Edge Model Bridge
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- OpenAI-kompatible Bridge-Endpunkte;
- Edge-Modell-Fallbacks;
- Tests;
- Evidence.

### Release 03C — cloudflare-rag to BKG RAG Core
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- hybride Suche;
- Wissens- und Retrieval-Pipelines;
- Tests;
- Evidence.

### Release 03D — vectorize-mcp-worker to BKG Knowledge Edge
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- Hybrid Search;
- MCP-Integration;
- multimodale Ingestion;
- Knowledge- und Query-Analytics;
- Tests;
- Evidence.

### Release 06A — Cloudflare-Image-Worker to BKG Image Forge
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- sichere Bild-API- und Bildjob-Integration;
- Asset- und Object-Storage-Verknüpfung;
- Tests;
- Evidence.

### Release 06B — Audio2Audio-Cloudflare-Expo to BKG Voice Loop
- vollständiger Audit;
- vollständiger Refactor;
- vollständiger Rust-Recode;
- vollständiger BKG-Rebrand;
- Voice-Streaming;
- Audio-zu-Audio-Agentenpipeline;
- TTS/STT-Integration;
- Tests;
- Evidence.

### Release 07A — Texel Studio to BKG Paint Studio
- vollständiger Rust/WASM-Recode;
- vollständiger BKG-Rebrand;
- Tests;
- Evidence.

### Release 08A — FalSprite to BKG Animation Studio
- vollständiger Rust/WASM-Recode;
- vollständiger BKG-Rebrand;
- Tests;
- Evidence.

### Release 09A — Kilo Runtime to BKG Coding Runtime Layer
- vollständige BKG-kontrollierte Rust-Neuumsetzung der benötigten Coding-Layer;
- Policy, MCP, Sessions, Audit, Workflows, Skills, Context, Validation;
- Tests;
- Evidence.

### Release 13A — Gastown to BKG Orchestration Engine / Wasteland / Operations Recode
- vollständiger Rust/WASM-Recode;
- vollständiger BKG-Rebrand;
- operative Dashboards;
- Adminflächen;
- Struktur- und Produktionssicht;
- Tests;
- Evidence.

## 3B.6 DEFINITION OF DONE — ERWEITERUNG

BKG gilt zusätzlich nur dann als production-ready, wenn:

- Supabase, Gastown, Wasteland, Texel Studio, FalSprite, Kilo CLI, Cloudflare-Image-Worker, Audio2Audio-Cloudflare-Expo, CloudFlare-ImgBed, cloudflare-openai-worker, openai-cf-workers-ai, cloudflare-rag, vectorize-mcp-worker, Achsi und weitere benannte Systeme nicht mehr als separate Produktinseln sichtbar sind;
- die finalen produktiven Systeme in Rust umgesetzt sind;
- browserseitige Oberflächen in WASM umgesetzt sind;
- Full Rebrand vollständig umgesetzt ist;
- keine Mocks, Placeholder oder Vaporware verbleiben;
- alle übernommenen Bereiche in BKG-Auth, BKG-Permissions, BKG-Audit und BKG-Tests integriert sind;
- alle Recode-/Rebrand-Releases grün sind;
- die Evidence vollständig vorliegt;
- Gastown als zentrale BKG Orchestration Engine arbeitet;
- alle produktiven Bereiche später über diese Orchestration Engine koordiniert werden;
- nirgends mehr impliziert wird, dass BKG selbst das Game ist.



---

# 3C. VERBINDLICHE REFACTOR-, RENAME- UND ZIELSYSTEM-MATRIX

## 3C.1 GRUNDREGEL

Für **jedes** benannte externe System gilt verbindlich:

- vollständiger Audit;
- vollständiger Funktionsvergleich;
- vollständiger Architekturvergleich;
- vollständiger Sicherheitsreview;
- vollständiger Datenmodellvergleich;
- vollständiger Workflowvergleich;
- vollständiger Refactor;
- vollständiger Rust-Recode der produktiven Kernlogik;
- vollständiger BKG-Rebrand;
- vollständige Integration in BKG Auth, BKG Permissions, BKG Audit, BKG Storage, BKG Live Events und BKG Release Evidence.

Nicht zulässig:

- Wrapper-only;
- Adapter-only als Endlösung;
- Fork mit neuem Logo;
- bloße UI-Übernahme;
- TypeScript-/JavaScript-/Cloudflare-/Node-Produktbasis als finaler Zustand;
- parallele Produktinseln;
- halbfertige Portierung;
- Mocks;
- Placeholder;
- Vaporware.

## 3C.2 KANONISCHE ZIELNAMEN

Ab sofort gelten folgende verbindliche BKG-Zielnamen:

- **Supabase** → **BKG Supabase Core**
- **Supabase Auth** → **BKG Identity Core**
- **Supabase Realtime** → **BKG Live Core**
- **Supabase Storage** → **BKG Asset Core**
- **Supabase Policies** → **BKG Access Policies**
- **Gastown** → **BKG Orchestration Engine**
- **Gastown UI / Ops Surface** → **BKG Control Center**
- **Wasteland** → **BKG Runtime Forge**
- **Texel Studio** → **BKG Paint Studio**
- **FalSprite** → **BKG Animation Studio**
- **Kilo Code** → **BKG Coding Runtime**
- **Kilo CLI** → **BKG Coding CLI**
- **AlmostNode Integration** → **BKG Browser Sandbox**
- **OpenRouter Fabric** → **BKG Model Router**
- **Cloudflare-Image-Worker** → **BKG Image Forge**
- **Audio2Audio-Cloudflare-Expo** → **BKG Voice Loop**
- **CloudFlare-ImgBed** → **BKG Asset Core**
- **cloudflare-openai-worker** → **BKG Prompt Gateway**
- **openai-cf-workers-ai** → **BKG Edge Model Bridge**
- **cloudflare-rag** → **BKG RAG Core**
- **vectorize-mcp-worker** → **BKG Knowledge Edge**
- **Achsi** → **BKG Achsi Integration Layer**

## 3C.3 REFACTOR-EBENEN

Jedes benannte Fremdsystem muss entlang dieser Ebenen refactored werden:

- Architektur-Refactor;
- Naming-Refactor;
- Datenmodell-Refactor;
- Workflow-Refactor;
- UI-Refactor;
- Runtime-Refactor;
- Security-Refactor;
- Ownership-Refactor;
- Permissions-Refactor;
- Event-Refactor;
- Observability-Refactor;
- Release-Evidence-Refactor.

## 3C.4 SYSTEMWEISE VERBINDLICHE ZIELROLLE

### BKG Supabase Core
Zielrolle:
- Plattformkern für Auth, Sessions, Realtime, Storage, Policies.

Vollständig zu refactoren:
- Auth-Flows;
- Rollen;
- Projektgrenzen;
- RLS-nahe Zugriffsmuster;
- Storage;
- Tokens;
- Secrets;
- Realtime-Kanäle;
- Ownership.

Nur als Referenz zu behalten:
- Architekturideen;
- Betriebsmodelle;
- Sicherheitsmuster.

### BKG Orchestration Engine
Aus Gastown hervorgehend.

Zielrolle:
- zentrale operative Steuerungsebene von BKG.

Vollständig zu refactoren:
- Task-Systeme;
- Studio-Organisation;
- Admin- und Operatorflächen;
- Produktionsübersichten;
- Pipeline-Steuerung;
- Workstation-Zuweisung;
- Queue- und Review-Steuerung.

### BKG Runtime Forge
Aus Wasteland hervorgehend.

Zielrolle:
- Runtime-, Build-, Preview- und Produktionskern für erzeugte Games.

Vollständig zu refactoren:
- Runtime-Schichten;
- Builder-Muster;
- Entwicklungs- und Ausführungslogik;
- Spielproduktionsanbindung.

### BKG Paint Studio
Aus Texel Studio hervorgehend.

Zielrolle:
- Pixelproduktion, Asset-Bearbeitung, manuelle und agentische Paint-Workflows.

Vollständig zu refactoren:
- Canvas;
- Tools;
- Layer;
- Palette;
- History;
- Export;
- Referenzvergleiche;
- Audit- und Approval-Flows.

### BKG Animation Studio
Aus FalSprite hervorgehend.

Zielrolle:
- Sprite-, Frame- und Timeline-Animation.

Vollständig zu refactoren:
- Action Rows;
- Frames;
- Onion Skin;
- Timing;
- Preview;
- Sprite-Sheet- und GIF-Export;
- Eventframes;
- Produktionsverknüpfung.

### BKG Coding Runtime
Aus Kilo Code hervorgehend.

Zielrolle:
- kontrollierte Coding-Agent-Runtime für Repository-Arbeit.

Vollständig zu refactoren:
- Sessions;
- Modes;
- Skills;
- Workflows;
- MCP-Anbindung;
- Patch- und Plan-Modelle;
- Context-Management;
- Audit;
- Kosten;
- Policy Enforcement.

### BKG Coding CLI
Aus Kilo CLI hervorgehend.

Zielrolle:
- kontrollierte BKG-CLI für Coding-, Validation- und Release-Aufgaben.

Vollständig zu refactoren:
- Commands;
- Policy Checks;
- Session Hooks;
- Validation und Evidence-Kommandos.

### BKG Browser Sandbox
Aus AlmostNode hervorgehend.

Zielrolle:
- browsernahe isolierte Experimentsandbox.

Vollständig zu refactoren:
- Sandbox-Policies;
- Snapshots;
- Diffs;
- Import-Pläne;
- Preview;
- Sicherheitsgrenzen;
- Tenant-Isolation.

### BKG Model Router
Aus OpenRouter hervorgehend.

Zielrolle:
- providerneutrale Modellrouting-Fabric.

Vollständig zu refactoren:
- Free/Paid-Routing;
- Model Health;
- Capability Profiles;
- Circuit Breaker;
- Quarantäne;
- Cost Policies;
- Routing Decisions;
- Usage und Audit.

### BKG Image Forge
Aus Cloudflare-Image-Worker und verwandten Bild-Workern hervorgehend.

Zielrolle:
- Bildgenerierung, Bildedits, Concept-Art- und Asset-Bildjobs.

Vollständig zu refactoren:
- Modellrouting für Bildjobs;
- Jobannahme;
- Prompt-Schema;
- Sicherheitsgrenzen;
- Storage-Integration;
- Asset-Metadaten;
- Kosten- und Audit-Tracking.

### BKG Voice Loop
Aus Audio2Audio-Cloudflare-Expo hervorgehend.

Zielrolle:
- Echtzeit-Audio-zu-Audio- und Voice-Streaming-Schicht.

Vollständig zu refactoren:
- Audio-Pipeline;
- WebSockets;
- TTS/STT;
- Sprecherwechsel;
- Auth;
- Kosten;
- Caching;
- Voice-Playback;
- Agenten-Diskussionsanbindung.

### BKG Asset Core
Aus CloudFlare-ImgBed und Storage-Schichten hervorgehend.

Zielrolle:
- zentrale Medien- und Dateischicht für BKG.

Vollständig zu refactoren:
- Uploads;
- Buckets;
- signierte URLs;
- Ownership;
- Asset-Versionen;
- Storage-Policies;
- Export-Dateien;
- Quarantäne-/Review-Flows.

### BKG Prompt Gateway
Aus cloudflare-openai-worker hervorgehend.

Zielrolle:
- schlanke Edge-Gateway-Schicht für generative Jobs.

Vollständig zu refactoren:
- Request-/Response-Formate;
- Prompt-Schemas;
- Auth;
- Audit;
- Rate Limits;
- Kostenkontrolle;
- Jobtypen statt Demo-/Madlib-Funktionen.

### BKG Edge Model Bridge
Aus openai-cf-workers-ai hervorgehend.

Zielrolle:
- OpenAI-kompatible Bridge zu Edge-Modellschichten.

Vollständig zu refactoren:
- Provider-Bridges;
- Fallback-Logik;
- Bridge-Auth;
- Routing-Kontext;
- Kosten- und Rate-Limit-Handling;
- Sicherheitsfilter.

### BKG RAG Core
Aus cloudflare-rag hervorgehend.

Zielrolle:
- dokumenten- und wissensbasierte Retrieval-Schicht.

Vollständig zu refactoren:
- RAG-Pipelines;
- Doku- und PDF-Kontext;
- Retrieval für Agenten;
- semantische Suche;
- Streaming-Kontext;
- Projektbezogene Wissensräume.

### BKG Knowledge Edge
Aus vectorize-mcp-worker hervorgehend.

Zielrolle:
- Hybrid Search + MCP + multimodale Wissensschicht.

Vollständig zu refactoren:
- Vector Search;
- BM25;
- Metadata Filtering;
- multimodale Ingestion;
- MCP-Tools;
- Query Analytics;
- Query Routing;
- Projekt-/Tenant-Grenzen;
- Audit und Permissions.

### BKG Achsi Integration Layer
Aus Achsi hervorgehend.

Zielrolle:
- vom Nutzer definierte Spezialintegration unter BKG-Kontrolle.

Vollständig zu refactoren:
- Naming;
- Auth;
- Datenmodell;
- Workflow;
- Audit;
- Release Evidence.

## 3C.5 TECHNIKREGEL FÜR ALLE FREMDSYSTEME

Alle finalen produktiven Zielsysteme müssen in **Rust** neu umgesetzt werden.

Browserseitige Oberflächen müssen in **WASM** neu umgesetzt werden, soweit sie produktive UI sind.

Externe Originalsysteme dürfen nur bleiben als:

- Analysequelle;
- Referenzquelle;
- Migrationsquelle;
- Feature-Parity-Quelle;
- Test- und Evidence-Quelle.

Sie dürfen **nicht** die finale Produktbasis bleiben.

## 3C.6 VERBINDLICHE REFACTOR-MATRIX ALS ARBEITSFORM

Für jedes benannte System ist eine reale Matrix zu erzeugen mit mindestens:

- Originalname;
- BKG-Zielname;
- Originalzweck;
- BKG-Zweck;
- Was vollständig übernommen wird;
- Was fachlich umgebaut wird;
- Was komplett entfernt wird;
- Was nur als Referenz bleibt;
- Welche Rust-Neuimplementierung erforderlich ist;
- Welche WASM-Neuimplementierung erforderlich ist;
- Welche Sicherheitsmaßnahmen nötig sind;
- Welche Tests nötig sind;
- Welcher Release-Block zuständig ist;
- Welche Evidence erzeugt werden muss.


# 4. MONOREPO

Erstelle mindestens folgende Rust/WASM-Monorepo-Struktur:

```text
bkg/
├── apps/
│   ├── web/
│   └── jobs/
├── packages/
│   ├── ui/
│   ├── database/
│   ├── contracts/
│   ├── validation/
│   ├── auth/
│   ├── ai/
│   ├── agents/
│   ├── live-events/
│   ├── voice/
│   ├── game-docs/
│   ├── game-engine/
│   ├── pixel-engine/
│   ├── animation-engine/
│   ├── level-engine/
│   ├── audio-engine/
│   ├── observability/
│   ├── config/
│   └── testing/
├── docs/
│   └── release-evidence/
├── migrations/
├── scripts/
├── tests/
├── package.json
├── pnpm-workspace.yaml
├── turbo.json
├── docker-compose.yml
├── dev-vars-example
└── readme.md
```

## 4.1 `apps/web`

Enthält:

* Rust/WASM-Webanwendung;
* Marketingseiten;
* Authentifizierung;
* Nutzerstudio;
* Game-Docs-Editor;
* Live-Agentenkonferenz;
* Production Studio;
* Code Studio;
* Paint Studio;
* Animation Studio;
* Level Studio;
* Audio Studio;
* Preview;
* Export;
* Launch;
* Administration;
* API-BFF;
* Live-Event-Verbindungen.

## 4.2 `apps/jobs`

Enthält:

* Rust-Worker und Queue-Orchestrierung;
* Game-Docs-Jobs;
* Agentendiskussions-Jobs;
* TTS-Jobs;
* Speech-to-Text-Jobs;
* Image-Jobs;
* Pixel-Jobs;
* Animations-Jobs;
* Audio-Jobs;
* Level-Jobs;
* Code-Jobs;
* Build-Jobs;
* Quality-Gate-Jobs;
* Repair-Jobs;
* Export-Jobs;
* Launch-Jobs;
* Heartbeats;
* Retry;
* Stalled-Job-Recovery;
* Dead-Letter-Verarbeitung.

---

# 4A. ALMOSTNODE — BROWSER-NATIVE NODE.JS-SANDBOX

Integriere AlmostNode als browsernative, projektbezogene Entwicklungs- und Preview-Sandbox.

AlmostNode ermöglicht Node.js-artige Workflows im Browser, einschließlich virtuellem Dateisystem, npm-Paketinstallation und Development-Servern für unterstützte Vite- oder Next.js-Projekte.

## 4A.1 Verwendungszweck

AlmostNode wird innerhalb von BKG ausschließlich für folgende Aufgaben eingesetzt:

- browserbasierte Codeexperimente;
- interaktive Live-Code-Vorschau;
- temporäre Agenten-Workspaces;
- virtuelles Dateisystem;
- unterstützte npm-Paketinstallation;
- Development-Server;
- Vite-Preview;
- Next.js-Development-Preview, soweit unterstützt;
- reproduzierbare Nutzerexperimente;
- Darstellung geplanter Codeänderungen;
- clientseitige Prototypisierung vor serverseitiger Übernahme;
- isolierte Lehr- und Erkläransichten im Code Studio.

## 4A.2 AlmostNode ist keine Production-Runtime

AlmostNode ersetzt niemals:

- PostgreSQL;
- Prisma;
- Redis;
- BullMQ;
- serverseitige Worker;
- den Secret Vault;
- Object Storage;
- CI;
- serverseitige Tests;
- Production Builds;
- Release Builds;
- Security Gates;
- Export Gates;
- Deployment;
- Release Evidence;
- den kontrollierten CodeBuilderAgent.

Ein in AlmostNode erfolgreich gestartetes Projekt gilt nicht als Production Build.

## 4A.3 Interner Adapter

Erstelle in `packages/sandbox`:

```text
packages/sandbox/
├── src/
│   ├── contracts.ts
│   ├── browser-node-sandbox.ts
│   ├── almostnode-adapter.ts
│   ├── sandbox-policy.ts
│   ├── sandbox-events.ts
│   ├── sandbox-snapshots.ts
│   ├── sandbox-diff.ts
│   └── index.ts
├── tests/
└── package.json
```

Pflichtinterface:

```ts
interface BrowserNodeSandbox {
  getCapabilities(): Promise<SandboxCapabilities>;

  createSession(
    input: CreateSandboxSessionInput
  ): Promise<SandboxSession>;

  writeFiles(
    input: WriteSandboxFilesInput
  ): Promise<WriteSandboxFilesResult>;

  readFiles(
    input: ReadSandboxFilesInput
  ): Promise<ReadSandboxFilesResult>;

  listFiles(
    input: ListSandboxFilesInput
  ): Promise<ListSandboxFilesResult>;

  installPackages(
    input: InstallSandboxPackagesInput
  ): Promise<InstallSandboxPackagesResult>;

  runCommand(
    input: RunSandboxCommandInput
  ): Promise<RunSandboxCommandResult>;

  startPreview(
    input: StartSandboxPreviewInput
  ): Promise<PreviewSession>;

  stopPreview(
    input: StopSandboxPreviewInput
  ): Promise<void>;

  createSnapshot(
    input: CreateSandboxSnapshotInput
  ): Promise<SandboxSnapshot>;

  restoreSnapshot(
    input: RestoreSandboxSnapshotInput
  ): Promise<void>;

  createDiff(
    input: CreateSandboxDiffInput
  ): Promise<SandboxDiff>;

  cancelOperation(
    input: CancelSandboxOperationInput
  ): Promise<void>;

  resetSession(
    input: ResetSandboxSessionInput
  ): Promise<void>;

  destroySession(
    input: DestroySandboxSessionInput
  ): Promise<void>;
}
```

## 4A.4 Sandbox Capability Discovery

Die Anwendung darf keine Fähigkeiten annehmen, die die installierte AlmostNode-Version nicht besitzt.

Ermittle und speichere:

- unterstützte Node APIs;
- unterstützte Package Manager;
- unterstützte npm-Pakete;
- unterstützte Frameworks;
- unterstützte Dev-Server;
- verfügbare Dateisystemoperationen;
- Netzwerkfähigkeit;
- Worker-Unterstützung;
- Speichergrenzen;
- bekannte Browsergrenzen.

Bei nicht unterstützten Funktionen:

- klare Fehlermeldung;
- serverseitigen Fallback anbieten;
- keine Fake-Erfolgsantwort;
- keine stillen Funktionsverluste.

## 4A.5 Sandbox-Datenmodell

Erweitere die Datenbank mindestens um:

- sandbox-sessions;
- sandbox-session-members;
- sandbox-files;
- sandbox-file-snapshots;
- sandbox-commands;
- sandbox-command-results;
- sandbox-package-installs;
- sandbox-preview-sessions;
- sandbox-events;
- sandbox-policy-violations;
- sandbox-import-plans;
- sandbox-import-files;
- sandbox-resource-usage.

Jeder Datensatz benötigt:

- User Ownership;
- Project Ownership;
- Created At;
- Updated At;
- Status;
- Audit-Bezug;
- Ablaufzeit;
- Löschstatus;
- Fehlerstatus, falls relevant.

## 4A.6 Sicherheitsmodell

Jede Sandbox muss isoliert sein.

Pflichtregeln:

- eindeutige Sandbox-ID;
- eindeutige User-ID;
- eindeutige Project-ID;
- Session Ownership;
- Cross-Tenant-Blockierung;
- erlaubte Workspace-Wurzel;
- normalisierte Pfade;
- Schutz vor `../`;
- Schutz vor absoluten Host-Pfaden;
- Schutz vor Symlink Escape;
- Dateigrößenlimits;
- Gesamtgrößenlimit;
- Dateianzahllimit;
- CPU-Zeitlimit;
- Command-Laufzeitlimit;
- Speicherlimit;
- Output-Limit;
- Log-Limit;
- Paket-Allowlist;
- Paket-Denylist;
- Command-Allowlist;
- Netzwerk standardmäßig deaktiviert;
- optionale Domain-Allowlist;
- keine Datenbank-Credentials;
- keine Redis-Credentials;
- keine Object-Storage-Credentials;
- keine Provider-Secrets;
- keine Session-Secrets;
- keine Admin-Tokens;
- keine Deployment-Credentials;
- keine unkontrollierten nativen Binärdateien.

## 4A.7 Paketinstallation

Paketinstallationen benötigen:

- normalisierten Paketnamen;
- erlaubte Version;
- Lockfile;
- Paketgrößenprüfung;
- Lizenzprüfung;
- Dependency Audit;
- bekannte Vulnerability-Prüfung;
- Installations-Timeout;
- Installationslog;
- Audit Event;
- Cache-Key;
- reproduzierbare Wiederherstellung.

Nicht zulässig:

- Installation aus beliebigen Dateipfaden;
- Installation aus ungeprüften Git-URLs;
- postinstall-Skripte ohne Policy;
- Pakete mit blockierten nativen Abhängigkeiten;
- ungeprüfte globale Installationen.

## 4A.8 Netzwerkpolitik

Standard:

```text
network-access = denied
```

Optional erlaubte Zugriffe müssen:

- pro Projekt konfiguriert;
- pro Domain eingeschränkt;
- serverseitig genehmigt;
- auditierbar;
- zeitlich begrenzt

sein.

Private IP-Bereiche, Metadatenendpunkte und lokale Infrastruktur müssen blockiert werden.

Blockiere mindestens:

- `127.0.0.0/8`;
- `10.0.0.0/8`;
- `172.16.0.0/12`;
- `192.168.0.0/16`;
- Link-Local-Adressen;
- Cloud-Metadata-Endpunkte;
- interne Service-Namen;
- Datenbankhosts;
- Redis-Hosts;
- Object-Storage-Admin-Endpunkte.

## 4A.9 Übernahme in Production-Code

Code aus AlmostNode darf niemals direkt in das Repository geschrieben werden.

Verbindlicher Ablauf:

```text
Sandbox Experiment
→ Sandbox Snapshot
→ Sandbox Diff
→ Import Plan
→ Dateiliste
→ Risikoanalyse
→ Nutzer- oder Policy-Approval
→ CodeBuilderAgent Review
→ serverseitiger Patch
→ Format
→ Lint
→ Typecheck
→ Unit Tests
→ Integration Tests
→ Security Scan
→ Production Build
→ Quality Gate
→ Release Evidence
```

Jede importierte Datei benötigt:

- ursprüngliche Sandbox-ID;
- Snapshot-ID;
- Dateipfad;
- vorherigen Hash;
- neuen Hash;
- Change Reason;
- Task-ID;
- Game-Docs-Referenz;
- Approval;
- Testnachweise.

## 4A.10 AlmostNode Studio UI

Erweitere das Code Studio um:

- Sandbox erstellen;
- Sandbox stoppen;
- Sandbox zurücksetzen;
- Dateibaum;
- Editor;
- Terminalausgabe;
- Package-Installationsansicht;
- Preview;
- Command-History;
- Ressourcenanzeige;
- Snapshot erstellen;
- Snapshot wiederherstellen;
- Diff anzeigen;
- Import Plan erstellen;
- Import genehmigen;
- Audit anzeigen;
- Policy Violations anzeigen.

## 4A.11 AlmostNode Live Events

Implementiere mindestens:

```text
sandbox-created
sandbox-ready
sandbox-file-written
sandbox-command-started
sandbox-command-output
sandbox-command-completed
sandbox-command-failed
sandbox-package-install-started
sandbox-package-install-completed
sandbox-package-install-failed
sandbox-preview-started
sandbox-preview-stopped
sandbox-snapshot-created
sandbox-restored
sandbox-policy-violation
sandbox-import-plan-created
sandbox-import-approved
sandbox-destroyed
```

## 4A.12 AlmostNode Tests

Unit Tests:

- Pfadnormalisierung;
- Policy Engine;
- Paket-Allowlist;
- Command-Allowlist;
- Ressourcengrenzen;
- Diff-Erzeugung;
- Snapshot-Metadaten.

Integration Tests:

- Session erstellen;
- Dateien schreiben und lesen;
- Paket installieren;
- Command ausführen;
- Preview starten;
- Snapshot erzeugen;
- Restore;
- Import Plan;
- Cleanup.

Security Tests:

- Cross-Tenant-Zugriff;
- Path Traversal;
- Symlink Escape;
- Secret Injection;
- verbotene Domain;
- private IP;
- Command Injection;
- Output Flooding;
- Paket-Denylist;
- Timeout;
- Speicherüberschreitung.

E2E-Test:

1. Nutzer erstellt Sandbox.
2. Agent schreibt ein minimales Spielmodul.
3. Sandbox startet Preview.
4. Nutzer sieht Preview.
5. Nutzer erstellt Snapshot.
6. Agent erzeugt Diff.
7. Import Plan wird genehmigt.
8. Server übernimmt Patch.
9. Typecheck und Tests laufen.
10. Production Build besteht.
11. Audit Trail ist vollständig.


---

# 5. PRODUKTROUTEN

Implementiere mindestens:

```text
/
/login
/register
/studio
/dashboard
/projects/[project-id]

/game-docs/[game-docs-id]
/game-docs/[game-docs-id]/review
/game-docs/[game-docs-id]/discussion

/live/[pipeline-run-id]
/production/[project-id]

/code/[code-session-id]
/paint/[pixel-document-id]
/animate/[animation-id]
/levels/[level-id]
/audio/[audio-workspace-id]

/preview/[build-id]
/export/[game-id]
/launch/[game-id]
/marketing/[game-id]
/settings

/admin
/admin/dashboard
/admin/studio/[game-id]
/admin/agents
/admin/discussions
/admin/voices
/admin/queues
/admin/rag
/admin/costs
/admin/security
/admin/structure
```


Zusätzliche Pflichtrouten:

```text
/sandbox/[sandbox-session-id]
/sandbox/[sandbox-session-id]/preview
/settings/models
/settings/coding-agent
/admin/models
/admin/models/routing
/admin/models/health
/admin/sandboxes
/admin/kilo-runtime
/admin/kilo-runtime/skills
/admin/kilo-runtime/extensions
/admin/kilo-runtime/hooks
/admin/kilo-runtime/mcp
```


Jede Route benötigt:

* Loading State;
* Error State;
* Empty State;
* Permission State;
* serverseitige Zugriffskontrolle;
* Cross-Tenant-Schutz;
* sinnvolle Fehlerbehandlung;
* responsive Darstellung;
* Tastaturbedienung;
* Accessibility-Grundlagen.

---

# 6. STARTSEITE DES STUDIOS

Auf der ersten Studioseite befindet sich die zentrale Funktion:

# FULL DOCS CONCEPT ERSTELLEN

Der Nutzer gibt mindestens ein:

* Spielidee;
* Genre;
* Zielplattform;
* gewünschte Perspektive;
* visuelle Stilrichtung;
* Inspirationsquellen;
* Produktionsumfang;
* besondere Mechaniken;
* optionale Referenzbilder;
* optionale Referenzdokumente;
* gewünschte Sprache;
* gewünschte Voice-Sprache;
* optionale technische Einschränkungen.

Die KI darf bei fehlenden Angaben sinnvolle Vorschläge erzeugen.

Ungeklärte Annahmen müssen sichtbar markiert und später in der Agentendiskussion geprüft werden.

Nach dem Start erzeugt die Plattform nicht sofort das Spiel.

Sie startet zuerst den vollständigen Game-Docs-Workflow.

---

# 7. GAME-DOCS-GRUNDPRINZIP

Die Game Specification Documents bilden die verbindliche Produktionsgrundlage.

Ohne vollständige, validierte, bestätigte und gesperrte Dokumente darf keine Produktionspipeline starten.

Die Dokumente definieren:

* Spielidee;
* technische Rahmenbedingungen;
* Genre;
* Perspektive;
* Welt;
* Story;
* Quests;
* Spieler;
* Fähigkeiten;
* Gegner;
* Bosse;
* Items;
* Levels;
* Regeln;
* Art Direction;
* Pixel-Art-Richtung;
* Animation;
* Audio;
* UI;
* Produktionsplanung;
* Risiken;
* Validierungsregeln;
* Exportziel.

---

# 8. DOKUMENTSTATUS

Jeder Dokumentabschnitt besitzt einen serverseitig gespeicherten Status.

Erlaubte Statuswerte:

```text
draft
ready-for-review
approved
locked
needs-revalidation
conflicted
archived
```

## Draft

Der Abschnitt wird erzeugt oder bearbeitet.

## Ready for Review

Pflichtfelder und Mindestvalidierungen sind erfüllt.

## Approved

Der Nutzer oder der definierte Review-Prozess hat den Inhalt bestätigt.

## Locked

Der Abschnitt ist verbindlicher Bestandteil der aktuellen Game Specification.

## Needs Revalidation

Ein früheres Dokument wurde geändert und dieser Abschnitt muss erneut geprüft werden.

## Conflicted

Der Abschnitt enthält ungelöste Widersprüche.

## Archived

Die Version wurde durch eine neuere Version ersetzt.

Ein Dokument darf erst gesperrt werden, wenn:

* alle Pflichtfelder vorhanden sind;
* seine Abhängigkeiten gültig sind;
* keine blockierenden Konflikte bestehen;
* die automatische Validierung erfolgreich ist;
* der Review-Prozess abgeschlossen ist;
* der Nutzer oder der erlaubte Bestätigungsprozess zugestimmt hat.

---

# 9. VERBINDLICHE DOKUMENTREIHENFOLGE

Die Dokumente werden exakt in dieser Reihenfolge erstellt:

## 1. Basic Idea

Definiert:

* Kernidee;
* zentrale Fantasy;
* Core Gameplay Loop;
* Zielgruppe;
* Plattform;
* Alleinstellungsmerkmale;
* gewünschte Spielzeit;
* gewünschtes Spielerlebnis;
* Scope-Rahmen.

## 2. Technical Decision

Definiert:

* Game Template;
* Engine-Architektur;
* Zielplattform;
* Bildschirmauflösung;
* interne Renderauflösung;
* Pixel Scaling;
* Koordinatensystem;
* Maßeinheiten;
* Framerate;
* Update Rate;
* Performance-Ziele;
* Speichergrenzen;
* Inputgeräte;
* Save-System;
* technische Einschränkungen.

## 3. Genre Perspective

Definiert:

* Genre;
* Subgenre;
* Kameraperspektive;
* Kameraverhalten;
* Bewegungsmodell;
* Interaktionsmodell;
* typische Genreerwartungen;
* Spielgeschwindigkeit;
* Koordinatenskalen;
* Sichtweiten;
* Interaktionsdistanzen.

## 4. Quest

Definiert:

* Questtypen;
* Ziele;
* Voraussetzungen;
* Zustände;
* Fortschritt;
* Scheitern;
* Wiederholung;
* Belohnungen;
* Abhängigkeiten;
* Quest Chains;
* Story-Verknüpfungen.

## 5. World

Definiert:

* Spielwelt;
* Regionen;
* Biome;
* Orte;
* Fraktionen;
* Zeitepoche;
* Umweltregeln;
* Navigation;
* Weltfortschritt;
* Levelverbindungen.

## 6. Story

Definiert:

* Haupthandlung;
* Konflikt;
* Figuren;
* Motivation;
* Dramaturgie;
* Wendepunkte;
* Story-Fortschritt;
* Dialoganforderungen;
* Enden.

## 7. Player

Definiert:

* Spielerfigur;
* Steuerung;
* Bewegung;
* Statuswerte;
* Ressourcen;
* Trefferpunkte;
* Schaden;
* Interaktionen;
* Zustände;
* Tod;
* Respawn;
* Fortschritt.

## 8. Abilities

Definiert:

* aktive Fähigkeiten;
* passive Fähigkeiten;
* Zauber;
* Kosten;
* Cooldowns;
* Reichweiten;
* Wirkungsflächen;
* Freischaltungen;
* Statusveränderungen;
* Kombinationen;
* visuelles Feedback;
* Audio-Feedback.

## 9. Enemies

Definiert:

* Gegnertypen;
* Zustände;
* Wahrnehmung;
* Navigation;
* Angriffe;
* Werte;
* Spawn-Regeln;
* Drops;
* Schwierigkeitsstufen;
* technische Grenzen.

## 10. Bosses

Definiert:

* Bosskonzept;
* Phasen;
* Angriffe;
* Telegraphing;
* Schwachstellen;
* Arena;
* Übergänge;
* Belohnungen;
* Scheitern;
* Wiederholung.

## 11. Items

Definiert:

* Gegenstandskategorien;
* Werte;
* Seltenheiten;
* Inventarregeln;
* Nutzung;
* Verbrauch;
* Ausrüstung;
* Loot;
* Fundorte;
* Crafting;
* Wirtschaft.

## 12. Level Structure

Definiert:

* Leveltypen;
* Räume;
* Tile Grid;
* Progression;
* Checkpoints;
* Übergänge;
* Spawnpunkte;
* Ausgänge;
* Geheimnisse;
* Skalierung;
* Navigationslogik;
* Erreichbarkeit.

## 13. Rules

Definiert:

* verbindliche Spielregeln;
* Siegbedingungen;
* Niederlagebedingungen;
* Ressourcensysteme;
* Systeminteraktionen;
* Kollisionsregeln;
* Schadensregeln;
* Pausenregeln;
* Save-Regeln;
* Restart-Regeln.

## 14. Look and Feel

Definiert:

* Atmosphäre;
* Farbwelt;
* visuelle Sprache;
* Stimmung;
* Kontraste;
* Beleuchtung;
* visuelle Hierarchie;
* Referenzprinzipien;
* gewünschtes Spielgefühl.

## 15. Pixel Art Direction

Definiert:

* interne Auflösung;
* Sprite-Größen;
* Tile-Größen;
* Farbpaletten;
* Outline-Regeln;
* Shading;
* Highlighting;
* Perspektive;
* Detailgrad;
* Transparenz;
* Layering;
* Exportformate;
* zulässige Farbanzahl.

## 16. Animation Direction

Definiert:

* Animationsstil;
* Actions;
* Frames pro Action;
* FPS;
* Timing;
* Loops;
* Übergänge;
* Lesbarkeit;
* Hit Frames;
* Hurt Frames;
* Events;
* benötigte Zustände.

## 17. Sound Direction

Definiert:

* Musikstil;
* Soundeffekte;
* Audiofeedback;
* räumliche Regeln;
* Lautstärkeverhältnisse;
* Zustandswechsel;
* Formate;
* Sample Rates;
* Loop-Anforderungen;
* Speichergrenzen.

## 18. UI Direction

Definiert:

* HUD;
* Menüs;
* Navigation;
* Informationshierarchie;
* Eingabemethoden;
* Controller-Navigation;
* Tastaturnavigation;
* visuelle Regeln;
* Feedback;
* Accessibility;
* sichere Flächen.

## 19. Production Plan

Definiert:

* Produktionsphasen;
* Meilensteine;
* Agentenzuständigkeiten;
* Prioritäten;
* benötigte Assets;
* benötigte Systeme;
* Parallelisierung;
* Blocker;
* Review Points;
* Build-Zeitpunkte.

## 20. Risks and Constraints

Definiert:

* Scope-Risiken;
* technische Risiken;
* Plattformgrenzen;
* Abhängigkeiten;
* Kostenrisiken;
* Performance-Risiken;
* Asset-Risiken;
* Voice-Risiken;
* Produktionsblocker;
* Fallback-Strategien.

## 21. Validation Rules

Definiert:

* automatische Prüfungen;
* Akzeptanzkriterien;
* Testfälle;
* Konsistenzregeln;
* Grenzwerte;
* Quality Gates;
* Build-Regeln;
* Export-Regeln;
* Security-Regeln;
* Regressionsregeln.

## 22. Export Target

Definiert:

* Zielplattform;
* Buildformat;
* Ordnerstruktur;
* Dateinamen;
* Auflösung;
* Inputgeräte;
* Browseranforderungen;
* Paketinhalt;
* Checksums;
* Manifest;
* Downloadformat;
* Releaseanforderungen.

---

# 10. DOKUMENTABHÄNGIGKEITEN

Jeder Abschnitt baut auf den vorherigen Abschnitten auf.

Der Coding Agent muss eine echte Dependency-Struktur implementieren.

Beispiele:

* Technical Decision hängt von Basic Idea ab.
* Genre Perspective hängt von Basic Idea und Technical Decision ab.
* Quest hängt unter anderem von Genre Perspective, World und Story ab.
* Player hängt von Technical Decision, Genre Perspective und Rules ab.
* Abilities hängen von Player, Rules und Technical Decision ab.
* Pixel Art Direction hängt von Technical Decision, Genre Perspective, World und Look and Feel ab.
* Animation Direction hängt von Player, Enemies, Bosses und Pixel Art Direction ab.
* Production Plan hängt von allen Content-, Gameplay- und Asset-Dokumenten ab.
* Validation Rules prüfen alle vorherigen Dokumente.
* Export Target muss mit Technical Decision, Production Plan und Validation Rules übereinstimmen.

Wird ein früheres Dokument geändert:

1. Änderung als neue Version speichern.
2. Diff berechnen.
3. betroffene Abhängigkeiten bestimmen.
4. abhängige Abschnitte auf `needs-revalidation` setzen.
5. Konfliktprüfung starten.
6. erforderliche Agentenreviews erzeugen.
7. betroffene Tasks und Assets markieren.
8. keine stille automatische Überschreibung durchführen.
9. Nutzer über Auswirkungen informieren.

---

# 11. DETAILSTUFEN DER GAME DOCS

Jedes Dokument wird von groben Entscheidungen zu produktionsfähigen Workflows ausgearbeitet.

## Stufe 1: High-Level Concept

* Vision;
* Ziel;
* gewünschtes Erlebnis;
* Grundannahmen.

## Stufe 2: System Groups

Aufteilung in zusammengehörige Bereiche:

* Gameplay;
* Player;
* Combat;
* World;
* Story;
* Quest;
* Items;
* Art;
* Animation;
* Audio;
* UI;
* Technik;
* Produktion;
* Qualität.

## Stufe 3: Detailed Specification

* konkrete Werte;
* Maßeinheiten;
* Zustände;
* Eingaben;
* Ausgaben;
* Grenzen;
* Abhängigkeiten;
* Sonderfälle.

## Stufe 4: Complete Workflows

Jeder relevante Workflow enthält:

* Auslöser;
* Startbedingung;
* beteiligte Systeme;
* Eingaben;
* Zustandsänderungen;
* Ausgaben;
* Fehlerfälle;
* Abbruchbedingungen;
* visuelles Feedback;
* Audiofeedback;
* benötigte Assets;
* Speicherung;
* Validierung;
* Testkriterien.

## Stufe 5: Production-Ready Specification

Die Spezifikation muss vollständig genug sein, damit Coder, Pixel Artist, Animator, World Designer, Quest Designer, Audio Designer und QA-Agent ohne weitere grundlegende Produktentscheidungen arbeiten können.

---

# 12A. OPENROUTER — DYNAMISCHE FREE-MODEL AGENT FABRIC

Alle ausführbaren BKG-Fachagenten müssen über den providerneutralen BKG Provider Router mit OpenRouter verbunden werden können.

Die OpenRouter Free-Models-Collection dient als primäre Quelle für kostenlose Modelle.

Die konkrete Modellliste darf nicht fest in den Quellcode kopiert werden, weil:

- Modelle hinzukommen;
- Modelle entfernt werden;
- Free-Status sich ändern kann;
- Limits sich ändern können;
- Provider ausfallen können;
- Kontextlängen sich ändern können;
- Tool-Unterstützung variieren kann.

## 12A.1 Provider-Architektur

Erstelle:

```text
packages/ai/
├── src/
│   ├── providers/
│   │   ├── provider.ts
│   │   ├── openrouter-provider.ts
│   │   └── provider-errors.ts
│   ├── catalog/
│   │   ├── model-catalog.ts
│   │   ├── model-sync.ts
│   │   ├── capability-normalizer.ts
│   │   └── model-health.ts
│   ├── routing/
│   │   ├── routing-policy.ts
│   │   ├── model-selector.ts
│   │   ├── fallback-chain.ts
│   │   ├── circuit-breaker.ts
│   │   └── budget-policy.ts
│   ├── execution/
│   │   ├── completion.ts
│   │   ├── streaming.ts
│   │   ├── structured-output.ts
│   │   ├── tool-loop.ts
│   │   └── output-repair.ts
│   └── safety/
│       ├── context-filter.ts
│       ├── secret-redaction.ts
│       ├── prompt-injection-check.ts
│       └── data-minimization.ts
```

## 12A.2 Model Catalog

Speichere mindestens:

- Provider;
- Model ID;
- Display Name;
- Beschreibung;
- Free-Status;
- Pricing Metadata;
- Kontextlänge;
- maximale Ausgabelänge;
- Eingabemodalitäten;
- Ausgabemodalitäten;
- Tool-Calling-Support;
- Structured-Output-Support;
- JSON-Support;
- Streaming-Support;
- Reasoning-Eignung;
- Coding-Eignung;
- Creative-Writing-Eignung;
- Long-Context-Eignung;
- bekannte Einschränkungen;
- Rate-Limit-Status;
- Health Score;
- durchschnittliche Latenz;
- Fehlerrate;
- letzte erfolgreiche Nutzung;
- letzte fehlgeschlagene Nutzung;
- Quarantäne-Status;
- Synchronisierungszeitpunkt;
- Rohmetadaten-Hash.

## 12A.3 Katalogsynchronisierung

Implementiere Jobs:

- openrouter-catalog-sync;
- openrouter-free-models-sync;
- openrouter-model-health-check;
- openrouter-capability-probe;
- openrouter-model-quarantine-review.

Synchronisierung muss:

1. aktuelle Daten abrufen;
2. Antworten validieren;
3. Free-Status normalisieren;
4. Fähigkeiten normalisieren;
5. entfernte Modelle deaktivieren;
6. keine historischen Nutzungsdaten löschen;
7. Änderungen protokollieren;
8. Routing Cache invalidieren;
9. Admin-Warnungen erzeugen.

## 12A.4 Agent Capability Profiles

Jeder Agent erhält kein festes Modell, sondern ein Capability Profile.

Profile:

```text
reasoning-heavy
coding
creative-writing
structured-json
fast-review
long-context
tool-use
low-latency
multilingual
fallback-general
```

Beispiel:

```ts
type AgentModelRequirements = {
  requiredCapabilities: ModelCapability[];
  preferredCapabilities: ModelCapability[];
  minimumContextTokens: number;
  requiresStructuredOutput: boolean;
  requiresToolCalling: boolean;
  allowsStreaming: boolean;
  freeOnly: boolean;
  maxEstimatedCostUsd?: number;
  preferredLatencyClass?: "low" | "normal" | "high";
};
```

## 12A.5 Routing Algorithmus

Der Router berücksichtigt:

1. Agentenanforderungen;
2. Free-Status;
3. Nutzer- und Projektpolicy;
4. Modellverfügbarkeit;
5. Health Score;
6. Kontextlänge;
7. Tool Support;
8. Structured Output;
9. aktuelle Rate Limits;
10. Fehlerrate;
11. Latenz;
12. Budget;
13. Datenschutz;
14. Modellquarantäne;
15. bisherige Qualität für dieselbe Taskklasse.

Speichere die Auswahlentscheidung mit Begründung.

## 12A.6 Fallback-Kette

Verbindlicher Ablauf:

```text
Primary Eligible Free Model
→ Secondary Eligible Free Model
→ General Free Fallback Model
→ User-Configured Paid Model, nur bei Freigabe
→ Pause Task
→ Request User Action
```

Ein Paid Model darf nur genutzt werden, wenn:

- Nutzer es konfiguriert hat;
- Secret vorhanden ist;
- Budget vorhanden ist;
- Projektpolicy es erlaubt;
- Agentenpolicy es erlaubt;
- vorherige Free-Fallbacks fehlgeschlagen sind oder ungeeignet waren;
- Cost Estimate vorliegt.

## 12A.7 OpenRouter Request Handling

Jeder Request benötigt:

- Request ID;
- User ID, intern;
- Project ID;
- Agent ID;
- Task ID;
- Prompt Version;
- Model ID;
- Routing Decision ID;
- Timeout;
- Retry Policy;
- Max Tokens;
- Temperature Policy;
- Schema, falls strukturiert;
- Redaction;
- Cost Limit;
- Audit Event.

OpenRouter-spezifische App-Identifikationsheader werden zentral konfiguriert.

Keine Provider-Secrets im Browser.

## 12A.8 Rate Limits und Ausfälle

Implementiere:

- HTTP-Status-Normalisierung;
- `Retry-After`;
- Exponential Backoff;
- Jitter;
- Max Attempts;
- Circuit Breaker;
- Model Circuit Breaker;
- Provider Circuit Breaker;
- Quarantäne;
- Health Recovery;
- Timeout;
- Abort Signal;
- teilweise Streaming-Ergebnisse;
- sichere Wiederaufnahme;
- Idempotency.

## 12A.9 Structured Output

Für strukturierte Agentenausgaben:

1. Schema aus Prompt Registry laden.
2. Provider Request erstellen.
3. Rohantwort speichern, redigiert.
4. JSON extrahieren.
5. Zod validieren.
6. bei Fehler kontrollierte Reparatur versuchen.
7. maximal erlaubte Reparaturversuche beachten.
8. bei weiterem Fehler anderes Modell versuchen.
9. niemals ungültige Struktur als Erfolg speichern.

## 12A.10 Tool Calls

Tool Calls benötigen:

- Tool Registry;
- Tool Permission;
- Argument Schema;
- Output Schema;
- Timeout;
- Audit;
- Secret Filter;
- Rate Limit;
- User- und Project-Kontext;
- Approval bei riskanten Tools.

Ein Modell darf keine unbekannten Tools frei erfinden und ausführen.

## 12A.11 Datenminimierung

Vor jedem Modellaufruf:

- Secrets entfernen;
- Tokens entfernen;
- unnötige personenbezogene Daten entfernen;
- fremde Projektdaten entfernen;
- Kontext auf erforderliche Abschnitte begrenzen;
- RAG-Quellen begrenzen;
- Uploads nach Berechtigung filtern;
- Prompt-Injection-Risiken markieren;
- sensible Daten klassifizieren.

## 12A.12 OpenRouter Datenbank

Erweitere mindestens um:

- model-catalog-entries;
- model-catalog-sync-runs;
- model-capability-probes;
- model-health-checks;
- model-routing-policies;
- model-routing-decisions;
- model-fallback-attempts;
- model-circuit-breakers;
- model-quarantines;
- agent-model-profiles;
- model-quality-scores;
- model-rate-limit-events;
- provider-request-records;
- provider-response-records;
- provider-usage-records;
- provider-cost-records.

## 12A.13 Agentenzuordnung

Mindestens folgende Agenten werden über OpenRouter ausführbar:

- CreativeDirectorAgent;
- TechnicalDirectorAgent;
- ProducerAgent;
- GameDesignerAgent;
- QuestDesignerAgent;
- DialogueAgent;
- StoryDesignerAgent;
- WorldDesignerAgent;
- ItemSystemsEngineerAgent;
- AbilitiesAndSpellsEngineerAgent;
- AssetPlannerAgent;
- ArtDirectorAgent;
- PixelPainterAgent;
- SpriteAnimatorAgent;
- TilesetArtistAgent;
- BackgroundArtistAgent;
- UIArtistAgent;
- MusicArtistAgent;
- SoundFXAgent;
- LevelDesignerAgent;
- ValidatorAgent;
- QAAgent;
- PlaytestAgent;
- BugTriageAgent;
- RepairAgent;
- ExportAgent;
- ReleaseManagerAgent;
- CoverDesignAgent;
- MarketingAgent;
- StorePageAgent;
- SocialMediaPosterAgent;
- TrailerScriptAgent;
- PressKitAgent;
- CommunityReplyAgent.

Der CodeBuilderAgent kann fachliche Planung über OpenRouter verwenden, seine eigentliche kontrollierte Repository-Arbeit wird jedoch über die Kilo-Code-Runtime und deren Berechtigungsmodell ausgeführt.

## 12A.14 OpenRouter UI

Settings:

- OpenRouter aktivieren;
- API-Key speichern;
- Verbindung testen;
- Free-Only-Modus;
- Paid-Fallback erlauben;
- Budget;
- bevorzugte Modelle;
- blockierte Modelle;
- Agentenprofile;
- Routing Logs;
- Health;
- Quarantäne;
- Usage;
- Kosten.

Admin:

- Katalogsynchronisierung;
- Modellstatus;
- Capability Matrix;
- Routing Decisions;
- Fehler;
- Rate Limits;
- Circuit Breaker;
- Quarantäne;
- Kosten;
- Agentenqualität.

## 12A.15 OpenRouter Tests

Unit Tests:

- Capability Matching;
- Free-Only-Filter;
- Routing Score;
- Fallback-Reihenfolge;
- Budgetprüfung;
- Quarantäne;
- Circuit Breaker;
- Schema-Reparatur;
- Datenminimierung.

Integration Tests:

- Katalog synchronisieren;
- Modell auswählen;
- Free-Modell aufrufen;
- Streaming;
- Structured Output;
- Tool Call;
- Rate Limit;
- Timeout;
- Fallback;
- Paid-Modell blockieren;
- Usage speichern.

E2E-Test:

1. Nutzer speichert OpenRouter-Key.
2. Provider Test besteht.
3. Free-Model-Katalog wird synchronisiert.
4. Agent erhält Capability Profile.
5. Router wählt geeignetes Free Model.
6. Primärmodell schlägt kontrolliert fehl.
7. Fallback wird gewählt.
8. strukturierte Ausgabe wird validiert.
9. Routing Decision und Usage sind sichtbar.
10. keine Secrets erscheinen im Client oder Log.


---

# 12. GAME-DOCS-EDITOR

Route:

```text
/game-docs/[game-docs-id]
```

Implementiere:

* Seitennavigation für alle 22 Abschnitte;
* Fortschrittsanzeige;
* Statusanzeige;
* Dependency-Anzeige;
* Rich-Text- oder strukturierten Dokumenteditor;
* strukturierte Felder für messbare Werte;
* Autosave;
* Versionierung;
* Diff;
* Wiederherstellung alter Versionen;
* AI Draft;
* AI Improve;
* Check Consistency;
* Submit for Review;
* Approve;
* Lock;
* Unlock;
* Conflict Handling;
* Audit Trail;
* Live Sync;
* Presence-Information;
* Validierung;
* Kommentare;
* Änderungsanforderungen;
* dokumentübergreifende Referenzen.

Aktionen:

```text
Generate AI Draft
Improve with AI
Check Consistency
Save Changes
Submit for Review
Approve
Lock Document
Unlock Document
View Dependencies
View Diff
Open Discussion
```

Ein nachfolgendes Dokument darf erst geöffnet werden, wenn die definierte Mindestvoraussetzung erfüllt ist.

Die Produktionspipeline bleibt gesperrt, bis alle 22 Dokumente `locked` sind.

---

# 13. LIVE SYNC UND AUDIT MONITOR

Implementiere eine echte Live-Synchronisation.

Beispielereignisse:

```text
game-doc-section-opened
game-doc-section-saved
game-doc-version-created
game-doc-validation-started
game-doc-validation-completed
game-doc-conflict-detected
game-doc-approved
game-doc-locked
game-doc-unlocked
dependent-doc-invalidated
discussion-started
agent-joined-discussion
agent-spoke
agent-voted
consensus-updated
director-decision-created
user-change-requested
```

Die UI zeigt:

* aktiven Abschnitt;
* verbundenen Agenten;
* letzte Speicherung;
* Synchronisationszustand;
* Konflikte;
* Validierungsfortschritt;
* Audit-Ereignisse;
* Reconnect-Status.

Keine statischen Konsolentexte als Ersatz für echte Events.

---

# 14. AUTOMATISCHE GAME-DOCS-VALIDIERUNG

Die automatische Prüfung umfasst mindestens:

* Vollständigkeit aller Pflichtfelder;
* Widerspruchsfreiheit;
* definierte Maßeinheiten;
* definierte Geschwindigkeiten;
* definierte Zeitwerte;
* definierte Größen;
* definierte Interaktionsdistanzen;
* definierte Wertebereiche;
* technische Umsetzbarkeit;
* Performance-Grenzen;
* Plattformkompatibilität;
* einheitliche Begriffe;
* referenzierte Abhängigkeiten;
* markierte Annahmen;
* markierte Platzhalter;
* AABB-Konsistenz;
* Kollisionskonsistenz;
* Quest-Erreichbarkeit;
* Level-Erreichbarkeit;
* Asset-Umsetzbarkeit;
* Animationsumsetzbarkeit;
* Audioformat-Kompatibilität;
* UI-Umsetzbarkeit;
* automatisierbare Testbarkeit;
* Exportkompatibilität;
* fehlende Fehlerfälle;
* fehlende Zustände;
* unauflösbare Produktionsabhängigkeiten.

Validierungsergebnisse müssen mit Severity gespeichert werden:

```text
info
warning
error
blocking
```

---

# 15. LIVE-TTS-AGENTENDISKUSSION

Nachdem alle 22 Dokumente einen vollständigen Entwurf besitzen, startet eine moderierte Live-Diskussion.

Route:

```text
/game-docs/[game-docs-id]/discussion
```

Die Diskussion muss gleichzeitig als:

* serverseitig gespeicherter Diskussionslauf;
* Agenten-Eventstream;
* sichtbares Live-Transkript;
* hörbare TTS-Ausgabe;
* strukturierter Review-Prozess;
* Abstimmungsprozess;
* Änderungsworkflow

implementiert werden.

Jeder Agent besitzt:

* eine eindeutige Agentenrolle;
* eine konfigurierbare Stimme;
* Fachzuständigkeiten;
* Prioritätsgewichtungen;
* Zugriff auf relevante Game Docs;
* Zugriff auf relevante RAG-Kontexte;
* gespeicherte Aussagen;
* gespeicherte Einwände;
* gespeicherte Empfehlungen;
* gespeicherte Stimmen;
* Kosten- und Tokenprotokollierung.

---

# 16. AGENTEN DER DOKUMENTDISKUSSION

Implementiere mindestens folgende ausführbare Agentenrollen.

## CreativeDirectorAgent

Leitet die Diskussion.

Aufgaben:

* eröffnet Reviews;
* fasst Dokumente zusammen;
* bestimmt zuständige Agenten;
* stellt Fragen;
* moderiert Konflikte;
* verhindert Endlosschleifen;
* priorisiert Entscheidungen;
* startet Abstimmungen;
* überwacht Konsens;
* entscheidet offene Minderheitsfragen;
* erstellt die finale Zusammenfassung;
* fordert Nutzerbestätigung an.

## TechnicalDirectorAgent

Prüft:

* Systemarchitektur;
* technische Grenzen;
* Performance;
* Rendering;
* Input;
* Speicherung;
* Export;
* Buildbarkeit;
* Plattformkompatibilität.

## GameDesignerAgent

Prüft:

* Core Loop;
* Regeln;
* Progression;
* Balancing;
* Motivation;
* Schwierigkeitskurve;
* Systeminteraktionen.

## CodeBuilderAgent

Prüft:

* Implementierbarkeit;
* Datenmodelle;
* Zustandsmaschinen;
* Schnittstellen;
* Testbarkeit;
* Performance;
* Build-Risiken;
* technische Abhängigkeiten.

## ArtDirectorAgent

Prüft:

* Stil;
* Formen;
* Farben;
* Silhouetten;
* Perspektive;
* visuelle Konsistenz;
* Concept-Art-Anforderungen.

## PixelPainterAgent

Prüft:

* Sprite-Größen;
* Tile-Größen;
* Farbpaletten;
* Pixel-Lesbarkeit;
* Shading;
* Produktionsaufwand;
* technische Pixelgrenzen.

## SpriteAnimatorAgent

Prüft:

* Animationszustände;
* Frames;
* FPS;
* Übergänge;
* Hit Frames;
* Timing;
* Sprite-Sheet-Aufwand.

## StoryDesignerAgent

Prüft:

* Handlung;
* Figuren;
* Konflikte;
* Dramaturgie;
* Story-Konsistenz;
* Gameplay-Verknüpfung.

## QuestDesignerAgent

Prüft:

* Questzustände;
* Abhängigkeiten;
* Belohnungen;
* Story-Verknüpfungen;
* Scheitern;
* Wiederholung;
* Testbarkeit.

## WorldDesignerAgent

Prüft:

* Regionen;
* Biome;
* Orte;
* Navigation;
* Levelverbindungen;
* Fraktionen;
* Weltlogik.

## ItemSystemsEngineerAgent

Prüft:

* Items;
* Loot;
* Inventar;
* Seltenheit;
* Wirtschaft;
* Crafting;
* Balancing.

## AbilitiesAndSpellsEngineerAgent

Prüft:

* Fähigkeiten;
* Zauber;
* Kosten;
* Cooldowns;
* Effekte;
* Trefferlogik;
* Kombinationen;
* technische Umsetzbarkeit.

## LevelDesignerAgent

Prüft:

* Levelstruktur;
* Spawnpunkte;
* Ausgänge;
* Erreichbarkeit;
* Kollisionsflächen;
* Navigation;
* Schwierigkeitsverlauf.

## AudioDesignerAgent

Prüft:

* Musik;
* Soundeffekte;
* Zustandswechsel;
* Audiofeedback;
* Dateiformate;
* Speicherbedarf.

## UIUXDesignerAgent

Prüft:

* HUD;
* Menüs;
* Navigation;
* Lesbarkeit;
* Eingabe;
* Accessibility;
* Informationshierarchie.

## ProducerAgent

Prüft:

* Scope;
* Reihenfolge;
* Meilensteine;
* Ressourcen;
* Parallelisierung;
* Blocker;
* Kosten.

## ValidatorAgent

Prüft:

* Vollständigkeit;
* Widersprüche;
* undefinierte Zustände;
* fehlende Werte;
* fehlende Tests;
* Quality Gates.

## QAAgent

Prüft:

* Testbarkeit;
* Regression;
* Grenzfälle;
* Fehlerzustände;
* Acceptance Criteria.

---

# 17. DISKUSSIONSABLAUF

Für jedes Dokument wird folgender Ablauf ausgeführt:

1. Creative Director lädt den aktuellen Dokument-Snapshot.
2. Er fasst den Abschnitt zusammen.
3. Er nennt relevante Abhängigkeiten.
4. Er wählt die fachlich zuständigen Agenten aus.
5. Jeder Agent analysiert den Abschnitt.
6. Jeder Agent nennt:

   * Zustimmung;
   * Einwände;
   * Risiken;
   * fehlende Werte;
   * konkrete Änderungsvorschläge.
7. Agenten dürfen sich gegenseitig befragen.
8. Konflikte werden als strukturierte Discussion Issues gespeichert.
9. Änderungsvorschläge werden als Document Change Proposals gespeichert.
10. Betroffene Dokumente werden als Draft-Version aktualisiert.
11. Validator und QA prüfen die neue Version.
12. Die zuständigen Agenten stimmen ab.
13. Der gewichtete Konsens wird berechnet.
14. Bei weniger als 70 Prozent wird weiterdiskutiert.
15. Bei mindestens 70 Prozent beendet der Creative Director die Fachrunde.
16. Offene Minderheitsfragen werden vom Creative Director entschieden.
17. Die Entscheidung wird begründet und gespeichert.
18. Der Nutzer erhält eine finale Zusammenfassung.
19. Der Nutzer kann bestätigen oder Änderungen verlangen.

Die Diskussion darf nicht allein aufgrund einer Nachrichtenanzahl enden.

Sie endet erst, wenn:

* mindestens 70 Prozent gewichtete Zustimmung erreicht sind;
* keine blockierenden Validation Findings offen sind;
* der Creative Director verbleibende Konflikte entschieden hat;
* eine verständliche Nutzerzusammenfassung existiert.

---

# 18. GEWICHTETES KONSENSMODELL

Mögliche Stimmen:

```text
approve
approve-with-reservations
reject
abstain
```

Empfohlene Basisscores:

```text
approve = 1.0
approve-with-reservations = 0.65
reject = 0.0
abstain = aus der Berechnung entfernen
```

Jeder Agent besitzt je Dokument und Entscheidung ein Zuständigkeitsgewicht.

Beispiel:

Bei Sprite-Größen erhalten:

* Art Director;
* Pixel Painter;
* Animator;
* Technical Director;
* Code Builder

höhere Gewichte als Story- oder Quest-Agenten.

Konsensformel:

```text
gewichtete Zustimmung
=
Summe(Stimmwert × Zuständigkeitsgewicht)
/
Summe(aktiver Zuständigkeitsgewichte)
```

Der Mindestwert beträgt:

```text
0.70
```

Der Wert muss aus gespeicherten Einzelstimmen berechnet werden.

Er darf nicht vom UI erfunden oder hartcodiert werden.

---

# 19. ENTSCHEIDUNG DER VERBLEIBENDEN 30 PROZENT

Erreicht die Diskussion mindestens 70 Prozent Zustimmung, darf der Creative Director verbleibende Konflikte entscheiden.

Dabei muss er dokumentieren:

* offene Gegenargumente;
* betroffene Agenten;
* Risiken;
* Alternativen;
* Entscheidung;
* Begründung;
* Auswirkungen;
* zusätzliche Validation Rules;
* mögliche spätere Change Requests.

Prioritäten:

1. ausdrückliche Nutzeranforderungen;
2. technische Umsetzbarkeit;
3. Kernvision;
4. Gameplay-Konsistenz;
5. kontrollierbarer Scope;
6. Produktionsaufwand;
7. Performance;
8. visuelle und akustische Qualität;
9. Erweiterbarkeit.

Der Creative Director darf Nutzeranforderungen nicht still überschreiben.

---

# 20. NUTZERBETEILIGUNG AN DER DISKUSSION

Der Nutzer kann während der Voice-Diskussion:

* Textnachrichten senden;
* Voice-Eingaben senden;
* Agenten direkt ansprechen;
* Anforderungen ändern;
* Entscheidungen ablehnen;
* Alternativen fordern;
* Dokumente erneut öffnen;
* Diskussion pausieren;
* Diskussion fortsetzen;
* einzelne Punkte bestätigen;
* eine neue Abstimmung verlangen.

Voice-Eingaben werden über Speech-to-Text verarbeitet.

Nutzeränderungen werden als Change Requests gespeichert.

Der Creative Director muss die Änderung an alle betroffenen Fachagenten weiterleiten.

Beispiel:

```text
Der Spieler darf keinen Doppelsprung besitzen.
```

Mindestens folgende Agenten müssen die Auswirkungen prüfen:

* Game Designer;
* Code Builder;
* Animator;
* Level Designer;
* World Designer;
* Validator;
* QA.

---

# 21. TTS- UND VOICE-SYSTEM

Implementiere:

* konfigurierbare Stimmen pro Agent;
* Voice Provider Abstraction;
* TTS Jobs;
* STT Jobs;
* Audio Job Status;
* Audio Streaming oder segmentiertes Playback;
* Unterbrechung;
* Pause;
* Fortsetzung;
* Lautstärkeregelung;
* Geschwindigkeit;
* Texttranskript;
* Sprecheranzeige;
* Audio-Caching;
* Object Storage;
* Berechtigungen;
* Kostenprotokollierung;
* Fehlerbehandlung;
* Fallback auf Textausgabe.

TTS darf die Diskussion nicht blockieren.

Die semantische Agentenentscheidung wird zuerst gespeichert.

Die Audioausgabe wird daraus asynchron erzeugt.

Scheitert TTS, bleibt das Texttranskript vollständig nutzbar.

---

# 22. ABSCHLUSS DER DOKUMENTPHASE

Der Creative Director erstellt eine Abschlusszusammenfassung mit:

* finaler Spielvision;
* Core Gameplay Loop;
* technischen Entscheidungen;
* Welt;
* Story;
* Quests;
* Player-System;
* Fähigkeiten;
* Gegnern;
* Bossen;
* Items;
* Levelstruktur;
* Regeln;
* Art Direction;
* Pixel-Art-Richtung;
* Animationsrichtung;
* Sound-Richtung;
* UI-Richtung;
* Produktionsplan;
* Risiken;
* Quality Gates;
* Exportziel;
* erzieltem Konsenswert;
* verbleibenden Minderheitspositionen;
* Director-Entscheidungen;
* offenen optionalen Erweiterungen.

Danach erscheint:

# GAME SPECIFICATION BESTÄTIGEN UND PRODUCTION STUDIO ÖFFNEN

Mögliche Aktionen:

```text
Confirm and Lock All Docs
Request Changes
Reopen Specific Document
Restart Discussion
Cancel Project
```

Der Bestätigungsprozess muss atomar und idempotent sein.

Doppelte Bestätigung darf keine doppelten Pipeline Runs oder Tasks erzeugen.

---

# 23. CONFIRM-DOCS-FLOW

Der Confirm-Flow führt serverseitig aus:

1. alle 22 Pflichtabschnitte laden;
2. Status prüfen;
3. Dokumentabhängigkeiten prüfen;
4. Konflikte prüfen;
5. letzte Validation Runs prüfen;
6. Konsensnachweise prüfen;
7. Nutzerberechtigung prüfen;
8. finalen Version Snapshot erzeugen;
9. alle Dokumente atomar auf `locked` setzen;
10. Game Specification Version erzeugen;
11. erforderliche Systeme ableiten;
12. erforderliche Assets ableiten;
13. erforderliche Workflows ableiten;
14. Produktionsplan erzeugen;
15. Production Tasks erzeugen;
16. Task Dependencies erzeugen;
17. Quality Gates erzeugen;
18. Agenten zuweisen;
19. Pipeline Run erzeugen;
20. Audit Event schreiben;
21. Production Studio freischalten.

---

# 24. PRODUCTION STUDIO

Nach erfolgreicher Bestätigung öffnet sich:

```text
/production/[project-id]
```

Das Production Studio zeigt:

* Gesamtfortschritt;
* Produktionsphasen;
* Agenten;
* Workstations;
* aktive Tasks;
* blockierte Tasks;
* Abhängigkeiten;
* Live Events;
* offene Reviews;
* Quality Gates;
* Kosten;
* Builds;
* Fehler;
* Repair-Aktivitäten.

Arbeitsbereiche:

* Code Studio;
* Concept Art Studio;
* Pixel Art Studio;
* Animation Studio;
* World and Level Studio;
* Quest Studio;
* Audio Studio;
* UI Studio;
* Testing Studio;
* Build and Export Studio.

---

# 25. PARALLELE PRODUKTION

Nach dem Docs Lock dürfen geeignete Aufgaben parallel laufen.

Beispiel:

* Coder erstellt Architektur und Runtime.
* Art Director erstellt Concept-Art-Vorgaben.
* Image Agent erzeugt Concept Arts.
* Pixel Artist überträgt bestätigte Concepts in Pixel Art.
* Animator animiert fertige Sprites.
* World Designer plant Welt und Level.
* Level Designer arbeitet zunächst mit Platzhaltern.
* Quest Designer implementiert Quest-Flows.
* Audio Designer erzeugt Audio-Pläne und Assets.
* UI Designer erstellt HUD und Menüs.
* QA testet fortlaufend.
* Repair Agent behandelt Fehler.

Der Orchestrator muss Abhängigkeiten beachten.

Ein Agent darf nicht mit finalen Inputs arbeiten, wenn die Grundlage nicht bestätigt ist.

Explizit markierte Platzhalter sind erlaubt, wenn:

* sie als Placeholder Asset gespeichert sind;
* ihre spätere Ersetzung geplant ist;
* kein finaler Gate-Status davon abhängt;
* ihre Nutzung im Audit sichtbar ist.

---

# 26. CODE STUDIO UND CODEBUILDERAGENT

Der CodeBuilderAgent startet direkt nach Produktionsfreigabe und arbeitet bis zum Ende des Projekts.

Route:

```text
/code/[code-session-id]
```

Der Nutzer sieht live:

* aktuelle Datei;
* geplante Dateiänderungen;
* Code-Diffs;
* ausgeführte Tools;
* Tests;
* Typecheck;
* Buildstatus;
* Fehler;
* Reparaturen;
* Dokumentreferenzen;
* Taskreferenzen;
* Quality-Gate-Referenzen.

Implementiere:

* Code Sessions;
* Context;
* Context Summaries;
* Tool Registry;
* Tool Permissions;
* Permission Requests;
* File Change Plans;
* Patches;
* Patch Files;
* Diff;
* Validation;
* Cost Tracking;
* Audit Logs;
* Repair Integration;
* Structure Gate.

Erlaubte Tools:

```text
read-file
list-files
search-files
write-file-plan
create-file
edit-file
delete-file-plan
move-file-plan
generate-code
apply-patch
show-diff
validate-code
run-tests
run-typecheck
run-next-build
run-job-build
run-preview-check
validate-manifest
validate-export-package
create-repair-task
log-agent-event
```

Regeln:

* Lesezugriff nur in erlaubten Bereichen.
* Schreibzugriff nur für den zugewiesenen Task.
* Löschen und Verschieben nur über einen Plan.
* riskante Patches benötigen Approval.
* keine Secret-Dateien lesen.
* keine unkontrollierten Commands.
* keine Deployments ohne Release Approval.
* jede Änderung wird validiert.
* jede Änderung erhält eine Verbindung zu Game Docs, Task und Tests.

Der Coder arbeitet bis zuletzt und integriert fortlaufend:

* Game Engine;
* Player;
* Abilities;
* Enemies;
* Bosses;
* Items;
* Quests;
* Levels;
* Animationen;
* Audio;
* UI;
* Save-System;
* Tests;
* Optimierungen;
* Builds;
* Exporte.

---

# 26A. KILO CODE — VERBINDLICHE CODING-AGENT-RUNTIME UND FREE-MODEL-ROUTER

Der CodeBuilderAgent muss auf `https://github.com/kilo-org/kilocode` als kontrollierter Coding-Runtime aufbauen.

Kilo Code ist die primäre agentische Coding-Oberfläche für:

- Repository-Analyse;
- Architekturplanung;
- Codeänderungen;
- Terminalbefehle;
- Browserautomation;
- Tests;
- Debugging;
- Reviews;
- Reparaturen;
- Worktree-basierte Parallelisierung;
- Modellwahl;
- Modellrouting;
- Provider-Fallbacks.

Kilo Code wird als CLI und, sofern für den Betreiber sinnvoll, zusätzlich als VS-Code-Extension unterstützt.

Kilo Code ist nicht:

- die Produktdatenbank;
- der Pipeline-Orchestrator;
- die alleinige Berechtigungsquelle;
- der Release Manager;
- die Source of Truth für Tasks;
- die Source of Truth für Builds;
- berechtigt, ohne Approval zu deployen;
- berechtigt, Quality Gates zu umgehen.

## 26A.1 Offizielle Quelle und Versionsprüfung

Verbindliche Quelle:

```text
https://github.com/kilo-org/kilocode
```

Vor Implementierung:

1. aktuelle README lesen;
2. `AGENTS.md` lesen;
3. Paketstruktur untersuchen;
4. CLI-Installationsweg prüfen;
5. Extension-Installationsweg prüfen;
6. Kilo-Gateway- und Providerkonfiguration prüfen;
7. aktuelle Regeln-, Modes-, Skills-, Workflows- und MCP-Unterstützung prüfen;
8. bekannte Versionsprobleme prüfen;
9. getestete Version oder Commit SHA pinnen;
10. Release Evidence erstellen.

Kilo Code entwickelt sich aktiv weiter. Der Coding Agent darf keine Syntax oder Dateistruktur aus Erinnerung erfinden.

## 26A.2 Reproduzierbare Installation

Erstelle:

```text
tools/kilocode/
├── install.mjs
├── verify.mjs
├── health-check.mjs
├── version.json
├── config.template.json
├── providers.template.json
├── modes.template.yaml
├── security-policy.md
├── upgrade.md
├── rollback.md
└── readme.md
```

Pflicht:

- getestete Version oder Commit pinnen;
- Lockfile oder Toolchain-Manifest;
- reproduzierbare Installation;
- Health Check;
- CLI-Binary-Prüfung;
- Extension-Kompatibilitätsprüfung;
- Update Check;
- Rollback;
- Lizenznachweis;
- Security Review;
- Release Evidence.

Eine unversionierte globale Installation ist nicht ausreichend.

## 26A.3 Betriebsformen

Unterstütze:

- Kilo CLI im isolierten Worker;
- Kilo Code VS-Code-Extension für lokale Entwickler;
- Headless Task Mode;
- Read-Only Architect Mode;
- Code Mode;
- Debug Mode;
- Test Mode;
- Review Mode;
- Security Mode;
- Documentation Mode;
- Repair Mode;
- Release-Audit Mode;
- Worktree Agent Mode.

Jeder Modus erhält eigene Tool-, Datei- und Command-Berechtigungen.

## 26A.4 Kilo Gateway und integrierter Modellrouter

Kilo Code bietet Zugriff auf einen großen Modellkatalog über Kilo Gateway und konfigurierbare Provider.

BKG nutzt diesen Router primär für den CodeBuilderAgent.

Die Anwendung darf trotzdem keinen konkreten Modellbestand hartcodieren.

Implementiere einen `KiloModelCatalogAdapter`, der mindestens normalisiert:

- Model ID;
- Anzeigename;
- Provider;
- Gateway-Verfügbarkeit;
- Free- oder Promotional-Status, soweit zuverlässig gemeldet;
- Preis;
- Kontextlänge;
- Tool Calling;
- Coding-Eignung;
- Reasoning-Eignung;
- Bildverständnis;
- Streaming;
- Health;
- Latenz;
- Fehlerrate;
- Rate-Limit-Status;
- letzter erfolgreicher Aufruf.

## 26A.5 Free-Model-Routing

Der CodeBuilderAgent soll, soweit aktuell verfügbar und qualitativ geeignet, kostenlose Modelle bevorzugen.

Routing:

```text
Eligible Kilo Free Model
→ Secondary Kilo Free Model
→ Kilo Gateway Standard Model innerhalb Budget
→ eigener OpenRouter Free-Model-Fallback
→ lokaler Provider, falls konfiguriert
→ Pause und User Action
```

Wichtig:

- Free-Status dynamisch prüfen;
- keine Modellnamen fest codieren;
- Qualität vor Taskausführung bewerten;
- Rate Limits erkennen;
- Modellquarantäne;
- Circuit Breaker;
- Budgetgrenzen;
- Nutzerpolicy;
- Projektpolicy;
- Task-Komplexität;
- Kontextbedarf;
- Tool-Anforderungen.

Ein kostenpflichtiges Modell darf nur genutzt werden, wenn Nutzer- oder Adminpolicy es erlaubt.

## 26A.6 Trennung von Kilo Router und OpenRouter

BKG besitzt zwei providerneutrale Ebenen:

```text
Fachliche Game-Agenten
→ BKG Provider Router
→ OpenRouter Free Models / weitere konfigurierte Provider

Repository- und Coding-Arbeit
→ CodeBuilderAgent
→ Kilo Code
→ Kilo Gateway / Kilo Provider Router
→ optional OpenRouter als Kilo-Provider oder BKG-Fallback
```

Doppelte Abrechnung, doppelte Retries und unklare Fallback-Loops müssen verhindert werden.

Jeder Request erhält genau eine Routing Decision ID.

## 26A.7 Projektkontext mit AGENTS.md

Erstelle im Repository-Root eine verbindliche `AGENTS.md`.

Sie enthält:

- Produktziel;
- Architektur;
- Monorepo-Struktur;
- Source-of-Truth-Regeln;
- No-MVP-Regel;
- Verbot von Scheinimplementierungen;
- Coding Standards;
- TypeScript Strict Mode;
- Next.js-Regeln;
- Server-/Client-Grenzen;
- Prisma- und Migrationsregeln;
- Auth- und Cross-Tenant-Regeln;
- Secret-Regeln;
- Tool-Berechtigungen;
- Command-Allowlist;
- verbotene Pfade;
- Patch-Workflow;
- Testpflichten;
- Buildpflichten;
- Release Gates;
- Evidence-Pflicht;
- Verbot erfundener Ergebnisse;
- Eskalationsregeln.

Zusätzliche Kontexte:

```text
apps/web/AGENTS.md
apps/jobs/AGENTS.md
packages/database/AGENTS.md
packages/game-engine/AGENTS.md
packages/pixel-engine/AGENTS.md
packages/animation-engine/AGENTS.md
packages/level-engine/AGENTS.md
packages/ai/AGENTS.md
```

Untergeordnete Regeln dürfen den Root-Regeln nicht widersprechen.

## 26A.8 Kilo Rules

Erstelle projektbezogene Regeln:

```text
.kilocode/
├── rules/
│   ├── architecture.md
│   ├── security.md
│   ├── testing.md
│   ├── database.md
│   ├── releases.md
│   ├── evidence.md
│   └── no-fake-results.md
├── workflows/
├── skills/
├── modes/
└── mcp.json
```

Da sich unterstützte Ordner und Formate je Version ändern können, muss die konkrete Struktur gegen die gepinnte Kilo-Version getestet werden.

Regeln benötigen:

- Version;
- Scope;
- betroffene Pfade;
- Priorität;
- Konfliktregel;
- Test;
- Owner;
- Änderungsverlauf.

## 26A.9 Custom Modes

Erstelle mindestens:

### Architect Mode

- read;
- search;
- planning;
- keine Writes;
- keine Commands mit Side Effects.

### Code Mode

- begrenzte Writes;
- Patch-System;
- erlaubte Build- und Testcommands;
- kein Deployment.

### Debug Mode

- Logs;
- reproduzierbare Fehler;
- begrenzte Patches;
- keine Feature-Erweiterungen ohne Task.

### Test Engineer Mode

- Tests lesen und schreiben;
- Produktcode nur bei genehmigtem Repair Task;
- Coverage und Regression.

### Security Reviewer Mode

- read-only;
- Scans;
- Findings;
- keine automatischen riskanten Fixes.

### Database Migration Mode

- Prisma;
- Migration Plan;
- Drift Check;
- keine Production-Migration ohne Approval.

### Release Manager Mode

- Evidence;
- Gates;
- Builds;
- keine Produktänderungen außer Release-Metadaten.

### Documentation Mode

- nur Dokumentationspfade;
- keine Codeänderungen.

### Sandbox Integration Mode

- AlmostNode-Adapter;
- Sandbox-Policies;
- keine Host-Secrets.

Jeder Mode definiert:

- Slug;
- Anzeigename;
- Role Definition;
- Tool Groups;
- File Regex;
- Command IDs;
- Approval Policy;
- maximale Laufzeit.

## 26A.10 BKG Skills für Kilo Code

Erstelle Skills in der von der gepinnten Kilo-Version unterstützten Struktur.

Mindestens:

```text
bkg-repository-audit
bkg-release-planning
bkg-nextjs-app-router
bkg-react-server-components
bkg-typescript-strict
bkg-prisma-schema
bkg-prisma-migrations
bkg-postgresql-integrity
bkg-auth-security
bkg-cross-tenant-review
bkg-secret-vault
bkg-bullmq-reliability
bkg-object-storage
bkg-openrouter-routing
bkg-kilo-model-routing
bkg-almostnode-sandbox
bkg-game-docs-workflow
bkg-doc-dependency-graph
bkg-agent-consensus
bkg-live-events
bkg-tts-stt
bkg-pixel-engine
bkg-animation-engine
bkg-level-engine
bkg-game-runtime
bkg-build-system
bkg-export-security
bkg-code-patching
bkg-unit-testing
bkg-integration-testing
bkg-playwright-e2e
bkg-accessibility
bkg-observability
bkg-security-audit
bkg-performance-audit
bkg-release-evidence
bkg-production-readiness
bkg-repair-workflow
```

Jeder Skill enthält:

```text
Name
Version
Purpose
Activation Triggers
Required Inputs
Optional Inputs
Allowed Modes
Allowed Tools
Forbidden Tools
Allowed Paths
Forbidden Paths
Preconditions
Workflow
Validation Steps
Expected Artifacts
Evidence Requirements
Failure Conditions
Escalation Rules
Examples
```

## 26A.11 Skill-Aktivierung

Speichere:

- Session;
- Task;
- Skill;
- Version;
- Aktivierungsgrund;
- Mode;
- Modell;
- Provider;
- erlaubte Tools;
- Ergebnis;
- Fehler;
- Start;
- Ende.

Skill-Auswahl muss im Live Code Studio sichtbar sein.

## 26A.12 Workflows

Erstelle wiederverwendbare Kilo-Workflows:

```text
audit-repository
plan-release
implement-task
review-diff
validate-change
run-targeted-tests
run-full-gates
repair-failure
write-release-evidence
security-review
migration-review
production-readiness
```

Jeder Workflow benötigt:

- Inputs;
- Preconditions;
- Mode;
- Skills;
- Tools;
- Approval Points;
- Success Criteria;
- Failure Criteria;
- Evidence.

## 26A.13 Slash Commands oder äquivalente Commands

Soweit die gepinnte Kilo-Version sie unterstützt, erstelle:

```text
/bkg-audit-repository
/bkg-inspect-task
/bkg-plan-release
/bkg-plan-change
/bkg-implement-task
/bkg-review-diff
/bkg-validate-change
/bkg-run-tests
/bkg-run-gates
/bkg-repair-failure
/bkg-write-evidence
/bkg-check-security
/bkg-check-production-ready
/bkg-summarize-session
```

Falls die aktuelle CLI keine stabilen Custom Slash Commands unterstützt, implementiere dieselben Funktionen als versionierte Workflows und dokumentiere die Abweichung.

## 26A.14 MCP-Integration

Konfiguriere einen lokalen BKG MCP Server für Kilo Code.

Pflichttools:

```text
read-allowed-file
read-allowed-files
list-allowed-files
search-code
search-symbol
read-package-manifest
read-prisma-schema
read-migration
read-game-doc
read-task
read-acceptance-criteria
create-file-plan
create-patch
validate-patch
apply-approved-patch
show-diff
revert-patch
run-allowlisted-command
run-format
run-format-check
run-lint
run-typecheck
run-unit-tests
run-integration-tests
run-component-tests
run-e2e-tests
run-accessibility-tests
run-security-scan
run-secret-scan
run-dependency-scan
run-production-build
run-jobs-build
validate-prisma-migration
validate-database
validate-structure
validate-game-docs
validate-discussion
validate-consensus
validate-build-manifest
validate-export-package
write-release-evidence
create-repair-task
log-agent-event
complete-task
fail-task
```

Die MCP-Konfiguration muss zur gepinnten Kilo-Version passen.

## 26A.15 MCP-Sicherheit

Jedes Tool prüft:

- authentifizierten Worker;
- Code Session;
- Task-ID;
- Project-ID;
- User oder Service Principal;
- erlaubten Mode;
- erlaubten Skill;
- erlaubte Pfade;
- erlaubte Operation;
- Approval;
- Timeout;
- Rate Limit;
- Output-Limit;
- Audit;
- Secret Redaction.

Toolargumente werden mit Zod validiert.

Keine rohen Shellstrings aus Modelltext.

## 26A.16 Terminal- und Command-Policy

Verwalte Commands als IDs.

Erlaubte Beispiele:

```text
pnpm-install-frozen
pnpm-format
pnpm-format-check
pnpm-lint
pnpm-typecheck
pnpm-test-unit
pnpm-test-integration
pnpm-test-e2e
pnpm-build-web
pnpm-build-jobs
pnpm-scan-secrets
pnpm-scan-dependencies
pnpm-validate-database
pnpm-validate-structure
prisma-validate
prisma-migrate-diff
git-diff
git-status
```

Blockiert:

- beliebige Shellstrings;
- `eval`;
- `curl | sh`;
- unkontrolliertes `npx`;
- unkontrollierte Paketinstallation;
- `rm -rf`;
- Home-Verzeichniszugriff;
- SSH-Schlüssel;
- globale Credentials;
- Deployments ohne Approval;
- destruktive Datenbankbefehle ohne Plan.

## 26A.17 Browserautomation

Kilo Code darf Browserautomation für UI- und E2E-Validierung verwenden.

Regeln:

- nur lokale oder genehmigte Testumgebungen;
- keine fremden Konten;
- keine realen Käufe;
- keine Social-Posts ohne Approval;
- keine Production-Mutationen;
- Screenshots als Evidence;
- sensible Felder redigieren;
- Session Cleanup.

## 26A.18 Worktrees und Parallel Agents

Für parallele Coding Tasks:

- eigener Git Worktree oder isolierter Workspace;
- eindeutige Branch;
- eindeutige Code Session;
- Task Ownership;
- keine parallelen Writes auf dieselben Dateien ohne Lock;
- Merge Plan;
- Konfliktprüfung;
- Tests vor Merge;
- Audit.

Der Orchestrator muss Worktree- und Dateilocks koordinieren.

## 26A.19 Hooks und Policy Enforcement

Wenn die gepinnte Version native Hooks unterstützt, verwende sie.

Andernfalls implementiere äquivalente Enforcement-Punkte im BKG MCP Proxy und Worker Wrapper.

Pflichtpunkte:

### Session Start

- Task laden;
- Project laden;
- Berechtigungen laden;
- Game Docs laden;
- Workspace prüfen;
- Secrets registrieren;
- Modellrouting festlegen;
- Audit Event.

### Before Tool

- Tool Permission;
- Argumentvalidierung;
- Pfadnormalisierung;
- Secret-Schutz;
- Command-Allowlist;
- Risikoanalyse;
- Approval.

### After Tool

- Ergebnis normalisieren;
- Output begrenzen;
- Secrets redigieren;
- Audit;
- Diff bei Dateiänderung.

### After File Change

- Format;
- Lint;
- Typecheck;
- relevante Tests;
- Requirements markieren.

### Before Task Complete

- Acceptance Criteria;
- Tests;
- Build;
- Security;
- Evidence;
- offene TODOs;
- offene Mocks;
- blockierende Findings.

### Session End

- Summary;
- Kosten;
- Modellnutzung;
- Änderungen;
- Risiken;
- Audit;
- Cleanup.

## 26A.20 Plan- und Patch-Workflow

Vor jeder Write-Operation:

1. Task laden.
2. Acceptance Criteria laden.
3. Game Docs laden.
4. Repository read-only analysieren.
5. betroffene Dateien bestimmen.
6. Risiken bestimmen.
7. Tests bestimmen.
8. File Change Plan erzeugen.
9. Approval prüfen.
10. Patch erzeugen.

Jeder Patch enthält:

- Patch ID;
- Code Session;
- Task;
- Mode;
- Skill;
- Modell;
- Provider;
- Basis-Commit;
- betroffene Dateien;
- Diff;
- Risiko;
- Approval;
- Validation;
- Tests;
- Build;
- Rollback.

Basis-Hashes und Konflikte müssen geprüft werden.

## 26A.21 Verbindlicher Coding Workflow

```text
Task laden
→ Acceptance Criteria laden
→ Game Docs laden
→ Kilo Mode wählen
→ Skills aktivieren
→ Modell über Kilo Router wählen
→ Read-Only Analyse
→ File Change Plan
→ Permission Check
→ Risiko- und Approval-Check
→ Patch erzeugen
→ Diff anzeigen
→ Patch validieren
→ Patch anwenden
→ Format
→ Lint
→ Typecheck
→ Unit Tests
→ Integration Tests
→ E2E Tests, falls betroffen
→ Security Scan
→ Secret Scan
→ Production Build
→ Evidence schreiben
→ Quality Gate
→ Task abschließen
```

Bei Fehler:

```text
Fehler klassifizieren
→ Logs speichern
→ Task nicht abschließen
→ Modell- oder Provider-Fallback prüfen
→ bekannten Fix prüfen
→ Repair Task erzeugen
→ begrenzten Repair-Zyklus starten
→ Regression erneut ausführen
```

## 26A.22 Kontextverwaltung

Implementiere:

- Session Context;
- Task Context;
- File Context;
- Game-Docs Context;
- Test Context;
- Context Summary;
- Context Compaction;
- Token Budget;
- Retrieval Limits;
- Secret Filter;
- stale Context Detection;
- Worktree Context;
- Model Context Limit Awareness.

Keine fremden Projekte oder vollständigen Datenbanken in den Kontext laden.

## 26A.23 Kilo-Code-Datenmodell

Erweitere mindestens um:

- kilo-installations;
- kilo-versions;
- kilo-health-checks;
- kilo-sessions;
- kilo-session-events;
- kilo-modes;
- kilo-mode-activations;
- kilo-rules;
- kilo-rule-load-results;
- kilo-skills;
- kilo-skill-activations;
- kilo-workflows;
- kilo-workflow-runs;
- kilo-provider-configurations;
- kilo-model-catalog-entries;
- kilo-routing-decisions;
- kilo-fallback-attempts;
- kilo-mcp-servers;
- kilo-mcp-tools;
- kilo-mcp-tool-runs;
- kilo-command-policies;
- kilo-command-runs;
- kilo-worktrees;
- kilo-policy-violations;
- kilo-context-summaries;
- kilo-browser-runs.

## 26A.24 Kilo Code Admin UI

Zeige:

- installierte Version;
- erwartete Version;
- Health;
- CLI Status;
- Extension Status;
- Sessions;
- Modes;
- Rules;
- Rule Load Results;
- Skills;
- Aktivierungen;
- Workflows;
- Provider;
- Modelle;
- Routing Decisions;
- Free-Model-Status;
- Fallbacks;
- MCP Server;
- MCP Tools;
- Commands;
- Worktrees;
- Policy Violations;
- Kosten;
- Fehler;
- Patches;
- Tests;
- Builds;
- Evidence.

## 26A.25 Kilo Code Tests

Unit Tests:

- Mode Permissions;
- Rule Matching;
- Skill Matching;
- Tool Permissions;
- Command-Allowlist;
- Pfadregeln;
- Approval-Regeln;
- Patch Hashes;
- Context Filtering;
- Model Routing;
- Free-Model-Filter;
- Fallback Chain.

Integration Tests:

- CLI Health Check;
- Extension-Verbindung;
- Rules laden;
- Mode aktivieren;
- Skill aktivieren;
- Workflow starten;
- MCP Tool aufrufen;
- Modell auswählen;
- Patch erzeugen;
- Patch anwenden;
- Tests ausführen;
- Build ausführen;
- Evidence schreiben;
- Repair Task erzeugen.

Security Tests:

- Secret File Read;
- Path Traversal;
- verbotener Command;
- Toolargument-Injection;
- ungeprüfte MCP-Konfiguration;
- fehlendes Approval;
- Cross-Project-Zugriff;
- Deployment ohne Approval;
- destruktive Datenbankoperation;
- Browserautomation gegen Production;
- Worktree Escape.

E2E-Test:

1. Production Task wird erstellt.
2. Kilo Session startet.
3. Mode wird gewählt.
4. Skills werden aktiviert.
5. Free Model wird über Kilo Router gewählt.
6. Kilo analysiert read-only.
7. File Change Plan wird gespeichert.
8. Patch wird erzeugt.
9. Diff wird angezeigt.
10. Patch wird genehmigt.
11. MCP Tool wendet Patch an.
12. Format, Lint und Typecheck laufen.
13. Tests laufen.
14. Production Build läuft.
15. Evidence wird geschrieben.
16. Task wird erst danach abgeschlossen.

## 26A.26 Bekannte Versionsrisiken

Da Kilo Code aktiv entwickelt wird, muss Release 00A ausdrücklich prüfen:

- CLI-Modelllisten;
- Providerkonfiguration;
- MCP-Konfigurationsmigration;
- Rules Discovery;
- Skills Discovery;
- Slash Commands;
- Worktrees;
- Headless Mode;
- Extension-/CLI-Parität.

Ein in einer GitHub-Issue beschriebenes Feature gilt nicht automatisch als stabil.

Nur gegen die gepinnte Version erfolgreich getestete Funktionen dürfen als Production Capability markiert werden.


---

# 27. CONCEPT ART STUDIO

Der Art Director und der Image Job Service erstellen zunächst Concept Arts.

Jedes Concept Art besitzt:

* Prompt;
* negative Einschränkungen;
* Style Reference;
* Game-Doc-Referenz;
* Version;
* Status;
* Approval;
* Asset Record;
* Object-Storage-Datei;
* Checksum;
* Metadaten.

Concept Arts definieren:

* Silhouette;
* Proportionen;
* Formen;
* Farben;
* Kleidung;
* Ausrüstung;
* Materialien;
* Umgebung;
* Stimmung;
* Licht;
* charakteristische Merkmale.

Vor der Pixel-Art-Produktion muss das Concept Art bestätigt oder automatisch freigegeben sein.

---

# 28. PIXEL ART STUDIO

Route:

```text
/paint/[pixel-document-id]
```

Der Pixel Painter verwendet bestätigte Concept Arts als Referenz.

„1:1 nachpixeln“ bedeutet:

Die visuelle Identität, Silhouette, Farbverteilung und charakteristischen Merkmale werden innerhalb der festgelegten Pixel-Art-Grenzen so originalgetreu wie möglich übertragen.

Es bedeutet nicht, ein hochauflösendes Bild Pixel für Pixel zu kopieren.

Der Editor enthält:

* Canvas;
* Zoom;
* Pan;
* Pencil;
* Eraser;
* Fill;
* Line;
* Circle;
* Selection;
* Move;
* Copy;
* Paste;
* Palette;
* Palette Lock;
* Layers;
* Layer Visibility;
* History;
* Undo;
* Redo;
* Manual Edit;
* Continue Agent;
* Approve;
* Reject;
* Regenerate;
* Reference Image;
* Side-by-Side Comparison;
* Abweichungsprüfung;
* Agent Tool Timeline;
* Autosave;
* Conflict Handling;
* Export to Asset.

Pixel-Operationen müssen deterministisch und persistent sein.

Pflichtoperationen:

```text
draw-pixel
draw-pixels
fill-rect
draw-line
draw-circle
flood-fill
replace-color
outline
shade
highlight
mirror
erase
select-area
move-selection
copy-selection
paste-selection
apply-palette
render-preview
view-canvas
```

---

# 29. ANIMATION STUDIO

Route:

```text
/animate/[animation-id]
```

Animationstypen:

```text
idle
walk
run
jump
fall
land
attack
hurt
death
cast
block
dodge
summon
interact
custom
```

Implementiere:

* Animation Documents;
* Actions;
* Action Rows;
* Frames;
* Frame Timing;
* Timeline;
* FPS;
* Loop;
* Onion Skin;
* Sprite Sheet Layout;
* transparente Hintergründe;
* Frame Validation;
* Sprite Sheet Export;
* GIF Export;
* History;
* Frame Edit als Pixel Document;
* Live Preview;
* Hitbox Events;
* Hurtbox Events;
* Audio Events;
* Code Integration.

Der Nutzer kann dem Animator live bei der Arbeit zusehen.

---

# 30. LEVEL STUDIO

Route:

```text
/levels/[level-id]
```

Leveltypen:

* platformer-level;
* topdown-level;
* isometric-level;
* arena-level;
* shooter-wave-level;
* rpg-room-level.

Implementiere:

* Tile Grid;
* Layers;
* Collision Layer;
* Spawnpunkte;
* Ausgänge;
* Gegner;
* Items;
* Trigger;
* Quest Marker;
* Kamera-Bereiche;
* AABB;
* Grid Collision;
* Path Check;
* Spawn Validation;
* Exit Reachability;
* Enemy Bounds;
* Item Reachability;
* Playtest;
* Versions;
* Autosave;
* Validation.

---

# 31. AUDIO STUDIO

Implementiere:

* Music Tracks;
* Sound Effects;
* Audio Uploads;
* Audio References;
* Voice Assets;
* TTS Jobs;
* STT Jobs;
* Audio Metadata;
* Waveform Preview;
* Loop Preview;
* Format Validation;
* Size Validation;
* Ownership;
* Versionierung;
* Object Storage;
* Approval;
* Integration Events.

---

# 32. GAME ENGINE

Implementiere eine echte TypeScript-Browsergame-Engine.

Pflichtfunktionen:

* Game Loop;
* Fixed oder Semi-Fixed Update;
* Delta Time;
* deterministic seed;
* Input Mapping;
* Keyboard Input;
* optional Gamepad;
* Entity Model;
* Scene Manager;
* Camera;
* AABB Collision;
* Grid Collision;
* Animation Playback;
* Audio Playback;
* Asset Loader;
* Level Loader;
* Quest State;
* Item State;
* Ability State;
* Win Condition;
* Lose Condition;
* Restart;
* Pause;
* Fullscreen;
* Runtime Error Handling;
* Performance Metrics;
* Save State;
* Load State.

Templates:

* platformer;
* side-scroller;
* top-down;
* top-down-2-5d;
* isometric;
* shooter;
* rpg-lite;
* boss-arena;
* collectathon.

---

# 33. DATENBANKDOMÄNEN

Verwende PostgreSQL und Prisma.

Implementiere mindestens:

## Nutzer und Projekte

* users;
* accounts;
* sessions;
* projects;
* project-members;
* user-settings;
* audit-events.

## Provider und Secrets

* provider-configurations;
* encrypted-secrets;
* secret-access-events;
* provider-test-runs;
* provider-usage;
* provider-cost-records.

## Compliance und RAG

* source-compliance;
* source-compliance-events;
* knowledge-sources;
* knowledge-documents;
* knowledge-chunks;
* knowledge-retrieval-logs;
* agent-knowledge-usage.

## Game Docs

* game-docs;
* game-doc-sections;
* game-doc-section-dependencies;
* game-doc-versions;
* game-doc-validation-runs;
* game-doc-findings;
* game-doc-change-requests;
* game-specification-snapshots.

## Diskussion

* discussion-runs;
* discussion-sections;
* discussion-participants;
* discussion-messages;
* discussion-issues;
* discussion-proposals;
* discussion-votes;
* consensus-snapshots;
* director-decisions;
* user-discussion-inputs;
* voice-segments;
* voice-playback-events.

## Pipeline

* pipeline-runs;
* pipeline-phase-runs;
* production-tasks;
* task-dependencies;
* agent-task-queue;
* agent-events;
* agent-workstations;
* resource-locks;
* user-agent-limits.

## Agenten

* agent-roles;
* agent-departments;
* agent-teams;
* agent-team-members;
* workflows;
* workflow-runs;
* prompt-registry;
* milestone-reviews.

## Assets und Produktion

* assets;
* asset-versions;
* image-jobs;
* pixel-documents;
* pixel-operations;
* pixel-revisions;
* animations;
* animation-actions;
* animation-frames;
* levels;
* level-entities;
* music-tracks;
* sound-effects;
* audio-uploads;
* audio-jobs.

## Builds und Qualität

* builds;
* build-files;
* quality-gates;
* quality-gate-runs;
* validation-results;
* repair-tasks;
* repair-attempts;
* game-pattern-library;
* build-rules;
* repair-fix-catalog;
* playtest-reports;
* bug-reports.

## Export und Launch

* exports;
* export-files;
* security-reports;
* launch-kits;
* cover-designs;
* marketing-plans;
* store-pages;
* social-posts;
* trailer-scripts;
* press-kits;
* community-replies.

## CodeBuilderAgent

* code-sessions;
* code-session-events;
* code-session-context;
* code-session-summaries;
* code-tool-registry;
* code-tool-runs;
* code-tool-permissions;
* code-permission-rules;
* code-permission-requests;
* code-permission-decisions;
* file-change-plans;
* code-patches;
* code-patch-files;
* code-patch-validations;
* code-validation-runs;
* code-validation-results;
* code-cost-tracking;
* code-audit-logs.


## Externe Runtime- und Sandbox-Domänen

Ergänze zusätzlich:

### AlmostNode

- sandbox-sessions;
- sandbox-session-members;
- sandbox-files;
- sandbox-file-snapshots;
- sandbox-commands;
- sandbox-command-results;
- sandbox-package-installs;
- sandbox-preview-sessions;
- sandbox-events;
- sandbox-policy-violations;
- sandbox-import-plans;
- sandbox-import-files;
- sandbox-resource-usage.

### OpenRouter Model Fabric

- model-catalog-entries;
- model-catalog-sync-runs;
- model-capability-probes;
- model-health-checks;
- model-routing-policies;
- model-routing-decisions;
- model-fallback-attempts;
- model-circuit-breakers;
- model-quarantines;
- agent-model-profiles;
- model-quality-scores;
- model-rate-limit-events.

### Kilo Code Runtime

- kilo-runtime-installations;
- kilo-runtime-versions;
- kilo-runtime-health-checks;
- kilo-runtime-sessions;
- kilo-runtime-events;
- kilo-runtime-skills;
- kilo-runtime-skill-activations;
- kilo-runtime-extensions;
- kilo-runtime-extension-consents;
- kilo-runtime-hooks;
- kilo-runtime-hook-runs;
- kilo-runtime-commands;
- kilo-runtime-command-runs;
- kilo-runtime-mcp-tools;
- kilo-runtime-mcp-tool-runs;
- kilo-runtime-policy-violations;
- kilo-runtime-context-summaries.


---

# 34. PIPELINEPHASEN

Implementiere folgende Phasen:

```text
settings-and-provider-check
idea-intake
full-docs-concept
sequential-doc-generation
docs-validation
live-agent-discussion
user-doc-approval
specification-lock
task-seeding
orchestrator-assignment
agent-production
concept-art-generation
pixel-production
animation-production
level-production
audio-production
code-production
integration
quality-gates
preview
playtest
repair
export
security-review
launch-kit
iteration
production-release
```

Pflichtfunktionen:

* start-pipeline;
* advance-phase;
* complete-phase;
* fail-phase;
* pause-for-user;
* resume-after-user-action;
* attach-tasks;
* attach-quality-gates;
* attach-export;
* attach-launch-kit;
* Retry;
* Idempotenz;
* Crash Recovery;
* Audit Events.

---

# 35. BACKGROUND JOBS

Verwende BullMQ.

Jeder Job benötigt:

* stabile Job ID;
* Idempotency Key;
* Attempts;
* Backoff;
* Timeout;
* Heartbeat;
* Lock Renewal;
* Stalled Job Recovery;
* Dead Letter Status;
* Cancel;
* Retry;
* Progress;
* Result;
* Error Classification;
* Event Stream;
* Ownership;
* Audit.

Ein Worker-Abbruch darf keine doppelten:

* Dokumentversionen;
* Diskussionen;
* Stimmen;
* Assets;
* Tasks;
* Builds;
* Exporte

erzeugen.

---

# 36. ORCHESTRATOR

Die Orchestrator-Schicht wird operativ von der aus Gastown hervorgehenden **BKG Orchestration Engine** getragen.

Implementiere:

* GameAgentOrchestrator;
* DocsWorkflowOrchestrator;
* DiscussionOrchestrator;
* ConsensusEngine;
* TaskScheduler;
* DependencyResolver;
* PlanLimitService;
* ResourceLockService;
* QualityGateRunner;
* WorkflowRunner;
* WorkstationAssigner;
* VoiceJobCoordinator;
* ChangeImpactAnalyzer.

Regeln:

* bestätigte und gesperrte Game Docs erforderlich;
* Dependencies prüfen;
* Planlimits beachten;
* Ressourcen sperren;
* Workstation zuweisen;
* Events schreiben;
* Gates starten;
* Repair Agent bei Fehler;
* Locks zuverlässig freigeben;
* Heartbeat Timeouts erkennen;
* Nutzerpausen respektieren;
* keine Produktion vor Specification Lock.

Planlimits:

```text
Normal: 1 paralleler Hauptagent
Pro: 2
Elite: 4
Admin: konfigurierbar
```

---

# 37. PROMPT REGISTRY

Prompts werden versioniert in der Datenbank gespeichert.

Felder:

* Prompt Key;
* Version;
* Status;
* Input Schema;
* Output Schema;
* System Instruction;
* Template;
* Provider Hints;
* Model Hints;
* Created By;
* Audit;
* Rollback;
* Fallback.

Pflichtprompts:

```text
create-basic-idea
create-technical-decision
create-genre-perspective
create-quest-specification
create-world-specification
create-story-specification
create-player-specification
create-abilities-specification
create-enemies-specification
create-bosses-specification
create-items-specification
create-level-structure
create-game-rules
create-look-and-feel
create-pixel-art-direction
create-animation-direction
create-sound-direction
create-ui-direction
create-production-plan
create-risks-and-constraints
create-validation-rules
create-export-target

review-game-doc-section
detect-doc-conflicts
moderate-agent-discussion
create-agent-review
create-agent-vote
calculate-consensus
resolve-minority-conflict
summarize-game-specification

create-asset-plan
create-art-direction
create-concept-art-prompt
pixel-tool-call-loop
animation-plan-loop
level-design-plan
create-audio-plan
build-game-from-template
validate-quality-gate
repair-failed-task
export-release-package
create-cover-design
create-marketing-plan
create-social-posts
run-security-check
```

---

# 38. PROVIDER UND SECRET VAULT

Provider-Keys werden ausschließlich serverseitig verschlüsselt gespeichert.

Implementiere:

* encrypt-secret;
* decrypt-secret-for-use;
* mask-secret;
* rotate-secret;
* revoke-secret;
* audit-secret-access;
* Schlüsselversionierung;
* authenticated encryption;
* Redaction;
* serverseitigen Zugriff;
* Provider Tests;
* Kostenlimits;
* Provider Fallback;
* Timeouts;
* Retry;
* strukturierte Outputvalidierung.

Der Browser erhält niemals Klartext-Secrets.

---

# 39. LIVE EVENTS

Verwende WebSockets oder Server-Sent Events.

Pflichtmerkmale:

* Event Cursor;
* Reconnect;
* Resume;
* Deduplizierung;
* Reihenfolgeprüfung;
* Heartbeat;
* Gap Detection;
* Polling Fallback;
* Permission Check;
* Rate Limit;
* Secret Redaction.

Events umfassen mindestens:

```text
agent-started
agent-message
agent-tool-call
agent-tool-result
agent-vote
consensus-updated
director-decision
user-change-request
task-progress
asset-created
canvas-updated
animation-updated
level-updated
audio-created
code-file-changed
test-started
test-completed
gate-passed
gate-failed
repair-started
repair-completed
build-created
export-completed
launch-completed
agent-failed
```

---

# 40. QUALITY GATES

Implementiere:

* secret-safety-gate;
* docs-gate;
* docs-consensus-gate;
* technical-direction-gate;
* quest-gate;
* dialogue-gate;
* audio-gate;
* asset-plan-gate;
* art-direction-gate;
* concept-art-gate;
* pixel-asset-gate;
* animation-gate;
* level-gate;
* code-structure-gate;
* build-gate;
* security-gate;
* export-gate;
* launch-gate;
* playtest-gate.

Jedes Gate besitzt:

* Input Snapshot;
* Regeln;
* Status;
* Evidence;
* Findings;
* Severity;
* Blocking Decision;
* Run History;
* Retry;
* Audit.

Kein Gate darf statisch bestanden sein.

---

# 41. REPAIR SYSTEM

Implementiere:

* Repair Fix Catalog;
* bekannte Fixes zuerst;
* Provider Fallback;
* Retry Task;
* Split Task;
* Improve Prompt;
* Regenerate Asset;
* Repair Pixel Asset;
* Repair Level;
* Repair Animation;
* Repair Code;
* Repair Manifest;
* Follow-up Task;
* Request User Action;
* Abort;
* Attempt Limit;
* Loop Prevention;
* Regression Validation.

---

# 42. BUILD, PREVIEW UND EXPORT

Ein Build enthält:

* Build Manifest;
* Assets;
* Animationen;
* Levels;
* Audio;
* Runtime Config;
* Input Mapping;
* Game Rules;
* Win Condition;
* Lose Condition;
* Save Config;
* Preview Entrypoint;
* Export Manifest.

Implementiere:

* Create Build;
* Assemble Build;
* Validate Build;
* Build Versions;
* Build Files;
* Reproducible Build;
* Checksum;
* Missing Reference Detection;
* Manifest Validation;
* Preview Creation.

Preview Route:

```text
/preview/[build-id]
```

Preview enthält:

* spielbare Canvas Runtime;
* Tastatur;
* Gamepad, soweit unterstützt;
* Fokusverwaltung;
* Restart;
* Pause;
* Fullscreen;
* Loading;
* Runtime Error Boundary;
* Debug Metrics;
* Bug Report;
* Playtest Feedback;
* Ownership;
* keine Secrets.

Export enthält niemals:

* Provider Keys;
* Tokens;
* Session Secrets;
* Admin Flags;
* Encryption Keys;
* interne Auditdaten.

---

# 43. LAUNCH KIT

Implementiere:

* Security Report;
* Anti-Cheat Checks;
* Cover Art;
* Marketing Plan;
* Store Page;
* Social Posts;
* Trailer Script;
* Press Kit;
* Community Replies;
* Readiness Score;
* Approval Flow.

Social Posts dürfen niemals ohne Nutzerfreigabe veröffentlicht werden.

---

# 44. AUTHENTIFIZIERUNG UND SICHERHEIT

Implementiere:

* Registrierung;
* Login;
* Logout;
* Session Refresh;
* Passwort-Reset oder sicheren externen Login;
* E-Mail-Verifikation bei Passwortlogin;
* Rollen;
* Nutzerrolle;
* Adminrolle;
* Projektmitgliedschaften;
* Resource Ownership;
* Cross-Tenant-Schutz;
* Audit Events;
* Session Expiry;
* CSRF-Schutz;
* sichere Cookies;
* Rate Limits;
* CSP;
* Security Headers;
* XSS-Schutz;
* SQL-Injection-Schutz;
* SSRF-Schutz;
* Path-Traversal-Schutz;
* Upload-Validierung;
* Request Size Limits;
* sichere Redirects;
* Signed URLs;
* Secret Encryption;
* Secret Redaction;
* Export Secret Scan;
* Admin Audit.

Teste ausdrücklich:

* Nutzer A kann keine Projekte von Nutzer B lesen.
* Nutzer A kann keine Jobs von Nutzer B starten.
* Nutzer A kann keine Diskussionen von Nutzer B öffnen.
* Nicht-Admin kann keine Adminroute öffnen.
* manipulierte IDs umgehen keine Berechtigungen.
* abgelaufene Sessions werden korrekt behandelt.
* signierte Asset-URLs respektieren Ownership und Ablaufzeit.
* kritische Security Findings blockieren den Release.

---

# 45. TESTS

## Unit Tests

Teste:

* Statusmaschinen;
* Game-Docs-Abhängigkeiten;
* Dokumentinvalidierung;
* Konsensberechnung;
* Agentengewichte;
* Director-Entscheidungsregeln;
* Permissions;
* Schemas;
* Encryption;
* Pixel Operations;
* Animation Timing;
* Collision;
* Reachability;
* Game Loop;
* Manifests;
* Cost Calculation;
* Retry;
* Locking;
* Idempotency.

## Integration Tests

Teste:

* Auth;
* PostgreSQL;
* Redis;
* BullMQ;
* Object Storage;
* Provider Router;
* Secret Vault;
* RAG;
* Game-Docs-Erstellung;
* Docs Confirm;
* Diskussion;
* Abstimmungen;
* TTS Jobs;
* STT Jobs;
* Pipeline;
* Queue;
* Asset Jobs;
* Build;
* Export;
* Launch.

## Component Tests

Teste:

* Formulare;
* Game-Docs-Editor;
* Statusnavigation;
* Diff;
* Live-Transkript;
* Sprecheranzeige;
* Konsensanzeige;
* Change Requests;
* Pixel Editor;
* Animation Editor;
* Level Editor;
* Timeline;
* Gate Matrix;
* Agent Events;
* Admin Tables;
* Approval Dialogs.

## End-to-End Tests

Teste vollständig:

1. Registrierung;
2. Login;
3. Provider Key;
4. Projekt;
5. Spielidee;
6. Full Docs Concept;
7. alle 22 Dokumente;
8. Dokumentabhängigkeiten;
9. Versionierung;
10. Validierung;
11. Live-TTS-Diskussion;
12. Nutzereingriff per Chat;
13. Nutzereingriff per Voice;
14. Agentenstimmen;
15. 70-Prozent-Konsens;
16. Director-Entscheidung;
17. Nutzerbestätigung;
18. Specification Lock;
19. Pipeline;
20. Queue;
21. Workstations;
22. Concept Art;
23. Pixel Art;
24. Manual Pixel Edit;
25. Animation;
26. Level;
27. Audio;
28. Live Code Session;
29. Build;
30. spielbare Preview der erzeugten Games;
31. Bug Report;
32. Repair;
33. Export;
34. Security Gate;
35. Launch Kit;
36. Admin Audit;
37. Cross-Tenant Denial;
38. Session Expiry;
39. Worker Crash Recovery.

## Nichtfunktionale Tests

Teste:

* Accessibility;
* Responsive Design;
* Visual Regression;
* Performance;
* Load;
* Queue Recovery;
* Rate Limits;
* Security Headers;
* CSP;
* Dependency Scan;
* Secret Scan;
* Object-Storage-Permissions;
* Browserkompatibilität;
* Reconnect von Live Events;
* TTS-Fallback;
* STT-Fehlerbehandlung.


## Integrationsspezifische Pflicht-Tests

### AlmostNode

- Browser-Sandbox startet;
- Dateisystem ist isoliert;
- npm-Paketinstallation folgt Policy;
- Dev Preview startet;
- Timeout funktioniert;
- Netzwerk ist standardmäßig blockiert;
- Snapshot und Restore funktionieren;
- Diff wird korrekt erzeugt;
- Import benötigt Approval;
- Production-Übernahme wird serverseitig validiert.

### OpenRouter

- Free-Katalog wird dynamisch synchronisiert;
- entfernte Modelle werden deaktiviert;
- Agentenprofile wählen geeignete Modelle;
- Rate Limit löst Fallback aus;
- Paid-Modell wird ohne Freigabe blockiert;
- Structured Output wird validiert;
- ungültige Antworten werden nicht als Erfolg gespeichert;
- Secrets werden vor Request entfernt;
- Routing Decision ist auditierbar.

### Kilo Code

- gepinnte Version wird geprüft;
- BKG Extension lädt;
- Skills werden entdeckt;
- Skill-Aktivierung wird protokolliert;
- MCP Tools prüfen Berechtigungen;
- verbotene Commands werden blockiert;
- Secret-Pfade werden blockiert;
- Patch benötigt gültigen Task;
- Taskabschluss ohne Tests wird blockiert;
- Taskabschluss ohne Build wird blockiert;
- Taskabschluss ohne Evidence wird blockiert;
- Repair Workflow funktioniert.


---

# 46. VERBINDLICHER SMOKE TEST

Verwende dieses Spiel:

> Ein Froschritter erkundet eine verfluchte Sumpfburg, sammelt leuchtende Glühwürmchen und besiegt den Schleimkönig.

Der vollständige Smoke Test muss nachweisen:

* BKG Branding;
* Registrierung;
* Login;
* Projekt;
* Provider Key sicher gespeichert;
* Provider Test;
* Spielidee;
* Full Docs Concept;
* alle 22 Game Docs;
* sequenzielle Dokumenterstellung;
* Dokumentversionen;
* Abhängigkeiten;
* Validierung;
* Live-Agentendiskussion;
* hörbare TTS-Ausgabe;
* Live-Transkript;
* Nutzereingriff;
* Agentenstimmen;
* mindestens 70 Prozent Konsens;
* Director-Entscheidung;
* Nutzerbestätigung;
* Docs Lock;
* Pipeline;
* Tasks;
* Queue;
* Workstations;
* RAG Context;
* Image Job;
* Concept Art;
* Asset im Object Storage;
* Asset Record in PostgreSQL;
* PixelPainterAgent;
* Pixel Operations;
* Manual Edit;
* Continue Agent;
* Animation;
* Action Rows;
* FPS Preview;
* Sprite Sheet;
* GIF;
* Level;
* Collision;
* CodeBuilderAgent;
* Live Code Events;
* Tests;
* Build;
* spielbare Preview der erzeugten Games;
* Bug Report;
* Repair;
* Export;
* Security Gate;
* Launch Kit;
* Admin Audit;
* keine Secret-Leaks.

---

# 47. RELEASE-REIHENFOLGE

Arbeite strikt in dieser Reihenfolge.

## Release 00 — Repository und Toolchain

Ab diesem Release gilt verbindlich: Rust + WASM ersetzen Next.js/TypeScript als Produktbasis.

* Repository untersuchen;
* Monorepo;
* pnpm;
* Turborepo;
* Next.js;
* Jobs App;
* Packages;
* Docker;
* PostgreSQL;
* Redis;
* Object Storage;
* CI;
* Format;
* Lint;
* Typecheck;
* Tests;
* Builds.


## Release 00A — External Runtime Verification

Dieser Gate-Abschnitt ist Teil von Release 00 und muss vor Release 01 bestanden sein.

Pflicht:

- AlmostNode Repository und API prüfen;
- AlmostNode Version oder Commit pinnen;
- AlmostNode Adapter implementieren;
- Sandbox Threat Model erstellen;
- Sandbox Smoke Test ausführen;
- OpenRouter Provider Adapter implementieren;
- aktuellen Free-Model-Katalog synchronisieren;
- Routing Policy implementieren;
- Free-Model-Fallback testen;
- Kilo Code installieren;
- Kilo Code Version pinnen;
- BKG Extension scaffolden;
- Root `AGENTS.md` erstellen;
- Pflicht-Skills anlegen;
- MCP Server anlegen;
- Hooks anlegen;
- Command-Allowlist anlegen;
- Coding-Runtime-Smoke-Test ausführen;
- externe Komponenten in Release Evidence dokumentieren.

Release 01 darf erst beginnen, wenn Release 00 und Release 00A bestanden sind.



## Release 00B — Kilo Code Router und Coding Runtime Verification

Dieser Gate-Abschnitt ist ebenfalls Teil von Release 00.

Pflicht:

- Kilo Code Repository und `AGENTS.md` prüfen;
- CLI und optional Extension reproduzierbar installieren;
- Version oder Commit pinnen;
- Kilo Gateway und Providerkonfiguration prüfen;
- aktuellen Modellkatalog abrufen;
- Free-Model-Erkennung implementieren;
- Kilo-Routing und Fallbacks testen;
- OpenRouter-Fallback ohne Schleifen testen;
- Root-`AGENTS.md` erstellen;
- `.kilocode`-Regeln erstellen;
- Custom Modes erstellen;
- Skills erstellen;
- Workflows erstellen;
- MCP Server verbinden;
- Command-Allowlist durchsetzen;
- Browserautomation absichern;
- Worktree-Isolation testen;
- Read-only Plan Mode testen;
- Patch-Workflow testen;
- Taskabschluss ohne Tests blockieren;
- Taskabschluss ohne Build blockieren;
- Taskabschluss ohne Evidence blockieren;
- Release-00B-Evidence erzeugen.

Release 01 darf erst beginnen, wenn Release 00, Release 00A und Release 00B `pass` sind.


## Release 01 — App Shell und Auth

* Branding;
* Layouts;
* Design System;
* Login;
* Registrierung;
* Sessions;
* Rollen;
* Projektzuordnung;
* Adminschutz.

## Release 02 — Datenbank, Secrets und Provider

* Prisma;
* Kernschema;
* Migrationen;
* Seeds;
* Secret Vault;
* Provider Settings;
* Audit.

## Release 03 — Compliance, RAG und Prompt Registry

* Source Compliance;
* Knowledge Import;
* Chunking;
* Retrieval;
* Promptversionen;
* Admin RAG.

## Release 04 — Full Docs Concept

* Idea Intake;
* 22 Game-Docs-Abschnitte;
* sequenzielle Erstellung;
* Dependencies;
* Editor;
* Versionen;
* Diff;
* Autosave.

## Release 05 — Docs Validation und Live Discussion

* Validation Engine;
* Discussion Orchestrator;
* Agent Reviews;
* Votes;
* Consensus Engine;
* Director Decisions;
* TTS;
* STT;
* User Intervention;
* Specification Lock.

## Release 06 — Pipeline, Queue und Orchestrator

* Pipeline;
* Tasks;
* Dependencies;
* BullMQ;
* Locks;
* Workstations;
* Live Events;
* Plan Limits.

## Release 07 — Assets, Concept Art und Pixel

* Asset System;
* Image Jobs;
* Concept Art;
* Pixel Engine;
* Pixel Documents;
* Paint Studio;
* PixelPainterAgent.

## Release 08 — Animation, Level und Audio

* Animation Engine;
* Animation Studio;
* Level Engine;
* Level Studio;
* Collision;
* Audio Studio;
* Voice Assets.

## Release 09 — Studio-Agenten und CodeBuilderAgent

* Agent Roles;
* Departments;
* Workflows;
* Code Sessions;
* Permissions;
* Patches;
* Validation;
* Admin Code Panel.

## Release 10 — Game Engine, Build und Preview

* Game Engine;
* Templates;
* Build Assembly;
* Validation;
* Preview Runtime;
* Playability.

## Release 11 — Quality, QA und Repair

* Quality Gates;
* QA;
* Playtest;
* Bug Triage;
* Repair;
* Regression.

## Release 12 — Export, Security und Launch

* Export;
* Security;
* Cover;
* Marketing;
* Store Page;
* Social;
* Trailer;
* Press Kit;
* Launch Approval.

## Release 13 — Admin, Observability und Recovery

* Admin;
* Health;
* Costs;
* Errors;
* Queue Recovery;
* Lock Recovery;
* Failure Drills;
* Structure Scan.

## Release 14 — Production Release

* vollständiger Smoke Test;
* Load Test;
* Security Audit;
* Production Build;
* Staging;
* Migration Dry Run;
* Deployment;
* Post-Deploy-Test;
* Rollback-Test;
* Release Report.

Du darfst nicht zum nächsten Release wechseln, solange das Gate des aktuellen Releases rot ist.

---

# 48. RELEASE EVIDENCE

Erstelle pro Release:

```text
docs/release-evidence/release-XX/
├── report.md
├── changed-files.md
├── commands.md
├── build-results.md
├── test-results.md
├── security-results.md
├── migration-results.md
├── api-results.md
├── ui-results.md
├── known-issues.md
└── rollback.md
```

Erfinde keine Ergebnisse.

Bei einem Fehler muss der Release-Status `fail` bleiben.

---

# 49. REQUIREMENTS TRACEABILITY

Erstelle:

```text
docs/release-evidence/requirements-traceability.md
```

Schema:

| ID | Requirement | Release | Code | Tests | Evidence | Status |
| -- | ----------- | ------- | ---- | ----- | -------- | ------ |

Erlaubte Statuswerte:

```text
open
in-progress
blocked
verified
```

Kein Sammelstatus wie „größtenteils fertig“.

---

# 50. BUILD- UND QUALITÄTSBEFEHLE

Richte mindestens ein:

```bash
pnpm install --frozen-lockfile
pnpm format
pnpm format:check
pnpm lint
pnpm typecheck
pnpm test
pnpm test:unit
pnpm test:integration
pnpm test:e2e
pnpm test:accessibility
pnpm test:visual
pnpm test:smoke
pnpm build
pnpm build:web
pnpm build:jobs
pnpm scan:secrets
pnpm scan:dependencies
pnpm validate:database
pnpm validate:structure
pnpm validate:game-docs
pnpm validate:discussion
pnpm validate:consensus
pnpm docker:up
pnpm docker:down
pnpm db:migrate
pnpm db:seed
pnpm dev
```

Kein Script darf Fehler über `|| true`, ignorierte Exit Codes oder deaktivierte Tests verstecken.

---

# 51. DEFINITION OF DONE

BKG ist nur production-ready, wenn:

* alle Releases bestanden sind;
* alle Pflichtrouten funktionieren;
* die 22 Game Docs sequenziell erzeugt werden;
* Dokumentabhängigkeiten funktionieren;
* Änderungen abhängige Dokumente invalidieren;
* die Live-Agentendiskussion funktioniert;
* TTS und Texttranskript funktionieren;
* Voice-Eingaben verarbeitet werden können;
* Agenten echte gespeicherte Stimmen abgeben;
* der Konsens korrekt berechnet wird;
* der Mindestwert von 70 Prozent durchgesetzt wird;
* Director-Entscheidungen gespeichert und begründet sind;
* der Nutzer die Specification bestätigen kann;
* vor dem Docs Lock keine Produktion startet;
* alle Kernagenten ausführbar sind;
* PostgreSQL Source of Truth ist;
* Redis und BullMQ zuverlässig laufen;
* Object Storage funktioniert;
* Concept Arts gespeichert werden;
* Pixel Editor vollständig funktioniert;
* Animation Editor vollständig funktioniert;
* Level Editor vollständig funktioniert;
* Audio Studio funktioniert;
* CodeBuilderAgent nachvollziehbar arbeitet;
* die Browsergame-Runtime spielbar ist;
* Builds reproduzierbar sind;
* Export funktioniert;
* Launch Kit funktioniert;
* Adminsystem reale Daten zeigt;
* Cross-Tenant-Zugriff blockiert ist;
* keine Secrets geleakt werden;
* keine kritischen oder hohen Security Findings offen sind;
* Migrationen geprüft sind;
* Worker Crash Recovery geprüft ist;
* Live-Event-Reconnect geprüft ist;
* Rollback geprüft ist;
* Production Build erfolgreich ist;
* Staging Smoke Test erfolgreich ist;
* Release Evidence vollständig ist.



Zusätzlich gilt BKG nur als production-ready, wenn:

- Kilo Code reproduzierbar installiert und gepinnt ist;
- Kilo CLI Health Checks bestehen;
- Kilo Gateway und Modellrouting funktionieren;
- Free-Model-Status dynamisch ermittelt wird;
- keine Kilo-Modellliste hartcodiert ist;
- OpenRouter-Fallback keine Routing-Schleifen erzeugt;
- Root-`AGENTS.md` und bereichsspezifische Regeln geladen werden;
- Custom Modes ihre Dateiberechtigungen durchsetzen;
- Skills versioniert und auditierbar aktiviert werden;
- Workflows reproduzierbar laufen;
- MCP Tools serverseitig autorisiert werden;
- Command-Allowlist durchgesetzt wird;
- Browserautomation keine Production-Mutationen ausführt;
- Worktrees isoliert sind;
- Coding Tasks ohne Tests, Build und Evidence blockiert werden;
- Kilo-spezifische Policy Violations im Admin sichtbar sind.

Zusätzlich gilt BKG nur als production-ready, wenn:

- AlmostNode über einen austauschbaren Adapter integriert ist;
- Browser-Sandboxes Cross-Tenant-isoliert sind;
- Sandbox-Netzwerk standardmäßig blockiert ist;
- Sandbox-Code niemals ungeprüft Production-Code wird;
- OpenRouter-Free-Model-Katalog dynamisch synchronisiert wird;
- keine Free-Modellliste fest im Quellcode steht;
- Agenten Capability Profiles verwenden;
- Modell-Fallbacks und Circuit Breaker funktionieren;
- kostenpflichtige Modelle ohne Freigabe blockiert sind;
- Kilo Code reproduzierbar installiert und gepinnt ist;
- die BKG Kilo Code Extension funktioniert;
- alle Pflicht-Skills vorhanden und validiert sind;
- MCP Tools serverseitig autorisiert sind;
- Hooks riskante Operationen blockieren;
- Coding Tasks ohne Tests, Build und Evidence nicht abgeschlossen werden können;
- alle drei Integrationen vollständige Audit Trails besitzen.


---

# 52. JETZT BEGINNEN


## Verbindlicher Integrations-Bootstrap

Noch vor dem normalen Release-00-Abschluss:

1. Prüfe die aktuelle AlmostNode-Dokumentation und den Quellcode.
2. Dokumentiere unterstützte und nicht unterstützte APIs.
3. Pinne die AlmostNode-Version oder den Commit.
4. Implementiere den `BrowserNodeSandbox`-Adapter.
5. Erstelle das Sandbox Threat Model.
6. Prüfe die aktuelle OpenRouter-Free-Models-Collection.
7. Implementiere die dynamische Katalogsynchronisierung.
8. Lege Capability Profiles für alle Agenten an.
9. Implementiere Routing, Fallbacks, Circuit Breaker und Quarantäne.
10. Installiere Kilo Code reproduzierbar.
11. Pinne und dokumentiere die Kilo-Code-Version.
12. Erstelle Root-`AGENTS.md`.
13. Erstelle die BKG Kilo Code Extension.
14. Erstelle alle Pflicht-Skills.
15. Erstelle MCP Server, Hooks und Custom Commands.
16. Teste Berechtigungen und Secret-Schutz.
17. Erzeuge Release-00A-Evidence.
18. Setze Release 00 nur auf `pass`, wenn Release 00A ebenfalls `pass` ist.


Beginne sofort mit Release 00.

Führe zuerst aus:

1. Repository untersuchen.
2. vorhandene Dateien inventarisieren.
3. vorhandene Abhängigkeiten prüfen.
4. vorhandene Builds ausführen.
5. vorhandene Tests ausführen.
6. reale Fehler dokumentieren.
7. Monorepo-Grundlage herstellen.
8. Docker-Infrastruktur herstellen.
9. PostgreSQL, Redis und Object Storage herstellen.
10. Next.js Production Build herstellen.
11. Jobs Build herstellen.
12. Release-00-Evidence erzeugen.
13. Release-00-Gate ausführen.
14. bei Erfolg selbstständig mit Release 01 fortfahren.

Arbeite danach Release für Release weiter.

Höre nicht nach einem Mockup auf.

Höre nicht nach einem Scaffold auf.

Höre nicht nach den Game Docs auf.

Höre nicht nach der Agentendiskussion auf.

Höre nicht nach dem Pixel Editor auf.

Höre nicht nach einer spielbaren Demo auf.

Höre nicht nach einem lokalen Build auf.

# Höre erst nach dem verifizierten, getesteten und dokumentierten Production Release von BKG auf.


---

# 53. VERBINDLICHE QUELLEN UND VERIFIKATION

Vor Implementierung und bei jedem Upgrade müssen die offiziellen Quellen geprüft werden:

## AlmostNode

```text
https://github.com/macaly/almostnode
```

Zu verifizieren:

- aktuelle README;
- Installationsweg;
- unterstützte APIs;
- Browseranforderungen;
- Lizenz;
- bekannte Einschränkungen;
- Version oder Commit.

## OpenRouter Free Models

```text
https://openrouter.ai/collections/free-models
```

Zu verifizieren:

- aktuell verfügbare kostenlose Modelle;
- Modell-IDs;
- Free-Status;
- Rate Limits;
- Kontextlängen;
- Fähigkeiten;
- Providerbedingungen.

Die Collection ist eine dynamische Informationsquelle und keine statische Konfigurationsdatei.

## Kilo Code

```text
https://github.com/kilo-org/kilocode
```

Zu verifizieren:

- aktuelle README und `AGENTS.md`;
- CLI-Installation;
- VS-Code-Extension;
- Kilo Gateway;
- Provider- und Modellkonfiguration;
- Free-Model-Verfügbarkeit;
- Custom Modes;
- Rules;
- Workflows;
- Skills;
- MCP Server;
- Terminal- und Browsertools;
- Headless Mode;
- Worktrees;
- Settings;
- Sicherheits- und Consent-Verhalten;
- konkrete Stabilität in der gepinnten Version.

## Verifikationsregel

Der Coding Agent darf keine veraltete Syntax raten.

Er muss:

1. offizielle Dokumentation lesen;
2. verwendete Version pinnen;
3. die Syntax gegen diese Version testen;
4. Abweichungen dokumentieren;
5. Release Evidence erzeugen.

---

# 54. ABSCHLIESSENDE AUSFÜHRUNGSREGEL

Dieser Prompt ist ein Ausführungsauftrag.

Der Coding Agent muss:

- Dateien erstellen;
- Code implementieren;
- Migrationen schreiben;
- Tests schreiben;
- Tests ausführen;
- Builds ausführen;
- Fehler reparieren;
- Evidence erzeugen;
- Gates respektieren;
- reale Resultate berichten.

Er darf den Auftrag nicht lediglich zusammenfassen oder in einen neuen Plan umformulieren.

Er darf erst stoppen, wenn:

- ein externer, nicht durch Code lösbarer Blocker vorliegt;
- eine zwingende Nutzerentscheidung benötigt wird;
- oder die vollständige Definition of Done verifiziert erfüllt ist.

Bei einem Blocker muss er exakt angeben:

- betroffene Anforderung;
- ausgeführte Schritte;
- reale Fehlermeldung;
- gespeicherte Evidence;
- sichere nächste Nutzeraktion.

