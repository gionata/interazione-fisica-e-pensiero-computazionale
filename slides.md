---
title: |
  Interazione fisica e pensiero computazionale:\
  Fare, descrivere, modellizzare
author: Gionata Massi ed Emanuele Lorenzoni
theme: default
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
mcp: true
hideInToc: true
comark: true
duration: 18min
date: 2026-10-09-T17:00
location: Sala Elettra Grigia (piano terra), centro congressi Palazzo della Salute, Via San Francesco 90. Padova.
---

<Frontespizio
  titolo="Interazione Fisica e Pensiero Computazionale"
  sottotitolo="Fare, descrivere, modellizzare"
/>

<!--
Buon pomeriggio, sono Gionata Massi e presento, insieme al collega Emanuele Lorenzoni, un percorso di dieci ore realizzato all’Istituto Savoia Benincasa di Ancona. La proposta usa il physical computing, approcciato con una scheda Micro:bit, non come semplice occasione per “fare qualcosa con la tecnologia”, ma come un sistema concreto sul quale osservare e discutere idee fondamentali dell’informatica.

Il titolo sintetizza il movimento didattico: partire dall’interazione fisica, descrivere con precisione che cosa deve fare il dispositivo e arrivare a modellizzarne il comportamento. Il sottotitolo richiama perciò tre passaggi, non tre attività separate: fare, descrivere, modellizzare. Durante la presentazione seguirò questa progressione, poi discuterò che cosa abbiamo osservato e quali limiti sono emersi.
-->

---
layout: itadinfo
hideInToc: true
---

# Percorso della presentazione

<Toc maxDepth="2" minDepth="1" text-sm/>

<!--
Partirò dal contesto e dagli obiettivi disciplinari, perché aiutano a capire perché è stata scelta proprio la Micro:bit, e indicherò la grande idea dell'informatica attorno alla quale abbiamo progettato il percorso. Poi ricostruirò i cinque incontri seguendo la progressione dei concetti: dagli eventi e dagli output, alle variabili di stato, fino alle transizioni temporizzate. Chiuderò con gli strumenti di valutazione, i risultati del questionario e alcune criticità che suggeriscono come migliorare una futura edizione. L’attenzione sarà soprattutto su ciò che gli studenti erano chiamati a capire, non soltanto sui programmi che hanno realizzato.
-->

---
layout: itadinfo
---

# Introduzione
## Contesto e destinatari

<!-- ## Un percorso STEM nel primo biennio -->

- Progetto **“Citizen scientists of the future”**, PNRR – DM 65/2023
- IIS “Savoia Benincasa”, Ancona
- Classe seconda **ITE AFM**
- 10 ore: cinque incontri da due ore
- Nessuna competenza di programmazione richiesta

### Prerequisiti reali

- Leggere consegne operative
- distinguere causa ed effetto
- usare numeri naturali per conteggi e misure (inter. di tempo)

<!--
L’esperienza si colloca nel progetto “Citizen scientists of the future”, finanziato nell’ambito del DM 65 del 2023 per il potenziamento delle competenze STEM. Il gruppo era una classe seconda dell’indirizzo Amministrazione, Finanza e Marketing dell’Istituto tecnico economico Savoia Benincasa. Il percorso occupava dieci ore, organizzate in cinque incontri di due ore.

Non era richiesta alcuna esperienza di programmazione. È una scelta importante: il punto di partenza non era saper già scrivere codice, ma possedere prerequisiti accessibili, come leggere una consegna operativa, riconoscere una relazione di causa ed effetto e usare i numeri naturali per contare o misurare intervalli. Questo rendeva possibile concentrarsi sulla costruzione di idee informatiche, invece che sulla selezione di studenti già esperti. (circa 1 minuto)
-->

---
layout: itadinfo
---

## Obiettivi
### Riferimento alle indicazioni CINI

