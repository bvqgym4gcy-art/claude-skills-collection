# Claude Skills Collection

> Raccolta di skills modulari per estendere le capacità di Claude Code con competenze specializzate

## Descrizione

**Claude Skills Collection** è un progetto che raccoglie **skills** — competenze modulari e auto-contenute — progettate per trasformare Claude, l'assistente AI di Anthropic, da agente generico a specialista in ambiti specifici. Le skills funzionano come manuali di istruzioni specializzati che forniscono a Claude conoscenze procedurali, flussi di lavoro strutturati e strumenti per compiti complessi.

Il progetto nasce dall'esigenza di colmare il gap tra le capacità generiche di un modello AI e le necessità operative reali: analisi critica di progetti, ricerche di mercato approfondite e creazione di nuove competenze in modo sistematico.

È pensato per sviluppatori, professionisti e team che utilizzano Claude Code come strumento di lavoro quotidiano e vogliono potenziarne le capacità in domini specifici.

## Obiettivi

- **Estendere le capacità di Claude** con conoscenze procedurali che nessun modello AI può possedere nativamente
- **Standardizzare flussi di lavoro complessi** attraverso procedure step-by-step riproducibili
- **Creare un ecosistema modulare** dove ogni skill è indipendente, testabile e distribuibile
- **Fornire una meta-skill** (Skill Creator) per consentire la creazione autonoma di nuove competenze
- **Garantire qualità e rigore** nei processi di analisi e ricerca attraverso framework strutturati

## Funzionalità

### Funzionalità esistenti

- **Revisione Critica (Critical Review)** — Analisi strutturata fase per fase di qualsiasi compito complesso, con valutazione su 9 dimensioni: assunzioni, alternative, rischi, dipendenze, costo/impegno, scalabilità, manutenibilità, casi limite e allineamento
- **Ricerca di Mercato (Market Research)** — Conduzione di ricerche di mercato complete in 5 fasi: briefing, analisi di mercato, analisi competitiva (8-12 competitor su 3 livelli), identificazione angoli di comunicazione e compilazione report strutturato
- **Creazione di Skills (Skill Creator)** — Meta-skill che guida nella creazione di nuove skills seguendo un processo in 6 fasi, con principi di design (concisione, gradi di libertà, progressive disclosure) e strumenti di inizializzazione e pacchettizzazione

### Funzionalità in sviluppo

- Espansione della libreria con nuove skills per domini verticali
- Integrazione di script Python per automazione e validazione
- Sistema di distribuzione tramite file `.skill` pacchettizzati

## Stack Tecnologico

| Tecnologia | Ruolo nel progetto |
|---|---|
| **Markdown (.md)** | Formato principale per la definizione delle skills e della documentazione |
| **YAML** | Metadati delle skills nel frontmatter (nome, descrizione, trigger) |
| **Claude Code (CLI)** | Ambiente di esecuzione e testing delle skills |
| **Python** | Script di utilità per inizializzazione (`init_skill.py`) e pacchettizzazione (`package_skill.py`) |
| **Git / GitHub** | Versionamento del codice e collaborazione |
| **VS Code** | Editor di sviluppo consigliato con configurazioni personalizzate |

## Architettura

Il sistema si basa su un'architettura a **progressive disclosure** a tre livelli, progettata per gestire efficientemente la finestra di contesto di Claude:

```
┌─────────────────────────────────────────────────────┐
│                   CLAUDE CODE                        │
│                                                      │
│  ┌───────────────────────────────────────────────┐  │
│  │  Livello 1: METADATI (~100 parole)            │  │
│  │  name + description — sempre in contesto      │  │
│  │  → Determina QUANDO attivare la skill         │  │
│  └───────────────────┬───────────────────────────┘  │
│                      │ trigger                       │
│  ┌───────────────────▼───────────────────────────┐  │
│  │  Livello 2: SKILL.md BODY (<5k parole)        │  │
│  │  Istruzioni operative — caricato al trigger   │  │
│  │  → Definisce COME eseguire la skill           │  │
│  └───────────────────┬───────────────────────────┘  │
│                      │ se necessario                 │
│  ┌───────────────────▼───────────────────────────┐  │
│  │  Livello 3: RISORSE BUNDLE (illimitate)       │  │
│  │  scripts/ references/ assets/                 │  │
│  │  → Caricati on-demand da Claude               │  │
│  └───────────────────────────────────────────────┘  │
│                                                      │
└─────────────────────────────────────────────────────┘
```

### Flusso di lavoro di una skill

```
Utente → richiesta a Claude Code
            │
            ▼
   Claude legge i METADATI di tutte le skills
            │
            ▼
   La description matcha la richiesta?
     │                    │
    SÌ                   NO
     │                    │
     ▼                    ▼
  Carica SKILL.md    Risposta generica
     │
     ▼
  Esegue il workflow definito
     │
     ▼
  Carica risorse bundle se necessario
     │
     ▼
  Output strutturato all'utente
```

## Installazione e Setup

### Prerequisiti

- **Git** — per il versionamento del codice
- **Un editor di testo** — consigliato Visual Studio Code
- **Claude Code** (opzionale) — per testare le skills in ambiente reale
- **Python 3** (opzionale) — per gli script di utilità

### Installazione

```bash
# Clona il repository
git clone https://github.com/bvqgym4gcy-art/claude-skills-collection.git

# Entra nella cartella del progetto
cd claude-skills-collection

# (Opzionale) Apri in VS Code
code .
```

