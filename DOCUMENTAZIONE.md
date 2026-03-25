# Documentazione Completa del Progetto Skill

> Questa documentazione e' pensata per sviluppatori junior che si avvicinano per la prima volta al progetto. Ogni concetto viene spiegato in modo chiaro e accessibile.

---

## Indice

1. [Cos'e' questo progetto](#cose-questo-progetto)
2. [Concetti fondamentali](#concetti-fondamentali)
3. [Stack tecnologico](#stack-tecnologico)
4. [Struttura del progetto](#struttura-del-progetto)
5. [Setup e installazione](#setup-e-installazione)
6. [Flusso di sviluppo](#flusso-di-sviluppo)
7. [Operativita'](#operativita)
8. [Sviluppatori](#sviluppatori)
9. [Glossario](#glossario)

---

## Cos'e' questo progetto

Il progetto **Skill** e' una raccolta di **skills** (competenze modulari) progettate per estendere le capacita' di **Claude**, l'assistente AI di Anthropic. In parole semplici, le skills sono come dei "manuali di istruzioni specializzati" che trasformano Claude da un assistente generico a uno specialista in un determinato ambito.

### A cosa serve?

Immagina di avere un assistente molto intelligente ma generico. Le skills gli danno conoscenze specifiche per svolgere compiti particolari in modo eccellente. Ad esempio:

- **Revisione critica**: una skill che insegna a Claude come analizzare in modo rigoroso ogni fase di un lavoro, identificando rischi, alternative e punti deboli
- **Ricerca di mercato**: una skill che guida Claude nella conduzione di ricerche di mercato complete, analisi della concorrenza e individuazione di strategie di comunicazione
- **Creazione di skills**: una meta-skill (cioe' una skill che insegna a creare altre skills) che fornisce le linee guida per costruire nuove competenze

### Perche' esistono le skills?

Quando Claude lavora su un compito complesso, ha bisogno di conoscenze procedurali specifiche che nessun modello AI puo' possedere completamente di suo. Le skills colmano questa lacuna fornendo:

1. **Flussi di lavoro specializzati** - Procedure passo-passo per domini specifici
2. **Integrazioni con strumenti** - Istruzioni per lavorare con formati di file o API specifiche
3. **Competenze di dominio** - Conoscenze specifiche dell'azienda, schemi, logica di business
4. **Risorse incluse** - Script, riferimenti e risorse per compiti complessi e ripetitivi

---

## Concetti fondamentali

Questa sezione spiega i concetti base che ogni sviluppatore deve conoscere prima di lavorare su qualsiasi progetto software.

### Git

#### Cos'e' Git?

**Git** e' un **sistema di controllo versione distribuito**. In parole povere, e' un programma che tiene traccia di tutte le modifiche che fai ai tuoi file nel tempo. Pensa a Git come a una "macchina del tempo" per il tuo codice: puoi tornare indietro a qualsiasi versione precedente, vedere chi ha modificato cosa e quando, e lavorare su piu' versioni contemporaneamente senza rischiare di perdere nulla.

#### Perche' si usa?

- **Sicurezza**: non perdi mai il tuo lavoro, puoi sempre tornare a una versione precedente
- **Collaborazione**: piu' persone possono lavorare sullo stesso progetto senza sovrascriversi a vicenda
- **Tracciabilita'**: ogni modifica e' registrata con autore, data e descrizione

#### Comandi base di Git

| Comando | Cosa fa | Esempio |
|---------|---------|---------|
| `git clone <url>` | Scarica una copia completa di un progetto remoto sul tuo computer | `git clone https://github.com/utente/progetto.git` |
| `git status` | Mostra lo stato dei tuoi file (modificati, nuovi, pronti per il commit) | `git status` |
| `git add <file>` | Prepara un file per essere salvato (lo mette in "staging") | `git add skill-creator.md` |
| `git commit -m "messaggio"` | Salva le modifiche preparate con una descrizione | `git commit -m "Aggiunta nuova skill"` |
| `git push` | Invia i tuoi commit al repository remoto (su GitHub) | `git push origin main` |
| `git pull` | Scarica le ultime modifiche dal repository remoto | `git pull origin main` |
| `git branch <nome>` | Crea un nuovo ramo di sviluppo | `git branch feature/nuova-skill` |
| `git checkout <branch>` | Passa a un altro ramo | `git checkout feature/nuova-skill` |
| `git merge <branch>` | Unisce le modifiche di un ramo nel ramo corrente | `git merge feature/nuova-skill` |
| `git log` | Mostra la storia dei commit | `git log --oneline` |

#### Esempio pratico di flusso Git

```bash
# 1. Clona il progetto (solo la prima volta)
git clone https://github.com/utente/skill.git

# 2. Crea un nuovo branch per la tua modifica
git checkout -b feature/nuova-skill-marketing

# 3. Fai le tue modifiche ai file...

# 4. Controlla cosa hai modificato
git status

# 5. Prepara i file per il commit
git add market-research/market-research.md

# 6. Salva le modifiche con un messaggio descrittivo
git commit -m "Aggiornata la skill di ricerca di mercato con nuove fonti"

# 7. Invia le modifiche al repository remoto
git push origin feature/nuova-skill-marketing
```

---

### GitHub

#### Cos'e' GitHub?

**GitHub** e' una piattaforma web che ospita repository Git. Se Git e' il motore che gestisce le versioni del tuo codice, GitHub e' il "garage" online dove parcheggi il tuo progetto e lo condividi con altri.

#### Differenza tra Git e GitHub

| Git | GitHub |
|-----|--------|
| E' un software che installi sul tuo computer | E' un sito web / servizio cloud |
| Funziona anche offline | Richiede connessione internet |
| Gestisce le versioni dei file | Ospita i repository e facilita la collaborazione |
| E' uno strumento da riga di comando | Ha un'interfaccia grafica web |
| E' gratuito e open source | Ha piani gratuiti e a pagamento |

#### Concetti chiave di GitHub

- **Repository (repo)**: e' la "cartella" del tuo progetto su GitHub. Contiene tutti i file, la cronologia delle modifiche e le configurazioni. Esempio: `github.com/azienda/skill` sarebbe il repository di questo progetto.

- **Issues**: sono i "ticket" del progetto. Servono per segnalare bug, proporre nuove funzionalita' o discutere miglioramenti. Ogni issue ha un titolo, una descrizione, e puo' essere assegnata a una persona.

- **Pull Request (PR)**: quando hai finito di lavorare su un branch, crei una Pull Request per proporre le tue modifiche. E' come dire "Ho finito, potete controllare e approvare il mio lavoro?". La PR permette agli altri di revisionare il codice prima che venga unito al ramo principale.

- **Code Review**: e' il processo in cui altri sviluppatori controllano il tuo codice nella Pull Request. Possono lasciare commenti, suggerire modifiche o approvare. E' una pratica fondamentale per mantenere alta la qualita' del codice.

- **Fork**: e' una copia personale di un repository di qualcun altro. Puoi modificare il fork liberamente senza influenzare il progetto originale.

---

### Sviluppo software

#### Cos'e' lo sviluppo software?

Lo **sviluppo software** e' il processo di creazione, progettazione, scrittura, test e manutenzione di programmi informatici. Non si tratta solo di "scrivere codice", ma di un ciclo completo che va dall'idea iniziale al prodotto finito e alla sua manutenzione nel tempo.

#### Ciclo di vita di un progetto

Un progetto software attraversa tipicamente queste fasi:

1. **Analisi dei requisiti**: capire cosa deve fare il software, chi lo usera' e quali problemi deve risolvere
2. **Progettazione**: decidere l'architettura, le tecnologie, la struttura del codice
3. **Implementazione**: scrivere il codice vero e proprio
4. **Test**: verificare che tutto funzioni come previsto, cercare e correggere bug
5. **Deploy (distribuzione)**: rendere il software disponibile agli utenti
6. **Manutenzione**: correggere bug, aggiungere funzionalita', aggiornare dipendenze

#### Ambienti

Nello sviluppo software si usano diversi **ambienti** (environments) per separare le fasi di lavoro:

| Ambiente | Scopo | Chi lo usa |
|----------|-------|------------|
| **Development (dev)** | Dove gli sviluppatori scrivono e testano il codice sul proprio computer | Sviluppatori |
| **Staging** | Una copia quasi identica all'ambiente di produzione, usata per i test finali prima del rilascio | Team QA, sviluppatori |
| **Production (prod)** | L'ambiente reale usato dagli utenti finali | Utenti finali |

L'idea e' semplice: non vuoi mai testare qualcosa direttamente nell'ambiente che usano i clienti. Per questo si procede per gradi: dev -> staging -> production.

---

### Codebase

#### Cos'e' una codebase?

La **codebase** e' l'insieme completo di tutto il codice sorgente di un progetto. Include tutti i file, le cartelle, le configurazioni e le risorse necessarie per far funzionare il software.

#### Come e' organizzata

Una codebase ben organizzata segue alcune regole:

- **Separazione delle responsabilita'**: ogni cartella e file ha uno scopo preciso
- **Nomi significativi**: file e cartelle hanno nomi che descrivono il loro contenuto
- **Struttura prevedibile**: chi arriva sul progetto deve capire dove trovare le cose
- **Documentazione**: file come README.md o DOCUMENTAZIONE.md spiegano il progetto

#### Best practices

- Mantieni i file piccoli e focalizzati su un unico scopo
- Usa nomi coerenti (in questo progetto: nomi in inglese, minuscoli, separati da trattini)
- Non duplicare informazioni: se qualcosa e' scritta in un posto, non riscriverla in un altro
- Tieni il progetto pulito: rimuovi file non necessari
- Documenta le scelte importanti

---

## Stack tecnologico

Questo progetto ha uno stack tecnologico particolarmente semplice perche' non e' un'applicazione software tradizionale, ma una raccolta di documenti strutturati (skills) per un agente AI.

### Tecnologie utilizzate

| Tecnologia | Tipo | A cosa serve | Spiegazione per principianti |
|------------|------|-------------|------------------------------|
| **Markdown (.md)** | Linguaggio di markup | Scrivere i contenuti delle skills | Markdown e' un modo semplice per formattare testo. Usi simboli come `#` per i titoli, `**testo**` per il grassetto, `-` per le liste. E' il formato standard per la documentazione nel mondo dello sviluppo software. |
| **YAML** | Linguaggio di serializzazione | Definire i metadati delle skills (nome, descrizione) nel frontmatter | YAML e' un formato per scrivere dati strutturati in modo leggibile. Si usa all'inizio dei file Markdown, racchiuso tra `---`, per definire proprieta' come il nome e la descrizione della skill. |
| **Claude Code (CLI)** | Strumento AI | Ambiente di esecuzione per le skills | Claude Code e' l'interfaccia a riga di comando ufficiale di Anthropic per Claude. Le skills sono progettate per essere usate all'interno di questo strumento. |
| **Python** | Linguaggio di programmazione | Script di utilita' (init_skill.py, package_skill.py) | Python e' un linguaggio di programmazione molto popolare e leggibile. Nel contesto delle skills, viene usato per gli script che inizializzano e impacchettano le skills. |
| **VS Code** | Editor di codice | Ambiente di sviluppo | Visual Studio Code e' un editor di codice gratuito di Microsoft, usato per scrivere e modificare i file del progetto. Il progetto include una cartella `.vscode/` con configurazioni personalizzate. |

### Formati dei file

- **`.md`** (Markdown): tutti i contenuti delle skills sono scritti in questo formato
- **`.json`** (JSON): file di configurazione (settings di VS Code e Claude)
- **`.skill`** (formato personalizzato): file di distribuzione delle skills pacchettizzate (in realta' sono file ZIP rinominati)

---

## Struttura del progetto

```
Skill/
|
|-- skill-creator.md              # Meta-skill: guida per creare nuove skills
|
|-- critical-review/              # Cartella della skill "Critical Review"
|   |-- critical-review.md        # Definizione della skill di revisione critica
|
|-- market-research/              # Cartella della skill "Market Research"
|   |-- market-research.md        # Definizione della skill di ricerca di mercato
|
|-- DOCUMENTAZIONE.md             # Questo file di documentazione
```

### Descrizione dettagliata di ogni file

#### `skill-creator.md`

Questo e' il file piu' importante del progetto. E' una **meta-skill**, cioe' una skill che insegna a Claude come creare altre skills. Contiene:

- **Cosa sono le skills**: definizione, scopo, struttura
- **Principi fondamentali**: concisione, gradi di liberta', progressive disclosure
- **Anatomia di una skill**: struttura delle cartelle (SKILL.md, scripts/, references/, assets/)
- **Processo di creazione in 6 fasi**:
  1. Comprendere la skill con esempi concreti
  2. Pianificare i contenuti riutilizzabili
  3. Inizializzare la skill (con `init_skill.py`)
  4. Modificare la skill (implementare risorse e scrivere SKILL.md)
  5. Pacchettizzare la skill (con `package_skill.py`)
  6. Iterare sulla base dell'uso reale

Ogni skill ha un **frontmatter YAML** all'inizio del file che contiene:
- `name`: il nome della skill
- `description`: la descrizione che Claude usa per capire quando attivare la skill

Esempio di frontmatter:
```yaml
---
name: skill-creator
description: Guide for creating effective skills. This skill should be used when...
---
```

#### `critical-review/critical-review.md`

Questa skill insegna a Claude a eseguire una **revisione critica strutturata** su qualsiasi compito complesso. Il flusso di lavoro e':

1. **Scomporre il compito in fasi**: identificare le fasi principali
2. **Revisione critica per fase**: per ogni fase, analizzare 9 dimensioni:
   - Assunzioni: cosa diamo per scontato?
   - Alternative: quali altri approcci esistono?
   - Rischi: cosa puo' andare storto?
   - Dipendenze: da cosa dipende questa fase?
   - Costo/Impegno: e' proporzionato al valore?
   - Scalabilita': reggera' su larga scala?
   - Manutenibilita': sara' facile da capire e modificare?
   - Casi limite: cosa potrebbe rompersi?
   - Allineamento: questa fase e' coerente con l'obiettivo generale?
3. **Eseguire la fase**: procedere con l'implementazione
4. **Transizione alla fase successiva**: riepilogare e passare avanti
5. **Riepilogo finale**: tabella riassuntiva con decisioni, rischi e livello di confidenza

#### `market-research/market-research.md`

Questa skill guida Claude nella conduzione di una **ricerca di mercato completa**. Il processo si articola in 5 fasi:

1. **Briefing**: chiarire con l'utente prodotto, mercato, target, budget e lingua
2. **Ricerca di mercato**: dimensioni del mercato, tendenze, dinamiche, segmenti target
3. **Ricerca sulla concorrenza**: analisi di 8-12 competitor su 3 livelli (diretti, indiretti, aspirazionali)
4. **Angoli di comunicazione**: identificare 5-8 strategie comunicative con nome, messaggio, emozione target, evidenze, canali adatti e headline d'esempio
5. **Compilazione del report**: documento Markdown strutturato con executive summary, panoramica di mercato, pubblico target, panorama competitivo, angoli di comunicazione e raccomandazioni strategiche

---

## Setup e installazione

### Prerequisiti

Prima di iniziare, assicurati di avere installato sul tuo computer:

1. **Git** - per gestire il versioning del codice
   ```bash
   # Verifica se Git e' installato
   git --version
   # Se non e' installato, su macOS:
   xcode-select --install
   ```

2. **Un editor di testo** - consigliato Visual Studio Code
   - Scaricalo da: https://code.visualstudio.com/

3. **Claude Code** (opzionale, per testare le skills)
   - Segui le istruzioni su: https://docs.anthropic.com/en/docs/claude-code

4. **Python 3** (opzionale, per gli script di utilita')
   ```bash
   # Verifica se Python e' installato
   python3 --version
   ```

### Clonare il repository

```bash
# 1. Apri il terminale

# 2. Vai nella cartella dove vuoi scaricare il progetto
cd ~/Desktop

# 3. Clona il repository (sostituisci URL con l'indirizzo reale)
git clone <URL-del-repository>

# 4. Entra nella cartella del progetto
cd Skill
```

### Configurare l'ambiente

Questo progetto non richiede installazione di dipendenze particolari perche' e' composto principalmente da file Markdown. Tuttavia, per un'esperienza di sviluppo ottimale:

1. **Apri il progetto in VS Code**:
   ```bash
   code .
   ```

2. **Estensioni VS Code consigliate**:
   - **Markdown All in One**: per l'anteprima e la formattazione dei file Markdown
   - **YAML**: per il supporto alla sintassi YAML nel frontmatter
   - **markdownlint**: per controllare la qualita' dei file Markdown

### Avviare il progetto

Non c'e' un "avvio" vero e proprio come in un'applicazione web. Per lavorare con le skills:

1. **Per leggere/modificare le skills**: apri i file `.md` con un qualsiasi editor di testo
2. **Per testare una skill in Claude Code**: segui le istruzioni nella sezione [Flusso di sviluppo](#flusso-di-sviluppo)
3. **Per creare una nuova skill**: segui il processo descritto in `skill-creator.md`

---

## Flusso di sviluppo

### Come creare una nuova skill

#### 1. Crea un nuovo branch

```bash
# Assicurati di essere sul branch principale e aggiornato
git checkout main
git pull origin main

# Crea un nuovo branch con un nome descrittivo
git checkout -b feature/nome-della-nuova-skill
```

**Convenzione per i nomi dei branch**:
- `feature/nome-skill` - per nuove skills
- `fix/nome-correzione` - per correzioni a skills esistenti
- `update/nome-skill` - per aggiornamenti a skills esistenti

#### 2. Crea la struttura della skill

```bash
# Crea la cartella della nuova skill
mkdir nome-skill

# Crea il file principale
touch nome-skill/nome-skill.md
```

Oppure, se disponibile, usa lo script di inizializzazione:
```bash
scripts/init_skill.py nome-skill --path ./
```

#### 3. Scrivi la skill

Apri il file `.md` e scrivi:

1. **Frontmatter YAML** (obbligatorio):
```yaml
---
name: nome-skill
description: Descrizione chiara di cosa fa la skill e quando deve essere usata.
---
```

2. **Corpo in Markdown** (obbligatorio): le istruzioni operative per Claude.

**Regole importanti per la scrittura**:
- Sii conciso: ogni parola occupa spazio nella "finestra di contesto" di Claude
- Usa la forma imperativa/infinitiva
- Includi solo informazioni che Claude non ha gia'
- Se necessario, aggiungi cartelle `scripts/`, `references/`, `assets/`

#### 4. Testa la skill

Testa la skill utilizzandola in Claude Code per verificare che:
- Il frontmatter e' corretto
- La descrizione attiva la skill nei contesti giusti
- Le istruzioni producono i risultati attesi
- Gli script (se presenti) funzionano senza errori

#### 5. Fai commit e push

```bash
# Controlla lo stato dei file
git status

# Aggiungi i file modificati
git add nome-skill/nome-skill.md

# Fai commit con messaggio descrittivo
git commit -m "Aggiunta skill nome-skill per [scopo]"

# Invia al repository remoto
git push origin feature/nome-della-nuova-skill
```

#### 6. Crea una Pull Request

1. Vai su GitHub nel browser
2. Clicca su "Compare & pull request" (appare dopo il push)
3. Compila:
   - **Titolo**: breve descrizione della modifica
   - **Descrizione**: spiega cosa fa la nuova skill, perche' e' utile, come testarla
4. Assegna i revisori
5. Clicca "Create pull request"

#### 7. Code Review

I revisori:
- Leggono il codice e lasciano commenti
- Suggeriscono miglioramenti
- Approvano o richiedono modifiche

Se vengono richieste modifiche:
```bash
# Fai le modifiche richieste
# ...

# Aggiungi e committa
git add .
git commit -m "Applicate modifiche richieste nella review"
git push origin feature/nome-della-nuova-skill
```

Una volta approvata la PR, viene unita (merge) al branch principale.

---

## Operativita'

### Deploy (distribuzione)

In questo progetto il "deploy" consiste nel **pacchettizzare e distribuire le skills** affinche' possano essere usate da Claude Code.

#### Processo di pacchettizzazione

```bash
# Pacchettizza una skill (crea un file .skill)
scripts/package_skill.py percorso/della/skill

# Pacchettizza specificando la cartella di output
scripts/package_skill.py percorso/della/skill ./dist
```

Lo script di pacchettizzazione:
1. **Valida** la skill automaticamente (controlla frontmatter, struttura, qualita' della descrizione)
2. **Crea** un file `.skill` (che e' un file ZIP rinominato) contenente tutti i file della skill

Se la validazione fallisce, lo script riporta gli errori. Bisogna correggerli e riprovare.

#### Distribuzione

Il file `.skill` generato puo' essere:
- Condiviso direttamente con gli utenti
- Caricato su un repository o sistema di distribuzione
- Installato in Claude Code

### Monitoraggio

Il monitoraggio in questo contesto si basa su:
- **Feedback degli utenti**: raccogliere segnalazioni su skill che non funzionano come previsto
- **Test manuali**: provare periodicamente le skills con scenari reali
- **Iterazione continua**: migliorare le skills basandosi sull'uso reale (Fase 6 del processo di creazione)

### Gestione errori

Gli errori piu' comuni e come risolverli:

| Errore | Causa | Soluzione |
|--------|-------|-----------|
| Validazione fallita durante la pacchettizzazione | Frontmatter YAML malformato o incompleto | Controlla che `name` e `description` siano presenti e correttamente formattati |
| Skill non si attiva | Descrizione nel frontmatter non sufficientemente chiara | Riscrivi la description includendo tutti i contesti d'uso e le parole chiave che l'utente potrebbe usare |
| Risultati incoerenti | Istruzioni ambigue nel corpo della skill | Riscrivi le istruzioni in modo piu' specifico, con esempi concreti |
| Script non funziona | Bug nel codice Python o dipendenze mancanti | Testa lo script manualmente, controlla le dipendenze |

---

## Sviluppatori

### Informazioni sul team

Sulla base dei file di configurazione e della struttura del progetto, il progetto e' gestito da:

| Ruolo | Nome/Identificativo | Note |
|-------|---------------------|------|
| Sviluppatore principale | **Stefano De Cubellis** | Proprietario del progetto (dedotto dalla struttura delle cartelle utente macOS: `/Users/stefanodecubellis/`) |
| Assistente AI | **Claude (Anthropic)** | Utilizzato come strumento di sviluppo, configurato tramite `.claude/settings.local.json` |

### Strumenti usati dal team

- **Visual Studio Code** come editor principale (configurazione in `.vscode/settings.json`)
- **Claude Code** come assistente di sviluppo (configurazione in `.claude/settings.local.json`)
- **Plugin claude-mem** (by thedotmack) per la gestione della memoria persistente in Claude Code

> **Nota**: trattandosi di un progetto senza repository Git inizializzato al momento della stesura di questa documentazione, non e' possibile estrarre informazioni dettagliate dai log di Git sui contributori.

---

## Glossario

Elenco dei termini tecnici utilizzati nel progetto, spiegati in modo semplice.

| Termine | Spiegazione |
|---------|-------------|
| **AI (Intelligenza Artificiale)** | Tecnologia che permette ai computer di eseguire compiti che normalmente richiedono intelligenza umana, come capire il linguaggio o prendere decisioni. |
| **API** | "Application Programming Interface" - un modo standardizzato per far comunicare due programmi tra loro. Come un cameriere che prende il tuo ordine (richiesta) e ti porta il piatto (risposta) dalla cucina (server). |
| **Assets** | File di risorse (immagini, template, font) inclusi in una skill e usati nell'output prodotto da Claude, senza essere caricati nella finestra di contesto. |
| **Branch** | Un "ramo" del codice. Permette di lavorare su una nuova funzionalita' senza toccare il codice principale. Come avere una bozza separata di un documento. |
| **CLI (Command Line Interface)** | Interfaccia a riga di comando - un modo di interagire con il computer scrivendo comandi testuali anziche' cliccando con il mouse. |
| **Clone** | L'operazione di copiare un repository remoto (da GitHub) sul proprio computer locale. |
| **Codebase** | L'insieme completo di tutto il codice sorgente e i file di un progetto software. |
| **Commit** | Un "salvataggio" delle modifiche in Git. Ogni commit ha un messaggio che descrive cosa e' stato cambiato e perche'. |
| **Context window (finestra di contesto)** | La quantita' massima di testo che un modello AI come Claude puo' "vedere" e considerare contemporaneamente. Le skills devono essere concise per non occupare troppo spazio. |
| **Deploy** | Il processo di mettere un software (o in questo caso, una skill) a disposizione degli utenti finali. |
| **Frontmatter** | La sezione iniziale di un file Markdown, racchiusa tra `---`, che contiene metadati in formato YAML (come nome e descrizione). |
| **Fork** | Una copia personale di un repository di qualcun altro su GitHub, che puoi modificare liberamente. |
| **Git** | Sistema di controllo versione distribuito per tracciare le modifiche ai file nel tempo. |
| **GitHub** | Piattaforma web che ospita repository Git e facilita la collaborazione tra sviluppatori. |
| **Issue** | Un "ticket" su GitHub per segnalare bug, proporre funzionalita' o discutere miglioramenti. |
| **Markdown** | Un linguaggio di formattazione del testo semplice e leggibile. I file hanno estensione `.md`. Usa simboli come `#` per titoli, `**testo**` per grassetto, `- ` per elenchi. |
| **Merge** | L'operazione di unire le modifiche di un branch in un altro. Come incorporare le modifiche della bozza nel documento finale. |
| **Meta-skill** | Una skill che insegna a creare altre skills (nel nostro caso, `skill-creator.md`). |
| **Plugin** | Un componente aggiuntivo che estende le funzionalita' di un programma. Nel progetto viene usato il plugin `claude-mem` per la memoria persistente. |
| **Progressive Disclosure** | Principio di design delle skills: mostrare prima le informazioni essenziali, poi i dettagli solo quando servono. Come un manuale che ha un sommario e approfondimenti separati. |
| **Pull Request (PR)** | Una richiesta di revisione su GitHub: proponi le tue modifiche e chiedi al team di controllarle prima di unirle al codice principale. |
| **Push** | L'operazione di inviare i propri commit dal computer locale al repository remoto su GitHub. |
| **References** | File di documentazione inclusi in una skill che Claude puo' consultare quando necessario, senza caricarli tutti in memoria. |
| **Repository (repo)** | Il "contenitore" di un progetto su Git/GitHub. Include tutti i file, la cronologia e le configurazioni. |
| **Scripts** | Piccoli programmi (solitamente in Python o Bash) inclusi in una skill per eseguire compiti ripetitivi in modo affidabile e automatico. |
| **Skill** | Un pacchetto modulare che estende le capacita' di Claude con conoscenze specializzate, flussi di lavoro e strumenti per un dominio specifico. |
| **SKILL.md** | Il file principale e obbligatorio di ogni skill. Contiene il frontmatter (metadati) e le istruzioni operative. |
| **Staging** | Ambiente di test che replica l'ambiente di produzione, usato per verificare che tutto funzioni prima del rilascio agli utenti. |
| **YAML** | "YAML Ain't Markup Language" - un formato per scrivere dati strutturati in modo leggibile dagli umani. Usato nel frontmatter delle skills. |
| **ZIP** | Formato di compressione dei file. I file `.skill` sono in realta' file ZIP rinominati che contengono tutti i file della skill. |

---

> **Ultimo aggiornamento**: 25 Marzo 2026
>
> **Autore della documentazione**: generata con Claude Code (Anthropic)
>
> Per domande o dubbi, contatta il team di sviluppo o apri una issue sul repository GitHub del progetto.
