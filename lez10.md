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

Fisica 2 - Lezione 10
=====================

Il Circuito RLC:
----------------

Tornando a parlare di circuiti RLC ricordiamoci la soluzione al caso sovrasmorzato:  
$$I_L(t)=(\frac{1}{x_1-x_2}(x_2e^{x_1t}-x_1e^{x_2t}) + 1)H(t)
$$  
E la soluzione al caso sottosmorzato:  
$$I_L(t)=(-\frac{\omega_0}{\omega_d}e^{-\alpha t}\cos(\omega_d t-\phi)+1)H(t)$$  
Ed osserviamo il comportamento della corrente descritto da queste due equazioni in maniera grafica:  

![Image](img/lez10/eq_rlc_stato_zero.png)  

Proviamo quindi a studiare il comportamento della tensione di lato partendo dalle equazioni della corrente che abbiamo ricavato.  

![Image](img/lez10/tensione_di_lato_rlc_stato_zero.png)  

Notare come nel caso sottosmorzato la tensione di lato segue un'andamento sinusoidale, e cioè parte da 0.  
Ciò implica che nell'istante subito successivo all'accensione del generatore, nel resistore non scorrerà corrente, perchè deve seguire l'equazione $V_R = RI_R$, e quindi se $V_R = 0$ allora anche $I_R = 0$. E sicuramente non scorrerà corrente nell'induttore, in quanto si evince dall'equazione per la corrente dell'induttore, che parte anch'essa da 0, nell'istante 0. Quindi tutta la corrente nell'istante $t=0^+$ scorrerà all'interno del condensatore.  

Notiamo inotre che sempre nel caso sottosmorzato, se facciamo il limite per $t \to 0$ dell'equazione della tensione di lato del circuito, troviamo come si comporta la tensione in 0 e come varia la corrente in 0, in quanto vale sempre la relazione $I_C=\frac{d}{dt}V_C(t)$:  
$$\lim_{t\to 0}V(t)=\sqrt{\frac{L}{C}}\omega_{0}t$$  
Per tempi piccoli la tensione è proporzionale al tempo e la corrente ha una variazione direttamente proporzionale al tempo.  

Proviamo quindi a trovare la risposta all'impulso del circuito RLC partendo dalla risposta al gradino, ricordandoci sempre che vale la relazione $h(t) = \frac{d}{dt}g(t)$, per cui:  
$$h(t)=\frac{1}{L}\cdot\sqrt{\frac{L}{C}}\frac{\omega_0}{\omega_d}e^{-\alpha t}\sin(\omega_d t)H(t)=\frac{\omega_0^2}{\omega_d}e^{-\alpha t}\sin(\omega_d t)=I_L^\delta(t)$$  
$$V^\delta(t)=L\frac{dI_L^\delta(t)}{dt}=\sqrt{\frac{L}{C}}\frac{\omega_0^2}{\omega_d}e^{-\alpha t}\cos(\omega_d t + \phi)H(t)$$  
Da ciò scopriamo che la corrente nell'induttore, in risposta ad un impulso, sarà un'oscillazione centrata in $0$ che partità sempre da $0$ e col tempo si annullerà. Mentre la tensione di lato è più interessante, infatti sarà sempre un'oscillazione centrata in $0$ che col tempo viene dissipata ma questa volta non parte da $0$, anzi segue l'andamento del coseno ed inoltre ricompare il termine dello sfasamento di $\phi$ e quindi la tensione di lato iniziale sarà una funzione dei valori di R, L e C.  
Si può infatti ricavare che $cos(\omega_dt+\phi)=0$ quando $t=\frac{\frac{\pi}{2}-\phi}{\omega_d}$.  

Se proviamo a scrivere l'equazione differenziale dell'RLC in serie, notiamo che è molto simile all'equazione differenziale dell'RLC parallelo. Le due equazioni infatti, sono tanto simili da poter trovare un cambio di variabili che ci permetta istantaneamente di trovare le soluzioni del circuito in serie partendo dalla variante parallela.  
Quando ciò accade si dice che i due circuiti sono **duali** ossia conoscendo le soluzioni di un circuito posso trovare direttamente le soluzioni dell'altro valutando la corrispondenza tra le due equazioni.  

