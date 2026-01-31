# Guida per il Content Manager - Sito Web SS Thistlegorm

Benvenuto! Questa guida ti aiuterà a gestire i contenuti del sito web SS Thistlegorm utilizzando Sveltia CMS.

## Accesso al Sistema di Gestione Contenuti (CMS)

**URL del CMS:** https://ssthistlegorm.com/admin/

Il CMS fornisce un'interfaccia user-friendly per modificare i contenuti del sito web senza necessità di conoscenze tecniche.

---

## Primo Accesso

### Passo 1: Naviga al CMS
Apri il tuo browser e vai a: **https://ssthistlegorm.com/admin/**

### Passo 2: Scegli il Metodo di Accesso
Vedrai due opzioni di login:
- **"Sign In with GitHub"** - Richiede un account GitHub (non consigliato per te)
- **"Sign In with GitHub Using Token"** - Usa questa opzione

### Passo 3: Inserisci il Tuo Token di Accesso
1. Clicca su **"Sign In with GitHub Using Token"**
2. Apparirà un campo di testo
3. Incolla il Token di Accesso Personale che hai ricevuto (è una lunga stringa che inizia con `ghp_`)
4. Clicca su **"Sign in"**

### Passo 4: Sei Dentro!
Il pannello di controllo del CMS si caricherà, mostrando tutte le collezioni di contenuti disponibili.

---

## Importante: Archiviazione e Sicurezza del Token

### Come Funziona l'Archiviazione del Token
- Il tuo token viene salvato nella memoria locale del browser
- Devi inserirlo **una sola volta per browser**
- Persiste anche dopo aver chiuso il browser
- Funziona indefinitamente a meno che il token non scada

### Quando Devi Reinserire il Token
- Utilizzando un browser diverso (Chrome, Firefox, Safari, ecc.)
- Utilizzando un dispositivo diverso (laptop, tablet, telefono)
- Utilizzando la modalità navigazione in incognito/privata
- Dopo aver cancellato la cache/dati del browser
- Se il token scade (controlla la data di scadenza)

### Best Practice di Sicurezza
- ✅ Mantieni il tuo token confidenziale - è come una password
- ✅ Non condividerlo con nessun altro
- ✅ Non pubblicarlo o includerlo in screenshot
- ✅ Conservalo in modo sicuro (consigliato un password manager)
- ⚠️ Su un computer condiviso, usa la modalità incognito così il token non viene salvato
- ⚠️ Chiunque abbia accesso al tuo browser può usare il CMS se sei loggato

---

## Utilizzo del CMS

### Collezioni di Contenuti Disponibili

**1. Blog Posts (Articoli del Blog)**
- Crea nuovi articoli
- Modifica articoli esistenti
- Aggiungi categorie e tag
- Programma le date di pubblicazione

**2. Pages (Pagine)**
- Modifica le pagine principali del sito:
  - Home Page (Pagina Iniziale)
  - About Page (Chi Siamo)
  - Book Page (Libro)
  - Contact Page (Contatti)
  - Past Expeditions (Spedizioni Passate)
  - Work Page (Lavoro)

**3. Other Wrecks (Altri Relitti)**
- Aggiungi documentazione per altri siti di relitti
- Modifica pagine di relitti esistenti

### Apportare Modifiche

1. **Naviga a una collezione** (Posts, Pages, o Other Wrecks)
2. **Seleziona un elemento** da modificare o clicca "New" per crearne uno nuovo
3. **Modifica il contenuto** utilizzando l'editor visuale
4. **Aggiungi immagini** caricandole o selezionandole dalla libreria media
5. **Salva le modifiche** - clicca sul pulsante **"Save"**
6. **Pubblica** - Le modifiche vengono salvate nel repository

### Workflow di Pubblicazione

- **Draft (Bozza):** Lavoro in corso, non visibile sul sito
- **In Review (In Revisione):** Pronto per la revisione (workflow opzionale)
- **Published (Pubblicato):** Le modifiche sono salvate e appariranno sul sito web

**Importante:** Dopo il salvataggio, il sito web si ricostruisce automaticamente (richiede 1-2 minuti). Le tue modifiche saranno live poco dopo la pubblicazione.

---

## Suggerimenti per la Modifica dei Contenuti

### Formattazione del Testo
- Usa la barra degli strumenti dell'editor per la formattazione
- **Grassetto**, *corsivo*, elenchi, titoli sono tutti supportati
- Funziona anche la sintassi Markdown se la conosci

### Aggiungere Immagini
1. Clicca sul pulsante immagine o trascina e rilascia
2. Le immagini sono archiviate in `assets/images/`
3. Usa nomi di file descrittivi
4. Ottimizza le immagini prima del caricamento (comprimi file grandi)

### Campi Front Matter
Ogni tipo di contenuto ha campi specifici:
- **Title (Titolo):** Titolo della pagina o dell'articolo
- **Date (Data):** Data di pubblicazione (per gli articoli)
- **Layout:** Template utilizzato (di solito preimpostato)
- **Tagline:** Sottotitolo opzionale
- **Tags/Categories (Tag/Categorie):** Per organizzazione e filtri
- **Body (Corpo):** Area del contenuto principale (editor markdown)

---

## Risoluzione dei Problemi

### "Failed to load" o "Cannot connect"
- Controlla la tua connessione internet
- Verifica di essere loggato (aggiorna la pagina)
- Il token potrebbe essere scaduto - reinseriscilo

### Le Modifiche Non Appaiono
- Aspetta 2-3 minuti per la ricostruzione del sito
- Cancella la cache del browser
- Controlla di aver cliccato "Publish" non solo "Save"

### Token di Accesso Perso
- Contatta l'amministratore del sito per generare un nuovo token
- Il vecchio token verrà revocato quando ne viene emesso uno nuovo

### Hai Bisogno di Aiuto?
Contatta l'amministratore del sito web se incontri problemi o hai domande.

---

## Riferimento Rapido

| Azione | Come Fare |
|--------|-----------|
| Login | https://ssthistlegorm.com/admin/ → "Sign In with Token" |
| Crea Articolo | Blog Posts → New Post |
| Modifica Pagina | Pages → Seleziona pagina → Edit |
| Aggiungi Immagine | Pulsante Upload nell'editor |
| Anteprima Modifiche | Salva come Draft → Pulsante Preview |
| Pubblica | Save → Pulsante Publish |
| Logout | Clicca icona profilo → Sign out |

---

## Informazioni sul Sito Web

- **Sito Web Pubblico:** https://ssthistlegorm.com
- **Pannello Admin CMS:** https://ssthistlegorm.com/admin/
- **Hosting:** Netlify
- **Repository Contenuti:** GitHub (tutte le modifiche sono versionizzate)

---

*Ultimo aggiornamento: 31 Gennaio 2026*
