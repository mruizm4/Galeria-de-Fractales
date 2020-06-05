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
La funcio matematica para este fractal fue $x^3-1$

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mruizm4/Galeria-de-Fractales/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
3
