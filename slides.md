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
preloadImages: false
date: 2026-10-09-T17:00
location: Sala Elettra Grigia (piano terra), centro congressi Palazzo della Salute, Via San Francesco 90. Padova.
---

<script setup>
const titolo="Interazione Fisica e Pensiero Computazionale";
const sottotitolo="Fare, descrivere, modellizzare";
const url="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/";
const autori = [
  {
    nome: 'Gionata Massi',
    affiliazione: 'IIS "Savoia Benincasa"',
    citta: 'Ancona',
    presentatore: true,
  },
  {
    nome: 'Emanuele Lorenzoni',
    affiliazione: '',
    citta: '',
    presentatore: false,
  },
]
</script>

<Frontespizio
  :titolo="titolo"
  :sottotitolo="sottotitolo"
  :autori="autori"
  :url="url"
  conferenza="ITADINFO 2026"
  citta="Padova"
  data="09/10/2026"
/>

<!--
Buon pomeriggio. Presento un percorso di dieci ore progettato e realizzato con il collega Emanuele Lorenzoni all’Istituto Savoia Benincasa di Ancona. Abbiamo usato la Micro:bit non soltanto per costruire oggetti interattivi, ma come contesto concreto per affrontare concetti fondamentali dell’informatica.

Il titolo riassume la progressione proposta: si parte dall’interazione fisica, si descrive il comportamento atteso e si arriva a modellizzarlo. Il punto, quindi, non è solo far funzionare un programma: è rendere esplicito il modello che ci permette di capirlo e discuterlo.

-->

---
layout: itadinfo
hideInToc: true
---

# Percorso della presentazione

<Toc maxDepth="2" minDepth="1" text-sm/>

<!--
Presenterò il contesto e gli obiettivi disciplinari, poi il modello a stati che dà unità al percorso. Seguirò la progressione dei cinque incontri: dagli eventi e dalle uscite, alla variabile di stato, fino al controllo del tempo. Chiuderò con i risultati, le criticità e alcune indicazioni per una nuova edizione. L’attenzione sarà su ciò che gli studenti erano chiamati a comprendere, non soltanto sui programmi realizzati.

-->

---
layout: itadinfo
---

# Introduzione
## Contesto e destinatari

- Progetto finanziato con fondi del DM 65/2023 (STEM)
- IIS “Savoia Benincasa”, Ancona
- Classe seconda **ITE AFM**
- 10 ore: cinque incontri da due ore
- Nessuna competenza di programmazione richiesta

### Prerequisiti reali

- Leggere consegne operative
- Distinguere causa ed effetto
- Usare i numeri naturali per contare e misurare intervalli di tempo

<!--
Il percorso rientra nelle attività di potenziamento STEM finanziate dal DM 65/2023. Si è svolto con una classe seconda dell’indirizzo Amministrazione, Finanza e Marketing dell’Istituto Tecnico Economico: dieci ore, suddivise in cinque incontri.

Non era richiesta esperienza di programmazione. I prerequisiti erano leggere consegne operative, riconoscere relazioni di causa ed effetto e usare i numeri naturali per contare e misurare intervalli. Questo ci ha permesso di concentrare il lavoro sulle idee informatiche, senza dare per scontato un interesse o una preparazione specifici. Le attività sono state fatte svolgere in gruppi di 4 studenti, ognuni gruppo con un PC e una scheda Micro:bit. 

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
Abbiamo riletto a posteriori il percorso alla luce della Proposta di Indicazioni del CINI. I traguardi selezionati riguardano la realizzazione di programmi che modellano sistemi o processi e la rappresentazione dei dati, dei risultati e degli stati intermedi.

Le attività hanno permesso di riconoscere il contributo delle diverse parti di un programma, di usare variabili per rappresentare informazioni persistenti e di lavorare con condizioni e cicli. Pulsanti, sensori e display hanno dato concretezza al rapporto tra input e output.

La previsione dell’esecuzione è stata affrontata soprattutto leggendo blocchi già scritti. Il confronto tra blocchi, valori di stato e diagrammi ha introdotto il tema delle rappresentazioni alternative, senza svilupparlo in modo sistematico. È importante esplicitare questi limiti: i riferimenti indicano una lettura del percorso, non la pretesa di aver raggiunto ogni obiettivo con la stessa profondità.

-->