### Verifica prerequisiti

```bash
# Verifica Git
git --version

# Verifica Python (opzionale)
python3 --version

# Verifica Claude Code (opzionale)
claude --version
```

## Utilizzo

### Usare una skill esistente

Le skills vengono attivate automaticamente da Claude Code quando la richiesta dell'utente corrisponde alla `description` nel frontmatter YAML. Esempi:

- **Critical Review**: chiedere a Claude "fai una revisione critica di questo progetto" o "metti in discussione ogni fase"
- **Market Research**: chiedere "analizza il mercato per X" o "trova i competitor di X"

### Creare una nuova skill

```bash
# 1. Crea un branch dedicato
git checkout -b feature/nome-nuova-skill

# 2. Inizializza la struttura (se disponibile lo script)
scripts/init_skill.py nome-skill --path ./

# 3. Oppure crea manualmente
mkdir nome-skill
touch nome-skill/nome-skill.md

# 4. Scrivi il frontmatter YAML e il body Markdown

# 5. Testa la skill in Claude Code

# 6. Pacchettizza (se disponibile lo script)
scripts/package_skill.py nome-skill

# 7. Commit e push
git add nome-skill/
git commit -m "Aggiunta skill nome-skill"
git push origin feature/nome-nuova-skill
```

### Struttura di una skill

Ogni file `.md` di una skill deve contenere:

```yaml
---
name: nome-skill
description: Descrizione chiara di cosa fa e quando usarla.
---
```

Seguito dal body in Markdown con le istruzioni operative per Claude.

## Struttura del Progetto

```
claude-skills-collection/
│
├── skill-creator.md              # Meta-skill: guida per creare nuove skills
│                                  # Definisce il processo in 6 fasi, i principi
│                                  # di design e l'anatomia di una skill
│
├── critical-review/              # Skill "Critical Review"
│   └── critical-review.md        # Revisione critica strutturata su 9 dimensioni
│                                  # per qualsiasi compito multi-fase
│
├── market-research/              # Skill "Market Research"
│   └── market-research.md        # Ricerca di mercato completa in 5 fasi
│                                  # con analisi competitiva e angoli comunicativi
│
├── DOCUMENTAZIONE.md             # Documentazione completa del progetto
│                                  # pensata per sviluppatori junior
│
└── README.md                     # Questo file
```

## Problematiche Note / Falle

### Bug e limitazioni conosciute

- **Nessun repository Git era inizializzato** — Il progetto era privo di versionamento fino alla configurazione attuale, con rischio di perdita di modifiche e assenza di cronologia
- **Script di utilità non inclusi** — I file `init_skill.py` e `package_skill.py` sono referenziati nella documentazione e nella meta-skill, ma non sono presenti nel repository. Questo impedisce l'inizializzazione automatizzata e la pacchettizzazione delle skills
- **Nessun sistema di test automatizzato** — Le skills vengono testate solo manualmente tramite Claude Code, senza possibilità di regressione automatica o CI/CD
- **Validazione del frontmatter assente** — Non esiste un meccanismo automatico per verificare che il frontmatter YAML sia corretto e completo

### Debito tecnico

- **Documentazione e codice misallineati** — La `DOCUMENTAZIONE.md` descrive una struttura con cartelle `scripts/`, `references/`, `assets/` e file `.vscode/` che non esistono nel repository Skill
- **Assenza di linting** — Non ci sono strumenti di controllo qualità per i file Markdown (ad es. markdownlint)
- **Nessun file .gitignore** — Manca un `.gitignore` per escludere file di sistema (`.DS_Store`), file temporanei o artefatti di build

### Vulnerabilità architetturali

- **Dipendenza completa da Claude Code** — Le skills funzionano esclusivamente nell'ecosistema Claude Code di Anthropic; un cambio nelle API o nel formato delle skills potrebbe rendere obsoleta l'intera collezione
- **Nessun versionamento semantico delle skills** — Non esiste un meccanismo per tracciare le versioni delle singole skills, rendendo difficile la gestione di compatibilità e aggiornamenti
- **Distribuzione non automatizzata** — Il processo di distribuzione dei file `.skill` è completamente manuale

### Aree di miglioramento

- Aggiungere gli script Python (`init_skill.py`, `package_skill.py`) al repository
- Implementare un file `.gitignore` appropriato
- Creare una pipeline CI/CD per validazione automatica del frontmatter
- Aggiungere test di integrazione con Claude Code
- Implementare versionamento semantico per le singole skills

## Roadmap

- [ ] Aggiungere gli script Python di inizializzazione e pacchettizzazione al repository
- [ ] Implementare `.gitignore` e configurazioni di linting
- [ ] Creare nuove skills per domini aggiuntivi (es. copywriting, analisi dati, code review)
- [ ] Sviluppare un sistema di validazione automatica del frontmatter YAML
- [ ] Implementare versionamento semantico delle skills
- [ ] Creare una pipeline CI/CD per test e distribuzione
- [ ] Documentare le linee guida per i contributi esterni (CONTRIBUTING.md)
- [ ] Pubblicare le skills pacchettizzate come release GitHub

## Autori

| Ruolo | Nome |
|---|---|
| Sviluppatore principale | **Stefano De Cubellis** |
| Assistente AI | **Claude (Anthropic)** — utilizzato come strumento di sviluppo |

## Licenza

Nessuna licenza specificata. Tutti i diritti riservati all'autore.

---

> **Ultimo aggiornamento**: 25 Marzo 2026