<div class="grid grid-cols-2 gap-x-6 text-sm leading-tight">
<div>
<h3>Traguardi di competenza</h3>
<p><strong>T-S-6.</strong> Definisce, realizza e valida programmi e sistemi che modellano o simulano sistemi fisici o processi familiari del mondo reale o oggetto di studio nelle altre discipline.</p>
<p><strong>T-S-10.</strong> Sceglie e riconosce nei programmi la rappresentazione dei dati dei problemi, dei risultati che ottiene e degli elementi utili a tener traccia degli stadi intermedi dell’elaborazione.</p>
</div>
<div>
<h3>Obiettivi di apprendimento</h3>
<p><strong>O-S-P-1.</strong> Riconoscere come le varie parti di un programma contribuiscono al suo funzionamento.</p>
<p><strong>O-S-P-2.</strong> Predire il risultato di un programma senza farlo eseguire.</p>
<p><strong>O-S-P-4.</strong> Utilizzare cicli con condizioni per descrivere l’esecuzione di azioni parametriche.</p>
<p><strong>O-S-N-1.</strong> Realizzare esperienze di raccolta ed analisi dati attraverso sensori e di controllo di dispositivi esterni.</p>
<p><strong>O-S-D-1.</strong> Valutare vantaggi e svantaggi di rappresentazioni alternative della stessa informazione <em>(riferimento introduttivo)</em>.</p>
</div>
</div>

<!--
Questi sono i traguardi e gli obiettivi della proposta di Indicazioni CINI che hanno guidato la progettazione. Il traguardo T-S-6 riguarda la realizzazione e validazione di programmi che modellano sistemi o processi; T-S-10 porta l’attenzione su come il programma rappresenta i dati del problema, i risultati e gli stati intermedi.

Le attività su pulsanti, sensori e reazioni del dispositivo hanno permesso di lavorare su O-S-P-1, riconoscendo il contributo delle varie parti del programma. Il segnapunti e gli altri esempi con variabili hanno reso esplicita la rappresentazione dei dati e degli stadi intermedi. Il ciclo forever e le transizioni temporizzate del Tamagotchi hanno coinvolto O-S-P-4; l’uso della Micro:bit con sensori, pulsanti e display ha permesso di lavorare su O-S-N-1.

O-S-P-2 è stato affrontato in modo circoscritto, chiedendo di leggere blocchi già scritti e prevederne l’effetto osservabile. Il confronto fra blocchi MakeCode, stati numerici e diagrammi informali ha toccato O-S-D-1 solo in forma introduttiva: non va inteso come un obiettivo pienamente sviluppato o valutato. (circa 1 minuto e 30 secondi)
-->

---
layout: itadinfo
---

## Metodo e strumenti

### Una progressione di scoperta guidata
**Fare** → **descrivere** → **modellizzare**

