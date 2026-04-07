# 📘 Unidad II – Graficación 2D

---

## 📑 Índice

- [Introducción](#introducción)
- [2.1 Transformación Bidimensional](#21-transformación-bidimensional)
  - [2.1.1 Traslación](#211-traslación)
  - [2.1.2 Escalamiento](#212-escalamiento)
  - [2.1.3 Rotación](#213-rotación)
  - [2.1.4 Sesgado](#214-sesgado)
- [2.2 Representación Matricial de las Transformaciones](#22-representación-matricial-de-las-transformaciones)
- [Ejercicio: Control con teclas de dirección](#ejercicio-control-con-teclas-de-dirección)
- [2.3 Trazo de Líneas Curvas](#23-trazo-de-líneas-curvas)
  - [2.3.1 Curvas Bézier](#231-curvas-bézier)
  - [2.3.2 Curvas B-Spline](#232-curvas-b-spline)
- [Ejercicio: Dibujo y animación con curvas](#ejercicio-dibujo-y-animación-con-curvas)
- [2.4 Fractales](#24-fractales)
- [2.5 Uso y Creación de Fuentes de Texto](#25-uso-y-creación-de-fuentes-de-texto)
- [Referencias Bibliográficas](#referencias-bibliográficas)

---

## Introducción

La graficación 2D es una rama de la computación gráfica que permite representar objetos en un plano cartesiano mediante coordenadas (x, y). 

Se utiliza en videojuegos, interfaces gráficas, diseño digital, animaciones y simulaciones. Las transformaciones bidimensionales permiten modificar objetos sin alterar su estructura básica, facilitando la manipulación geométrica dentro de aplicaciones gráficas.

---

## 2.1 Transformación Bidimensional

Las transformaciones 2D permiten cambiar posición, tamaño, orientación o forma de un objeto en el plano.

---

### 2.1.1 Traslación

La traslación desplaza un objeto sin modificar su tamaño ni forma.

**Fórmulas:**
x' = x + tx
y' = y + ty

Donde:

- tx = desplazamiento en X  
- ty = desplazamiento en Y  

---

## 2.1.2 Escalamiento

El escalamiento modifica el tamaño del objeto.
x' = x · Sx
y' = y · Sy

Si S > 1 → aumenta tamaño.  
Si 0 < S < 1 → reduce tamaño.

---

## 2.1.3 Rotación

Permite girar un objeto respecto al origen.
x' = x cosθ − y sinθ
y' = x sinθ + y cosθ

El ángulo θ puede expresarse en grados o radianes.

---

## 2.1.4 Sesgado

El sesgado inclina la figura en el plano.

**Sesgado en X**
x' = x + Shx · y
y' = y

**Sesgado en Y**
x' = x
y' = y + Shy · x

---

# 2.2 Representación Matricial de las Transformaciones

Las transformaciones pueden representarse mediante matrices usando coordenadas homogéneas.

Un punto en coordenadas homogéneas se representa como:
| x |
| y |
| 1 |

### Matriz de Traslación
| 1 0 tx |
| 0 1 ty |
| 0 0 1 |

### Matriz de Escalamiento
| Sx 0 0 |
| 0 Sy 0 |
| 0 0 1 |
### Matriz de Rotación
| cosθ -sinθ 0 |
| sinθ cosθ 0 |
| 0 0 1 |

2.3 Trazo de Líneas Curvas

Las curvas permiten representar trayectorias suaves y continuas en el plano.

2.3.1 Curvas Bézier
B(t) = (1−t)²P0 + 2(1−t)tP1 + t²P2
Donde 0 ≤ t ≤ 1.

Se utilizan ampliamente en diseño gráfico, animación y tipografía digital.
2.3.2 Curvas B-Spline

Las curvas B-Spline permiten mayor suavidad y control local sobre la forma.

Ventajas:

No afectan toda la curva al mover un punto.
Ofrecen mayor estabilidad matemática.
Son utilizadas en modelado 2D y 3D.
Ejercicio: Dibujo y animación con curvas

Procedimiento general:

Definir los puntos de control.
Variar el parámetro t de 0 a 1.
Calcular los puntos intermedios.
Dibujar punto por punto.
Actualizar la pantalla para generar animación fluida.
2.4 Fractales

Un fractal es una figura geométrica que presenta autosimilitud, es decir, mantiene su estructura al observarse a diferentes escalas.

Ejemplos:

Conjunto de Mandelbrot
Triángulo de Sierpinski
Curva de Koch

Se generan mediante algoritmos recursivos y son utilizados en simulaciones naturales y gráficos por computadora.

2.5 Uso y Creación de Fuentes de Texto

Las fuentes permiten representar texto dentro de gráficos 2D.

Tipos principales:

Bitmap
TrueType (TTF)
OpenType (OTF)

Ejemplo en Pygame:
fuente = pygame.font.Font(None, 36)
texto = fuente.render("Graficación 2D", True, (0,0,0))
pantalla.blit(texto, (100,100))
Las fuentes pueden transformarse aplicando rotación, escalamiento o efectos gráficos.

Referencias Bibliográficas

Foley, J. D., van Dam, A., Feiner, S. K., & Hughes, J. F. (1996). Computer graphics: Principles and practice. Addison-Wesley.

Hearn, D., & Baker, M. P. (2011). Computer graphics with OpenGL. Pearson.

Rogers, D. F. (2001). An introduction to NURBS with historical perspective. Morgan Kaufmann.

Shirley, P. (2015). Fundamentals of computer graphics. A K Peters.
Son curvas paramétricas definidas por puntos de control.
