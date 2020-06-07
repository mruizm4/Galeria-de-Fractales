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
            r=i*20
            g=i*20
            b=i*20
            image.putpixel((x,y),(r,g,b))
image

```
La funcion matematica para este fractal fue $ x^3-1 $ y sus raiz real es 1, 0 y las imaginarias son $-1/2-\frac{\sqrt{3}}{2}i$ y $-\frac{1}{2}+\frac{\sqrt{3}}{2}i$

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
            r=i*20
            g=i*20
            b=i*20
            image.putpixel((x,y),(r,g,b))
image

```
En este caso el polinomio usado fue $x^3-x+5$:
* Raiz real:-1.9041608591349,0
* Raiz Imaginaria:0.9520804295675-1.3112480440771i 0.9520804295675+1.3112480440771i
