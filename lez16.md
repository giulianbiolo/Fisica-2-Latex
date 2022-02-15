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

Fisica 2 - Lezione 16
=====================

Riprendendo dalla lezione precedente, proviamo a risolvere lo stesso circuito ma questa volta avvalendoci dei fasori.  

![Image](img/lez16/rlc_fasori.PNG)  

Notiamo come la $\tilde{H}(\omega)$ è molto simile alla $I(s)$ che avevamo trovato nella lezione precedente. Così simile che se poniamo $s=j\omega$ sono uguali, chiaramente dobbiamo chiederci se è lecito porre $s=j\omega$ e dobbiamo controllare le ROC della trasformazione da $I(t)$ ad $I(s)$, se comprendono l'asse immaginario allora sarà un'operazione lecita.  

Si può dimostrare infatti questa relazione:  

![Image](img/lez16/fasori_dimostrazione.PNG)  

