<style TYPE="text/css">
code.has-jax {font: inherit; font-size: 100%; background: inherit; border: inherit;}
</style>
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    tex2jax: {
        inlineMath: [['$','$'], ['\\(','\\)']],
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'] // removed 'code' entry
    }
});
MathJax.Hub.Queue(function() {
    var all = MathJax.Hub.getAllJax(), i;
    for(i = 0; i < all.length; i += 1) {
        all[i].SourceElement().parentNode.className += ' has-jax';
    }
});
</script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/MathJax.js?config=TeX-AMS_HTML-full"></script>

## Bienvenidos a la galeria de fractales

Aqui alojare unos cuantos fractales hechos con codigo python. Los tipos de fractaes que se alojaran aqui sera los siguientes.

* Conjuntos de Newton
* Conjuntos de Julia
* Sistemas iterados de funciones 


### Conjuntos de newton

Aqui observaremos distintos fractales Newton y de paso datos como:
* Funcion utilizada para obtenerla
* Raices de la funcion
* Grafica de la velocidad y el punto de convergencia

![Mi primer Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%201.PNG)

```
import matplotlib.pyplot as plt
from PIL import Image
xa=-1
xb=1
ya=-1
yb=1
maxit=202
h=1e-6
eps=1e-3
def f(z):
    return z**3-1

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            dz=(f(z+complex(h,h))-f(z))/complex(h,h)
            z0=z-f(z)/dz
            if abs (z0-z)<eps:
                break
            z=z0
            r=i*8
            g=i*8
            b=i*8
            image.putpixel((x,y),(r,g,b))
image

```
La funcion matematica para este fractal fue $x^3-1$:
* Raiz real: $(1,0)$ 
* Raiz imaginaria:  
    * $-1/2-\frac{\sqrt{3}}{2}i$ 
    * $-\frac{1}{2}+\frac{\sqrt{3}}{2}i$

