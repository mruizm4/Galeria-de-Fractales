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
La funcion matematica para este fractal fue \insertequation[]{x^3-1} y sus raiz real es 1, 0 y las imaginarias son $-1/2-\frac{\sqrt{3}}{2}i$ y $-\frac{1}{2}+\frac{\sqrt{3}}{2}i$

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
* Raiz real:-1.9041608591349,0
* Raiz Imaginaria: 
    * 0.9520804295675-1.3112480440771i 
    * 0.9520804295675+1.3112480440771i      

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
    * -1.3802775690976+0i
    * 0.8191725133962+0i
* Raiz Imaginaria:
    * -0.2194474721493-0.9144736629677i
    * -0.2194474721493+0.9144736629677i
   
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
    * -2.658967081917-0i
* Raiz Imaginaria:
    * 0.3294835409585-0.8022545575574i
    * 0.3294835409585+0.8022545575574i

### Conjutos de Julia
Para los conjuntos de Julia daremos a conocer los siguientes aspectos.
* Funcio con la obtenimos el fractal
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