---
Le Tensioni Di Nodo:
--------------------

Possiamo definire dei nuovi riferimenti chiamati tensioni di nodo, che ci torneranno utili nella vita reale nella progettazione e lo studio di circuiti elettrici.  
Ci basterà sacrificare un nodo che faccia da riferimento, e poi potremo esprimere un valore di tensione ad ogni altro nodo della rete con riferimento a questo nodo.  

![Image](img/lez10/tensione_di_nodo.png)  

---
La Rete Schematizzata:
----------------------

Possiamo schematizzare una generica rete con un ingresso ed un'uscita come un blocco 'N', per cui graficamente: $x(t) \to N \to y(t)$.  
Allora sappiamo che varrà la relazione:  
$$\frac{d^ny(t)}{dt^n}+a_1\frac{d^{n-1}y(t)}{dt^{n-1}}+...+a_ny(t)=b_0\frac{d^mx(t)}{dt^m}+b_1\frac{d^{m-1}x(t)}{dt^{m-1}}+...+b_mx(t)$$  
Allora possiamo scrivere la soluzione dell'omogenea come:  
$$s^n+a_1s^{n-1}+...+a_ns=0$$  
E questa avrà soluzioni: $s_1, s_2, ..., s_n$.  
Allora possiamo scrivere che:  
$$y(t) = y^h(t) + y^P(t)$$
Dove la forma dell'omogenea sarà del tipo:  
$$y^h(t)=\sum_{i=1}^nk_ie^{s_it}$$  
Ove $s_1, s_2, ..., s_n$ distinte.  
Questo vale quindi per circuiti di qualsiasi ordine.  

---
L'Integrale Di Convoluzione:
----------------------------

Vogliamo ora capire come possiamo studiare il comportamento di un circuito LTI con un ingresso arbitrario.  
Dove l'ingresso dev'essere una funzione continua a tratti.  
E proviamo a fare ciò con una rete di cui conosciamo solo la risposta all'impulso.  

![Image](img/lez10/integrale_di_convoluzione.png)  

Scopriamo quindi che in un circuito LTI, la risposta ad un segnale generico non sarà altro che l'integrale di convoluzione e si può ricavare a partire dalla conoscenza della risposta impulsiva del circuito.  
Quindi preso un circuito sappiamo che se $x(t) \to N \to y(t)$ allora per definizione $\delta(t) \to N \to h(t)$. Ed inoltre, in quanto circuito LTI varrà anche $\delta(t-\tau) \to N \to h(t-\tau)$.  
Possiamo dire che varrà anche:  
$$x(t')\delta(t-t') \to N \to x(t')h(t-t')$$  
Ma allora sappiamo che:  
$$\int_{-\infty}^{+\infty}x(t')\delta(t-t')dt\to N \to\int_{-\infty}^{+\infty}x(t')h(t-t')dt$$  
Ma questo è equivalente a scrivere:  
$$x(t)\to N \to \int_{-\infty}^{+\infty}x(t')h(t-t')dt$$  
Ma allora:  
$$y(t) = \int_{-\infty}^{+\infty}x(t')h(t-t')dt=x(t)*y(t)$$  
Definiamo ora alcune proprietà dell'integrale di convoluzione:  
- E' lineare:  
$h(t)*(\alpha x_1(t)+\beta x_2(t))=\alpha h(t)*x_1(t)+\beta h(t)*x_2(t)$  
- E' causale:  
Se $x(t)=0\space\forall t<0 \Longrightarrow y(t)$ dipende da $x(t') : 0 \le t' < t$  
- E' un'invariante temporale:  
Posto che $y(t)=x(t)*h(t) \Longrightarrow y(t-\tau)=x(t-\tau)*h(t)$  
- Ha una forma equivalente:  
$y(t)=\int_{t_0}^tx(t')h(t-t')dt=\int_{0}^{t}x(t-t')h(t')dt'$  