---
layout: itadinfo
transition: fade-in
---

## Metodo e strumenti
### Strumenti

- [Micro:bit](https://microbit.org/): pulsanti e sensori come ingressi; display LED come uscita
- [MakeCode](https://makecode.microbit.org/): linguaggio a blocchi, simulatore, debugger e caricamento sul dispositivo

### Cornice pedagogica

<ul>
  <li>Ciclo di apprendimento esperienziale di Kolb
    <ul class="pl-6 list-none flex flex-col gap-1">
      <li v-click class="list-item list-disc flex justify-between items-center w-full">
        <span>Esperienza concreta</span>
        <b v-click="2" class="text-primary">FARE →</b>
      </li>
      <li v-click class="list-item list-disc flex justify-between items-center w-full">
        <span>Osservazione riflessiva</span>
        <b v-click="3" class="text-primary">DESCRIVERE →</b>
      </li>
      <li v-click class="list-item list-disc flex justify-between items-center w-full">
        <span>Concettualizzazione astratta</span>
        <b v-click="4" class="text-primary">MODELLIZZARE →</b>
      </li>
      <li v-click class="list-item list-disc flex justify-between items-center w-full">
        <span>Sperimentazione attiva</span>
        <b v-click="5" class="text-primary">MODELLIZZARE → DESCRIVERE → FARE</b>
      </li>
    </ul>
  </li>
</ul>

<!--
La cornice pedagogica richiama il ciclo di apprendimento esperienziale di Kolb. Nel nostro percorso, **FARE** significa interagire con la Micro:bit e osservare il comportamento prodotto. **DESCRIVERE** significa rendere esplicito il comportamento atteso e tradurlo in un programma, componendo i blocchi di MakeCode: il codice diventa una descrizione eseguibile, da provare sulla scheda o nel simulatore.

**MODELLIZZARE** significa ricondurre il comportamento del programma a uno degli schemi di macchina a stati esplorati nelle ricette. In alcuni schemi, l’uscita permette di riconoscere lo stato e un input determina la risposta; in altri, una variabile conserva lo stato corrente e viene aggiornata dagli eventi. Nel Tamagotchi temporizzato, una condizione sul tempo trascorso può attivare una transizione. Riconoscere lo schema aiuta a capire da che cosa dipende il passaggio e a prevedere che cosa accadrà.

La sperimentazione attiva riavvia il ciclo: si parte dal modello per modificare o progettare un programma, si descrive l’effetto atteso e lo si verifica con una nuova esecuzione. Le fasi non costituiscono una sequenza rigida, ma si richiamano e possono ripetersi durante l’attività.

La Micro:bit rende osservabile il rapporto tra programma e sistema fisico: pulsanti e sensori forniscono ingressi, il display a LED e lo speaker producono uscite, mentre le variabili rappresentano informazioni conservate. MakeCode, con i blocchi leggibili, il simulatore e il debugger, consente di comporre rapidamente il programma e confrontare il modello con il comportamento osservato.

-->

---
layout: itadinfo
---

## La grande idea
### Un comportamento si può descrivere: la macchina a stati

- **Eventi (ingressi + tempo):** pulsanti, sensori, scadenze temporali
- **Transizioni:** eventi e condizioni determinano il passaggio da uno stato all’altro
- **Uscite osservabili:** azioni come mostrare o riprodurre
- **Stati:** configurazioni del sistema, rappresentate nel programma anche tramite variabili

**Modello informale**: abbastanza rigoroso da discutere il programma ma senza introdurre la teoria degli automi

<div class="text-xs mt-2">
Esempi MakeCode: <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-1.hex">eventi</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-2.hex">stato</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-3.hex">ciclo</a> · <a href="https://gionata.github.io/interazione-fisica-e-pensiero-computazionale/microbit/microbit-recipe-4.hex">timer</a>
</div>

<!--
Questo è il modello che useremo per leggere gli esempi. Un sistema si trova in una certa configurazione, riceve input dai pulsanti e dai sensori oppure rileva il trascorrere di un intervallo, può cambiare stato e produce uscite osservabili. Le variabili rappresentano parte dello stato interno; gestori di eventi, condizioni e cicli controllano l’evoluzione. In questo senso, il tempo non è un ingresso esterno come la pressione di un pulsante: è una condizione temporale che può attivare una transizione.

Non introduciamo una teoria completa degli automi a stati finiti. Il diagramma è uno strumento per progettare e discutere il comportamento atteso e confrontarlo con i blocchi MakeCode. Vedremo il modello arricchirsi per gradi: prima la risposta a un evento, poi la memoria dello stato, infine il controllo del tempo.

-->

---
layout: itadinfo
---

# La progressione didattica

| Incontro | Attività |
|---|---|
| 1 | Familiarizzazione con Micro:bit e tutorial introduttivi |
| 2 | Transizioni guidate dagli input |
| 3 | Variabili di stato |
| 4 | Sequenze cicliche, codifica degli stati e selezione |
| 5 | Transizioni temporizzate e mini-progetti |
| - | Test e questionario |

<!--
La scansione dei cinque incontri segue una progressione concettuale. Si parte dalla familiarizzazione con la scheda; poi si descrivono stati riconoscibili, si introduce una variabile per conservare un valore e si codificano sequenze cicliche. Nell’ultimo incontro entra in gioco il tempo, rappresentato e controllato dal programma. Test e questionario completano il percorso.

La domanda cambia insieme alle attività: che cosa accade quando arriva un input? Quale informazione deve ricordare il programma? Che cosa deve controllare perché una transizione avvenga dopo un intervallo? Nei prossimi esempi seguirò questa progressione.

-->

---
layout: itadinfo-two-cols
---

## Incontro 1 — Familiarizzare con Micro:bit

- Conoscere il display LED e i pulsanti
- Esplorare i tutorial *Flashing Heart*, *Name Tag* e *Smiley Buttons*
- Osservare output visivi e testuali; sperimentare gli input dei pulsanti
- Confrontare simulatore e dispositivo

**Domanda guida:** come cambia l’effetto osservabile quando modifico il programma?

**Sperimentazione attiva:** personalizzare un tutorial a partire dal comportamento osservato

::right::

![](https://cdn.sanity.io/images/ajwvhvgo/production/4de361b622ac9bf5e8b9c3109a3935dd47b96167-1490x609.png)
![Esempio visivo di icone visualizzate sulla Micro:bit](./assets/img/faccine.png){width=60%}

<!--
Il primo incontro serve a prendere confidenza con la scheda e con l’ambiente di lavoro. Con tutorial come *Flashing Heart*, *Name Tag* e *Smiley Buttons*, gli studenti osservano messaggi e icone e provano i pulsanti come ingressi. Non chiediamo ancora di formalizzare il comportamento: il primo obiettivo è collegare una modifica del programma a un effetto osservabile.

Il confronto tra simulatore e dispositivo aiuta a discutere che cosa resta uguale e che cosa cambia passando dall’esecuzione simulata a quella fisica. Questa esperienza fornisce il lessico concreto di input e output che useremo negli incontri successivi.

-->

---
layout: itadinfo-two-cols-sx
---

## Incontro 2 — Descrivere stati osservabili

- Rappresentare stati con comportamenti e icone riconoscibili
- Provare input diversi e osservare le transizioni
- Passare dalla sequenza di azioni a una descrizione del sistema

**Non solo “che cosa fa”: anche “in quale stato è?”**

**Domanda guida:** lo stato cambia anche senza un nuovo input?

**Sperimentazione attiva:** un primo Tamagotchi

<div class="flex justify-end my-2">
  <a href="https://makecode.microbit.org/S13846-71170-84222-71645" target="_blank" alt="Simulazione Micro:bit su MakeCode - Ricetta 1">
    <img src="./assets/img/recipe-1.gif" class="w-24" />
  </a>
</div>

::right::

![Esempio MakeCode: comportamento guidato da eventi](./assets/img/microbit-recipe-1.png){width=100%}

<v-click>

### Macchina a stati

![Diagramma di stato con le icone Micro:bit e le transizioni A e B](./assets/img/diagramma-stati-eventi.png){width=100%}

</v-click>

<!--
Nel secondo incontro il Tamagotchi permette di passare dalla risposta visibile a una prima descrizione per stati. Gli studenti associano a ciascuna configurazione un comportamento e un’icona, poi osservano come i pulsanti attivino le transizioni mostrate nel diagramma.

Qui lo stato non cambia da solo: nel modello proposto, il passaggio avviene in risposta a un input. La domanda guida prepara quindi il confronto con l’ultimo incontro, in cui introdurremo una transizione legata al tempo. Il diagramma non è una notazione formale completa; serve a rendere esplicita l’idea prima di leggere o modificare i blocchi.

In gruppo, gli studenti progettano anche comportamenti in cui input diversi, compresi quelli rilevati dai sensori, producono uscite visive o sonore.

-->

---
layout: itadinfo-two-cols-dx
---

## Incontro 3 — Conservare informazione

- Il programma deve ricordare un valore tra un evento e il successivo
- La **variabile** conserva una parte dello stato del sistema
- **Input:** pulsante · **Stato:** punteggio · **Output:** valore mostrato

**Sperimentazione attiva:** segnapunti; estensione: punteggi di due squadre o differenza reti

<div class="flex justify-end my-2">
  <a href="https://makecode.microbit.org/S41178-88413-37695-37192" target="_blank" alt="Simulazione Micro:bit su MakeCode - Ricetta 2">
    <img src="./assets/img/recipe-2.gif" class="w-24" />
  </a>
</div>

::right::

![Esempio MakeCode con variabile e comportamento persistente](./assets/img/microbit-recipe-2.png)

<v-click>

## Macchina a stati

![Diagramma della progressione del punteggio, incrementato dal pulsante B](./assets/img/diagramma-stati-ricetta-2.png){width=100%}

</v-click>

<!--
Il segnapunti introduce la memoria del programma. Per aggiornare il totale a ogni pressione, non basta reagire all’evento: occorre conservare il valore precedente e usarlo nel calcolo successivo. La variabile rappresenta questa informazione persistente.

Possiamo così distinguere con precisione i tre elementi mostrati nella slide: il pulsante è l’input, il punteggio è una parte dello stato e il valore visualizzato è l’output. Il diagramma esplicita la successione dei valori. Come estensione, si può aggiungere la possibilità di annullare un punto oppure tenere il punteggio di due squadre: cambia la rappresentazione, ma resta la stessa idea di informazione conservata.

-->

---
layout: itadinfo-two-cols
---

## Incontro 4 — Codificare e far evolvere gli stati

- Rappresentare gli stati con valori numerici
- Usare condizioni per scegliere l’azione successiva
- Esplorare una sequenza ciclica: “Pronti, partenza, via!”

**Previsione:** se lo stato è **2** e si preme B, che cosa succede?

**Sperimentazione attiva:** operatore resto e debugger

**Sperimentazione attiva:** se/allora/altrimenti

<div class="flex justify-end my-2">
  <a href="https://makecode.microbit.org/S30553-34993-49578-00989" target="_blank" alt="Simulazione Micro:bit su MakeCode - Ricetta 3">
    <img src="./assets/img/recipe-3.gif" class="w-24" />
  </a>
</div>

::right::

![Esempio MakeCode con stati codificati e condizioni](./assets/img/microbit-recipe-3.png){width=65%}

<v-click>

### Macchina a stati

![Diagramma ciclico degli stati Pronti, Partenza e Via](./assets/img/diagramma-stati-ricetta-3.png){width=100%}

</v-click>

<!--
Nel quarto incontro codifichiamo gli stati con numeri e usiamo condizioni per selezionare la transizione successiva. A ogni pressione di B, la sequenza passa da “Pronti” a “Partenza”, poi a “Via!” e ricomincia. Il diagramma sulla slide rende visibile il ciclo.

La domanda di previsione chiede di determinare l’esito prima di eseguire il programma: bisogna combinare il valore corrente dello stato, l’input e la condizione. Il debugger permette poi di confrontare la previsione con l’esecuzione. Per estendere la sequenza a più stati introduciamo l’operatore resto, collegando una tecnica di programmazione a una progressione ciclica.

-->

---
layout: itadinfo-two-cols-dx
---

## Incontro 5 — Gestione del tempo e progetti di gruppo

<!-- L'elenco principale mostra le 4 frasi nei primi 4 click -->
<ul class="pl-6 flex flex-col gap-1">
  <!-- Sostituito flex con grid grid-cols-[6fr_4fr] per bloccare le proporzioni delle colonne -->
  <li v-click class="list-item list-disc grid grid-cols-[6fr_4fr] items-center w-full">
    <span>L'animale si sveglia felice ma, dopo un certo tempo senza stimoli...</span> 
    <!-- Click 5: Compaiono tutte le parti in grassetto -->
    <b v-click="5" class="text-primary pl-4">«all'avvio», stato iniziale, timer attivo, istante</b>
  </li>
  
  <li v-click class="list-item list-disc grid grid-cols-[6fr_4fr] items-center w-full">
    <span>...si annoia.</span> 
    <b v-click="5" class="text-primary pl-4">timer disattivato</b>
  </li>
  
  <li v-click class="list-item list-disc grid grid-cols-[6fr_4fr] items-center w-full">
    <span>Uno stimolo lo rende temporaneamente felice</span> 
    <b v-click="5" class="text-primary pl-4">timer attivo, istante</b>
  </li>
  
  <li v-click class="list-item list-disc grid grid-cols-[6fr_4fr] items-center w-full">
    <span><strong>Il tempo deve essere gestito!</strong></span> 
    <b v-click="5" class="text-primary pl-4">«Per sempre»</b>
  </li>
</ul>

<!-- Click 6: Compare la GIF della simulazione -->
<div class="flex justify-end my-2" v-click="6">
  <a href="https://makecode.microbit.org/S90051-13886-48915-94659" target="_blank" alt="Simulazione Micro:bit su MakeCode - Ricetta 4">
    <img src="./assets/img/recipe-4.gif" class="w-24" />
  </a>
</div>

::right::

<!-- Click 6: Compare l'immagine del codice a destra insieme alla GIF -->
<div class="flex justify-end w-full" v-click="6">
  <img src="./assets/img/microbit-recipe-4.png" class="w-[75%]" alt="Esempio MakeCode con controllo temporizzato" />
</div>

<!-- Usiamo un div standard con v-click="4" per far apparire l'intera sezione al quarto click -->
<div v-click="4" class="mt-4">
  <h2>Macchina a stati</h2>

  <div class="flex justify-end w-full">
    <img src="./assets/img/diagramma-stati-tempo.png" class="w-[80%]" alt="Diagramma di stato con transizioni e timeout" />
  </div>
</div>


<!--
Nell’ultimo incontro riprendiamo il Tamagotchi e aggiungiamo una transizione temporizzata. Quando si preme A, l’animale torna felice e il programma memorizza l’istante di avvio del timer. Nel ciclo «per sempre» controlla se è trascorso l’intervallo previsto; quando la soglia viene superata, passa allo stato annoiato e disattiva il timer.

Il punto concettuale è che il tempo deve essere rappresentato e confrontato: non è un evento che il programma possa semplicemente “aspettare” senza controllo. La soluzione richiede di coordinare stato, istante iniziale, durata e condizione. È un passaggio più impegnativo, coerentemente con le difficoltà emerse nella valutazione.

Nella parte di progetto gli studenti applicano gli schemi già incontrati, per esempio a un segnapunti, a un dado che usa l’accelerometro o a giochi tra dispositivi tramite Bluetooth, come i dadi o la morra cinese.

-->

---
layout: itadinfo
---

# Valutazione e risultati osservati

## Test finale
Lettura dei blocchi · input, output e stato · «all’avvio» e «per sempre» · previsione delle transizioni

## Questionario di gradimento
- Il corso è stato apprezzato, ma non è stato percepito come pienamente rispondente alle esigenze degli studenti
- Non si è realizzato l’atteso aumento delle iscrizioni all’indirizzo **Sistemi Informativi Aziendali (SIA)**

## Esito del test
- Risultati mediamente buoni su variabili, struttura dei programmi e diagrammi di stato
- Restano difficoltà nel classificare input/output e nel ragionare sul ciclo temporizzato

<!--
La valutazione ha incluso un test a scelta multipla, svolto in un’undicesima ora, e un questionario anonimo di gradimento, compilato a casa. Il test chiedeva di leggere blocchi, distinguere input, output e stato e prevedere transizioni, oltre a riconoscere alcuni elementi della Micro:bit.

Nel complesso, le prestazioni sono state buone soprattutto su variabili, struttura dei programmi e lettura dei diagrammi. Sono emerse difficoltà nel classificare le periferiche come input o output e nel comprendere il controllo del flusso, in particolare nel ciclo temporizzato. Non riporto percentuali: non sono disponibili distribuzioni dei punteggi che consentano una quantificazione più precisa.

Il questionario restituisce un dato diverso: il corso è stato apprezzato, ma non è stato percepito da tutti come pienamente rispondente alle proprie esigenze. Questo risultato va tenuto distinto dagli esiti del test.

-->

---
layout: itadinfo
---

## Criticità
### Fare non significa ancora saper spiegare

- La competenza pratica non sempre si accompagna a una spiegazione formale
- La gestione del tempo richiede variabili e controllo continuo, da consolidare

### Due piani da distinguere

**Gradimento:** il corso è stato apprezzato, ma non pienamente aderente alle esigenze percepite  
**Orientamento:** non si è ottenuto l’aumento atteso delle iscrizioni al SIA

<!--
La criticità didattica è la distanza possibile tra riuscire a costruire un comportamento e saperne spiegare il modello. I risultati sul test sono incoraggianti, ma la classificazione di input e output e il coordinamento di stato, tempo e ciclo richiedono altro lavoro.

C’è poi un esito di orientamento che è utile riferire con trasparenza. Il gruppo era stato coinvolto anche con l’aspettativa di favorire le iscrizioni al percorso Sistemi Informativi Aziendali; l’aumento atteso non si è verificato. Le risposte degli studenti sono state però articolate: alcuni, interessati soprattutto alle materie giuridico-economiche, non hanno trovato nel corso una piena corrispondenza con le proprie aspettative; altri lo hanno indicato come una delle attività più interessanti dell’anno.

Gradimento, apprendimento concettuale e orientamento sono quindi dimensioni collegate, ma non intercambiabili. Se l’orientamento è un obiettivo, va progettato e discusso esplicitamente: non possiamo assumere che derivi automaticamente dal coinvolgimento nel laboratorio.

-->


---
layout: itadinfo
---

## Conclusioni — Fare, descrivere, modellizzare

- La Micro:bit rende osservabile il legame tra programma e sistema fisico
- Eventi, variabili e transizioni rendono descrivibile il comportamento
- Il valore formativo emerge quando il ragionamento è esplicitato
- Non solo far funzionare un programma: descriverlo, prevederlo e discuterlo

## Sviluppi per una nuova edizione

- Più tempo per consolidare concetti e lessico
- Verbalizzare input, stato, output e transizioni durante le attività
- Chiedere di **prevedere prima di eseguire**
- Esercitare il passaggio diagramma → programma


<!--
Il messaggio conclusivo è che il physical computing può essere un contesto per insegnare concetti informatici, non soltanto un’occasione per costruire oggetti interattivi. La Micro:bit rende osservabile il legame tra programma e sistema fisico; gli eventi, le variabili e le transizioni offrono un lessico per descrivere quel legame.

Perché il laboratorio abbia valore formativo, però, il ragionamento va reso esplicito. Non basta verificare che il programma funzioni: chiediamo agli studenti di descrivere il comportamento, individuare lo stato, prevedere la transizione e confrontare la previsione con l’esecuzione. È questa la progressione del titolo: fare, descrivere, modellizzare.

Per una nuova edizione prevederei più tempo per consolidare il lessico e il controllo temporizzato, brevi momenti di verbalizzazione durante le attività e un esercizio ricorrente di previsione prima dell’esecuzione. Aggiungerei inoltre occasioni sistematiche per passare dal diagramma al programma e viceversa. Se il percorso deve sostenere anche l’orientamento, renderei espliciti i collegamenti con le discipline e con gli indirizzi STEM, invece di affidarmi al solo entusiasmo dell’attività.

In una frase: il punto non è soltanto far funzionare un programma, ma rendere visibile il modello concettuale che lo rende comprensibile.

-->

---

<RetroFrontespizio
  titolo="Interazione Fisica e Pensiero Computazionale"
  sottotitolo="Fare, descrivere, modellizzare"
  :autori="[
    {
      nome: 'Gionata Massi',
      affiliazione: 'IIS &quot;Savoia Benincasa&quot;',
      citta: 'Ancona',
      presentatore: true,
    },
    {
      nome: 'Emanuele Lorenzoni',
      affiliazione: '',
      citta: '',
      presentatore: false,
    },
  ]"
/>

<!--
Grazie per l'attenzione! Sono a disposizione per eventuali domande su questa esperienza didattica.

 -->