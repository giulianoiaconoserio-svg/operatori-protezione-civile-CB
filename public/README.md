# 🚨 Sistema Gestione Profili Operatori - Protezione Civile Forio CB

## 📋 Descrizione

Sistema statico per la gestione e visualizzazione dei profili degli operatori della Protezione Civile di Forio CB, con funzionalità di modifica dei corsi protetta da password.

## 🎯 Caratteristiche Principali

### ✅ COMPLETAMENTE STATICO
- **Un solo file HTML** (`index.html`)
- **Un solo file dati JSON** (`dati.json`)
- **Nessun backend, nessun database, nessun server**
- Funziona su **hosting statico** (GitHub Pages, Netlify, Vercel, ecc.)
- **100% HTML, CSS e JavaScript vanilla**

### 🔐 Sistema di Autenticazione
- **Password protetta**: `aprile95`
- Modalità visualizzazione (default): **solo lettura**
- Modalità modifica (con password): **gestione completa corsi**

### 💾 Persistenza Locale
- Utilizza **localStorage** del browser
- Le modifiche sono salvate **localmente sul dispositivo**
- **Non c'è sincronizzazione server** (è una soluzione statica)

### 🌐 Responsive Design
- ✅ Smartphone
- ✅ Tablet
- ✅ Desktop
- Design **istituzionale** con colori Protezione Civile (blu e arancione)

### 🔍 SEO
- Meta tag `noindex, nofollow` per impedire indicizzazione
- Ogni operatore ha un URL univoco: `?id=OPERATORE_ID`

## 🚀 Come Usare

### 1. Visualizzazione Operatore

Apri il file `index.html` nel browser con il parametro `id`:

```
index.html?id=N164
```

Esempio operatori disponibili:
- `?id=N1` - Giuseppe Cigliano
- `?id=N164` - Mario Rossi (con 5 corsi di esempio)
- `?id=N120` - Salvatore Romano (Coordinatore)

### 2. Modalità Modifica

1. Clicca su **"🔐 Accedi alla Modalità Modifica"**
2. Inserisci la password: `aprile95`
3. Ora puoi:
   - ➕ **Aggiungere** nuovi corsi
   - ✏️ **Modificare** corsi esistenti
   - 🗑️ **Eliminare** corsi

### 3. Gestione Corsi

#### Aggiungere un Corso
1. Clicca su **"➕ Aggiungi Nuovo Corso"**
2. Compila i campi:
   - Nome corso (es. "Primo Soccorso BLSD")
   - Anno (es. 2024)
   - Ente erogatore (es. "Croce Rossa Italiana")
   - Ore/Durata (es. "12 ore")
   - Link PDF (opzionale)
3. Clicca **"Salva"**

#### Modificare un Corso
1. Clicca su **"✏️ Modifica"** sul corso
2. Modifica i campi desiderati
3. Clicca **"Salva"**

#### Eliminare un Corso
1. Clicca su **"🗑️ Elimina"** sul corso
2. Conferma l'eliminazione

### 4. Esempio Pratico: Operatore N164

**Rimuovere il corso "AIB" e aggiungerne un altro:**

1. Apri `index.html?id=N164`
2. Accedi alla modalità modifica (password: `aprile95`)
3. Trova il corso "Antincendio Boschivo AIB"
4. Clicca **"🗑️ Elimina"** e conferma
5. Clicca **"➕ Aggiungi Nuovo Corso"**
6. Inserisci i dati del nuovo corso
7. Clicca **"Salva"**

Le modifiche sono ora **salvate localmente** e visibili ogni volta che ricarichi la pagina.

## 📁 Struttura File

```
/
├── index.html          # File principale (applicazione completa)
├── dati.json          # Database operatori e corsi
└── README.md          # Questo file
```

## 🎨 Design System

### Colori Istituzionali
- **Blu primario**: `#0053A6` (brand, link, pulsanti)
- **Blu scuro**: `#022A4A` (header, testo principale)
- **Arancione**: `#F26B0F` (accenti, CTA, badge anno)
- **Tricolore italiano**: banda superiore (verde, bianco, rosso)

### Tipografia
- Font: Segoe UI (system font)
- Responsive e accessibile

### Componenti
- Card operatore con header gradiente
- Lista corsi con hover effects
- Modal per autenticazione e form
- Alert informativi
- Pulsanti con stati hover/active

## 🔧 Tecnologie Utilizzate

