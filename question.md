# Pregunta y predicciones

Completen este archivo **antes** de ejecutar el experimento.

## Pregunta

¿Cómo cambia la trayectoria calculada con Euler cuando reducimos el paso
temporal `dt`?

## Respuesta
Mientras dt>resolución_float vamos a obtener una curva más suave, sino entre cada paso tendremos una recta con pendiente igual a la derivada en el punto de partida
Me imagino que la curva aproximada estará por encima de la exacta y, a medida que reduzcamos dt, se pegará más a la exacta

## Modelo y supuestos

- El proyectil es una partícula.
- La gravedad es constante y vertical: $\vec a=(0,-g)$.
- No hay rozamiento con el aire.
- La superficie terrestre es plana.

## Predicciones

1. ¿Qué componentes de la velocidad deberían cambiar? ¿Cuáles no?
2. ¿Qué forma esperan para la trayectoria en el plano $(x,y)$?
3. Si `dt` se reduce a la mitad, ¿qué esperan que ocurra con el error?

## Respuestas
1. Sólo va a cambiar la velocidad vertical. Como la horizontal tiene fuerza (y aceleración) nula, no hay término de O(dt^2) despreciado, ya que es nulo.
2. Una parábola cóncava, la solución aproximada por encima de la exacta.
3. El error local se reduce a la mitad y el global, mientras mantengamos el intervalo constante, se mantiene igual porque se reduce el paso pero se duplica la cantidad de los mismos.

## Criterio de aceptación

Propongan una tolerancia para la diferencia máxima entre la solución numérica
y la exacta cuando `dt = 0.01 s`. Expliquen brevemente por qué les parece
razonable.

## Respuesta
Error local = g*dt/2
Error global = N*g*dt/2
Si quiero ver la evolución en N*dt=10 s, entonces Error global = 46, que es, ¿muy grande?
Propongo Error global < 1 entonces N<20.