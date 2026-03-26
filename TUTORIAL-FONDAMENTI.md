# Tutorial Fondamenti Tecnologici

> Una guida completa per chi parte da zero. Ogni concetto e' spiegato con parole semplici, analogie, diagrammi e riferimenti pratici al progetto **Claude Skills Collection**.
>
> Autore: Stefano De Cubellis | Ultimo aggiornamento: 25 Marzo 2026

---

## Indice

1. [Cos'e' il Codice](#1-cose-il-codice)
2. [Cos'e' lo Sviluppo Software](#2-cose-lo-sviluppo-software)
3. [Cos'e' Git](#3-cose-git)
4. [Cos'e' GitHub](#4-cose-github)
5. [Cos'e' un LLM (Large Language Model)](#5-cose-un-llm-large-language-model)
6. [Cos'e' Claude](#6-cose-claude)
7. [Cos'e' un Agente AI](#7-cose-un-agente-ai)
8. [Le API](#8-le-api)
9. [Il Terminal / Command Line](#9-il-terminal--command-line)
10. [Docker e Deploy](#10-docker-e-deploy)
11. [Glossario Completo](#glossario-completo)

---

# 1. Cos'e' il Codice

## Il codice sorgente: la lingua dei computer

Immagina di dover spiegare a qualcuno che non parla la tua lingua come preparare una ricetta. Dovresti usare una lingua che entrambi capite. Il **codice sorgente** e' esattamente questo: un linguaggio che noi umani scriviamo e che il computer riesce a capire e a eseguire.

Il computer, di base, capisce solo numeri: sequenze di 0 e 1 (il cosiddetto **linguaggio macchina**). Scrivere direttamente in 0 e 1 sarebbe impossibile per noi. Per questo esistono i **linguaggi di programmazione**: sono un ponte tra il modo in cui pensiamo noi e il modo in cui ragiona il computer.

```
  Come pensi tu                Il codice               Cosa fa il computer
  ─────────────                ─────────               ───────────────────
  "Mostra un saluto    →    print("Ciao!")     →    Accende i pixel sullo
   sullo schermo"                                    schermo per formare
                                                     la parola "Ciao!"
```

## Come funziona: dal testo all'azione

Quando scrivi del codice, stai scrivendo un semplice file di testo — come scrivere in un blocco note. La differenza e' che quel file viene poi **letto da un programma speciale** (un interprete o un compilatore) che traduce le tue istruzioni in azioni concrete.

Il percorso e' questo:

```
┌──────────────────┐     ┌─────────────────┐     ┌──────────────────┐
│  Tu scrivi il    │     │  Il traduttore   │     │  Il computer     │
│  codice in un    │ ──> │  (interprete o   │ ──> │  esegue le       │
│  file di testo   │     │   compilatore)   │     │  istruzioni      │
│                  │     │  lo converte in  │     │                  │
│  es: bot.py      │     │  linguaggio      │     │  es: il bot      │
│                  │     │  macchina        │     │  parte!          │
└──────────────────┘     └─────────────────┘     └──────────────────┘
```

## Perche' esiste il codice

Il codice esiste per **automatizzare**. Qualsiasi cosa ripetitiva, complessa o che richiede velocita' puo' essere fatta meglio da un programma:

- **Calcoli**: un computer fa in un secondo calcoli che a noi richiederebbero ore
- **Ripetizione**: un programma puo' fare la stessa cosa un milione di volte senza stancarsi
- **Precisione**: non fa errori di distrazione
- **Velocita'**: opera in millisecondi

## I linguaggi di programmazione: quale scegliere?

Esistono centinaia di linguaggi di programmazione. Ognuno ha le sue caratteristiche, come le lingue umane. Ecco i principali:

| Linguaggio | A cosa serve | Difficolta' | Analogia |
|------------|-------------|-------------|----------|
| **Python** | Automazione, AI, analisi dati, bot | Facile | Come l'italiano: espressivo e leggibile |
| **JavaScript** | Siti web interattivi, app web | Media | Come l'inglese: usato ovunque |
| **HTML/CSS** | Struttura e aspetto delle pagine web | Facile | Non e' un vero linguaggio: e' come l'impaginazione di un giornale |
| **SQL** | Gestire database (archivi di dati) | Media | Come chiedere informazioni a un archivista |
| **Java** | App aziendali, app Android | Difficile | Come il tedesco: preciso ma verboso |
| **C/C++** | Sistemi operativi, videogiochi | Molto difficile | Come il latino: potente ma complesso |
| **Rust** | Sistemi ad alte prestazioni | Difficile | Come il giapponese: elegante ma ripido da imparare |
| **Go** | Server e microservizi | Media | Come l'olandese: pratico e diretto |
| **Markdown** | Documentazione e testi formattati | Molto facile | Come scrivere appunti con dei simboli |
| **YAML** | File di configurazione | Facile | Come compilare un modulo |

## Come il computer legge ed esegue il codice

Esistono due modi principali:

**1. Linguaggi interpretati** (es. Python, JavaScript)
Il codice viene letto ed eseguito **riga per riga**, in tempo reale. Come un interprete simultaneo che traduce una frase alla volta.

**2. Linguaggi compilati** (es. C, Java, Rust)
Il codice viene prima **tradotto tutto insieme** in un programma eseguibile, e poi viene eseguito. Come tradurre un intero libro prima di pubblicarlo.

```
  INTERPRETATO (Python):          COMPILATO (C):

  Riga 1 → Esegui               Riga 1 ─┐
  Riga 2 → Esegui               Riga 2  │── Traduci tutto ── Esegui
  Riga 3 → Esegui               Riga 3 ─┘      insieme         tutto
```

## Esempio pratico dal nostro progetto

Nel progetto **Claude Skills Collection**, il codice principale non e' Python o JavaScript — e' **Markdown** e **YAML**. Ma perche'?

Perche' le skills sono **istruzioni per un'intelligenza artificiale**, non per un computer tradizionale. Claude legge il Markdown come noi leggiamo un manuale.

Ecco un esempio reale dal file `market-research.md`:

```yaml
---
name: market-research
description: Perform comprehensive market research, competitor analysis,
  and communication angle discovery for any product, service, or business idea.
---
```

Questa parte si chiama **frontmatter YAML**. E' come la copertina di un libro: dice a Claude il nome della skill e quando usarla.

Nel progetto collegato **adrow-leads-bot**, invece, c'e' un vero programma Python (`bot.py`) che e' un bot Telegram — un programma che risponde automaticamente ai messaggi. In quel caso il codice Python da' istruzioni dirette al computer per connettersi a Telegram, leggere messaggi, elaborarli e rispondere.

La differenza chiave:

```
  Skill (Markdown)                    Bot (Python)
  ──────────────────                  ──────────────
  Istruzioni per Claude    vs.     Istruzioni per il computer
  Claude le interpreta             Python le esegue
  Risultato: comportamento AI      Risultato: programma funzionante
```

---

# 2. Cos'e' lo Sviluppo Software

## Cosa significa "sviluppare software"

Sviluppare software NON significa solo scrivere codice. E' come costruire una casa: non basta sapere usare il martello. Serve un progetto, un piano, dei materiali, delle verifiche e poi la manutenzione nel tempo.

**Sviluppare software** e' il processo completo che va dall'idea iniziale fino al prodotto finito e alla sua cura nel tempo. Include:

- Capire cosa serve (il problema da risolvere)
- Progettare la soluzione
- Scrivere il codice
- Verificare che funzioni
- Metterlo a disposizione degli utenti
- Continuare a migliorarlo

## Il ciclo di vita del software

Ogni software attraversa delle fasi, proprio come un essere vivente. Questo si chiama **SDLC** (Software Development Life Cycle):

```
    ┌─────────┐     ┌──────────────┐     ┌───────────┐
    │  IDEA   │ ──> │ PROGETTAZIONE│ ──> │ SVILUPPO  │
    └─────────┘     └──────────────┘     └─────┬─────┘
                                               │
                                               ▼
    ┌──────────────┐     ┌─────────┐     ┌───────────┐
    │ MANUTENZIONE │ <── │ DEPLOY  │ <── │   TEST    │
    └──────┬───────┘     └─────────┘     └───────────┘
           │
           └──> (il ciclo ricomincia con nuove idee e miglioramenti)
```

### Fase 1: Idea

Tutto parte da un problema. Qualcuno dice: "Servirebbe un modo per fare X piu' velocemente."

**Esempio dal nostro progetto**: "Claude e' molto intelligente, ma quando gli chiedi di fare una ricerca di mercato, non segue un processo strutturato. Servirebbe un modo per dargli istruzioni specifiche." Ecco l'idea dietro le **skills**.

### Fase 2: Progettazione

Si decide COME risolvere il problema. Quali tecnologie usare? Come organizzare il lavoro? Che struttura dare al progetto?

**Esempio**: Si e' deciso che le skills sarebbero state file Markdown con un frontmatter YAML, organizzate in cartelle separate, con un sistema a tre livelli (metadati, istruzioni, risorse).

### Fase 3: Sviluppo

Si scrive il codice (o, nel nostro caso, si scrivono le skills). E' la fase in cui si "costruisce" effettivamente.

**Esempio**: Scrivere il file `critical-review.md` con tutte le 9 dimensioni di analisi, oppure il `market-research.md` con le 5 fasi della ricerca.

### Fase 4: Test

Si verifica che tutto funzioni. Si cercano errori (bug), si prova con casi diversi, si controlla che il risultato sia quello atteso.

**Esempio**: Provare la skill di market research chiedendo a Claude "analizza il mercato per Adrow" e verificare che segua tutte le 5 fasi correttamente.

### Fase 5: Deploy (distribuzione)

Si rende il software disponibile agli utenti. Nel mondo web, significa mettere il programma su un server. Nel nostro caso, significa rendere le skills installabili in Claude Code.

**Esempio**: Pacchettizzare una skill in un file `.skill` e distribuirla.

### Fase 6: Manutenzione

Il software non e' mai "finito". Si correggono bug, si aggiungono funzionalita', si aggiornano le dipendenze.

**Esempio**: Aggiornare la skill di market research per aggiungere nuove fonti di dati o migliorare il formato del report finale.

## Metodologie di sviluppo

Come organizzi il lavoro? Ci sono diversi approcci:

### Agile

**Analogia**: Invece di costruire tutta la casa e poi consegnarla, costruisci una stanza alla volta. Dopo ogni stanza, il cliente verifica se gli piace e puo' chiedere modifiche.

Principi chiave:
- Rilasci frequenti e piccoli (non un unico grande rilascio)
- Adattamento al cambiamento (i requisiti possono cambiare)
- Collaborazione continua con il cliente
- Il software che funziona e' piu' importante della documentazione perfetta

### Scrum

**Analogia**: Il lavoro viene diviso in "sprint" — periodi di 1-4 settimane in cui il team si impegna a completare un set definito di attivita'. Come una serie di mini-maratone.

Elementi chiave:
- **Sprint**: periodo fisso (es. 2 settimane) per completare un gruppo di attivita'
- **Daily standup**: riunione giornaliera di 15 minuti dove ognuno dice cosa ha fatto, cosa fara', cosa lo blocca
- **Sprint review**: alla fine dello sprint, si mostra il lavoro fatto
- **Sprint retrospective**: si discute cosa e' andato bene e cosa migliorare

### Kanban

**Analogia**: Una lavagna con colonne ("Da fare", "In corso", "Fatto") dove ogni attivita' e' un bigliettino che si sposta da sinistra a destra.

```
┌──────────────┬──────────────┬──────────────┐
│   DA FARE    │   IN CORSO   │    FATTO     │
├──────────────┼──────────────┼──────────────┤
│ Nuova skill  │ Scrittura    │ Critical     │
│ copywriting  │ market-      │ review       │
│              │ research     │ completata   │
│ Script di    │              │              │
│ validazione  │ Test skill   │ Skill        │
│ YAML         │ creator      │ creator v1   │
│              │              │              │
└──────────────┴──────────────┴──────────────┘
```

## Ruoli nel team di sviluppo

| Ruolo | Cosa fa | Analogia |
|-------|---------|----------|
| **Developer** (Sviluppatore) | Scrive il codice, implementa le funzionalita' | Il muratore che costruisce la casa |
| **Project Manager (PM)** | Coordina il team, gestisce tempi e priorita' | Il direttore dei lavori |
| **Designer (UX/UI)** | Progetta l'aspetto e l'esperienza dell'utente | L'architetto che disegna la planimetria |
| **QA (Quality Assurance)** | Testa il software, trova i bug | L'ispettore che verifica la qualita' |
| **DevOps** | Gestisce server, deploy, automazione | L'impiantista che fa funzionare tutto |
| **Product Owner** | Decide COSA costruire e la priorita' | Il proprietario della casa che decide cosa vuole |

**Nel nostro progetto**: Stefano De Cubellis ricopre tutti i ruoli (sviluppatore, PM, product owner), con Claude come assistente AI che aiuta nello sviluppo e nella documentazione.

## Ambienti di sviluppo

Quando sviluppi software, non lavori mai direttamente sulla versione che usano gli utenti. Sarebbe come fare lavori di ristrutturazione con le persone dentro casa. Per questo esistono diversi "ambienti":

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  DEVELOPMENT (dev)        STAGING              PRODUCTION   │
│  ───────────────         ─────────             ──────────   │
│  Il tuo computer         Copia di prova        Il "vero"    │
│                                                ambiente     │
│  Qui scrivi e            Qui testi prima       Qui lo       │
│  sperimenti              di rilasciare         usano gli    │
│  liberamente             agli utenti           utenti       │
│                                                             │
│  Errori? Nessun          Errori? Li            Errori?      │
│  problema!               correggi prima        Problema     │
│                          del rilascio          serio!       │
│                                                             │
│          ──────>              ──────>                        │
│        "Funziona!"        "Confermato!"                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

| Ambiente | Scopo | Chi lo usa | Rischio errori |
|----------|-------|------------|----------------|
| **Development** | Scrivere e testare codice localmente | Sviluppatori | Basso (nessun utente vede) |
| **Staging** | Testare in un ambiente simile a quello reale | Team QA, PM | Medio (simula il reale) |
| **Production** | L'ambiente reale, usato dai clienti | Utenti finali | Alto (impatta gli utenti) |

**Esempio dal progetto**: Quando si scrive una nuova skill, la si testa prima localmente in Claude Code (development), poi si verifica con scenari reali (staging), e infine la si pacchettizza e distribuisce (production).

---

# 3. Cos'e' Git

## Perche' esiste il version control

Hai mai lavorato a un documento e creato copie come queste?

```
relazione_finale.docx
relazione_finale_v2.docx
relazione_finale_v2_corretta.docx
relazione_finale_DEFINITIVA.docx
relazione_finale_DEFINITIVA_davvero.docx
relazione_finale_QUESTA_E_QUELLA_GIUSTA.docx
```

Questo e' il caos che succede senza **version control** (controllo di versione). Git risolve esattamente questo problema. E' come avere una macchina del tempo per i tuoi file: puoi tornare a qualsiasi versione precedente, vedere chi ha modificato cosa e quando, e lavorare in parallelo su versioni diverse senza rischiare di perdere nulla.

## Come funziona Git: snapshots, non differenze

Molti pensano che Git salvi le differenze tra una versione e l'altra. In realta', Git funziona a **snapshot** (istantanee): ogni volta che fai un "commit" (un salvataggio), Git scatta una foto completa di tutti i tuoi file in quel momento.

```
  Momento 1          Momento 2           Momento 3
  (Commit A)         (Commit B)          (Commit C)
  ┌──────────┐      ┌──────────┐       ┌──────────┐
  │ foto di  │      │ foto di  │       │ foto di  │
  │ TUTTI i  │ ──>  │ TUTTI i  │ ──>   │ TUTTI i  │
  │ file     │      │ file     │       │ file     │
  └──────────┘      └──────────┘       └──────────┘
       │                 │                   │
  skill-creator.md  skill-creator.md   skill-creator.md
  critical-review/  critical-review/   critical-review/
                    market-research/   market-research/
                                       DOCUMENTAZIONE.md
```

(In realta' Git e' intelligente: se un file non e' cambiato, salva solo un riferimento alla versione precedente, risparmiando spazio.)

## Concetti fondamentali di Git

### Repository (repo)

Il **repository** e' la cartella del tuo progetto con tutta la sua storia. Contiene:
- I file del progetto
- Una cartella nascosta `.git` che contiene tutta la cronologia

**Analogia**: Il repository e' come un quaderno con tutte le pagine mai scritte, comprese quelle cancellate e riscritte. Puoi tornare a leggere qualsiasi pagina passata.

### Commit

Un **commit** e' un salvataggio. Ogni commit ha:
- Un **identificatore unico** (un codice tipo `a1b2c3d`)
- Un **messaggio** che spiega cosa e' cambiato
- Un **autore** e una **data**
- Un collegamento al commit precedente

**Analogia**: Ogni commit e' come una foto polaroid del tuo progetto in quel momento, con una nota attaccata dietro che spiega cosa e' cambiato.

```
  ┌─────────┐     ┌─────────┐     ┌─────────┐     ┌─────────┐
  │ Commit  │ ──> │ Commit  │ ──> │ Commit  │ ──> │ Commit  │
  │  #1     │     │  #2     │     │  #3     │     │  #4     │
  │         │     │         │     │         │     │         │
  │"Inizio  │     │"Aggiunta│     │"Aggiunta│     │"Aggiunta│
  │progetto"│     │critical │     │market   │     │documen- │
  │         │     │review"  │     │research"│     │tazione" │
  └─────────┘     └─────────┘     └─────────┘     └─────────┘
```

### Branch (ramo)

Un **branch** e' una linea di sviluppo parallela. Immagina di voler provare una modifica rischiosa: crei un branch, lavori li' sopra, e se funziona lo unisci al branch principale. Se non funziona, lo elimini senza danni.

**Analogia**: E' come fare una fotocopia del tuo quaderno per provare a riscrivere un capitolo. Se la riscrittura ti piace, sostituisci il capitolo originale. Se non ti piace, butti la fotocopia.

```
         main (branch principale)
         ──●────●────●────●────●──────●──
                     │              ╱
                     │    merge   ╱
                     │          ╱
                     └──●──●──●
                     feature/nuova-skill
                     (branch secondario)
```

### Merge (unione)

Il **merge** e' l'operazione di unire le modifiche di un branch in un altro. Di solito si unisce un branch di feature nel branch principale (main).

### Conflict (conflitto)

Un **conflitto** succede quando due persone hanno modificato la stessa parte dello stesso file in modo diverso. Git non sa quale versione tenere e chiede a te di decidere.

**Analogia**: Due cuochi hanno modificato la stessa ricetta — uno ha cambiato la quantita' di sale, l'altro ha cambiato il tipo di sale. Qualcuno deve decidere cosa tenere.

## Comandi fondamentali di Git

### Iniziare un progetto

```bash
# Creare un nuovo repository nella cartella corrente
git init

# Oppure: scaricare un progetto esistente da remoto
git clone https://github.com/utente/claude-skills-collection.git
```

`git init` e' come comprare un quaderno nuovo.
`git clone` e' come fotocopiare il quaderno di qualcun altro.

### Controllare lo stato

```bash
# Vedere lo stato dei file (modificati, nuovi, pronti)
git status

# Output tipico:
# On branch main
# Changes not staged for commit:
#   modified:   market-research/market-research.md
#
# Untracked files:
#   nuova-skill/nuova-skill.md
```

`git status` e' come guardare la tua scrivania e vedere cosa e' cambiato.

### Preparare e salvare le modifiche

```bash
# Preparare un file specifico per il salvataggio
git add market-research/market-research.md

# Preparare tutti i file modificati
git add .

# Salvare le modifiche con un messaggio
git commit -m "Aggiornata skill market research con nuove fonti"
```

```
  ┌─────────────┐    git add    ┌──────────────┐   git commit   ┌────────────┐
  │  MODIFICHE  │ ───────────>  │   STAGING    │ ────────────>  │  SALVATO   │
  │ (working    │               │   AREA       │                │ (history)  │
  │  directory) │               │ (pronti per  │                │            │
  │             │               │  il commit)  │                │            │
  └─────────────┘               └──────────────┘                └────────────┘
```

**Analogia**: `git add` e' come mettere i fogli nella busta. `git commit` e' come sigillare la busta e scriverci sopra il contenuto.

### Inviare e ricevere dal remoto

```bash
# Inviare i tuoi commit al repository remoto (su GitHub)
git push origin main

# Scaricare le ultime modifiche dal remoto
git pull origin main
```

`git push` e' come spedire la busta alla sede centrale.
`git pull` e' come ricevere le buste che altri hanno spedito.

### Lavorare con i branch

```bash
# Creare un nuovo branch
git branch feature/skill-copywriting

# Passare a quel branch
git checkout feature/skill-copywriting

# Oppure: creare e passare in un solo comando
git checkout -b feature/skill-copywriting

# Unire il branch nel branch corrente
git checkout main
git merge feature/skill-copywriting
```

### Vedere la storia

```bash
# Vedere la lista dei commit
git log

# Versione compatta (una riga per commit)
git log --oneline

# Output tipico:
# a1b2c3d Aggiunta documentazione completa
# e4f5g6h Aggiunta skill market-research
# i7j8k9l Aggiunta skill critical-review
# m0n1o2p Primo commit: skill-creator

# Vedere le differenze tra i file
git diff
```

## Workflow tipico di uno sviluppatore

Ecco il flusso completo che uno sviluppatore segue giorno per giorno:

```
  1. INIZIO GIORNATA
     │
     ├── git pull origin main              ← scarica le ultime novita'
     │
  2. INIZIA A LAVORARE
     │
     ├── git checkout -b feature/xxx       ← crea un branch per la tua modifica
     │
  3. LAVORA
     │
     ├── (modifica i file...)
     ├── git status                        ← controlla cosa hai cambiato
     ├── git diff                          ← vedi le differenze nel dettaglio
     │
  4. SALVA
     │
     ├── git add file1.md file2.md         ← prepara i file
     ├── git commit -m "Descrizione"       ← salva con un messaggio
     │
  5. CONDIVIDI
     │
     ├── git push origin feature/xxx       ← invia al repository remoto
     │
  6. RICHIEDI REVISIONE
     │
     └── Crea una Pull Request su GitHub   ← chiedi al team di revisionare
```

### Esempio concreto dal nostro progetto

Vuoi aggiungere una nuova skill di "copywriting" al progetto:

```bash
# 1. Aggiornati
git pull origin main

# 2. Crea un branch
git checkout -b feature/skill-copywriting

# 3. Crea la struttura
mkdir copywriting
touch copywriting/copywriting.md

# 4. Scrivi la skill (con il tuo editor)...

# 5. Controlla cosa hai fatto
git status
# Output:
# Untracked files:
#   copywriting/copywriting.md

# 6. Prepara e salva
git add copywriting/copywriting.md
git commit -m "Aggiunta skill copywriting per scrittura persuasiva"

# 7. Invia al remoto
git push origin feature/skill-copywriting

# 8. Vai su GitHub e crea la Pull Request
```

## Errori comuni e come risolverli

| Errore | Causa | Soluzione |
|--------|-------|-----------|
| "fatal: not a git repository" | Sei in una cartella senza Git | Esegui `git init` oppure spostati nella cartella giusta con `cd` |
| "nothing to commit" | Non hai modificato nulla, o hai dimenticato `git add` | Controlla con `git status` e usa `git add` |
| "CONFLICT" durante un merge | Due persone hanno modificato lo stesso punto | Apri il file, cerca i marcatori `<<<<<<<`, scegli cosa tenere, poi `git add` e `git commit` |
| "rejected" durante un push | Il remoto ha commit che tu non hai | Fai prima `git pull`, risolvi eventuali conflitti, poi riprova `git push` |
| "detached HEAD" | Hai fatto checkout su un commit specifico | Torna al branch con `git checkout main` |
| Ho fatto commit sul branch sbagliato | Distrazione | Usa `git log` per identificare il commit, poi `git cherry-pick` per copiarlo nel branch giusto |

## Diagramma ASCII del flusso Git completo

```
  REPOSITORY LOCALE                           REPOSITORY REMOTO
  (il tuo computer)                           (GitHub)
  ─────────────────                           ─────────────────

  ┌─────────────┐                             ┌─────────────┐
  │  WORKING    │                             │   REMOTE    │
  │  DIRECTORY  │                             │   REPO      │
  │ (i tuoi     │        git push             │  (GitHub)   │
  │  file)      │  ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ >  │             │
  └──────┬──────┘                             └──────┬──────┘
         │                                           │
    git add                                     git pull /
         │                                      git fetch
         ▼                                           │
  ┌─────────────┐                                    │
  │  STAGING    │                                    │
  │  AREA       │                                    │
  │ (pronti per │                                    │
  │  il commit) │                                    │
  └──────┬──────┘                                    │
         │                                           │
   git commit                                        │
         │                                           │
         ▼                                           ▼
  ┌─────────────┐                             ┌─────────────┐
  │  LOCAL      │                             │             │
  │  REPO       │  < ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─  │             │
  │ (la tua     │        git pull             │             │
  │  storia)    │                             │             │
  └─────────────┘                             └─────────────┘
```

---

# 4. Cos'e' GitHub

## Differenza tra Git e GitHub

Questa e' una delle confusioni piu' comuni. Chiariamola una volta per tutte:

**Git** e' il **software** che gestisce le versioni dei tuoi file. Funziona sul tuo computer, anche senza internet.

**GitHub** e' il **sito web** che ospita i tuoi repository Git online e aggiunge funzionalita' di collaborazione.

| | Git | GitHub |
|--|-----|--------|
| **Cos'e'** | Un programma | Un sito web / servizio cloud |
| **Dove funziona** | Sul tuo computer | Su internet |
| **Funziona offline?** | Si' | No |
| **Creato da** | Linus Torvalds (2005) | GitHub Inc. (2008), poi acquistato da Microsoft |
| **Costo** | Gratuito, open source | Gratis per uso base, piani a pagamento per team |
| **Interfaccia** | Riga di comando (terminale) | Interfaccia web grafica |

**Analogia**: Git e' come un diario personale. GitHub e' come una biblioteca pubblica dove puoi esporre il tuo diario, leggere quelli degli altri, e collaborare per scrivere libri insieme.

Esistono alternative a GitHub: **GitLab**, **Bitbucket**, **Codeberg**. Tutti usano Git come motore, ma offrono interfacce e funzionalita' diverse.

## Repository remoto vs locale

Quando lavori con Git e GitHub, hai **due copie** del tuo progetto:

```
  ┌──────────────────────┐          ┌──────────────────────┐
  │  REPOSITORY LOCALE   │          │  REPOSITORY REMOTO   │
  │  (il tuo computer)   │  <────>  │  (GitHub.com)        │
  │                      │  push/   │                      │
  │  Qui lavori          │  pull    │  Qui condividi       │
  │  Qui fai commit      │          │  Qui collabori       │
  │  Funziona offline    │          │  Serve internet      │
  └──────────────────────┘          └──────────────────────┘
```

Per il nostro progetto, il repository del progetto Skill vive localmente nella cartella `Skill/` e remotamente su GitHub.

## I concetti chiave di GitHub

### Fork

Un **fork** e' una copia completa del repository di qualcun altro nel tuo account GitHub. Puoi modificarla liberamente senza influenzare l'originale.

**Analogia**: E' come fotocopiare il libro di un amico per poterci scrivere sopra le tue note.

```
  Repository originale            Il tuo fork
  (di qualcun altro)              (la tua copia)
  ┌────────────────┐    fork     ┌────────────────┐
  │ skills-        │ ─────────> │ skills-        │
  │ collection     │            │ collection     │
  │ (originale)    │            │ (la tua copia) │
  └────────────────┘            └────────────────┘
```

### Pull Request (PR)

Una **Pull Request** e' una proposta di modifica. Dici: "Ho fatto queste modifiche nel mio branch. Potete controllarle e, se vanno bene, unirle al branch principale?"

**Analogia**: E' come portare una bozza al tuo capo e dirgli "Ho scritto questo capitolo, puoi controllarlo e approvarlo?"

Il flusso di una PR:

```
  1. Crei un branch         → feature/nuova-skill
  2. Fai le modifiche       → scrivi la skill
  3. Fai push su GitHub     → git push origin feature/nuova-skill
  4. Crei la Pull Request   → su GitHub, clicchi "New Pull Request"
  5. I revisori controllano → leggono il codice, commentano
  6. Modifichi se necessario → aggiorni il branch
  7. Viene approvata        → un revisore clicca "Approve"
  8. Merge                  → le modifiche entrano in main
```

### Code Review

La **code review** e' il processo in cui i colleghi leggono il tuo codice e danno feedback. E' una delle pratiche piu' importanti nello sviluppo software:

- Trova bug prima che arrivino in produzione
- Condivide la conoscenza nel team
- Mantiene alta la qualita' del codice
- Insegna ai piu' junior

### Issues

Le **issues** sono i "biglietti" del progetto. Servono per:

- **Segnalare bug**: "La skill di market research non genera il report finale"
- **Proporre funzionalita'**: "Servirebbe una skill per il copywriting"
- **Discutere idee**: "Dovremmo aggiungere validazione automatica del YAML?"
- **Tracciare il lavoro**: "Da fare: aggiungere script init_skill.py"

Ogni issue puo' essere:
- Assegnata a una persona
- Etichettata (bug, enhancement, documentation...)
- Collegata a una Pull Request
- Commentata e discussa

### Projects (Lavagne di progetto)

GitHub **Projects** e' una lavagna Kanban integrata (come quella descritta nella sezione sulle metodologie). Puoi organizzare le issues in colonne come "Da fare", "In corso", "Fatto".

## GitHub Actions (CI/CD)

### Cos'e' CI/CD

**CI** sta per **Continuous Integration**: ogni volta che qualcuno fa push del codice, vengono eseguiti automaticamente dei test per verificare che non si sia rotto nulla.

**CD** sta per **Continuous Delivery/Deployment**: se i test passano, il codice viene automaticamente preparato (o distribuito) per l'uso.

**Analogia**: Immagina una fabbrica di automobili. La CI e' il controllo qualita' automatico che verifica ogni pezzo appena prodotto. La CD e' la catena di montaggio che, se il pezzo e' approvato, lo installa automaticamente nella macchina.

### GitHub Actions

GitHub Actions permette di creare dei **workflow automatici** che si attivano quando succede qualcosa nel repository (un push, una PR, un rilascio...).

**Esempio pratico per il nostro progetto**: Si potrebbe creare un'azione che, ogni volta che qualcuno fa push di una nuova skill:

```yaml
# .github/workflows/validate-skill.yml
name: Valida Skill
on:
  push:
    paths:
      - '**/*.md'

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Verifica frontmatter YAML
        run: |
          # Script che controlla che ogni skill abbia
          # name e description nel frontmatter
          python scripts/validate_frontmatter.py
```

Questo e' uno dei miglioramenti previsti nella roadmap del progetto.

## Come navigare un repository su GitHub

Quando apri un repository su GitHub nel browser, ecco cosa vedi:

```
┌─────────────────────────────────────────────────────────────┐
│  utente/claude-skills-collection                            │
│                                                             │
│  ┌─────────┐ ┌───────┐ ┌────────────┐ ┌──────────┐        │
│  │  Code   │ │Issues │ │Pull Request│ │ Actions  │  ...    │
│  └─────────┘ └───────┘ └────────────┘ └──────────┘        │
│                                                             │
│  📁 critical-review/                                        │
│  📁 market-research/                                        │
│  📄 DOCUMENTAZIONE.md                                       │
│  📄 README.md                                               │
│  📄 skill-creator.md                                        │
│                                                             │
│  ─── README.md ───────────────────────────────────────      │
│  # Claude Skills Collection                                 │
│  Raccolta di skills modulari per estendere le               │
│  capacita' di Claude Code...                                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

- **Code**: i file del progetto
- **Issues**: i biglietti / segnalazioni
- **Pull Requests**: le proposte di modifica in attesa
- **Actions**: le automazioni CI/CD
- **README.md**: mostrato automaticamente nella pagina principale

## Come contribuire a un progetto

Se vuoi contribuire a un progetto open source su GitHub:

```
  1. FORK          ── Crea la tua copia del repository
       │
  2. CLONE         ── Scarica la tua copia sul tuo computer
       │                git clone https://github.com/TUO-UTENTE/progetto.git
       │
  3. BRANCH        ── Crea un branch per la tua modifica
       │                git checkout -b feature/la-tua-modifica
       │
  4. MODIFICA      ── Fai le tue modifiche
       │
  5. COMMIT + PUSH ── Salva e invia
       │                git add . && git commit -m "..." && git push
       │
  6. PULL REQUEST  ── Proponi le modifiche al progetto originale
       │                Su GitHub: "Create Pull Request"
       │
  7. REVIEW        ── I maintainer revisionano
       │
  8. MERGE         ── Se approvato, le tue modifiche entrano nel progetto!
```

---

# 5. Cos'e' un LLM (Large Language Model)

## Intelligenza Artificiale: un brevissimo riassunto

**Intelligenza Artificiale (AI)** e' un termine ampio che indica qualsiasi sistema informatico in grado di svolgere compiti che normalmente richiedono intelligenza umana: capire il linguaggio, riconoscere immagini, prendere decisioni.

```
  ┌─────────────────────────────────────────────┐
  │         INTELLIGENZA ARTIFICIALE             │
  │     (tutto cio' che "sembra" intelligente)   │
  │                                              │
  │   ┌───────────────────────────────────┐      │
  │   │       MACHINE LEARNING            │      │
  │   │   (impara dai dati)               │      │
  │   │                                   │      │
  │   │   ┌───────────────────────┐       │      │
  │   │   │    DEEP LEARNING      │       │      │
  │   │   │  (reti neurali)       │       │      │
  │   │   │                       │       │      │
  │   │   │  ┌─────────────────┐  │       │      │
  │   │   │  │      LLM        │  │       │      │
  │   │   │  │ (modelli        │  │       │      │
  │   │   │  │  linguistici)   │  │       │      │
  │   │   │  └─────────────────┘  │       │      │
  │   │   └───────────────────────┘       │      │
  │   └───────────────────────────────────┘      │
  └─────────────────────────────────────────────┘
```

## Machine Learning: imparare dai dati

Il **Machine Learning** (apprendimento automatico) e' un approccio all'AI dove il sistema **impara dai dati** invece di essere programmato esplicitamente con regole.

**Analogia**: Invece di insegnare a un bambino le regole della grammatica (programmazione tradizionale), gli fai leggere migliaia di libri finche' non impara a parlare correttamente da solo (machine learning).

## Cos'e' un LLM e come funziona

Un **Large Language Model** (Grande Modello Linguistico) e' un programma di intelligenza artificiale addestrato su enormi quantita' di testo per capire e generare linguaggio umano.

### Come funziona (semplificato)

Un LLM fa una cosa apparentemente semplice: **predice la parola successiva**. Ma lo fa cosi' bene, avendo letto cosi' tanto, che il risultato sembra "intelligente".

```
  Input:  "Il cielo oggi e' molto ___"

  Il modello calcola le probabilita':
  - "blu"       → 35%
  - "nuvoloso"  → 25%
  - "sereno"    → 20%
  - "grigio"    → 15%
  - "bello"     → 5%

  Sceglie → "blu"

  Poi continua: "Il cielo oggi e' molto blu e ___"
  - "le"        → 30%
  - "si"        → 20%
  - ...

  E cosi' via, parola dopo parola.
```

### Come viene addestrato

L'addestramento di un LLM avviene in piu' fasi:

**1. Pre-training (addestramento preliminare)**
Il modello legge miliardi di pagine di testo: libri, siti web, articoli, codice, enciclopedie. Non "memorizza" i testi, ma impara i **pattern** del linguaggio — come le parole si relazionano tra loro, come funziona la logica, come si costruisce un ragionamento.

**2. Fine-tuning (affinamento)**
Il modello viene affinato per compiti specifici: rispondere a domande, seguire istruzioni, essere utile e sicuro.

**3. RLHF (Reinforcement Learning from Human Feedback)**
Esseri umani valutano le risposte del modello ("questa e' buona", "questa e' cattiva") e il modello impara a produrre risposte migliori.

### Concetti chiave

| Concetto | Spiegazione | Analogia |
|----------|-------------|----------|
| **Parametri** | I "neuroni" del modello. Piu' parametri = piu' capacita' di apprendimento. GPT-4 ha centinaia di miliardi di parametri | Come le connessioni neuronali nel cervello: piu' ce ne sono, piu' si puo' imparare |
| **Token** | L'unita' base di testo. Una parola italiana e' circa 1-2 token. "Ciao" = 1 token, "intelligenza artificiale" = 3-4 token | Come le sillabe: il modello non legge per lettere ne' per frasi, ma per "pezzi" intermedi |
| **Context window** | La quantita' massima di testo che il modello puo' considerare in una conversazione | Come la memoria a breve termine: piu' e' grande, piu' il modello ricorda della conversazione |
| **Training data** | I testi su cui il modello e' stato addestrato | Come i libri che uno studente ha letto durante il percorso scolastico |
| **Inference** | Il processo di generare una risposta | Come rispondere a una domanda d'esame dopo aver studiato |
| **Temperatura** | Parametro che controlla la "creativita'": bassa = risposte prevedibili, alta = risposte creative/rischiose | Come il peperoncino: poco = sicuro, tanto = imprevedibile |

## Cosa puo' fare un LLM

- Rispondere a domande su qualsiasi argomento
- Scrivere testi, email, articoli, codice
- Riassumere documenti lunghi
- Tradurre tra lingue
- Analizzare dati e ragionare su problemi
- Generare idee creative
- Spiegare concetti complessi in modo semplice
- Assistere nella programmazione

## Cosa NON puo' fare un LLM

- **Non naviga internet** (a meno che non abbia strumenti collegati)
- **Non ha memoria tra conversazioni** (ogni chat ricomincia da zero, a meno di sistemi di memoria)
- **Non "capisce" veramente**: predice pattern statistici, non ha comprensione profonda
- **Non puo' eseguire azioni nel mondo reale** (a meno che non sia un agente con strumenti)
- **Non e' aggiornato in tempo reale**: ha una "data di taglio" oltre la quale non sa nulla

## Limiti importanti

### Allucinazioni
A volte il modello genera informazioni **false ma convincenti**. Inventa citazioni, dati, fatti che sembrano veri ma non lo sono.

**Analogia**: E' come uno studente che, non sapendo la risposta, ne inventa una plausibile sperando che il professore non se ne accorga.

### Bias (pregiudizi)
Il modello riflette i pregiudizi presenti nei testi su cui e' stato addestrato. Se i testi contenevano stereotipi o errori, il modello li puo' riprodurre.

### Context window limitata
Il modello non puo' considerare testi infinitamente lunghi. Oltre un certo limite, "dimentica" l'inizio della conversazione.

**Questo e' rilevante per il nostro progetto**: le skills devono essere concise perche' condividono la context window con tutto il resto. Per questo il progetto usa un'architettura a **progressive disclosure** a tre livelli: metadati (~100 parole), istruzioni (<5.000 parole), risorse (caricate solo quando servono).

## Confronto tra i principali LLM

| Modello | Azienda | Punti di forza | Punti deboli | Parametri (stimati) |
|---------|---------|----------------|--------------|---------------------|
| **GPT-4o** | OpenAI | Multimodale (testo, immagini, audio), molto popolare | Costoso, a volte verboso | ~200B+ (stimati) |
| **Claude (Opus, Sonnet, Haiku)** | Anthropic | Sicurezza, ragionamento lungo, contesto fino a 1M token | Meno multimodale di GPT-4o | Non divulgati |
| **Gemini** | Google | Integrazione con Google, grandi finestre di contesto | A volte meno preciso | Non divulgati |
| **LLaMA 3** | Meta | Open source, personalizzabile, gratuito | Richiede hardware potente per i modelli grandi | 8B, 70B, 405B |
| **Mistral** | Mistral AI | Leggero, efficiente, open source | Meno capace dei modelli piu' grandi | 7B, 8x7B, 8x22B |
| **Qwen** | Alibaba | Buono in cinese e multilingue, open source | Meno testato in contesti occidentali | 7B - 72B |
| **Grok** | xAI | Accesso a dati X/Twitter in tempo reale | Ecosistema limitato | Non divulgati |
| **Command R+** | Cohere | Ottimo per RAG (retrieval), multilingue | Meno noto, ecosistema piu' piccolo | Non divulgati |

**Legenda parametri**: B = miliardi. Un modello con 70B parametri ha 70 miliardi di parametri.

---

# 6. Cos'e' Claude

## Chi e' Anthropic

**Anthropic** e' un'azienda di ricerca sull'intelligenza artificiale fondata nel 2021 da ex membri di OpenAI (tra cui Dario e Daniela Amodei). La missione di Anthropic e' costruire **AI sicura e affidabile**.

Mentre altre aziende puntano principalmente sulle capacita' (rendere i modelli piu' potenti), Anthropic pone una forte enfasi sulla **sicurezza**: creare modelli che siano utili ma anche onesti, innocui e controllabili.

## Le versioni di Claude

Claude e' disponibile in diverse versioni, ognuna con un equilibrio diverso tra capacita' e costo:

| Versione | Caratteristiche | Ideale per | Analogia |
|----------|----------------|------------|----------|
| **Haiku** | Velocissimo, economico, meno capace | Risposte rapide, compiti semplici, classificazione | L'auto utilitaria: va dappertutto, costa poco |
| **Sonnet** | Equilibrio tra velocita', costo e capacita' | La maggior parte dei compiti quotidiani | L'auto familiare: buona per tutto |
| **Opus** | Il piu' capace, piu' lento e costoso | Compiti complessi, ragionamento avanzato, analisi | L'auto di lusso: prestazioni massime |

```
  Capacita' ▲
             │
   Opus      │                                    ★
             │
   Sonnet    │                        ★
             │
   Haiku     │            ★
             │
             └────────────────────────────────────> Costo
                   $        $$          $$$
```

## Constitutional AI: cos'e' e perche' e' importante

**Constitutional AI** e' l'approccio di Anthropic per rendere Claude sicuro. Invece di addestrare il modello solo con feedback umano (che e' soggettivo e costoso), danno a Claude un set di **principi** (una "costituzione") che il modello deve rispettare.

**Analogia**: Invece di dire a un bambino caso per caso "questo e' giusto, questo e' sbagliato" (RLHF), gli insegni dei principi generali: "sii onesto", "non fare del male", "rispetta gli altri". Il bambino poi applica quei principi autonomamente.

Principi della "costituzione" di Claude:
- Essere **utile**: rispondere nel modo piu' utile possibile
- Essere **onesto**: non mentire, ammettere quando non sa qualcosa
- Essere **innocuo**: rifiutarsi di fare cose dannose

## Come si usa Claude

Claude e' accessibile in diversi modi:

### 1. Chat web (claude.ai)
L'interfaccia piu' semplice: apri il sito, scrivi la tua domanda, ricevi la risposta. Come usare WhatsApp.

### 2. API (Application Programming Interface)
Per gli sviluppatori: invii richieste programmaticamente e ricevi risposte. Permette di integrare Claude nelle proprie applicazioni.

```python
# Esempio di chiamata API (Python)
import anthropic

client = anthropic.Anthropic(api_key="la-tua-chiave")
message = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    messages=[
        {"role": "user", "content": "Analizza il mercato per Adrow"}
    ]
)
```

### 3. Claude Code (CLI)
L'interfaccia a riga di comando ufficiale di Anthropic. E' lo strumento fondamentale del nostro progetto: Claude Code e' l'ambiente in cui le skills vengono eseguite.

```bash
# Avviare Claude Code
claude

# Claude Code legge automaticamente le skills dalla cartella .claude/
# e le attiva quando la richiesta dell'utente corrisponde
```

## Pricing e token

Claude usa un sistema di pricing basato sui **token** (le unita' di testo):

| Modello | Input (per 1M token) | Output (per 1M token) | Context window |
|---------|---------------------|-----------------------|----------------|
| **Haiku** | ~$0.25 | ~$1.25 | 200K token |
| **Sonnet** | ~$3 | ~$15 | 200K token |
| **Opus** | ~$15 | ~$75 | 200K - 1M token |

**Quanto e' 1 milione di token?** Circa 750.000 parole, cioe' circa 5-6 romanzi completi. Nella pratica, una conversazione tipica usa da poche centinaia a poche migliaia di token.

## Quando usare Claude vs altri LLM

| Scenario | Modello consigliato | Perche' |
|----------|-------------------|---------|
| Compiti rapidi e semplici | Claude Haiku o GPT-4o mini | Veloce ed economico |
| Scrittura e analisi quotidiana | Claude Sonnet | Buon equilibrio |
| Ragionamento complesso, codice, analisi lunga | Claude Opus | Massima capacita' |
| Serve accesso a internet in tempo reale | ChatGPT con browsing o Gemini | Claude non naviga di base |
| Serve un modello da far girare in locale | LLaMA o Mistral | Open source, gratuiti |
| Compiti con immagini/video/audio | GPT-4o o Gemini | Piu' multimodali |
| Sicurezza e affidabilita' sono prioritarie | Claude (qualsiasi versione) | Constitutional AI |

## Esempi pratici di utilizzo in questo progetto

Il nostro progetto **Claude Skills Collection** e' interamente costruito attorno a Claude:

**1. Le skills estendono Claude**: Ogni skill (critical-review, market-research, skill-creator) e' un set di istruzioni che Claude legge e segue per svolgere compiti specializzati.

**2. Claude come sviluppatore**: Gran parte della documentazione e del codice del progetto e' stata scritta con l'assistenza di Claude Code.

**3. Il ciclo di feedback**: Le skills vengono create, testate in Claude Code, e poi migliorate sulla base dei risultati — un ciclo di iterazione continua (Fase 6 del processo di creazione delle skills).

**4. Il plugin claude-mem**: Il progetto usa un plugin per la memoria persistente in Claude Code, che permette a Claude di ricordare informazioni tra sessioni diverse.

---

# 7. Cos'e' un Agente AI

## Definizione

Un **agente AI** e' un sistema di intelligenza artificiale che non si limita a rispondere alle domande, ma **agisce autonomamente** per raggiungere un obiettivo. Puo' usare strumenti, prendere decisioni, e completare compiti complessi con piu' passaggi.

**Analogia**: Un chatbot e' come un bibliotecario che risponde alle tue domande. Un agente AI e' come un assistente personale che, quando gli dici "organizzami il viaggio a Roma", cerca i voli, prenota l'albergo, pianifica l'itinerario e te lo presenta — tutto autonomamente.

## Differenza tra chatbot, assistente e agente

| | Chatbot | Assistente AI | Agente AI |
|--|---------|---------------|-----------|
| **Cosa fa** | Risponde a domande | Risponde e suggerisce | Agisce autonomamente |
| **Autonomia** | Nessuna | Poca | Molta |
| **Strumenti** | Nessuno | Alcuni | Molti |
| **Esempio** | FAQ automatiche di un sito | Siri, Alexa | Claude Code, Devin |
| **Compiti** | Semplici, una domanda alla volta | Medi, puo' fare alcune azioni | Complessi, multi-step |

```
  COMPLESSITA'
       ▲
       │
       │    Agente AI ──────────────── ★
       │    (agisce, usa strumenti,    │
       │     prende decisioni)         │
       │                               │
       │    Assistente AI ────── ★     │
       │    (risponde, suggerisce)│     │
       │                         │     │
       │    Chatbot ───── ★      │     │
       │    (risponde)    │      │     │
       │                  │      │     │
       └──────────────────┴──────┴─────┴──> AUTONOMIA
```

## Come funziona un agente: percezione, ragionamento, azione

Un agente AI segue un ciclo continuo:

```
  ┌──────────────────────────────────────────────────┐
  │                                                  │
  │   1. PERCEZIONE         2. RAGIONAMENTO          │
  │   ┌────────────┐       ┌────────────────┐        │
  │   │ Riceve     │       │ Analizza la    │        │
  │   │ input      │ ────> │ situazione,    │        │
  │   │ (richiesta,│       │ decide cosa    │        │
  │   │  risultati │       │ fare           │        │
  │   │  strumenti)│       └───────┬────────┘        │
  │   └────────────┘               │                 │
  │         ▲                      ▼                 │
  │         │              3. AZIONE                 │
  │         │              ┌────────────────┐        │
  │         │              │ Usa uno        │        │
  │         └───────────── │ strumento,     │        │
  │        (il risultato   │ scrive codice, │        │
  │         diventa nuovo  │ legge un file, │        │
  │         input)         │ cerca online   │        │
  │                        └────────────────┘        │
  │                                                  │
  │   Il ciclo si ripete finche' il compito          │
  │   non e' completato                              │
  └──────────────────────────────────────────────────┘
```

**Esempio concreto**: Quando chiedi a Claude Code di "creare una nuova skill di copywriting":

1. **Percezione**: Claude legge la tua richiesta
2. **Ragionamento**: Capisce che deve creare una cartella, un file .md con frontmatter, e scrivere le istruzioni
3. **Azione**: Crea la cartella (`mkdir copywriting`), crea il file, scrive il contenuto
4. **Percezione**: Vede il risultato dei comandi
5. **Ragionamento**: Verifica che tutto sia corretto
6. **Azione**: Ti mostra il risultato e chiede se va bene

## Tool use / Function calling

Il **tool use** (o **function calling**) e' la capacita' di un agente AI di **usare strumenti esterni**. L'agente non fa tutto da solo — chiama degli strumenti per fare cose specifiche.

**Analogia**: Un agente AI e' come un artigiano con una cassetta degli attrezzi. Per ogni compito usa lo strumento giusto: il martello per i chiodi, il cacciavite per le viti, il metro per misurare.

Strumenti tipici di un agente AI:

| Strumento | Cosa fa | Esempio |
|-----------|---------|---------|
| **Lettura file** | Legge il contenuto di un file | Leggere `skill-creator.md` |
| **Scrittura file** | Crea o modifica un file | Creare `copywriting/copywriting.md` |
| **Esecuzione comandi** | Esegue comandi nel terminale | `git status`, `mkdir`, `python script.py` |
| **Ricerca web** | Cerca informazioni online | Cercare dati di mercato per una ricerca |
| **Ricerca nel codice** | Cerca testo nei file del progetto | Trovare dove e' definita una funzione |

## Esempi di agenti AI

| Agente | Cosa fa | Chi lo sviluppa |
|--------|---------|-----------------|
| **Claude Code** | Scrive codice, gestisce file, esegue comandi nel terminale | Anthropic |
| **Cursor** | Editor di codice con AI integrata che modifica e genera codice | Cursor Inc. |
| **Devin** | Agente software che puo' completare interi compiti di programmazione | Cognition |
| **AutoGPT** | Agente generico che scompone obiettivi in sotto-compiti | Open source |
| **GitHub Copilot** | Suggerisce e completa il codice mentre scrivi | GitHub / Microsoft |

## MCP (Model Context Protocol)

Il **Model Context Protocol** e' uno standard creato da Anthropic per permettere agli agenti AI di **connettersi a strumenti e servizi esterni** in modo standardizzato.

**Analogia**: Pensa alle prese elettriche. In Italia usiamo un tipo, in Inghilterra un altro, negli USA un altro ancora. L'MCP e' come uno standard universale di presa: se un servizio segue lo standard MCP, qualsiasi agente compatibile puo' connettersi ad esso.

```
  ┌─────────────┐     MCP      ┌──────────────────┐
  │  Claude     │ ◄──────────► │  Database         │
  │  Code       │              └──────────────────┘
  │             │     MCP      ┌──────────────────┐
  │  (agente)   │ ◄──────────► │  File system      │
  │             │              └──────────────────┘
  │             │     MCP      ┌──────────────────┐
  │             │ ◄──────────► │  API esterne      │
  │             │              └──────────────────┘
  │             │     MCP      ┌──────────────────┐
  │             │ ◄──────────► │  Plugin claude-mem│
  └─────────────┘              └──────────────────┘
```

**Nel nostro progetto**: Il plugin **claude-mem** (di thedotmack) usa MCP per dare a Claude Code una **memoria persistente** — la capacita' di ricordare informazioni tra sessioni diverse.

## Agentic workflows

Gli **agentic workflows** (flussi di lavoro agentici) sono processi in cui uno o piu' agenti AI collaborano per completare un compito complesso, spesso con intervento umano minimo.

```
  WORKFLOW SEQUENZIALE:           WORKFLOW COLLABORATIVO:

  Agente 1                        Agente 1 ◄───► Agente 2
     │                                  │
     ▼                                  ▼
  Agente 2                        Agente 3 ◄───► Agente 4
     │                                  │
     ▼                                  ▼
  Agente 3                           Risultato
     │                                finale
     ▼
  Risultato
```

**Esempio dal progetto**: Quando usi Claude Code con la skill di **market research**:

1. Claude Code (agente) riceve la richiesta "analizza il mercato per X"
2. Legge i metadati delle skills (tool: lettura file)
3. La description della skill market-research corrisponde alla richiesta
4. Carica il corpo della skill (tool: lettura file)
5. Segue il workflow in 5 fasi definito dalla skill
6. Usa la ricerca web (tool: WebSearch) per trovare dati di mercato
7. Compila il report finale (tool: scrittura file)

Tutto questo e' un **agentic workflow**: un agente che segue istruzioni strutturate (la skill) e usa strumenti per completare un compito complesso.

---

# 8. Le API

## Cos'e' un'API

**API** sta per **Application Programming Interface** (Interfaccia di Programmazione delle Applicazioni). E' il modo in cui due programmi comunicano tra loro.

### L'analogia del ristorante

Immagina di essere in un ristorante:

```
  ┌─────────────┐     ┌─────────────┐     ┌─────────────┐
  │   TU        │     │  CAMERIERE  │     │   CUCINA    │
  │  (cliente)  │     │   (API)     │     │  (server)   │
  │             │     │             │     │             │
  │ "Vorrei una │ ──> │ Prende il   │ ──> │ Prepara il  │
  │  margherita"│     │ tuo ordine  │     │ piatto      │
  │             │     │             │     │             │
  │ Ricevi la   │ <── │ Ti porta    │ <── │ Piatto      │
  │ pizza       │     │ il piatto   │     │ pronto      │
  └─────────────┘     └─────────────┘     └─────────────┘
```

- **Tu** (il programma che fa la richiesta) non vai in cucina a farti la pizza da solo
- Il **cameriere** (l'API) prende il tuo ordine in un formato standardizzato (il menu)
- La **cucina** (il server) fa il lavoro e ti restituisce il risultato

Senza API, ogni programma dovrebbe sapere esattamente come funziona internamente l'altro. Con le API, serve solo conoscere il "menu" (la documentazione) — cioe' cosa puoi chiedere e in che formato.

## REST API: i metodi fondamentali

**REST** (Representational State Transfer) e' lo standard piu' usato per le API web. Funziona con dei "metodi" che corrispondono ad azioni:

| Metodo | Azione | Analogia ristorante | Esempio |
|--------|--------|---------------------|---------|
| **GET** | Leggere dati | "Mi porti il menu?" | Ottenere la lista delle skills |
| **POST** | Creare qualcosa di nuovo | "Vorrei ordinare una pizza" | Creare una nuova skill |
| **PUT** | Aggiornare/sostituire | "Cambio il mio ordine" | Aggiornare una skill esistente |
| **PATCH** | Aggiornare parzialmente | "Aggiungi olive alla pizza" | Modificare solo la descrizione di una skill |
| **DELETE** | Eliminare | "Annulla il mio ordine" | Eliminare una skill |

Esempio pratico:

```
GET    /api/skills              → Ottieni tutte le skills
GET    /api/skills/market-research → Ottieni la skill "market-research"
POST   /api/skills              → Crea una nuova skill
PUT    /api/skills/market-research → Aggiorna la skill "market-research"
DELETE /api/skills/market-research → Elimina la skill "market-research"
```

## Autenticazione: come dimostrare chi sei

Quando usi un'API, devi spesso dimostrare la tua identita'. Ci sono diversi metodi:

### API Key

La piu' semplice: una stringa segreta (come una password) che includi in ogni richiesta.

```
# Esempio di richiesta con API key
curl -H "x-api-key: sk-ant-api03-xxxxx" \
     https://api.anthropic.com/v1/messages
```

**Analogia**: E' come il badge dell'ufficio — lo mostri ogni volta che entri.

### Bearer Token (OAuth)

Piu' sicuro: ottieni un "gettone" temporaneo dopo aver fatto login, e lo usi per le richieste successive.

```
# Esempio di richiesta con Bearer token
curl -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5..." \
     https://api.esempio.com/dati
```

**Analogia**: E' come il braccialetto del resort all-inclusive — lo ottieni al check-in e lo mostri per accedere ai servizi.

### Confronto

| Metodo | Sicurezza | Complessita' | Quando usarlo |
|--------|-----------|-------------|---------------|
| **API Key** | Base | Semplice | Accesso server-to-server |
| **Bearer Token** | Alta | Media | Accesso utente autenticato |
| **OAuth 2.0** | Molto alta | Complessa | Accesso a servizi terzi (es. "Accedi con Google") |

## JSON: il formato dei dati

**JSON** (JavaScript Object Notation) e' il formato piu' usato per scambiare dati tra programmi. E' leggibile sia dagli umani che dai computer.

```json
{
  "name": "market-research",
  "description": "Perform comprehensive market research",
  "version": "1.0",
  "author": "Stefano De Cubellis",
  "phases": [
    "Briefing",
    "Market Research",
    "Competitor Research",
    "Communication Angles",
    "Report Compilation"
  ],
  "active": true,
  "downloads": 42
}
```

Come leggere il JSON:

| Elemento | Significato | Esempio |
|----------|-------------|---------|
| `{ }` | Oggetto (un contenitore di dati) | `{ "name": "test" }` |
| `[ ]` | Lista (array) di elementi | `["uno", "due", "tre"]` |
| `"chiave": "valore"` | Coppia chiave-valore (tipo etichetta e contenuto) | `"name": "market-research"` |
| `"testo"` | Stringa (testo) | `"Ciao mondo"` |
| `42` | Numero | `42` |
| `true` / `false` | Booleano (vero/falso) | `"active": true` |
| `null` | Valore nullo (niente) | `"deleted_at": null` |

**Confronto con YAML** (usato nel nostro progetto per il frontmatter):

```
  JSON:                           YAML:
  ──────                          ──────
  {                               name: market-research
    "name": "market-research",    description: >
    "description": "Perform       Perform comprehensive
      comprehensive market         market research
      research",                  phases:
    "phases": [                     - Briefing
      "Briefing",                   - Market Research
      "Market Research",            - Competitor Research
      "Competitor Research"
    ]
  }
```

YAML e' piu' leggibile per gli umani, JSON e' piu' usato nelle API.

## Rate limiting e best practices

### Rate limiting

Le API hanno dei **limiti di utilizzo** per evitare sovraccarichi. Se fai troppe richieste in poco tempo, ricevi un errore.

**Analogia**: E' come il limite di velocita' in autostrada. Anche se la tua auto va piu' forte, non puoi superare un certo numero di richieste al minuto.

```
  Richieste per minuto: 60 (1 al secondo)

  Richiesta 1  ✅ OK
  Richiesta 2  ✅ OK
  ...
  Richiesta 60 ✅ OK
  Richiesta 61 ❌ Errore 429: "Too Many Requests"
                  (Troppe richieste, rallenta!)
```

### Best practices per usare le API

1. **Gestisci gli errori**: non dare per scontato che ogni richiesta andra' a buon fine
2. **Rispetta i rate limit**: aspetta se ricevi un errore 429
3. **Salva la tua API key al sicuro**: mai scriverla nel codice visibile; usa file `.env`
4. **Leggi la documentazione**: ogni API ha le sue regole
5. **Usa HTTPS**: mai inviare dati su connessioni non sicure (HTTP)

## Esempi dalle API del progetto

### API di Anthropic (Claude)

Nel progetto adrow-leads-bot (`bot.py`), un bot Telegram potrebbe usare l'API di Claude per generare risposte intelligenti:

```python
# Chiamata all'API di Anthropic
import anthropic

client = anthropic.Anthropic(api_key="sk-ant-...")
response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=1024,
    messages=[{"role": "user", "content": "Analizza questo lead..."}]
)
```

### API di Telegram

I bot nel progetto (adrow-bot, adrow-leads-bot) usano l'API di Telegram per ricevere e inviare messaggi:

```python
# Esempio concettuale di API Telegram
import requests

TELEGRAM_TOKEN = "il-tuo-token"
url = f"https://api.telegram.org/bot{TELEGRAM_TOKEN}/sendMessage"
data = {
    "chat_id": 123456789,
    "text": "Ecco il report della ricerca di mercato!"
}
response = requests.post(url, json=data)
```

### API di Meta (Facebook/Instagram)

Il progetto Adrow si collega all'API di Meta per gestire campagne pubblicitarie:

```
GET  https://graph.facebook.com/v18.0/act_123/campaigns
     → Ottiene le campagne dell'account pubblicitario

POST https://graph.facebook.com/v18.0/act_123/campaigns
     → Crea una nuova campagna
```

---

# 9. Il Terminal / Command Line

## Cos'e' il terminale e perche' e' importante

Il **terminale** (chiamato anche **console**, **shell**, o **command line**) e' un'interfaccia testuale per comunicare con il tuo computer. Invece di cliccare con il mouse su icone e menu, scrivi comandi testuali.

**Analogia**: Se l'interfaccia grafica (icone, finestre, menu) e' come ordinare al ristorante indicando le foto sul menu, il terminale e' come parlare direttamente con lo chef — piu' preciso, piu' veloce, piu' potente, ma devi conoscere la lingua.

### Perche' e' importante

- **Velocita'**: molte operazioni sono piu' rapide via terminale che via interfaccia grafica
- **Potenza**: alcune operazioni sono possibili SOLO via terminale
- **Automazione**: puoi creare script che eseguono sequenze di comandi automaticamente
- **Git**: Git si usa principalmente dal terminale
- **Claude Code**: Claude Code e' un'applicazione da terminale
- **Server**: i server (i computer che ospitano siti web) spesso hanno solo il terminale

### Come aprirlo

- **macOS**: Cerca "Terminale" (Terminal) in Spotlight, oppure vai in Applicazioni > Utility > Terminale
- **Windows**: Cerca "PowerShell" o "Prompt dei comandi" nel menu Start. Ancora meglio: installa Windows Terminal o WSL (Windows Subsystem for Linux)
- **Linux**: Cerca "Terminal" nel menu delle applicazioni

## Comandi base

### Navigare tra le cartelle

```bash
# Dove sono adesso?
pwd
# Output: /Users/stefanodecubellis/Desktop/Project /Skill

# Cosa c'e' in questa cartella?
ls
# Output:
# DOCUMENTAZIONE.md    critical-review/    skill-creator.md
# README.md            market-research/

# Vedere piu' dettagli (permessi, dimensioni, date)
ls -la
# Output:
# -rw-r--r--  27273 Mar 25 17:54 DOCUMENTAZIONE.md
# drwxr-xr-x     96 Feb  7 16:15 critical-review/
# -rw-r--r--   5405 Feb  7 16:08 market-research/
# ...

# Entrare in una cartella
cd critical-review

# Tornare alla cartella superiore
cd ..

# Andare alla propria cartella home
cd ~

# Andare a un percorso specifico
cd /Users/stefanodecubellis/Desktop/Project\ /Skill
```

**Analogia**: `pwd` e' come chiedere "in che via sono?". `ls` e' come guardare l'elenco dei negozi nella via. `cd` e' come camminare verso una destinazione.

### Gestire file e cartelle

```bash
# Creare una cartella
mkdir copywriting
# → Crea la cartella "copywriting"

# Creare una cartella con sotto-cartelle
mkdir -p copywriting/scripts/helpers
# → Crea tutta la struttura, anche se le cartelle intermedie non esistono

# Creare un file vuoto
touch copywriting/copywriting.md

# Copiare un file
cp skill-creator.md skill-creator-backup.md

# Copiare una cartella (con tutto il contenuto)
cp -r critical-review/ critical-review-backup/

# Spostare/rinominare un file
mv skill-creator-backup.md backups/skill-creator-backup.md

# Eliminare un file (ATTENZIONE: non finisce nel cestino!)
rm skill-creator-backup.md

# Eliminare una cartella con tutto il contenuto
rm -r critical-review-backup/
```

### Leggere il contenuto dei file

```bash
# Leggere tutto il contenuto di un file
cat README.md

# Leggere solo le prime 10 righe
head -10 README.md

# Leggere solo le ultime 10 righe
tail -10 README.md

# Cercare testo dentro i file
grep "market-research" README.md
# → Mostra tutte le righe che contengono "market-research"

# Cercare in tutti i file della cartella
grep -r "description" .
# → Cerca "description" in tutti i file, ricorsivamente
```

### Tabella riassuntiva

| Comando | Cosa fa | Esempio |
|---------|---------|---------|
| `pwd` | Mostra la cartella corrente | `pwd` |
| `ls` | Elenca i file nella cartella | `ls -la` |
| `cd` | Cambia cartella | `cd critical-review` |
| `mkdir` | Crea una cartella | `mkdir nuova-skill` |
| `touch` | Crea un file vuoto | `touch file.md` |
| `cp` | Copia file/cartelle | `cp file1.md file2.md` |
| `mv` | Sposta/rinomina | `mv vecchio.md nuovo.md` |
| `rm` | Elimina file/cartelle | `rm file.md` |
| `cat` | Mostra contenuto file | `cat README.md` |
| `head` | Mostra le prime N righe | `head -20 file.md` |
| `tail` | Mostra le ultime N righe | `tail -20 file.md` |
| `grep` | Cerca testo nei file | `grep "parola" file.md` |
| `echo` | Stampa testo | `echo "Ciao mondo"` |
| `clear` | Pulisce lo schermo | `clear` |
| `man` | Mostra il manuale di un comando | `man ls` |

## Variabili d'ambiente e file .env

Le **variabili d'ambiente** sono valori che il sistema operativo rende disponibili a tutti i programmi. Servono per configurazioni che non vuoi scrivere nel codice (come password e chiavi API).

```bash
# Vedere tutte le variabili d'ambiente
env

# Vedere una variabile specifica
echo $HOME
# Output: /Users/stefanodecubellis

# Impostare una variabile temporanea (vale solo in questa sessione)
export API_KEY="sk-ant-api03-xxxxx"

# Usarla
echo $API_KEY
# Output: sk-ant-api03-xxxxx
```

### Il file .env

Il file `.env` e' un file che contiene variabili d'ambiente specifiche per un progetto. NON va mai condiviso pubblicamente (contiene segreti!).

```bash
# Esempio di file .env del progetto adrow-leads-bot:
TELEGRAM_BOT_TOKEN=1234567890:ABCdefGHIjklMNOpqrSTUvwxYZ
ANTHROPIC_API_KEY=sk-ant-api03-xxxxx
DATABASE_URL=postgresql://user:pass@host:5432/db
```

**Regola fondamentale**: Il file `.env` va SEMPRE inserito nel `.gitignore` per evitare di pubblicare le password su GitHub.

Ecco perche' nei progetti trovi spesso un file `.env.example`:

```bash
# .env.example (questo SI' puo' andare su GitHub)
TELEGRAM_BOT_TOKEN=il-tuo-token-qui
ANTHROPIC_API_KEY=la-tua-chiave-qui
DATABASE_URL=il-tuo-database-url-qui
```

## PATH: come il computer trova i programmi

Quando scrivi un comando come `git` o `python3`, il computer deve sapere DOVE si trova quel programma. La variabile **PATH** contiene la lista di cartelle dove cercare.

```bash
# Vedere il PATH
echo $PATH
# Output (esempio):
# /usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin

# Il computer cerca in ordine:
# 1. /usr/local/bin    ← c'e' "git" qui? Si'! Lo eseguo.
# 2. /usr/bin
# 3. /bin
# 4. /usr/sbin
# 5. /sbin
```

**Analogia**: Il PATH e' come la rubrica telefonica. Quando chiami "git", il computer scorre la rubrica (le cartelle nel PATH) fino a trovare il numero (il file eseguibile).

Se ricevi l'errore `command not found`, significa che il programma non e' in nessuna delle cartelle del PATH. Devi installarlo o aggiungere la sua cartella al PATH.

## Package manager: installare programmi

Un **package manager** (gestore di pacchetti) e' un programma che installa, aggiorna e rimuove altri programmi per te. Come un app store per il terminale.

| Package manager | Per cosa | Sistema | Esempio |
|-----------------|----------|---------|---------|
| **brew** (Homebrew) | Programmi generali | macOS, Linux | `brew install git` |
| **pip** | Librerie Python | Tutti | `pip install anthropic` |
| **npm** | Librerie JavaScript / Node.js | Tutti | `npm install express` |
| **apt** | Programmi generali | Ubuntu/Debian Linux | `apt install git` |

```bash
# Installare Homebrew (macOS)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Installare Git con Homebrew
brew install git

# Installare una libreria Python
pip install anthropic

# Installare le dipendenze di un progetto Python
pip install -r requirements.txt
# (il file requirements.txt contiene la lista delle librerie necessarie)

# Vedere cosa e' installato
pip list
brew list
npm list
```

**Esempio dal progetto**: Il file `requirements.txt` del progetto adrow-leads-bot contiene le librerie Python necessarie per far funzionare il bot:

```
python-telegram-bot==20.x
anthropic==0.x.x
requests==2.x.x
```

Per installare tutto: `pip install -r requirements.txt`

---

# 10. Docker e Deploy

## Cos'e' un container e perche' serve

Hai mai sentito la frase "sul mio computer funziona!"? Questo succede perche' ogni computer ha configurazioni diverse: versioni diverse di Python, librerie diverse, sistemi operativi diversi. Un programma che funziona su un computer potrebbe non funzionare su un altro.

I **container** risolvono questo problema: impacchettano il tuo programma insieme a TUTTO cio' di cui ha bisogno (sistema operativo, librerie, configurazioni) in un unico "pacchetto" che funziona ovunque.

## Docker spiegato con analogia

**Analogia del container marittimo**: Prima dei container, le merci venivano caricate alla rinfusa sulle navi. Ogni porto aveva procedure diverse, ogni merce aveva esigenze diverse. Era un caos.

Poi e' arrivato il container standardizzato: un grande "scatolone" di dimensioni standard che contiene qualsiasi tipo di merce. Le gru, le navi e i camion sanno tutti come gestire un container. Non importa cosa c'e' dentro.

```
  SENZA DOCKER:                      CON DOCKER:

  ┌─────────────────┐               ┌─────────────────┐
  │  Il tuo PC      │               │  Container      │
  │  ┌───────────┐  │               │  ┌───────────┐  │
  │  │ Python 3.9│  │               │  │ Python 3.11│ │
  │  │ lib v1.2  │  │               │  │ lib v2.0   │ │
  │  │ macOS     │  │               │  │ Linux      │ │
  │  │ ✅ Funziona│ │               │  │ Il tuo bot │ │
  │  └───────────┘  │               │  └───────────┘  │
  └─────────────────┘               └─────────────────┘
                                           │
  ┌─────────────────┐               Funziona OVUNQUE:
  │  Server         │               - Sul tuo PC
  │  ┌───────────┐  │               - Sul server
  │  │ Python 3.7│  │               - Su Railway
  │  │ lib v1.0  │  │               - Su AWS
  │  │ Linux     │  │               - Su qualsiasi
  │  │ ❌ NON     │  │                 computer con
  │  │  funziona!│  │                 Docker installato
  │  └───────────┘  │
  └─────────────────┘
```

## I concetti di Docker

### Immagine (Image)

Un'**immagine Docker** e' il "progetto" del container — contiene tutte le istruzioni per creare il container. E' come la ricetta di una torta.

### Container

Il **container** e' l'immagine "in esecuzione" — e' la torta fatta seguendo la ricetta. Puoi creare tanti container dalla stessa immagine.

### Dockerfile

Il **Dockerfile** e' il file che contiene le istruzioni per costruire un'immagine. E' la ricetta scritta.

```dockerfile
# Esempio di Dockerfile per un bot Python (come adrow-leads-bot)

# 1. Parti da un'immagine base con Python
FROM python:3.11-slim

# 2. Crea una cartella di lavoro nel container
WORKDIR /app

# 3. Copia il file delle dipendenze
COPY requirements.txt .

# 4. Installa le dipendenze
RUN pip install -r requirements.txt

# 5. Copia tutto il codice del progetto
COPY . .

# 6. Comando per avviare il bot
CMD ["python", "bot.py"]
```

Leggiamo riga per riga:
- `FROM python:3.11-slim` → "Parti da un computer con Python 3.11 installato"
- `WORKDIR /app` → "Vai nella cartella /app"
- `COPY requirements.txt .` → "Copia il file requirements.txt nel container"
- `RUN pip install...` → "Installa le librerie"
- `COPY . .` → "Copia tutti i file del progetto"
- `CMD ["python", "bot.py"]` → "Quando il container parte, esegui il bot"

### docker-compose

**docker-compose** serve quando il tuo progetto ha bisogno di piu' servizi che lavorano insieme (es. il bot + un database + un server web).

```yaml
# docker-compose.yml
version: '3'
services:
  bot:
    build: .
    environment:
      - TELEGRAM_BOT_TOKEN=${TELEGRAM_BOT_TOKEN}
      - ANTHROPIC_API_KEY=${ANTHROPIC_API_KEY}
    restart: always

  database:
    image: postgres:15
    environment:
      - POSTGRES_PASSWORD=${DB_PASSWORD}
    volumes:
      - db_data:/var/lib/postgresql/data

volumes:
  db_data:
```

**Analogia**: Se il Dockerfile e' la ricetta per un piatto, docker-compose e' il menu completo del ristorante — coordina piu' piatti (servizi) per creare il pasto completo.

### Comandi Docker fondamentali

```bash
# Costruire un'immagine dal Dockerfile
docker build -t mio-bot .

# Avviare un container
docker run mio-bot

# Vedere i container in esecuzione
docker ps

# Fermare un container
docker stop <id-container>

# Avviare con docker-compose (tutti i servizi)
docker-compose up

# Fermare con docker-compose
docker-compose down
```

## Cos'e' il deploy e come funziona

Il **deploy** (distribuzione) e' il processo di mettere il tuo software a disposizione degli utenti. E' il momento in cui il tuo programma passa dal tuo computer a un server accessibile da tutti.

```
  ┌───────────────┐                    ┌───────────────┐
  │  Il tuo       │     DEPLOY         │  Server       │
  │  computer     │ ──────────────>    │  (cloud)      │
  │               │                    │               │
  │  Qui sviluppi │                    │  Qui il       │
  │  e testi      │                    │  programma    │
  │               │                    │  e' accessibile│
  │               │                    │  a tutti      │
  └───────────────┘                    └───────────────┘
```

### Metodi di deploy

| Metodo | Come funziona | Per chi |
|--------|--------------|---------|
| **Manuale** | Copi i file sul server a mano | Principianti, progetti piccoli |
| **Git push** | Fai push su un branch e il deploy parte automaticamente | La maggior parte dei progetti |
| **CI/CD** | Pipeline automatiche di test + deploy | Team strutturati |
| **Container** | Costruisci un container Docker e lo invii al server | Progetti complessi |

## Piattaforme di deploy

| Piattaforma | Tipo | Ideale per | Costo |
|-------------|------|------------|-------|
| **Railway** | PaaS (Platform as a Service) | Bot, API, microservizi | Gratis (limitato), poi a consumo |
| **Heroku** | PaaS | App web, API | Gratis (limitato), piani a pagamento |
| **Vercel** | PaaS (specializzato frontend) | Siti web, app React/Next.js | Gratis (generoso), piani a pagamento |
| **Netlify** | PaaS (specializzato frontend) | Siti statici, documentazione | Gratis (generoso) |
| **AWS** | IaaS (Infrastructure as a Service) | Tutto, qualsiasi scala | A consumo (complesso) |
| **Google Cloud** | IaaS | Tutto, integrazione con Google | A consumo |
| **DigitalOcean** | IaaS | Server semplici, economici | Da $4/mese |

### Come viene deployato questo progetto

Il progetto **Skill** non ha un deploy tradizionale perche' e' una collezione di file Markdown. Pero' i progetti collegati si':

**adrow-bot** (bot Telegram): utilizza **Railway** per il deploy. Il file `railway.toml` nella root del progetto configura il deployment:

```toml
# railway.toml
[build]
builder = "nixpacks"

[deploy]
startCommand = "python bot.py"
```

Il flusso di deploy:

```
  1. Sviluppi in locale
     │
  2. Fai commit e push su GitHub
     │    git push origin main
     │
  3. Railway rileva il push
     │    (webhook automatico)
     │
  4. Railway costruisce il progetto
     │    (legge requirements.txt, installa dipendenze)
     │
  5. Railway avvia il bot
     │    (esegue: python bot.py)
     │
  6. Il bot e' online! ✅
     I messaggi Telegram vengono gestiti
```

**Per le skills**: Il "deploy" delle skills consiste nel pacchettizzarle in file `.skill` (che sono ZIP rinominati) e distribuirle manualmente o tramite il repository GitHub. In futuro, con una pipeline CI/CD, questo processo sara' automatizzato.

**Procfile**: Alcuni progetti usano un file `Procfile` per dire alla piattaforma come avviare l'applicazione:

```
# Procfile del progetto adrow-leads-bot
worker: python bot.py
```

Questo dice: "Il mio programma e' un processo worker (non un sito web), e si avvia con il comando `python bot.py`."

---

# Glossario Completo

Elenco di oltre 80 termini tecnici spiegati in modo semplice, in ordine alfabetico.

| # | Termine | Spiegazione |
|---|---------|-------------|
| 1 | **Agente AI** | Un sistema di intelligenza artificiale che agisce autonomamente, usando strumenti e prendendo decisioni per raggiungere un obiettivo. Come un assistente personale digitale. |
| 2 | **Agile** | Metodologia di sviluppo software basata su rilasci frequenti, collaborazione e adattamento al cambiamento. L'opposto del "faccio tutto e consegno alla fine". |
| 3 | **AI (Intelligenza Artificiale)** | Tecnologia che permette ai computer di svolgere compiti che normalmente richiedono intelligenza umana (capire il linguaggio, riconoscere immagini, prendere decisioni). |
| 4 | **Allucinazione** | Quando un modello AI genera informazioni false presentandole come vere. Come uno studente che inventa risposte plausibili all'esame. |
| 5 | **API (Application Programming Interface)** | Un modo standardizzato per far comunicare due programmi tra loro. Come il cameriere che porta il tuo ordine dalla sala alla cucina. |
| 6 | **API Key** | Una stringa segreta (come una password) usata per autenticarsi quando si usa un'API. Va tenuta segreta e mai condivisa nel codice. |
| 7 | **Assets** | File di risorse (immagini, template, dati) inclusi in un progetto o in una skill. |
| 8 | **Autenticazione** | Il processo di verificare l'identita' di chi sta facendo una richiesta. "Chi sei?" |
| 9 | **Backend** | La parte di un'applicazione che l'utente non vede: server, database, logica di business. Come la cucina di un ristorante. |
| 10 | **Bearer Token** | Un tipo di credenziale temporanea usata per l'autenticazione API. Come un braccialetto identificativo. |
| 11 | **Bias** | Pregiudizi o parzialita' nei dati o nei modelli AI che possono portare a risultati distorti o ingiusti. |
| 12 | **Branch** | Un "ramo" di sviluppo in Git. Permette di lavorare su una funzionalita' senza influenzare il codice principale. |
| 13 | **Bug** | Un errore nel codice che causa un comportamento inatteso. La parola "bug" (insetto) nasce da una falena trovata in un computer nel 1947. |
| 14 | **CI/CD** | Continuous Integration / Continuous Delivery. Automazione dei test e del deploy: ogni modifica viene testata e pubblicata automaticamente. |
| 15 | **CLI (Command Line Interface)** | Interfaccia a riga di comando. Un modo di interagire con il computer scrivendo comandi testuali. Es: terminale, Claude Code. |
| 16 | **Clone** | Scaricare una copia completa di un repository Git da remoto al tuo computer. |
| 17 | **Cloud** | Server remoti accessibili via internet, gestiti da aziende come AWS, Google, Microsoft. "Il cloud e' il computer di qualcun altro." |
| 18 | **Codebase** | L'insieme completo di tutto il codice sorgente e i file di un progetto. |
| 19 | **Commit** | Un "salvataggio" in Git. Una foto istantanea del progetto con un messaggio descrittivo. |
| 20 | **Compilatore** | Un programma che traduce tutto il codice sorgente in linguaggio macchina in un colpo solo, prima dell'esecuzione. |
| 21 | **Conflict** | Quando due modifiche incompatibili si sovrappongono nello stesso punto del codice. Git chiede all'utente di risolvere. |
| 22 | **Constitutional AI** | L'approccio di Anthropic per rendere i modelli AI sicuri, basato su un insieme di principi etici. |
| 23 | **Container** | Un ambiente isolato che contiene un programma e tutte le sue dipendenze. Come un container marittimo standardizzato. |
| 24 | **Context Window** | La quantita' massima di testo che un modello AI puo' considerare in una conversazione. Come la memoria a breve termine. |
| 25 | **CSS** | Cascading Style Sheets. Il linguaggio che definisce l'aspetto visivo di una pagina web (colori, dimensioni, layout). |
| 26 | **Database** | Un sistema organizzato per archiviare e recuperare grandi quantita' di dati. Come un archivio ordinato. |
| 27 | **Debug** | Il processo di trovare e correggere errori (bug) nel codice. |
| 28 | **Deep Learning** | Sottoinsieme del Machine Learning che usa reti neurali profonde (con molti strati) per apprendere pattern complessi dai dati. |
| 29 | **Deploy** | Mettere un software a disposizione degli utenti finali, tipicamente su un server. |
| 30 | **Developer (Sviluppatore)** | La persona che scrive il codice. |
| 31 | **DevOps** | Pratiche e ruolo che uniscono sviluppo (Dev) e operazioni (Ops) per automatizzare e velocizzare il ciclo di vita del software. |
| 32 | **Docker** | Software per creare e gestire container. Permette di impacchettare un'applicazione con tutto il necessario per farla funzionare ovunque. |
| 33 | **Dockerfile** | File di istruzioni che definisce come costruire un'immagine Docker. La "ricetta" del container. |
| 34 | **Endpoint** | Un indirizzo specifico di un'API dove puoi inviare richieste. Come un numero di telefono specifico in un'azienda. |
| 35 | **Environment (Ambiente)** | Un contesto in cui il software viene eseguito: development (sviluppo), staging (test), production (utenti reali). |
| 36 | **Fine-tuning** | Processo di addestramento aggiuntivo di un modello AI pre-addestrato per renderlo specializzato in un compito specifico. |
| 37 | **Fork** | Una copia personale di un repository di qualcun altro su GitHub, che puoi modificare liberamente. |
| 38 | **Framework** | Un insieme di strumenti e librerie che forniscono una struttura predefinita per sviluppare software. Come un kit di costruzione. |
| 39 | **Frontend** | La parte di un'applicazione che l'utente vede e con cui interagisce: la pagina web, l'app mobile. Come la sala di un ristorante. |
| 40 | **Frontmatter** | La sezione iniziale di un file Markdown, racchiusa tra `---`, che contiene metadati in formato YAML. |
| 41 | **Function Calling** | La capacita' di un modello AI di chiamare funzioni esterne per svolgere azioni (leggere file, cercare online, eseguire codice). Sinonimo di "tool use". |
| 42 | **Git** | Sistema di controllo versione distribuito. Tiene traccia di tutte le modifiche ai file nel tempo. |
| 43 | **GitHub** | Piattaforma web che ospita repository Git online, con funzionalita' di collaborazione (PR, Issues, Actions). |
| 44 | **GitHub Actions** | Servizio di automazione CI/CD integrato in GitHub. Esegue workflow automatici su push, PR o altri eventi. |
| 45 | **Gitignore (.gitignore)** | File che dice a Git quali file/cartelle ignorare (non tracciare). Es: .env, .DS_Store, node_modules/. |
| 46 | **GPT** | Generative Pre-trained Transformer. Famiglia di modelli linguistici di OpenAI (GPT-3.5, GPT-4, GPT-4o). |
| 47 | **HTML** | HyperText Markup Language. Il linguaggio che definisce la struttura di una pagina web (titoli, paragrafi, link, immagini). |
| 48 | **HTTP/HTTPS** | I protocolli con cui il browser comunica con i server web. HTTPS e' la versione sicura (crittografata). |
| 49 | **IDE** | Integrated Development Environment. Un editor di codice avanzato con strumenti integrati (debug, terminale, Git). Es: VS Code. |
| 50 | **Inference** | Il processo in cui un modello AI genera una risposta a partire da un input. Come rispondere a una domanda d'esame. |
| 51 | **Interprete** | Un programma che legge ed esegue il codice riga per riga, in tempo reale. Python usa un interprete. |
| 52 | **Issue** | Un "ticket" su GitHub per segnalare bug, proporre funzionalita' o discutere miglioramenti del progetto. |
| 53 | **JSON** | JavaScript Object Notation. Formato standard per scambiare dati strutturati. Leggibile da umani e computer. |
| 54 | **Kanban** | Metodo di gestione del lavoro basato su una lavagna con colonne (Da fare, In corso, Fatto). Visivo e flessibile. |
| 55 | **Libreria (Library)** | Codice pre-scritto che puoi riusare nel tuo progetto per non dover reinventare la ruota. Es: `requests` per fare chiamate HTTP in Python. |
| 56 | **Linux** | Sistema operativo open source, molto usato per i server. La base di Android. |
| 57 | **LLM (Large Language Model)** | Un grande modello linguistico addestrato su enormi quantita' di testo per capire e generare linguaggio. Es: Claude, GPT, Gemini. |
| 58 | **Machine Learning** | Apprendimento automatico. Un approccio all'AI dove il sistema impara dai dati invece di essere programmato esplicitamente con regole. |
| 59 | **Main (branch)** | Il ramo principale di un repository Git. Contiene il codice "ufficiale" e stabile. |
| 60 | **Markdown** | Linguaggio di markup leggero per formattare testo. Usa simboli come `#` per titoli, `**` per grassetto. I file hanno estensione `.md`. |
| 61 | **MCP (Model Context Protocol)** | Standard creato da Anthropic per permettere agli agenti AI di connettersi a strumenti e servizi esterni in modo standardizzato. |
| 62 | **Merge** | L'operazione di unire le modifiche di un branch in un altro. Come incorporare le modifiche della bozza nel documento finale. |
| 63 | **Meta-skill** | Una skill che insegna a creare altre skills. Nel progetto: `skill-creator.md`. |
| 64 | **Microservizio** | Un componente software piccolo e indipendente che fa una sola cosa. L'opposto di un monolite (un unico programma che fa tutto). |
| 65 | **npm** | Node Package Manager. Il gestore di pacchetti per JavaScript/Node.js. Come un app store per librerie JS. |
| 66 | **OAuth** | Protocollo di autenticazione che permette di accedere a un servizio tramite un altro (es. "Accedi con Google"). |
| 67 | **Open Source** | Software il cui codice sorgente e' pubblico e gratuito. Chiunque puo' leggerlo, modificarlo e distribuirlo. |
| 68 | **PaaS (Platform as a Service)** | Servizio cloud che ti fornisce una piattaforma pronta per eseguire il tuo codice, senza dover gestire server. Es: Railway, Heroku. |
| 69 | **Package Manager** | Programma che installa, aggiorna e rimuove librerie e dipendenze. Es: pip (Python), npm (JavaScript), brew (macOS). |
| 70 | **Parametri (di un modello)** | I valori numerici interni di un modello AI che vengono "imparati" durante l'addestramento. Piu' parametri = piu' capacita'. |
| 71 | **PATH** | Variabile d'ambiente che contiene la lista di cartelle dove il sistema cerca i programmi eseguibili. |
| 72 | **pip** | Il package manager di Python. Installa librerie Python. Es: `pip install anthropic`. |
| 73 | **Plugin** | Un componente aggiuntivo che estende le funzionalita' di un programma. Nel progetto: `claude-mem` per la memoria persistente. |
| 74 | **Pre-training** | La prima fase di addestramento di un LLM, in cui legge enormi quantita' di testo per apprendere i pattern del linguaggio. |
| 75 | **Production** | L'ambiente reale dove il software e' usato dagli utenti finali. Errori qui impattano gli utenti. |
| 76 | **Progressive Disclosure** | Principio di design: mostrare prima le informazioni essenziali e i dettagli solo quando servono. Usato nell'architettura delle skills. |
| 77 | **Prompt** | L'input testuale che invii a un modello AI. La "domanda" o "richiesta" che fai a Claude. |
| 78 | **Pull** | Scaricare le ultime modifiche dal repository remoto al tuo computer locale. |
| 79 | **Pull Request (PR)** | Proposta di modifica su GitHub: "Ho fatto queste modifiche, potete controllarle e approvarle?" |
| 80 | **Push** | Inviare i tuoi commit dal computer locale al repository remoto (GitHub). |
| 81 | **Python** | Linguaggio di programmazione molto popolare, noto per la sua leggibilita'. Usato per AI, automazione, web, analisi dati. |
| 82 | **QA (Quality Assurance)** | Assicurazione qualita'. Il processo (e il ruolo) di verificare che il software funzioni correttamente prima del rilascio. |
| 83 | **Rate Limiting** | Limite al numero di richieste che puoi fare a un'API in un dato periodo. Serve a proteggere il server da sovraccarichi. |
| 84 | **README** | File di presentazione di un progetto (solitamente `README.md`). La prima cosa che leggi quando apri un repository. |
| 85 | **Repository (Repo)** | Il "contenitore" di un progetto in Git. Include tutti i file, la cronologia delle modifiche e le configurazioni. |
| 86 | **REST** | Representational State Transfer. Lo stile architetturale piu' comune per le API web. Usa metodi HTTP (GET, POST, PUT, DELETE). |
| 87 | **RLHF** | Reinforcement Learning from Human Feedback. Tecnica per migliorare i modelli AI usando valutazioni umane delle risposte. |
| 88 | **Scrum** | Framework Agile basato su sprint (periodi fissi), daily standup, sprint review e retrospective. |
| 89 | **Server** | Un computer (spesso remoto) che fornisce servizi ad altri computer. Ospita siti web, API, database. |
| 90 | **Skill** | Nel contesto del progetto: un pacchetto modulare che estende le capacita' di Claude con conoscenze, workflow e strumenti specializzati. |
| 91 | **Staging** | Ambiente di test che replica la produzione. Si usa per verifiche finali prima del rilascio agli utenti. |
| 92 | **Terminal (Terminale)** | Interfaccia testuale per comunicare con il computer tramite comandi. |
| 93 | **Token** | L'unita' base di testo per un LLM. Una parola italiana e' circa 1-2 token. I costi API si calcolano in token. |
| 94 | **Tool Use** | La capacita' di un agente AI di usare strumenti esterni (leggere file, eseguire codice, cercare online). Sinonimo di "function calling". |
| 95 | **Training Data** | I dati (testi, immagini, etc.) su cui un modello AI viene addestrato. Determinano cosa il modello "sa". |
| 96 | **Variabile d'ambiente** | Un valore di configurazione disponibile a tutti i programmi del sistema. Usata per dati sensibili (API key, password). |
| 97 | **Version Control** | Sistema per tracciare le modifiche ai file nel tempo. Git e' il sistema di version control piu' usato al mondo. |
| 98 | **VS Code** | Visual Studio Code. Editor di codice gratuito di Microsoft, molto popolare tra gli sviluppatori. Usato in questo progetto. |
| 99 | **Webhook** | Un meccanismo per cui un servizio invia automaticamente dati a un altro quando succede un evento. Come un avviso push. |
| 100 | **Workflow** | Un flusso di lavoro strutturato con passaggi definiti. Nelle skills: la sequenza di fasi che Claude deve seguire. |
| 101 | **YAML** | "YAML Ain't Markup Language". Formato per dati strutturati, leggibile dagli umani. Usato nel frontmatter delle skills. |
| 102 | **ZIP** | Formato di compressione file. I file `.skill` del progetto sono ZIP rinominati. |

---

> **Nota finale**: Questo tutorial e' stato scritto per essere un punto di partenza. La tecnologia si evolve rapidamente — i concetti fondamentali restano, ma gli strumenti e le versioni cambiano. Il consiglio migliore? **Sperimenta**. Apri il terminale, prova i comandi Git, leggi i file del progetto, rompi qualcosa e impara a ripararlo. E' cosi' che si diventa sviluppatori.
>
> **Ultimo aggiornamento**: 25 Marzo 2026
