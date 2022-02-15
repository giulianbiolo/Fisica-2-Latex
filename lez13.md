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

Fisica 2 - Lezione 13
=====================

Riprendendo dalle frequenze di taglio del passabanda trovate nell'ultima lezione:  
$$\omega_{3dB}=\sqrt{\frac{\omega_0^2}{Q^2}+4\omega_0^2}\mp\frac{\omega_0}{Q}$$  
Possiamo quindi definire anche la **larghezza di banda** come:  
$$\Delta\omega_{3dB}=\omega_{3dB,2}-\omega_{3dB,1}=\frac{\omega_0}{Q}$$  
Ricordiamo che:  
$$P(t)=I(t)\cdot V(t)$$  
Posto che:  
$$I(t)=|\tilde{I}(t)|\cos(\omega t+\phi_{I})$$  
$$V(t)=|\tilde{V}(t)|\cos(\omega t+\phi_{V})$$  
Allora:  
$$P(t)=|\tilde{I}(t)|\cos(\omega t+\phi_{I})\cdot|\tilde{V}(t)|\cos(\omega t+\phi_{V})$$  
$$P(t)=\frac{|\tilde{I}||\tilde{V}|}{2}(\cos(\omega t + \phi_I-\omega t -\phi_V)+cos(2\omega t + \phi_I + \phi_V))$$  
$$P(t)=\frac{|\tilde{I}||\tilde{V}|}{2}\cos(\phi_I-\phi_V)+\frac{|\tilde{I}||\tilde{V}|}{2}\cos(2\omega t)$$  
Se volessi trovare ora la potenza media su un periodo, mi accorgo che la componente $\cos(2\omega t)$ si annulla completamente, in quanto l'integrale su due periodi di un coseno, o in generale su n-periodi, è pari a zero.  
Quindi la potenza media dipende interamente da quello sfasamento tra corrente e tensione.  
Per cui:  
$$\tilde{P}_{media}=\frac{|\tilde{I}||\tilde{V}|}{2}=\frac{1}{2}|\tilde{V}||\tilde{I}|e^{i(\phi_V-\phi_I)}$$  
Definiamo quindi il **valore quadratico medio** come:  
$$x_{rms}=\sqrt{\frac{1}{T}\int_{0}^Tx^2(t)dt}\in\mathbb{R}$$  
Nel caso di una sinusoide, basta applicare la formula e ricordandoci che $\cos^2(x)=\frac{\cos(2x)+1}{2}$ riusciamo a trovare facilmente la primitiva all'interno dell'integrale, da cui si scopre che la potenza rms di una sinuoside vale $x_{rms}=\frac{|\tilde{X}|}{\sqrt{2}}$.  

---
La Serie Di Fourier:
--------------------

