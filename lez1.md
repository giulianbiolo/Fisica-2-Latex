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
Fisica 2 - Lezione 1
====================

Obbiettivo:
-----------
    Circuito Reale -> Modello -> Previsione/Comprensione

---
Modelli:
--------
- A Parametri **Concentrati**
- A Parametri **Distribuiti**

Il Modello **A Parametri Concentrati** saranno la branca di modelli trattati in questo corso.  
In questi modelli possiamo trattare gli elementi in maniera isolata, senza valutare possibili interferenze interne al circuito stesso.  
Ciò avviene quando la dimensione delle componenti del circuito sono molto minori della lunghezza d'onda minima prodotta dal circuito ($\lambda \gg d$).

Nel caso di segnali audio:
    $$f_{max} = \frac{c}{\lambda_{min}} \land f_{max} = 20kHz <=> \lambda_{min} = \frac{c}{f_{max}} => \lambda_{min} \approx 15km$$

---
Elementi Circuitali:
--------------------
Tratteremo principalmente elementi circuitali a 2 morsetti.  
Dovremo prima di tutto, per studiare il circuito, definire un verso della corrente, si tratta di un riferimento puramente arbitrario.  
$$V(t) = \Delta V(t) = V_{A}(t) - V_{B}(t), se V_{A}(t) > V_{B}(t) => V(t) > 0$$  
$V(t)$ è detta quindi tensione di lato ed $I(t)$ è la corrente di lato.  

---
Leggi Di Kirchoff:
------------------
- KCL: Per ogni circuito a parametri concentrati, per ogni tempo, per ogni nodo, la somma algebrica di tutte le correnti di lato che entrano e lasciano il nodo è uguale a 0.
- KVL: Per ogni circuito a parametri concentrati, per ogni tempo, per ogni maglia, la somma algebrica di tutte le tensioni di lato che entrano ed escono dalla maglia sono uguali a 0.

---
Elementi Circuitali:
--------------------
- R: Resistenza o Resistore:  
    Qualsiasi elemento a 2 morsetti che in qualsiasi istante soddisfa la seguente relazione tra tensione e corrente di lato: $V(t) = I(t)R.$  
    Ne esistono di vari tipi:
    - Lineare / Non lineare:  
        Segue l'equazione lineare di Kirchoff: $V(t) = I(t)R.$  
        Anche detti resistori ohmici.  
    - Tempo Variante / Tempo Invariante:  
        Soddisfa la proprietà di tempo invarianza, ossia soddisfa la seguente relazione: $R(t) = R \space \forall t.$  