![Mi segundo Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Newton%202.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
xa=-1
xb=1
ya=-1
yb=1
maxit=202
h=1e-6
eps=1e-3
def f(z):
    return z**(3)-z+5

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            dz=(f(z+complex(h,h))-f(z))/complex(h,h)
            z0=z-f(z)/dz
            if abs (z0-z)<eps:
                break
            z=z0
            r=i*32
            g=i*16
            b=i*8
            image.putpixel((x,y),(r,g,b))
image

```
En este caso el polinomio usado fue $x^3-x+5$:
* Raiz real:$-1.9041608591349,0$
* Raiz Imaginaria: 
    * $0.9520804295675-1.3112480440771i $
    * $0.9520804295675+1.3112480440771i  $    

![Mi Tercer Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Newton%203.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
xa=-2
xb=2
ya=-2
yb=2
maxit=30
h=1e-6
eps=1e-3
def f(z):
    return z**(4)+z**3-1

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            dz=(f(z+complex(h,h))-f(z))/complex(h,h)
            z0=z-f(z)/dz
            if abs (z0-z)<eps:
                break
            z=z0
            r=i*8
            g=i*16
            b=i*32
            image.putpixel((x,y),(r,g,b))
image
```
En este caso el polinomio usado fue $x^4+x^3-1$:
* Raiz real: 
    * $-1.3802775690976+0i$
    * $0.8191725133962+0i$
* Raiz Imaginaria:
    * $-0.2194474721493-0.9144736629677i$
    * $-0.2194474721493+0.9144736629677i$
   
![Mi Cuarto Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Newton%204.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
xa=-2
xb=2
ya=-2
yb=2
maxit=30
h=1e-6
eps=1e-3
def f(z):
    return z**(3)+2*z**(2)-z+2

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            dz=(f(z+complex(h,h))-f(z))/complex(h,h)
            z0=z-f(z)/dz
            if abs (z0-z)<eps:
                break
            z=z0
            r=i*32
            g=i*8
            b=i*64
            image.putpixel((x,y),(r,g,b))
image
```
En este caso el polinomio usado fue $x^3+2x^2-x+2$:
* Raiz Real:
    * $-2.658967081917-0i$
* Raiz Imaginaria:
    * $0.3294835409585-0.8022545575574i$
    * $0.3294835409585+0.8022545575574i$

### Conjutos de Julia
Para los conjuntos de Julia daremos a conocer los siguientes aspectos.
* Funcion con la obtenimos el fractal
* Grafica de la velocidad y la convergencia

![Mi quintoo Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Julia%201.PNG)

```
import matplotlib.pyplot as plt
from PIL import Image
xa=-2
xb=2
ya=-2
yb=2
maxit=30
def f(z):
    return z**3+z+complex(0.2,0.3)

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            z0=f(z)
            if abs(z)>1000:
                break
            z=z0
            r=i*8
            g=i*64
            b=i*32
            image.putpixel((x,y),(r,g,b))
image
```
La funcion que se uso para obtner este fractal fue $x^3+x+0.2+0.3i$

![Mi sexto Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Julia%202.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
xa=-2
xb=2
ya=-2
yb=2
maxit=30
def f(z):
    return z**5+2*z**3+5*z**2-complex(0.2,0.3)

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            z0=f(z)
            if abs(z)>1000:
                break
            z=z0
            r=i*50
            g=i*100
            b=i*150
            image.putpixel((x,y),(r,g,b))
```
En este fractal se utilizo la funcion $x^5+2x^3+5x^2-0.2-0.3i$

![Mi septimo Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Julia%203.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
imgx=800
imgy=800
image=Image.new("RGB",(imgx,imgy))
image.putpixel((100,100),(255,255,255))
xa=-2
xb=2
ya=-2
yb=2
maxit=30
def f(z):
    return 5*z**4+complex(0.1,0.2)

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            z0=f(z)
            if abs(z)>1000:
                break
            z=z0
            r=i*24
            g=i*12
            b=i*6
            image.putpixel((x,y),(r,g,b))
 image
```
este fractal de Juñia se obtuvo con el polinomio $5x^4+0.1+0.2i$

![Mi septimo Fractal](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20Julia%204.PNG)
```
import matplotlib.pyplot as plt
from PIL import Image
imgx=800
imgy=800
image=Image.new("RGB",(imgx,imgy))
image.putpixel((100,100),(255,255,255))
xa=-2
xb=2
ya=-2
yb=2
maxit=30
def f(z):
    return z**2-z+complex(0.1,0.2)

for y in range (imgy):
    zy=y*(yb-ya)/(imgy-1)+ya
    for x in range (imgx):
        zx=x*(xb-xa)/(imgx-1)+xa
        z=complex(zx,zy)
        for i in range (maxit):
            z0=f(z)
            if abs(z)>1000:
                break
            z=z0
            r=i*12
            g=i*6
            b=i*24
            image.putpixel((x,y),(r,g,b))
image
```
El polinomio utilizado fur $x^2-x+0.1+0.2i$
### Sistema Iterados de funciones:
Para este casi miraremos 2 tipos:
* Fractales generados por un algortimo deterministas
* Fractales generados por un algoritmo aleatorio

Los siguientes fractales fueron creados con algoritomos deterministas, empezando por el triangulo de sierpinski y sus diferentes iteraciones.

![Sierpinski 1](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20sierpinski%201.PNG)

![Sierpinski 2](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20sierpinski%202.PNG)


![Sierpinski 3](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20sierpinski%203.PNG)


![Sierpinski 4](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20sierpinski%204.PNG)

Debo aclarar que el codigo que se se va a mostrar a continuacion y el utilizado para generar el triangulo de sierpinski y sus iteraciones fue obetnido de: 
* "*Pintando el caos con Python"* Isabel Ruiz Buriticá 2018 Medellin Colombia pag 10 (recuperado de:https://2018.pycon.co/talks/painting-chaos-with-python/painting-chaos-with-python.pdf)

```
from tkinter import *
import math
def sierpinski(canvas,x,y,size,level):
    x=float(x)
    y=float(y)
    if (level==0):
        canvas.create_polygon(x,y,x+size,y,x+size/2,y-size*math.sqrt(3)/2,fill="green")
    else: 
        sierpinski(canvas,x,y,size/2,level-1)
        sierpinski(canvas,x+size/2,y,size/2,level-1)
        sierpinski(canvas,x+size/4,y-size*math.sqrt(3)/4,size/2,level-1)
root=Tk()
myCanvas=Canvas(root, width=600,height=600)
myCanvas.pack()
sierpinski(myCanvas,50,500,500,3)
root.mainloop()
```
Este fractal de algortimo es el copo de nieve de Kock y sus iteraciones

![Koch 1](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20koch%201.PNG)

![Koch 2](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20koch%202.PNG)

![Koch 3](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20koch%203.PNG)

![Koch 4](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20koch%204.PNG)

![Koch 5](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.determinista%20koch%205.PNG)

He de aclarar que el codigo que se muestra a continuacion y el utilizado para obtener los fractales anteriores fue obtenido de la siquiente pagina web :
* https://python-with-science.readthedocs.io/en/latest/koch_fractal/koch_fractal.html

```
from turtle import *

def koch(a, order):
    if order > 0:
        for t in [60, -120, 60, 0]:
            koch(a/3,order-1)
            left(t)
    else:
        forward(a)

color("sky blue", "white")
bgcolor("black")
size = 400
order = 6

# Ensure snowflake is centred
penup()
backward(size/1.732)
left(30)
pendown()

# Make it fast
tracer(100)
hideturtle()

begin_fill()

# Three Koch curves
for i in range(3):
    koch(size, order)
    right(120)

end_fill()

# Make the last parts appear
update()
reset()
```
EL siquiente es el helecho de Barnsley hecho con un algortimo aleatorio sacando del siguiente sito web:https://www.geeksforgeeks.org/barnsley-fern-in-python/

![Banrsley](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Barsnley%20.PNG)

![Banrsley 2](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Barsnley%202%20.PNG)

![Banrsley 3](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Barsnley%203%20.PNG)

![Banrsley 4](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Barsnley%204%20.PNG)

```
# importing necessary modules 
import matplotlib.pyplot as plt 
from random import randint 
  
# initializing the list 
x = [] 
y = [] 
  
# setting first element to 0 
x.append(0) 
y.append(0) 
  
current = 0
  
for i in range(1, 50000): 
  
    # generates a random integer between 1 and 100 
    z = randint(1, 100) 
  
    # the x and y coordinates of the equations 
    # are appended in the lists respectively. 
      
    # for the probability 0.01 
    if z == 1: 
        x.append(0) 
        y.append(0.16*(y[current])) 
      
    # for the probability 0.85     
    if z>= 2 and z<= 86: 
        x.append(0.85*(x[current]) + 0.04*(y[current])) 
        y.append(-0.04*(x[current]) + 0.85*(y[current])+1.6) 
      
    # for the probability 0.07     
    if z>= 87 and z<= 93: 
        x.append(0.2*(x[current]) - 0.26*(y[current])) 
        y.append(0.23*(x[current]) + 0.22*(y[current])+1.6) 
      
    # for the probability 0.07     
    if z>= 94 and z<= 100: 
        x.append(-0.15*(x[current]) + 0.28*(y[current])) 
        y.append(0.26*(x[current]) + 0.24*(y[current])+0.44) 
          
    current = current + 1
   
plt.scatter(x, y, s = 0.2, edgecolor ='green') 
plt.axis("equal")
plt.show()   

```
Este fractal con algoritmo aleatorio es otra vez el trinagulo de sierpinski pero esta vez con un algoritmo de creacion diferente:

![Sierpinski A1](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Sierpinski%201%20.PNG)

![Sierpinski A2](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Sierpinski%202%20.PNG)

![Sierpinski A3](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Sierpinski%203%20.PNG)

![Sierpinski A4](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Sierpinski%204%20.PNG)

![Sierpinski A5](https://raw.githubusercontent.com/mruizm4/Galeria-de-Fractales/master/Fractal%20A.aleatorio%20Sierpinski%205%20.PNG)
este codigo fue el utilizado para hacer las fu¿ifuras vustas anteriormente
```
import numpy as np
import matplotlib.pyplot as plt
fig=plt.figure()
ax=plt.gca()
Tri=np.array([[0,0],[1,0],[0,1],[0,0]])
plt.scatter(Tri.transpose()[0],Tri.transpose()[1])
plt.plot(Tri.transpose()[0],Tri.transpose()[1])
ax.set_xticks(np.arange(-0.2,1.4,0.2))
ax.set_yticks(np.arange(-0.2,1.4,0.2))
plt.grid()
ax.axis("equal")
def transafin(M,t,x):
    y=M@x+t
    return y
transafin([[0.5,0],[0,0.5]],[0,0],Tri[1])
fig=plt.figure()
ax=plt.gca()
Tri=np.array([[0,0]])
for i in range(8):
    tritrans=np.array([transafin([[0.5,0],[0,0.5]],[0,0],i) for i in Tri])
    tritrans2=np.array([transafin([[0.5,0],[0,0.5]],[0,0.5],i) for i in Tri])
    tritrans3=np.array([transafin([[0.5,0],[0,0.5]],[0.5,0],i) for i in Tri])
    Tri=np.concatenate((tritrans,tritrans2,tritrans3))
plt.scatter(Tri.transpose()[0],Tri.transpose()[1],color='black',s=0.2)
ax.set_xticks(np.arange(-0.2,1.4,0.2))
ax.set_yticks(np.arange(-0.2,1.4,0.2))
plt.grid()
ax.axis("equal")
```
si quiere modificar un fractak¿l, como el grado de su funcion o el color ingrese al link de abajo (puede que sea demorado en cargar)
[link interactivo](Codigointeractivo1.html)

Aveces cierta funciones matematicas pueden generar un fractal o asemejarse a uno con el que se va a ver abajo.
![Sierpinski A1]()