- [Micro:bit](https://microbit.org/): pulsanti e sensori come ingressi; display LED come uscita
- [MakeCode](https://makecode.microbit.org/): linguaggio a blocchi, simulatore e caricamento sul dispositivo
- Dal comportamento osservato al programma, e dal programma al modello

### Cornice pedagogica

- Learning by Doing (**Dewey**)
- Un approccio costruzionista (**Papert**), anche le costruzione è poi fortemente guidata.
- Didattica laboratoriale: il modello, informale, di macchina a stati, come modello progettuale, è il traguardo finale, da raggiungere per passi.


<!--
La metodologia è una scoperta guidata organizzata per “ricette di progettazione”: si propone un comportamento, lo si osserva, si modifica il programma e si discute perché la modifica produce un certo effetto. La Micro:bit rende visibili le relazioni tra il programma e il mondo fisico: i pulsanti e i sensori forniscono ingressi, il display a LED produce uscite, mentre le variabili permettono di rappresentare informazioni che il sistema conserva.

MakeCode è stato scelto perché presenta un linguaggio a blocchi leggibile, dispone di un simulatore e permette di trasferire rapidamente il programma sul dispositivo. Il feedback è quindi immediato e concreto. La scelta è coerente con una prospettiva costruzionista, ispirata a Papert: si impara costruendo e modificando oggetti significativi. La macchina a stati, però, non è stata presentata come teoria formale completa; è stata usata come modello informale sufficiente per progettare e discutere i comportamenti. (circa 1 minuto e 15 secondi)
-->

---
layout: itadinfo
---

## La grande idea: la macchina a stati

### Un comportamento si può descrivere

- **Eventi (ingressi):** pulsanti, sensori...
- **Transizioni:** gestore di eventi: quando..., `se <stato>`...
- **Uscite osservabili:** mostra, riproduci...
- **Stati:** variabili

**Modello informale**: abbastanza rigoroso da discutere il programma, senza introdurre tutta la teoria degli automi

<div class="text-xs mt-2">
Esempi MakeCode: <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-1.hex">eventi</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-2.hex">stato</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-3.hex">ciclo</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-4.hex">timer</a>
</div>

<!--
Prima di seguire gli incontri, introduco il modello che useremo come filo conduttore per leggerli. Un sistema ha stati, riceve eventi di input, effettua transizioni e produce uscite osservabili. Nel percorso gli eventi comprendono pulsanti e sensori; lo stato interno è rappresentato da variabili; il controllo si realizza con gestori di eventi, condizioni e, nei comportamenti temporizzati, con il ciclo forever.

Non si tratta di presentare una teoria completa degli automi a stati finiti: il diagramma informale serve come strumento di progettazione e discussione, per chiarire il comportamento atteso e confrontarlo con i blocchi MakeCode. Nei prossimi esempi vedremo come questo modello si arricchisce progressivamente: prima l’evento e la risposta, poi la memoria dello stato, infine il controllo del tempo. (circa 1 minuto)
-->

---
layout: itadinfo
---

# La progressione didattica

| Incontro | Attività |
|---|---|
| 1 | Familiarizzazione con il dispositvo, display LED, primi eventi da pulsante |
| 2 | Stati osservabili e reazioni agli input |
| 3 | Variabile di stato |
| 4 | Sequenze cicliche, codifica e ramificazioni |
| 5 | Mini-progetti, gestione degli intervalli di tempo |
| - | Test e questionario |

### Dall’evento allo stato, dallo stato al tempo

<!--
La scansione in cinque incontri accompagna un cambiamento nel modo di pensare il programma. All’inizio l’attenzione è sulla relazione diretta tra un evento e una risposta visibile. Nel secondo incontro si comincia a parlare di stati osservabili. Nel terzo, con il segnapunti, diventa centrale l’idea che il programma conservi un valore interno. Il quarto introduce sequenze cicliche e codifiche numeriche; il quinto combina gli elementi nei mini-progetti e affronta il tempo come parte esplicita del comportamento. Essendo il prof. Lorenzoni l'insegnante curriculare, abbiamo potuto investire altro tempo per la verifica delle competenze e per farci avere una valutazione del corso da parte degli studenti.

Questa progressione è il filo che userò nei prossimi lucidi: in ogni fase cambia la domanda. Prima “che cosa accade quando premo?”, poi “in quale stato si trova il sistema?”, infine “che cosa deve controllare il programma perché il passaggio avvenga dopo un intervallo?”. (circa 50 secondi)
-->

---
layout: two-cols
---

## Incontro 1 — Dall’input alla risposta

- Familiarizzare con la Micro:bit e il display
- Collegare un evento a un output osservabile
- Confrontare simulatore e dispositivo

**Domanda guida:** quale evento produce questa risposta?

**Attività:** modifica il programma per includere suoni o rappresentare quello che più ti gratifica

::right::

![Esempio MakeCode: comportamento guidato da eventi](./assets/img/microbit-recipe-1.png){width=100%}

<v-click>

### Macchina a stati

![Diagramma di stato con le icone Micro:bit e le transizioni A e B](./assets/img/diagramma-stati-eventi.png){width=100%}

</v-click>

<!--
Il primo incontro ha una funzione motivazionale, ma non si limita a “provare il dispositivo”. Gli studenti si familiarizzano con la scheda e osservano come il display a LED possa mostrare un’icona. L’attenzione si sposta presto sui primi eventi da pulsante: un’azione nel mondo fisico attiva una parte specifica del programma e produce una risposta.

La ricetta illustrata permette di nominare i tre elementi della relazione: evento, porzione di codice, effetto visibile. Il diagramma affiancato ai blocchi mostra come gli eventi A e B portino da un’icona all’altra. Lavorare prima nel simulatore e poi sulla scheda consente di confrontare due esecuzioni dello stesso programma. È il primo passo per capire che il codice non è una descrizione generica dell’intenzione: deve specificare che cosa fa l’esecutore quando riceve un particolare input. (circa 1 minuto)
-->

---
layout: two-cols
---

## Incontro 2 — Descrivere stati osservabili

- Rappresentare stati con comportamenti e icone riconoscibili
- Provare input diversi e osservare le transizioni
- Passare dalla sequenza di azioni a una descrizione del sistema

**Non solo “che cosa fa”: anche “in quale stato è?”**

**Domande:** Se non ci sono ingressi, lo stato cambia?

**Attività:** Un primo tamagotchi

::right::

![Diagramma degli stati osservabili e delle transizioni A e B](./assets/img/diagramma-stati-eventi.png){width=100%}

![Esempio MakeCode per reagire agli input](./assets/img/faccine.png){width=60%}

<!--
Nel secondo incontro il comportamento viene descritto anche attraverso gli stati che il sistema può mostrare. Le faccine offrono un riferimento intuitivo: non sono la teoria degli automi, ma aiutano a dare un nome a configurazioni osservabili e a chiedersi quali eventi possano portare dall’una all’altra. Il diagramma affiancato ai blocchi esplicita il passaggio dagli stati visualizzati alle transizioni attivate dai pulsanti.

L’insegnante guida gli studenti a distinguere una lista di azioni da una descrizione del comportamento: si parte da una situazione iniziale, si verifica quale input arriva e si osserva la nuova situazione. La rappresentazione è ancora informale, ma prepara il terreno ai diagrammi di stato e rende più facile discutere il programma prima di entrare nel dettaglio dei blocchi. (circa 1 minuto)
-->

---
layout: two-cols
---

## Incontro 3 — Conservare informazione: il segnapunti

- Il programma deve ricordare un valore tra un evento e il successivo
- La **variabile** rappresenta lo stato dell’elaborazione
- Distinguere
   - **Input:** pulsante
   - **Stato:** punteggio 
   - **Output:** valore mostrato

**Attività:** Segnapunti che mostrano la differenza reti; segnapunti con regole +3, +1, 0...

::right::

![Esempio MakeCode con variabile e comportamento persistente](./assets/img/microbit-recipe-2.png)

<v-click>

## Macchina a stati

![Diagramma della progressione del punteggio, incrementato dal pulsante B](./assets/img/diagramma-stati-ricetta-2.png){width=100%}

</v-click>

<!--
Il segnapunti introduce un passaggio concettuale decisivo. Se ogni pressione deve aggiornare un punteggio, il programma non può limitarsi a rispondere all’evento istantaneo: deve conservare informazione tra una pressione e la successiva. Questa memoria è rappresentata da una variabile.

È qui che si può discutere in modo concreto la distinzione fra input, stato e output. Il pulsante fornisce l’input; il punteggio è un dato interno che cambia durante l’elaborazione; il display mostra l’output. Il diagramma rende visibile la successione dei valori di stato a ogni pressione di B. Lo studente può premere, osservare il valore e confrontarlo con quello precedente. Il dispositivo diventa così un supporto per capire che una variabile non è soltanto un nome nel codice: rappresenta un’informazione che il programma usa per determinare il proprio comportamento. (circa 1 minuto e 10 secondi)
-->

---
layout: two-cols
---

## Incontro 4 — Codificare e far evolvere gli stati

- Rappresentare gli stati con valori numerici
- Usare condizioni per scegliere l’azione successiva
- Esplorare una sequenza ciclica: “Pronti, partenza, via!”

**Una domanda di previsione:** Se lo stato è **2** e arriva un nuovo input, che cosa succede?

**Attività:** Sperimentare l'uso dell'operatore resto; altre sequenze cicliche

::right::

![Esempio MakeCode con stati codificati e condizioni](./assets/img/microbit-recipe-3.png){width=65%}

<v-click>

### Macchina a stati

![Diagramma ciclico degli stati Pronti, Partenza e Via](./assets/img/diagramma-stati-ricetta-3.png){width=100%}

</v-click>

<!--
Nel quarto incontro la sequenza degli stati viene codificata con numeri e le condizioni selezionano il comportamento successivo. L’esempio “Pronti, partenza, via!” permette di ragionare su un ciclo: dopo una transizione, il sistema può tornare a una configurazione già attraversata e ripetere il percorso. Il diagramma mostra la stessa progressione e il ritorno da “Via!” a “Pronti” alla pressione di B.

Il modulo compare nel ragionamento come strumento per realizzare una progressione ciclica, senza trattare la matematica separatamente dalla programmazione. Una buona domanda didattica è chiedere di prevedere che cosa accadrà prima di eseguire il programma. La previsione costringe a leggere il valore dello stato e la condizione, invece di affidarsi soltanto al feedback del simulatore. Si comincia così a verificare il modello mentale dell’esecuzione. (circa 1 minuto e 10 secondi)
-->

---
layout: two-cols
---

## Incontro 5 — Un Tamagotchi che, dopo un po', si annoia

- Se manca interazione, l’animale cambia stato dopo un intervallo
- Variabile booleana: timer attivo o inattivo
- Variabile temporale: istante di avvio
- Blocco `forever`: controllo continuo della condizione

### Il tempo non “succede” nel programma: va rappresentato e controllato

::right::

![Esempio MakeCode con controllo temporizzato](./assets/img/microbit-recipe-4.png){width=75%}

<v-click>

## Macchina a stati

![Diagramma di stato del Tamagotchi con transizioni A e timeout](./assets/img/diagramma-stati-tempo.png){width=80%}

</v-click>

<!--
Il quinto incontro culmina nell’attività del Tamagotchi semplificato. L’animale virtuale cambia stato dopo un periodo senza interazione. Non basta reagire al pulsante: il programma deve tenere traccia del fatto che il timer sia attivo, ricordare l’istante iniziale e controllare continuamente se sia trascorso abbastanza tempo.

Per questo entrano in gioco una variabile booleana, una variabile che memorizza il tempo iniziale e il blocco forever con una condizione. Quando arriva un’interazione, lo stato può tornare felice; se invece il controllo rileva il timeout, passa alla noia. La lezione concettuale è che il tempo non è un evento magico: in un programma deve essere rappresentato e confrontato esplicitamente. Questa attività combina input, stato, controllo e comportamento osservabile. (circa 1 minuto e 20 secondi)
-->

---
layout: itadinfo
---

# Valutazione e risultati osservati

## Test finale
Lettura dei blocchi · input, output e stato · `all’avvio` e `forever` · previsione delle transizioni · componenti della Micro:bit

## Questionario di gradimento (15 risposte)
- Chiarezza e adeguatezza: prevalgono giudizi **“Così così”** e **“Abbastanza”**
- Interesse, utilità percepita e coerenza con bisogni e aspettative: esiti più deboli
- Funzione orientativa: solo alcuni hanno scelto l'indirizzo SIA soprattuto per motivi socio-relazionali

<!--
La valutazione conclusiva comprendeva un test e un questionario di gradimento. Il test proponeva domande a scelta multipla: leggere blocchi MakeCode, distinguere input, output e variabili di stato, comprendere il ruolo di all’avvio e forever, prevedere transizioni semplici e riconoscere sensori, display e radio come componenti funzionali del sistema. L’articolo non riporta una distribuzione dei punteggi del test, quindi non attribuiamo qui percentuali o livelli di apprendimento che non sono disponibili.

Il questionario ha raccolto quindici risposte e restituisce un quadro misto. Chiarezza e adeguatezza del corso si concentrano soprattutto tra “Così così” e “Abbastanza”. La valutazione del formatore è invece più positiva: nove risposte “Molto” per preparazione e competenza, otto per disponibilità. Interesse suscitato, utilità percepita e coerenza con bisogni e aspettative sono più deboli. Questi dati invitano a separare il gradimento della conduzione dall’efficacia percepita del percorso. (circa 1 minuto e 20 secondi)
-->

---
layout: itadinfo
---

## Una criticità: fare non significa ancora saper spiegare

- Alcuni studenti modificavano correttamente i programmi
- Non sempre sapevano spiegare **quale dato fosse lo stato**
- Nel Tamagotchi era difficile motivare il ruolo di `forever`
- Il "ciclo di controllo" è richiede di interiorizzare
  vari concetti e necessita di tempo per l'assimilazione 

### Due piani da distinguere
**Motivazionale:** il physical computing ha funzionato bene  
**Orientativo:** l’interesse non si è tradotto altrettanto in una scelta di studio

<!--
La criticità più rilevante emersa in aula è la distanza tra competenza operativa e concettuale. Alcuni studenti riuscivano a modificare un programma e a ottenere il comportamento atteso, ma non sempre sapevano dire con precisione quale variabile rappresentasse lo stato o perché il ciclo forever fosse necessario nella versione temporizzata del Tamagotchi.

Questo dato aiuta a interpretare anche il questionario. Sul piano motivazionale, lavorare con un dispositivo fisico ha funzionato: permette di vedere e toccare gli effetti del codice. Sul piano orientativo, però, l’associazione spontanea tra un’attività interessante e una possibile scelta di studio non si è prodotta con la stessa forza. Coinvolgimento e comprensione concettuale sono obiettivi collegati, ma non coincidono; e l’orientamento richiede intenzionalità, non si può dare per acquisito come effetto automatico del laboratorio. (circa 1 minuto)
-->

---
layout: itadinfo
---

## Sviluppi per una nuova edizione

- Più tempo per consolidare i concetti: dieci ore bastano per introdurli, non per stabilizzarli
- Verbalizzare input, stato, output e transizioni durante le attività
- Chiedere di **prevedere prima di eseguire**
- Esercitare il passaggio diagramma → programma

<!--
Le proposte di sviluppo derivano direttamente dalle criticità osservate. Dieci ore sono sufficienti per un’introduzione significativa, ma non per consolidare tutti i concetti che l’attività mette in gioco. Servirebbe tempo aggiuntivo per distinguere con sicurezza evento esterno e stato interno, usare il lessico di sensore come input e display come output e trasformare diagrammi di stato in programmi.

Sul piano metodologico si possono inserire brevi momenti di verbalizzazione: prima di modificare il codice, gli studenti dichiarano qual è lo stato, quale evento si aspettano e quale uscita dovrebbero osservare. Un esercizio sistematico di previsione prima dell’esecuzione aiuterebbe a far emergere eventuali misconcezioni. Infine, se si vuole che il percorso abbia anche una funzione orientativa, il collegamento con le discipline e con i percorsi STEM va reso esplicito attraverso esempi e momenti di riflessione, non lasciato al solo entusiasmo dell’attività. (circa 1 minuto e 15 secondi)
-->

---
layout: itadinfo
---

## Conclusioni — Fare, descrivere, modellizzare

- La Micro:bit rende osservabile il legame tra programma e sistema fisico
- Eventi e variabili aprono la strada alla modellizzazione degli stati
- Il laboratorio acquista valore formativo quando il ragionamento viene esplicitato

### Non solo programmare un comportamento: imparare a descriverlo e a discuterlo

<!--
In conclusione, l’esperienza mostra che il physical computing può offrire un contesto efficace per insegnare informatica nel primo biennio. Il suo valore non sta soltanto nella possibilità di costruire oggetti interattivi, ma nel rendere osservabile il legame tra input, stato, controllo e output. La Micro:bit offre un supporto concreto per parlare di questi concetti e per mettere alla prova le descrizioni costruite dagli studenti.

La condizione è esplicitare il contenuto disciplinare: non limitarsi a far funzionare un programma, ma chiedere di descrivere il comportamento, rappresentare lo stato, prevedere le transizioni e discutere la correttezza. È questa la progressione evocata dal titolo: fare, descrivere, modellizzare. Grazie. (circa 45 secondi)
-->

---

<RetroFrontespizio
  titolo="Interazione Fisica e Pensiero Computazionale"
  sottotitolo="Fare, descrivere, modellizzare"
/>