Se $f(x)$ è periodica di periodo $T=2\pi$ allora:  
$$f(x)=\frac{a_0}{2} + \sum_{n=1}^{\infty}a_n\cos(nx)+\sum_{n=1}^{\infty}b_n\sin(nx)$$  
Da cui:  
$$a_n=\frac{1}{\pi}\int_{0}^{2\pi}f(x)cos(nx)dx,\space n=0,1,...,\infty$$  
$$b_n=\frac{1}{\pi}\int_{0}^{2\pi}f(x)sin(nx)dx,\space n=1,...,\infty$$  
Queste formule sono leggermente flessibili in quanto non è importante integrare in $[0, 2\pi]$ ma bensì l'importante è lo star integrando su un periodo, se per esempio la funzione fosse periodica di $3\pi$ potrei integrare sia su $[-1.5\pi,1.5\pi]$ che su $[-3\pi, 0]$ o anche su $[0, 3\pi]$.  
Poi il moltiplicatore $\frac{1}{\pi}$ vale solo sul seno di periodicità $2\pi$ infatti si tratterebbe di $\frac{2}{T}$.  
E l'argomento delle funzioni seno e coseno è in generale $n\omega x$.  
In generale si può riscrivere l'equazione come:  
$$f(x)=\frac{a_0}{2}+\sum_{n=0}^{\infty}a_n\frac{e^{in\omega_0x}+e^{-in\omega_0x}}{2}+\sum_{n=1}^{\infty}b_n\frac{e^{i\omega_0nx}-e^{-i\omega_0nx}}{2i}$$  
Da cui:  
$$f(x)=\frac{a_0}{2}+\sum_{n=0}^{\infty}a_n\frac{e^{in\omega_0x}+e^{-in\omega_0x}}{2}-i\sum_{n=1}^{\infty}b_n\frac{e^{i\omega_0nx}-e^{-i\omega_0nx}}{2}$$  
$$f(x)=\frac{a_0}{2}+\sum_{n=1}^{\infty}e^{i\omega_0nx}(\frac{a_n-ib_n}{2})+e^{-i\omega_0nx}(\frac{a_n+ib_n}{2})$$  
Che si può riscrivere come:  
$$f(x)=C_0+\sum_{n=1}^{\infty}C_ne^{i\omega_0nx}+C_{-n}e^{-i\omega_0nx},\space C_n\in\mathbb{C}$$  
Dove $C_{\pm n}=\frac{a_n\mp ib_n}{2}$ e $C_0=\frac{a_0}{2}$.  
Quindi possiamo ricavare $C_n$ come:  
$$C_n=\frac{1}{2}\int_{-L}^{L}f(x)e^{-i\omega_0nx}dx, \space T=2L$$  
Applicando queste equazioni è immediato dimostrare che un'onda quadra che oscilla in $[0, l]$ con periodo $T=2\pi$ si può scrivere come:  
$$f(x)=\frac{l}{2}+\frac{2l}{\pi}\sum_{k=1}^{\infty}\frac{\sin((2k-1)x)}{2k-1}$$  

---
La Trasformata Di Fourier:
--------------------------

Definiamo la **Trasformata Integrale** come:  
$$g(\alpha)=\int_{a}^{b}
f(x)k(\alpha, x)dx$$  
Ove $k(\alpha, x)=e^{i\alpha x}$  
Riscriviamo il coefficiente $C_n$ come:  
$$\tilde{C_n}=\sqrt{2L}C_n$$  
Da cui:  
$$\tilde{C_n}=\frac{1}{\sqrt{2L}}\int_{-L}^{L}f(x)e^{-i\omega_0nx}dx, \space T=2L$$  
E se $L\gg \pi$ allora $\omega_0=\frac{2\pi}{2L}$ e quindi $\frac{\pi}{L}\ll 1$.  
Poniamo $\omega_n=n\omega_0$ per cui:  
$$\tilde{C_n}\sqrt{\frac{L}{\pi}}=\frac{1}{\sqrt{2\pi}}\int_{-L}^{L}f(x)e^{-i\omega_n x}dx=F(\omega_n)$$  
$$f(t)=\frac{1}{\sqrt{2\pi}}\sum_{n=-\infty}^{\infty}\tilde{C_n}\sqrt{\frac{L}{\pi}}e^{i\omega_n x}=\frac{1}{\sqrt{2\pi}}\sum_{n=-\infty}^{\infty}F(\omega_n)e^{i\omega_n x}$$  
Definiamo allora la **Trasformata Inversa Di Fourier** come:  
$$f(x)=\frac{1}{2\pi}\int_{-\infty}^{+\infty}F(\omega_n)e^{i\omega_n x}dx$$  
E Definiamo come **Trasformata Di Fourier** l'equazione:  
$$F(\omega)=\frac{1}{\sqrt{2\pi}}\int_{-L}^{L}f(t)e^{-i\omega t}dt$$  
Importante proprietà della trasformata di fourier è che:  
$$\mathbb{F}[f'(t)](\omega)=(i\omega)\mathbb{F}[f(t)](\omega)$$  
Quindi la trasformata della derivata di una funzione, non è altro che la trasformata della funzione moltiplicata per un fattore $i\omega$.  
