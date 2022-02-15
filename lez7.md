<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML">
</script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$','$'], ['\\(','\\)']],
      processEscapes: true},
      jax: ["input/TeX","input/MathML","input/AsciiMath","output/CommonHTML"],
      extensions: ["tex2jax.js","mml2jax.js","asciimath2jax.js","MathMenu.js","MathZoom.js","AssistiveMML.js", "[Contrib]/a11y/accessibility-menu.js"],
      TeX: {
      extensions: ["AMSmath.js","AMSsymbols.js","noErrors.js","noUndefined.js"],
      equationNumbers: {
      autoNumber: "AMS"
      }
    }
  });
</script>

Fisica 2 - Lezione 7
====================

Il circuito RL:
---------------

Studieremo ora il circuito RL della lezione precedente, utilizzando la funzione di Heaviside, o funzione gradino, per indicare lo spostamento dello switch dalla posizione B alla posizione A e viceversa.  

![Image](/img/lez7/funzione_heaviside.jpg)  

Questo è un buon modo per formalizzare il funzionamento di un interruttore all'interno di un circuito.  
Possiamo quindi esplicitare una formula che determini la tensione attraverso un condensatore in un RC, sia esso parallelo o in serie che soddisfi $\forall t \in \R$, sfruttando la funzione di Heaviside.  

![Image](/img/lez7/equazione_generale_circuito_rc_parallelo.jpg)  

---
L'Operatore Risposta Stato Zero:
--------------------------------

Definiamo quindi l'operatore **Risposta A Stato Zero**:  
$$V(t) = \mathscr{Z_{0}}(I_{S}(t))$$  
Riscriviamo il problema di cauchy dell'ultimo circuito RC trattato:  
$$C\frac{dV(t)}{dt}-\frac{V(t)}{R}=I_{S}(t) \land V(0) = 0$$  
E ricordiamoci che la forma d'onda della corrente era:  
$$I_{S}(t) = I_{0}\cdot H(t)$$  
Cosa succede allora se decido di traslare l'ingresso:  
$$I_{\Delta t}(t+\Delta t) = I_{S}(t)$$  
Che è la stessa cosa di dire:  
$$I_{\Delta t}(t) = I_{S}(t-\Delta t)$$  
Quindi $I_{\Delta t}(t)$ è solo il traslato a destra del gradino.  
Se volessi scoprire il $V(t)$ causato da questa nuova corrente, devo per forza rivalutare l'intera equazione differenziale o esiste una via più semplice?  
Ipotizziamo che la traslazione degli argomenti delle funzioni dipendenti dal tempo nel problema di cauchy possa esser soluzione:  
$$C\frac{dV(t-\Delta t)}{dt}-\frac{V(t-\Delta t)}{R}=I_{S}(t-\Delta t) \land t \ge \Delta t$$  
Definiamo ora : $y(t) = V(t-\Delta t)$ ove $V(t-\Delta t)$ è la soluzione del problema di cauchy originale, traslata.  
Allora $y(\Delta t) = V(\Delta t - \Delta t) = V(0)$.  
E' evidente quindi che il problema di cauchy:  
$$C\frac{dy(t)}{dt}-\frac{y(t)}{R}=I_{\Delta t}(t) \space \land y(\Delta t) = 0$$  
E' lo stesso problema di cauchy iniziale, ma con la condizione di bordo traslata.  
Ciò implica la **tempo invarianza** dell'operatore risposta a stato zero.  
Inoltre è di facile dimostrazione che l'operatore a stato zero **è lineare**.  

---
L'Operatore Traslazione Temporale:
----------------------------------

Viene definito come: $\mathscr{T_{\Delta t}}\space$ l'**operatore traslazione temporale**, che prende come argomento una funzione e la trasla di un $\Delta t$.  
Quindi:  
$$\mathscr{T_{\Delta t}}(f(t)) = f(t-\Delta t)$$  
Questo oggetto gode di due proprietà:
- Additività: $\mathscr{T_{\Delta t}}(f(t)+g(t)) = \mathscr{T_{\Delta t}}(f(t)) + \mathscr{T_{\Delta t}}(g(t))$  
- Omogeneità: $\mathscr{T_{\Delta t}}(Af(t)) = A\mathscr{T_{\Delta t}}(f(t))$  

Quindi l'operatore traslazione temporale **è lineare**.  

Un'ulteriore proprietà molto importante è che l'operatore traslazione temporale e l'operatore risposta a stato zero **commutano**:  
$$\mathscr{T_{\Delta t}}(\mathscr{Z_{0}}(I(t)))=\mathscr{Z_{0}}(\mathscr{T_{\Delta t}}(I(t)))=\mathscr{Z_{0}}(I(t-\Delta t))$$  
Questa proprietà è valida $\forall I(t), \forall t, \forall \Delta t:\Delta t \ge 0$.  

---
La Delta Di Dirac:
------------------

Definiamo ora la Delta Di Dirac, una distribuzione $\delta(t)$ che soddisfa la proprietà:  
$$\int_{-\infty}^{+\infty}\delta(t)f(t)dt=f(0), \forall f(t)$$  
Inoltre, se $f(t) = 1 \Longrightarrow A_{\delta(t)}=1$, notiamo che l'area sottesa dalla delta è uguale a 1, nonostante sia un impulso infinitamente stretto.  
La risposta a stato zero alla delta di Dirac prende il nome di **Risposta All'Impulso**: $h(t)$, mentre la risposta a stato zero al gradino unitario prende il nome di **Risposta Al Gradino Unitario** e viene spesso rappresentata con $g(t)$.  
Definiamo allora una funzione che approssimi la delta di Dirac:  
$$P_{d}(t):=0\space se\space t<0$$  
$$P_{d}(t):=\frac{1}{d}\space se\space 0\le t\le d$$  
$$P_{d}(t):=0\space se\space t>d$$  
Notare che soddisfa la proprietà di avere un'area pari a 1.  
Sappiamo inoltre che $\lim_{d \to 0}P_{d}(t)=\delta(t)$.  
Proviamo quindi a vedere cosa succede se applichiamo un simile segnale all'ingresso di un RC e lo mandiamo al limite per $d \to 0$.  

![Image](img/lez7/risposta_impulsiva_circuito_rc.jpg)  

Come possiamo vedere, al limite $d \to 0$ la nostra risposta impulsiva tende a $h(t)=\frac{1}{C}e^{-\frac{t}{RC}}$  
Inoltre nel periodo infinitesimale di impulso $0 < t < d$ sappiamo che la tensione nel condensatore sale in maniera lineare, infatti:  
$$\lim_{d \to 0}\frac{R}{d}(1-e^{-\frac{t}{RC}})=\frac{R}{d}(1-1+\frac{t}{RC})=\frac{t}{dC}$$  
E la pendenza della retta che formerà la tensione in quell'istante sarà:  
$$\frac{d}{dt}\frac{t}{dC}=\frac{1}{dC}$$  
Da cui possiamo notare che questa pendenza dipende fondamentalmente da due cose, dal quanto è stretto, istantaneo, l'impulso, e da quanta carica è in grado di immagazzinare il condensatore.  
Per evitare di dover sempre specificare $t\ge0$ possiamo riscrivere l'equazione finale come:  
$$h(t) = H(t)\cdot\frac{1}{C}e^{-\frac{t}{RC}}$$  
Nella prossima lezione verrà trattato come è dimostrabile che vale la proprietà:  
$$h(t) = \frac{d}{dt}g(t)$$  
Ossia la risposta all'impulso è equivalente alla derivata della risposta al gradino unitario.  
