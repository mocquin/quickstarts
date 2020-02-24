

# Latex
Pour écrire du latex : Mathjax
Inline expressions can be added by surrounding the latex code with $:

bla blabl $e^{i\pi} + 1 = 0$ blablalb

Expressions on their own line are surrounded by $$:

$$e^x=\sum_{i=0}^\infty \frac{e^{334}}{i+1!}x^i$$




# Equation
## Source

```
\begin{align}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{align}
```
## Display
\begin{align}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{align}

### Source
```
\begin{equation*}
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
\end{equation*}
```
### Display
\begin{equation*}
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
\end{equation*}

### Source
```
\begin{equation*}
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0
\end{vmatrix}  
\end{equation*}
```
### Display
\begin{equation*}
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} & \mathbf{j} & \mathbf{k} \\
\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\
\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0
\end{vmatrix}  
\end{equation*}

# Combinatoire
## Source
```
\begin{equation*}
P(E)   = {n \choose k} p^k (1-p)^{ n-k} 
\end{equation*}
```
## Display
\begin{equation*}
P(E)   = {n \choose k} p^k (1-p)^{ n-k} 
\end{equation*}

# Fraction
## Source
```
\begin{equation*}
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } } 
\end{equation*}
```
## Display
\begin{equation*}
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } } 
\end{equation*}

### Source 
```
\begin{equation*}
1 +  \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots =
\prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})},
\quad\quad \text{for $|q|<1$}. 
\end{equation*}
```
### Display
\begin{equation*}
1 + \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots =
\prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})},
\quad\quad \text{for $|q|<1$}. 
\end{equation*}

### Source
```
\begin{align}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\   \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0 
\end{align}
```
### Display
\begin{align}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\   \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0 
\end{align}

# Inline
## Source
``` This expression $\sqrt{3x-1}+(1+x)^2$ is an example of a TeX inline equation in a **[Markdown-formatted](http://daringfireball.net/projects/markdown/)** sentence.  
```
## Display
This expression $\sqrt{3x-1}+(1+x)^2$ is an example of a TeX inline equation in a **[Markdown-formatted](http://daringfireball.net/projects/markdown/)** sentence.  

### Source
```
$$
\begin{array}{c}
y_1 \\\
y_2 \mathtt{t}_i \\\
z_{3,4}
\end{array}
$$
```

```
$$
\begin{array}{c}
y_1 \cr
y_2 \mathtt{t}_i \cr
y_{3}
\end{array}
$$
```

```
$$\begin{eqnarray} 
x' &=& &x \sin\phi &+& z \cos\phi \\
z' &=& - &x \cos\phi &+& z \sin\phi \\
\end{eqnarray}$$
```

```
$$
x=4
$$
```

### Display
$$
\begin{array}{c}
y_1 \\\
y_2 \mathtt{t}_i \\\
z_{3,4}
\end{array}
$$

$$
\begin{array}{c}
y_1 \cr
y_2 \mathtt{t}_i \cr
y_{3}
\end{array}
$$

$$\begin{eqnarray} 
x' &=& &x \sin\phi &+& z \cos\phi \\
z' &=& - &x \cos\phi &+& z \sin\phi \\
\end{eqnarray}$$

$$
x=4
$$

# Ressources 
http://nbviewer.jupyter.org/github/ipython/ipython/blob/3.x/examples/Notebook/Typesetting%20Equations.ipynb


# Règles de LaTeX pour écrire des maths

Caractères pour écrire du texte : 
```
a-z A-Z 0-9 + = * / ( ) [ ]
```

Caractères de ponctuaction : 
```
, ; . ? ! : ‘ ’ -
```

Modifiers : 
```
\# $ % & ~ ^ \ f g @ " j
```

Modifiers supplémentaires pour les maths : 
| < >

Exemples :

$$a \cdot b$$  
$$a \times b$$    
$$a + b$$  
$$a - b$$  
$$-a$$  
$$a / b$$  
$$a b$$     
$$\frac{1 + 2x}{x + y + xy}$$  
$$a_{i_{1}}$$ 
$$a^{2}$$
$$a^{i_{1}}$$  
$$\bar{a}$$  
$$\hat{a}$$ 
$$\tilde{a}$$ 
$$\vec{a}$$  
$$\left( \frac{1 + x}{2 + y^{2}} \right)^{2}  $$
$$\left| \frac{a + b}{2} \right|  $$
$$\quad \left\| A^{2} \right\|  $$
$$\sin x$$  
$$\lim_{x \to 0} f(x) = 0$$
$$F(x_{1}, x_{2}, \ldots , x_{n})$$  
$$x_{1} + x_{2} + \cdots + x_{n}$$  
$$\int_{0}^{\pi} \sin x \, dx = 2$$  
$$\sqrt[n]{5}$$  
$$\sum_{i=1}^{n}$$  
$$x_{i}^{2} \qquad \prod_{i=1}^{n} x_{i}^{2}$$  
$$\sum_{i = 1}^{ \left[ \frac{n}{2} \right] }$$  
$$\binom{ x_{i, i + 1}^{i^{2}} }$$  
$$\frac{ \sqrt{ \mu(i)^{ \frac{3}{2}} (i^{2} - 1) } }$$  
$${ \sqrt[3]{\rho(i) - 2} + \sqrt[3]{\rho(i) - 1} }$$  
$$( a ), [ b ], \{ c \}, | d |, \| e \|,$$  
$$\langle f \rangle, \lfloor g \rfloor,$$  
$$\lceil h \rceil, \ulcorner i \urcorner$$ 
$$\alpha \beta \gamma \digamma \delta \epsilon \varepsilon \zeta \eta \theta \vartheta \iota \kappa \varkappa \lambda \mu \nu \xi \pi \varpi \rho \varrho \sigma \varsigma \tau \upsilon \phi \varphi \chi \psi $$  
$$ \begin{matrix}
  a & b & c \\
  d & e & f \\
  g & h & i
 \end{matrix}
$$