- **HTML5**: Struttura semantica
- **CSS3**: Design system, gradients, animations
- **JavaScript (Vanilla)**: Logica applicazione, localStorage
- **JSON**: Database operatori

## ⚠️ Limiti della Soluzione Statica

### 🚫 NON È POSSIBILE:
- ❌ Sincronizzare modifiche tra dispositivi diversi
- ❌ Backup automatico delle modifiche
- ❌ Accesso multi-utente con sync in tempo reale
- ❌ Protezione forte della password (è solo lato client)

### ⚠️ IMPORTANTE DA SAPERE:
- Le modifiche sono salvate **solo sul browser** dove sono state fatte
- Se cambi browser/dispositivo, vedrai i dati originali da `dati.json`
- Se cancelli i dati del browser (localStorage), perdi le modifiche
- La password è visibile nel codice sorgente (è solo una "barriera UI")

### ✅ È PERFETTO PER:
- Visualizzazione profili operatori via QR code
- Gestione locale temporanea
- Prototipo/demo
- Hosting gratuito senza backend

## 🌐 Deployment su Hosting Statico

### GitHub Pages
1. Crea repository su GitHub
2. Carica `index.html` e `dati.json`
3. Vai in Settings → Pages
4. Seleziona branch `main` e cartella `/root`
5. Il tuo sito sarà disponibile a: `https://username.github.io/repo-name/?id=N164`

### Netlify
1. Vai su [netlify.com](https://netlify.com)
2. Drag & drop la cartella con i file
3. Il sito è online in 30 secondi
4. URL esempio: `https://random-name.netlify.app/?id=N164`

### Vercel
1. Vai su [vercel.com](https://vercel.com)
2. Importa il progetto
3. Deploy automatico
4. URL esempio: `https://project-name.vercel.app/?id=N164`

## 📊 Database JSON

### Struttura `dati.json`

```json
{
  "operatori": {
    "N164": {
      "nome": "Mario",
      "cognome": "Rossi",
      "qualifica": "Capo Squadra Antincendio",
      "corsi": [
        {
          "nome": "Corso Base Protezione Civile",
          "anno": 2018,
          "ente": "DPC - Dipartimento Protezione Civile",
          "ore": "24 ore",
          "pdf": null
        }
      ]
    }
  }
}
```

### Aggiungere Operatori
Per aggiungere un nuovo operatore, modifica `dati.json`:

```json
"N999": {
  "nome": "Nuovo",
  "cognome": "Operatore",
  "qualifica": "Volontario Operativo",
  "corsi": []
}
```

Poi accedi con: `index.html?id=N999`

## 🔒 Sicurezza

### Password
- Password fissa: `aprile95`
- Modificabile nel codice (riga 370): `PASSWORD: 'aprile95'`
- **NON È SICURA** (è visibile nel codice sorgente)
- È solo una "barriera UI" per evitare modifiche accidentali

### Migliorare la Sicurezza (opzionale)
Se vuoi una soluzione più sicura, dovrai:
1. Implementare un backend (Node.js, PHP, Python)
2. Utilizzare un database vero (MongoDB, MySQL)
3. Implementare autenticazione server-side (JWT, session)
4. Usare HTTPS

Ma questo richiede hosting con server, non più statico.

## 🆘 Troubleshooting

### Il sito mostra "Parametro id mancante"
✅ **Soluzione**: Aggiungi `?id=OPERATORE_ID` all'URL

### Non vedo le mie modifiche
✅ **Soluzione**: 
- Controlla di essere nello stesso browser/dispositivo
- Verifica che localStorage non sia disabilitato
- Prova con CTRL+F5 per ricaricare

### "Operatore non trovato"
✅ **Soluzione**: Verifica che l'ID esista in `dati.json`

### La password non funziona
✅ **Soluzione**: La password è `aprile95` (tutto minuscolo, senza spazi)

## 📝 Changelog

### v1.0.0 (2025)
- ✅ Sistema statico completo
- ✅ Gestione corsi con CRUD operations
- ✅ Autenticazione con password
- ✅ Persistenza localStorage
- ✅ Design istituzionale Protezione Civile
- ✅ Responsive design
- ✅ 29 operatori precaricati

## 📧 Supporto

Per domande o problemi:
- Modifica il file direttamente (è open source!)
- Documenta bene le tue modifiche
- Testa sempre prima di fare deploy

## 📜 Licenza

Uso libero per Protezione Civile Forio CB - 1995

---

**Creato con ❤️ per la Protezione Civile**
