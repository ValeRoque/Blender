📌 UNIDAD 2 – GRAFICACIÓN 2D
Instituto Tecnológico de Cuautla

Asignatura: Graficación
Unidad: Unidad 2 – Graficación 2D
Alumno: Tu Nombre
Profesor: Nombre del Profesor
Fecha: 14 de abril de 2026

📑 Índice
Introducción
2.1 Transformación Bidimensional
2.1.1 Traslación
2.1.2 Escalamiento
2.1.3 Rotación
2.1.4 Sesgado
2.2 Representación Matricial
Ejercicio: Control con Teclas
2.3 Trazo de Líneas Curvas
2.3.1 Curvas Bézier
2.3.2 Curvas B-Spline
Ejercicio: Animación con Curvas
2.4 Fractales
2.5 Uso y Creación de Fuentes
Referencias Bibliográficas
Introducción

La graficación 2D es una rama de la computación gráfica que permite representar objetos en un plano cartesiano mediante coordenadas (x, y). Se utiliza en videojuegos, interfaces gráficas, diseño digital, animaciones y simulaciones.

Las transformaciones bidimensionales permiten modificar objetos sin alterar su estructura básica, facilitando la manipulación geométrica dentro de aplicaciones gráficas.

2.1 Transformación Bidimensional

Las transformaciones 2D permiten cambiar posición, tamaño, orientación o forma de un objeto en el plano.

2.1.1 Traslación

La traslación desplaza un objeto sin modificar su tamaño ni forma.

Fórmula:

x' = x + tx
y' = y + ty

Donde:

tx = desplazamiento en X
ty = desplazamiento en Y
2.1.2 Escalamiento

Modifica el tamaño del objeto.

x' = x · Sx
y' = y · Sy

Si S > 1 aumenta tamaño.
Si 0 < S < 1 reduce tamaño.

2.1.3 Rotación

Permite girar un objeto respecto al origen.

x' = x cosθ − y sinθ
y' = x sinθ + y cosθ

El ángulo θ puede expresarse en grados o radianes.

2.1.4 Sesgado

Inclina la figura.

Sesgado en X:

x' = x + Shx · y
y' = y

Sesgado en Y:

x' = x
y' = y + Shy · x
2.2 Representación Matricial de las Transformaciones

Las transformaciones pueden representarse mediante matrices usando coordenadas homogéneas.

Matriz de Traslación

| 1  0  tx |
| 0  1  ty |
| 0  0   1 |

Matriz de Escalamiento

| Sx  0   0 |
| 0   Sy  0 |
| 0   0   1 |

Matriz de Rotación

| cosθ  -sinθ  0 |
| sinθ   cosθ  0 |
| 0       0    1 |

Las matrices permiten combinar transformaciones mediante multiplicación matricial.

Ejercicio: Control con Teclas

Ejemplo en Python usando Pygame:

import pygame
import sys

pygame.init()
pantalla = pygame.display.set_mode((600, 400))
rect_x, rect_y = 300, 200
velocidad = 5

while True:
    for evento in pygame.event.get():
        if evento.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    teclas = pygame.key.get_pressed()
    if teclas[pygame.K_LEFT]:
        rect_x -= velocidad
    if teclas[pygame.K_RIGHT]:
        rect_x += velocidad
    if teclas[pygame.K_UP]:
        rect_y -= velocidad
    if teclas[pygame.K_DOWN]:
        rect_y += velocidad

    pantalla.fill((255,255,255))
    pygame.draw.rect(pantalla, (0,0,255), (rect_x, rect_y, 50, 50))
    pygame.display.update()
2.3 Trazo de Líneas Curvas

Las curvas permiten representar trayectorias suaves y continuas.

2.3.1 Curvas Bézier

Son curvas paramétricas definidas por puntos de control.

B(t) = (1−t)²P0 + 2(1−t)tP1 + t²P2

Donde 0 ≤ t ≤ 1.

Se utilizan en diseño gráfico, tipografía y animación.

2.3.2 Curvas B-Spline

Permiten mayor suavidad y control local sobre la curva.

Ventajas:

No afectan toda la curva al mover un punto.
Mayor estabilidad matemática.
Se usan en modelado y animación 2D y 3D.
Ejercicio: Animación con Curvas

Procedimiento:

Definir puntos de control.
Variar el parámetro t de 0 a 1.
Dibujar punto por punto.
Actualizar pantalla.
Generar animación fluida.
2.4 Fractales

Un fractal es una figura geométrica que presenta autosimilitud a diferentes escalas.

Ejemplos:

Conjunto de Mandelbrot
Triángulo de Sierpinski
Curva de Koch

Se generan mediante algoritmos recursivos.

2.5 Uso y Creación de Fuentes de Texto

Las fuentes permiten representar texto dentro de gráficos 2D.

Tipos:

Bitmap
TrueType (TTF)
OpenType (OTF)

Ejemplo en Pygame:

fuente = pygame.font.Font(None, 36)
texto = fuente.render("Graficación 2D", True, (0,0,0))
pantalla.blit(texto, (100,100))
Referencias Bibliográficas

Foley, J. D., van Dam, A., Feiner, S. K., & Hughes, J. F. (1996). Computer graphics: Principles and practice. Addison-Wesley.

Hearn, D., & Baker, M. P. (2011). Computer graphics with OpenGL. Pearson.

Rogers, D. F. (2001). An introduction to NURBS with historical perspective. Morgan Kaufmann.

Shirley, P. (2015). Fundamentals of computer graphics. A K Peters.
