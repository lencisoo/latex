# Distribuciones de probabilidad 
Este documento fue creado para la clase de probabilidad de la maestría en bioestadística de la PUJ. El codigo tiene dirección a imágenes de un repositorio local por lo que deben ser modificadas antes de su compilación en caso de utilizarlo. Las fórmulas están creadas en su totalidad en latex nativo utilizando un editor en los casos más complejos. 

```LATEX

\usepackage[utf8]{inputenc} % Para las tildes
\usepackage[spanish, es-tabla]{babel}
\usepackage{graphicx}
\usepackage{booktabs} % Better horizontal rules in tables
\usepackage{float}
\usepackage{amsmath}

%opening
\title{Distribuciones de probabilidad }
\author{Leonardo José Enciso Olivera}

\begin{document}

\maketitle

\begin{abstract}
Este documento resume las características de algunas distribuciones de probabilidad, tanto discretas como continuas. Se presentan la definición, la función de densidad $f_x(X)$, la función de distribución $F_x(x)$, la media y la varianza. 
\end{abstract}

\tableofcontents

\section{Distribuciones de probabilidad discretas}

\subsection{Distribución uniforme discreta }

\subsubsection{Definición}
Esta distribución describe situaciones donde el experimento aleatorio puede tener un número finito de resultados y la probabilidad de ocurrencia es la misma para cada resultado. 

\subsubsection{Ejemplo práctico}
El lanzamiento de un dado corriente o el lanzamiento de una moneda

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución uniforme discreta sobre el conjunto ${1, \cdots, N}$ si su función de densidad esta dada por:
 
\begin{center}
$f_x(x)=Pr(X=x)=\frac{1}{N}$
\end{center}

Si $[x=1,\cdots,N]$

$0$ en otro caso 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Media:} $E(X)=\frac{N+1}{2}$
	\item \textbf{Varianza:}$Var(X)=\frac{N^2-1}{12}$
\end{itemize}

\subsubsection{Función de distribución}
$F_x(x)=\frac{1}{n}\sum_{i=1}1_(-\infty,x)(x_i)$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics{uniforme_discreta}
	\label{uniforme}
\end{figure}

\subsection{Distribución Bernoulli}

\subsubsection{Definición}
Si se considera un experimento aleatorio que solo tiene dos posibles resultados que se etiquetan como éxito o fracaso, donde la probabilidad de éxito es denotada $p$, con $0<p<1$, una variable aleatoria que toma valor 1 si tiene \textit{éxito} y valor 0 cuando \textit{fracasa}, se dice que tiene distribución Bernoulli con parámetro $p$

\subsubsection{Ejemplo práctico}
El envio de un volante promocional que invita a llamar para pedir un servicio. Tiene éxito si el receptor llama y fracaso si no lo hace

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Bernoulli con parámetro $p\in(0,1)$, si su función de densidad esta dada por:

\begin{center}
	$f_x(x)=p^x(1-p)^{1-x}$, con $x={0,1}$
\end{center}

Si $f(x,p)$, entonces su formula será
 
$P(X=1) = p $

$P(X=0) = q $, donde $q=(1-p)$

\subsubsection{Notación}
$X\sim Ber(p)$ 

\subsubsection{Propiedades de la distribución}
\begin{itemize}
	\item \textbf{Parámetros:}$0<p<1$, con $p\in Real$
	\item \textbf{Media:} $E(X)=p$
	\item \textbf{Varianza:}$Var(X)=p(1-p)$
\end{itemize}


\subsubsection{Función de distribución}
$0$ para $x < 0$

$q$ para $0<=x<1$

$1$ para $x>1$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics{bernoulli}
	\label{Bernoulli}
\end{figure}

\subsection{Distribución Binomial}

\subsubsection{Definición}
En muchas situaciones no se realiza un solo ensayo de tipo Bernoulli sino una serie de ensayos. En este caso la variable de interés el el número de éxitos en $n$ ensayos de tipo Bernoulli. Este tipo de variables se describen por la distribución binomial. 

\subsubsection{Ejemplo práctico}
Siguiendo con el ejemplo de enviar un volante promocional, siendo el éxito que el receptor llame y el fracaso que no lo haga, el volante puede ser enviado a 100 personas distintas. Con la función de probabilidad podría estimar la probabilidad de que de 100 ensayos (envíos), 10 fueran éxitos (contestaran). 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Binomial con parámetro $n\in N$ y $p\in(0,1)$, si su función de densidad esta dada por:

\begin{center}
	$f_x(x)=Pr(X=x)=\binom{N}{x}p^x(1-p)^{n-x}$, con $x={0,\cdots,n}$ y $0<p<1$
\end{center}

\subsubsection{Notación}
$X\sim Bin(n,p)$ 

\subsubsection{Propiedades de la distribución}
\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $n>=0$ corresponde al número de ensayos y es un número natural natural 
		\item $0<=p<=1$ corresponde a la probabilidad de éxito
	\end{itemize}
	\item \textbf{Media:} $E(X)=np$
	\item \textbf{Varianza:}$Var(X)=np(1-p)$ o puede expresarse $npq$
\end{itemize}

\subsubsection{Función de distribución}
$I_q(n-k, 1+k)$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{binomial}
	\label{Binomial}
\end{figure}

\subsection{Distribución Hipergeométrica}

\subsubsection{Definición}
Describe situaciones en las que se desea extraer un número $n$ de unidades de un conjunto de $N$ objetos, que se pueden dividir en dos grupos, el primero de $R$ unidades y el segundo de $N-R$ unidades. La variable de interés es el número de unidades extraídas del primer grupo la cual tendrá distribución hipergeométrica con parametros $n, R y N$. 

\subsubsection{Ejemplo práctico}
Si se tienen un grupo de 15 estudiantes de los cuales 10 son hombres y 5 son mujeres y se desea extraer una muestra de 6 estudiantes, la variable X, definida como el número de estudiantes hombres seleccionados, tiene distribución hipergeométrica con parámetros (6,10,15)

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución hipergeométrica con parámetros $n$, $R$ y $N$, si su función de densidad esta dada por:

\begin{center}
	$f_x(x)=Pr(X=x)=\frac{\binom{R}{x}\binom{N-R}{n-x}}{\binom{N}{n}}$
\end{center}

\subsubsection{Notación}
$X\sim Hg(n,R,N)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $n$ que es un número natural, corresponde al número de unidades que se desea extraer 
		\item $N$ que es un número natural, corresponde al número total de objetos 
		\item $R$ que es un número natural, corresponde a un grupo del total de objetos. Si se suma $R + (N-R) = N$
	\end{itemize}
	\item \textbf{Media:}$E(X)=\frac{nR}{N}$
	\item \textbf{Varianza:}$Var(X)=\frac{nR(N-R)(N-n)}{N^2(N-1}$
\end{itemize}

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{hipergeo}
	\label{Hipergeo}
\end{figure}

\subsection{Distribución Poisson}

\subsubsection{Definición}
La distribución Poisson se utiliza para describir variables aleatorias en las cuales se presenta un número de ocurrencias de un evento o fenómeno durante un periodo definido de tiempo o en un área determinada, cuando la probabilidad de ocurrencia del fenómeno es constante en el tiempo o el área. 

\subsubsection{Ejemplo práctico}
Como se presenta en la definición, aquellos fenómenos que se presentan en un número determinado por unidad de tiempo o área pueden describirse con esta distribución. Así por ejemplo, el número de llamadas telefónicas que ingresa a una central telefónica por mínuto, sigue esta distribución. Otro ejemplo sería el número de motos que pasan por un punto determinado en una hora. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Poisson con parámetro $\lambda>0$ , si su función de densidad esta dada por:

\begin{center}
	$f_x(x)=Pr(X=x)=\frac{e^(-\lambda)\lambda^x}{x!}$
\end{center}

Donde $x$, es el número de ocurrencias del evento y $\lambda$ es un parámetro positivo que representa el número de veces que se espera que el fenómeno o evento suceda durante un intervalo dado. 

Si se esperan $x=5$ llamadas por minuto a una central telefónica y queremos calcular la probabilidad de que $x$ ocurra dentro de un intervalo de 10 minutos, el parámetro $\lambda$ sera igual a $\lambda=(5)(10)=50$ 

\subsubsection{Notación}
$X\sim Pois(\lambda)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $\lambda(0,\infty)$
	\end{itemize}
	\item \textbf{Media:}$E(X)=\lambda$
	\item \textbf{Varianza:}$Var(X)=\lambda$
\end{itemize}

\subsubsection{Función de distribución}
$F_x(x)=e^(-\lambda)\sum_{i=0}^{x}\frac{\lambda^1}{i!}$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{poisson}
	\label{Poisson}
\end{figure}

\subsection{Distribución Geométrica}

\subsubsection{Definición}
La distríbución geométrica describe experimentos que comparten características con el experimento binomial. El experimento consiste en pruebas idénticas e independientes que pueden tener como resultado éxito o fracaso. La probabilidad $p$ es constante de una prueba a la otra. A diferencia del experimento binomial, la variable aleatoria de interés no es el número de éxitos que se presentan en $n$ pruebas, sino la variable $Y$ que es el número de prueba en la que se presenta el primer éxito. El experimento podría terminar en la primera prueba o extenderse de forma infita

\subsubsection{Ejemplo práctico}
Un ejemplo simple podría ser el número de veces que se arroja un dado hasta que el resultado es 6. La variable $Y$ sería el primer número de intentos hasta el primer éxito. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución geométrica con parámetro $p$ , si su función de densidad esta dada por:

Si hay $k$ ensayos donde $k\in(1,2,3,\cdots)$ y para $0<p<1$ probabilidades de éxito

\begin{center}
	$f_x(x)=Pr(X=k)=(1-p)^{k-1}p$
\end{center}

Si hay $k$ fallas donde $k\in(0,1,2,3,\cdots)$ y para $0<p\leq1$ probabilidades de éxito

\begin{center}
	$f_x(k)=Pr(X=k)=(1-p)^(k)p$
\end{center}

\subsubsection{Notación}
$X\sim Geom(p)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $p$
	\end{itemize}
	\item \textbf{Media:}$E(X)=\frac{1}{p}$
	\item \textbf{Varianza:}$Var(X)=\frac{1-p}{p^2}$
\end{itemize}

\subsubsection{Función de distribución}
$F_x(k)=1-(1-p)^k$

$F_x(k)=1-(1-p)^{k+1}$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{geometrica}
	\label{Geometrica}
\end{figure}

\subsection{Distribución Binomial negativa}

\subsubsection{Definición}
Se origina en un experimento similar al de la distribución geométrica. Se trata en intentos independientes e idénticos, cada uno de los cuales tiene como resultado éxito o fracaso. La distribución geométrica toma como variable de interés el número del intento donde se obtiene el primer éxito. Si estamos interesados en conocer el número de intento en el que ocurre el segundo, tercero u otro éxito, la variable aleatoria $Y$ que es igual al número del intento en el que se presenta el r-ésimo éxito, es una distribución binomial negativa.

\subsubsection{Ejemplo práctico}
Si se tiene un pozo petrolero en una región y se sabe que debe producir petróleo con una probabilidad de 0.2, se puede tener interés en calcular la probabilidad de que el tercer descubrimiento de petróleo llegue en el quinto pozo perforado 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución binomial negativa con parámetro $r,p$ , si su función de densidad esta dada por:


\begin{center}
	$f_x(y)=\binom{y-1}{r-1}p^rq^{y-r}$
\end{center}

\subsubsection{Notación}
$X\sim NB(r,p)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $r,p$, donde $r$ es el número de fallas hasta que el primer experimento se detiene
	\end{itemize}
	\item \textbf{Media:}$E(Y)=\frac{r}{p}$
	\item \textbf{Varianza:}$Var(X)=\frac{r(1-p)}{p^2}$
\end{itemize}

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{binomialn}
	\label{Binomialn}
\end{figure}

\section{Distribuciones de probabilidad continuas}

\subsection{Distribución Uniforme continua}

\subsubsection{Definición}
Se trata de una familia de distribuciones en la cual, para cada miembro de la familia, todos los intervalos de igual longitud a lo largo de su rango son igualmente probables.

\subsubsection{Ejemplo práctico}
Un autobus para cada 15 minutos por un paradero. Se quiere calcular la probabilidad de que una persona que llega en un determinado momento, tenga que esperar mas de 5 minutos. Esta variable tiene una distríbución uniforme continua. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución uniforme continua con parámetros $a,b \in(-\infty,\infty)$, si su función de densidad esta dada por:

\begin{equation*}
f(x) =
\begin{cases}
\frac{1}{b-a} & \text{si a $\leq$ x $\leq$ b}\\
0  & \text{si $x<a$ o $x>b$}
\end{cases}
\end{equation*}

\subsubsection{Notación}
$X\sim U(a,b)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $a,b \in(-\infty,\infty)$
	\end{itemize}
	\item \textbf{Media:}$E(X)=\frac{a+b}{2}$
	\item \textbf{Varianza:}$Var(X)=\frac{(b-a)^2}{12}$ 
\end{itemize}

\subsubsection{Función de distribución}
$F(x)= \frac{x-a}{b-a}$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{continuau}
	\label{continuau}
\end{figure}

\subsection{Distribución Normal}

\subsubsection{Definición}
Es la distribución de probabilidad continua que se utiliza con más frecuencia. Numerosos datos de eventos naturales tienen esta distribución que tiene la forma de campana característica. 

\subsubsection{Ejemplo práctico}
Los calificaciones obtenidas por todos los estudiantes de Bogotá en las pruebas SABER durante un año, tienen distribución normal y la probabilidad de obtener un determinado valor puede ser estimada con esta distribución. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución normal con parámetros $\mu, \sigma^2$, si su función de densidad esta dada por:

\begin{equation*}
f(y) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(y-\mu)^2}{2\sigma^2}} 
\end{equation*}


\subsubsection{Notación}
$X\sim U(a,b)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $\mu$
		\item $\sigma^2$  $>0$ 
	\end{itemize}
	\item \textbf{Media:}$E(X)=\mu$
	\item \textbf{Varianza:}$\sigma^2$  $>0$ 
\end{itemize}

\subsubsection{Función de distribución}
No tiene una formula explicita y se debe calcular numericamente realizando la integral de la función de densidad. 

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{normal}
	\label{normal}
\end{figure}

\subsection{Distribución Gamma}

\subsubsection{Definición}
La distribución gamma es una distribución de gran importancia porque muchas distribuciones de uso común como la distribución exponencial y la distribución Ji-cuadrado son casos particulares de la misma. Esta distribución solamente toma valores positivos y tiene una función de densidad asimétrica porque el coeficiencia de asimetría es positivo. 

\subsubsection{Ejemplo práctico}
El salario de la población tiene una distribución Gamma. La mayoría de la población tiene un ingreso inferior a 1 millón de pesos y a medida que el salario aumenta es menor el número de individuos que puede obtener ese ingreso. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución con parámetro de forma $k>0$ y parámetro de escala $\theta >0$ si su función de densidad esta dada por: 

\begin{equation*}
fx(x) =\frac{x^{k-1}e^{-x/\theta}}{\theta^k{\Gamma}(k)} 
\end{equation*}
	
Donde ${\Gamma}(k)$ es la función gamma dada por: 
	
\begin{equation*}	
{\Gamma}(k)= \int_{0}^{\infty}u^{k-1}e^{-u}du
\end{equation*}
	
\subsubsection{Notación}
$X\sim Gamma(k,\theta)$ 
	
\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $k>0$, que es el parámetro de forma
		\item $\theta >0$, que es el parámetro de escala
	\end{itemize}
	\item \textbf{Media:}$E(X)=k\theta$
	\item \textbf{Varianza:}$Var(X)=k\theta^2$
\end{itemize}
	
\subsubsection{Función de distribución}

	
\subsubsection{Gráfica de su función de densidad}
	
	\begin{figure}[H]
		\centering
		\includegraphics[width=0.7\textwidth]{gamma}
		\label{gamma}
	\end{figure}

\subsection{Distribución Beta}

\subsubsection{Definición}
La distribución Beta, es una distribución de dos parámetros, definida en el intervalo cerrado $0\leq y \leq 1$ 

\subsubsection{Ejemplo práctico}
Suele utilizarse para proporciones, como por ejemplo, la proporción de impurezas en un producto químico o la proporción de tiempo que una máquina falla. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución con parámetro $\alpha>0$ y $\beta>0$ si su función de densidad esta dada por: 

\begin{equation*}
f(x) =
\begin{cases}
\frac{y^{\alpha-1}(1-y)^{\beta-1}}{B(\alpha,\beta)} & \text{0$\leq$y$\leq$1}\\
0 & \text{en cualquier otro punto}
\end{cases}
\end{equation*}

donde 

\begin{equation*}
B(\alpha,\beta)=\int_{0}^{1}(1-y)^{\beta-1}dy 
\end{equation*}

\subsubsection{Notación}
$X\sim Gamma(k,\theta)$ 

\subsubsection{Propiedades de la distribución}
\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $\alpha>0$
		\item $\beta>0$
	\end{itemize}
	\item \textbf{Media:}$E(X)=\frac{\alpha}{\alpha+\beta}$
	\item \textbf{Varianza:}$Var(X)=\frac{\alpha\beta}{(\alpha+\beta)^2(\alpha+\beta+1)}$
\end{itemize}

\subsubsection{Función de distribución}
$I_x(\alpha\beta)$

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{beta}
	\label{beta}
\end{figure}

\subsection{Distribución Weibull}

\subsubsection{Definición}
La distribución Weibull es una distribución utilizada en una rama de la estadística conocida como análisis de sobrevivencia, la cual estudia variables que denotan el tiempo transcurrido hasta la ocurriencia de un evento. 

\subsubsection{Ejemplo práctico}
El tiempo desde el diagnóstico hasta la muerte de un paciente con una determinada enfermedad sigue este tipo de distribución. 

\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Weibull con parámetro de forma $k>0$ y parámetro de escala $\theta>0$ si su función de densidad está dada por: 

\begin{equation*}
f(x; \theta,k) =
\begin{cases}
\frac{k}{\theta^k}x^{k-1}e^{\frac{-x^k}{\theta^k}} & \text{$x>0$}\\
0 & \text{en cualquier otro punto}
\end{cases}
\end{equation*}

\subsubsection{Notación}
$X\sim Weibull(k,\theta)$ 

\subsubsection{Propiedades de la distribución}
\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $k>0$, que es el parámetro de forma 
		\item $\theta>0$, que es el parámetro de escala
	\end{itemize}
	\item \textbf{Media:}\begin{equation*}
	E(X)=\theta\Gamma(1+\frac{1}{k})
	\end{equation*}
	\item \textbf{Varianza:}\begin{equation*}
	Var(X)=\theta^2[\Gamma(1+\frac{2}{k})-(\Gamma(1+\frac{1}{k}))^2]
	\end{equation*}
\end{itemize}

\subsubsection{Función de distribución}
\begin{equation*}
1-e^{\frac{-x}{\theta}^k}
\end{equation*}

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics[width=0.7\textwidth]{weibull}
	\label{weibull}
\end{figure}

\subsection{Distribución Cauchy}

\subsubsection{Definición}
Esta distribución de probabilidad continua, fue introducida por Simeon Denis Poisson en 1824 pero debe su nombre al matemático francés Augustin Louis Cauchy, quien la reintrodujo en 1853. Esta distribución tiene dos parámetros: escala $(\mu)$ y situación $(\theta)$. En el caso en el que $\mu=1$ y $\theta=0$, recibe el nombre de distribución Cauchy estándar. Esta distribución se caracteriza por carecer de momentos, por lo que no existen la media, la varianza, la simetría o la curtosis. 

\subsubsection{Ejemplo práctico}
Un arquero con los ojos vendados se posiciona en frente de una pared. Se le indica que debe disparar flechas que den directamente en el blanco frente a el. Si el arquero esta posicionado en el punto (0,0) es posible que cada disparo impacte una parte diferente de la pared. En algunas ocasiones en (x,y) y en otras en (x,-y), pero es posible además que ni siquiera golpee la pared. 


\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Cauchy con parámetros de escala $(\mu)$ y situación $(\theta)$ si su función de densidad está definida por: 

\begin{equation*}
f_x(x)=Pr(X=x)= \frac{\mu}{\pi}\frac{1}{\mu^2+(x-\theta)^2}
\end{equation*}


\subsubsection{Notación}
$X\sim C(\mu,\theta)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item $(\mu)$ que es el parámetro de escala 
		\item $\theta$, parámetro de situación
	\end{itemize}
	\item \textbf{Media:}No tiene momentos 
	\item \textbf{Varianza:}No tiene momentos 
\end{itemize}

\subsubsection{Función de distribución}

\begin{equation*}
F(X)=\frac{1}{2}+\frac{\arctan(x)}{\pi}
\end{equation*}

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics{cauchy}
	\label{Cauchy}
\end{figure}

\subsection{Distribución Laplace}

\subsubsection{Definición}
Es también conocida como distribución doble exponencial. Es una distribúción de probabilidad continua que resulta de la diferencia de dos variables aleatorias exponenciales, independientes e idénticamente distribuidas. 

\subsubsection{Ejemplo práctico}
Se utiliza para describir variables aleatorias  como los valores máximos de precipitación y descarga de los rios. 


\subsubsection{Función de densidad}
Una variable aleatoria X tiene distribución Laplace con parámetros de localización $(\mu)$ y de escala $(b)$, si su función de densidad está definida por: 

\begin{equation*}
f(x)=\frac{1}{2b}\exp(-\frac{\mid{x-\mu}\mid}{b}
\end{equation*}

\subsubsection{Notación}
$X\sim L(\mu,b)$ 

\subsubsection{Propiedades de la distribución}

\begin{itemize}
	\item \textbf{Parámetros:}
	\begin{itemize}
		\item Parámetro de localización $(\mu)$, en el conjunto Real 
		\item Parámetro de escala $b>0$, en el conjunto Real
	\end{itemize}
	\item \textbf{Media:} $\mu$
	\item \textbf{Varianza:} $2b^2$
\end{itemize}
 
\subsubsection{Función de distribución}

\begin{equation*}
f(\mu;b) =
\begin{cases}
\frac{1}{2}\exp(\frac{x-\mu}{b}) \text si  x\leq \mu\\
1- \frac{1}{2}\exp(-\frac{x-\mu}{b}) \text si  x\geq \mu\\
\end{cases}
\end{equation*}

\subsubsection{Gráfica de su función de densidad}

\begin{figure}[H]
	\centering
	\includegraphics{laplace}
	\label{Laplace}
\end{figure}

\end{document}
