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

Fisica 2 - Lezione 15
=====================

Nella lezione precedente abbiamo definito la trasformata di laplace come:  
$$F(s)=\int_0^\infty f(t)e^{-st}dt, \space s\in\mathbb{C}$$  
E ci siamo lasciati dicendo che in laplace le nostre equazioni, che sono come abbiamo visto tutte equazioni differenziali o integrodifferenziali diventeranno dei polinomi.  

Studiamo ora i passaggi per risolvere queste equazioni:  
- Riportare in **Forma Propria**:  
  $F(s)=\hat{P}(s)+\frac{R(s)}{Q(s)}$  
  Ove il grado di $R(s)$ è minore del grado di $Q(s)$.  
  Ossia per prima cosa raccogliamo quello che si riesce a raccogliere.  
- Esprimere $Q(s)$ come una produttoria, ovvero trovare i poli di $F(s)$.  
- Scomporre in frazioni parziali l'equazione:  
  $F(s)=\sum_{k}\frac{ki}{s-p_i}$  
  Questa equazione vale solo nel caso di **poli semplici**. Capita che ci siano poli doppi, o anche poli complessi.  

Dividiamo quindi lo studio in casistiche:  

Caso A - **Poli Semplici**:  

![Image](img/lez15/equazioni_parziali_poli_semplici.PNG)  

Caso B - **Poli Multipli**:  

![Image](img/lez15/equazioni_parziali_poli_multipli.PNG)  

Caso C - **Poli Complessi**:  

![Image](img/lez15/equazioni_parziali_poli_complessi.PNG)  

---
Il Circuito RLC:
----------------

Proviamo quindi a risolvere un circuito RLC utilizzando la trasformata di laplace:  

![Image](img/lez15/circuito_rlc_prima_parte.PNG)  

![Image](img/lez15/circuito_rlc_stato_zero.PNG)  

![Image](img/lez15/circuito_rlc_ingresso_zero.PNG)  
