# Pensamiento crítico — Versión 4

App web para desarmar pensamientos automáticos con IA o modo demo.

## Cambios de esta versión

- Agrega **Mapa de pensamiento**.
- El mapa muestra el ciclo que se repite:
  1. Situación que activa.
  2. Pensamiento automático.
  3. Emoción dominante.
  4. Filtro o distorsión posible.
  5. Respuesta alternativa.
- El mapa se construye con el historial real del perfil.
- No usa categorías fijas para los patrones dinámicos.
- Mantiene modo demo y modo IA real.
- Modelo por defecto recomendado: `gpt-5-mini`.

## Cómo ejecutar

```bash
npm install
node server.js
```

Abrí:

```txt
http://localhost:3000
```

## Modo demo

Para usar modo demo, dejá el archivo `.env` así:

```env
OPENAI_API_KEY=
OPENAI_MODEL=gpt-5-mini
PORT=3000
```

## Modo IA real

Para usar IA real:

```env
OPENAI_API_KEY=sk-proj-tuclave
OPENAI_MODEL=gpt-5-mini
PORT=3000
```

## Cómo funciona el mapa

El mapa analiza los registros guardados en el navegador y detecta:

- palabras frecuentes en situaciones y contexto;
- palabras frecuentes en pensamientos;
- emoción que más se repite;
- posibles distorsiones repetidas;
- una frase alternativa para cortar el ciclo.

Ejemplo:

Si varios registros hablan de jefe, error y despido, el mapa puede construir un ciclo como:

```txt
Situación: jefe / error / trabajo
Pensamiento: despedir / culpa / error
Emoción: ansiedad
Filtro: catastrofización
Alternativa: puedo buscar evidencia antes de creer el peor escenario
```

## Importante

La app es una herramienta de apoyo para ordenar pensamientos. No reemplaza terapia, diagnóstico médico ni servicios de emergencia.


## Corrección v4.1

- Corregido el plural incorrecto `vezes` por `veces`.


## Corrección v4.2

- Se agregaron como patrones de pensamiento:
  - Catastrofización.
  - Lectura de mente.
  - Adivinación del futuro.
  - Pensamiento todo o nada.
  - Filtro negativo.
  - Descalificar lo positivo.
  - Culpa excesiva.
  - Razonamiento emocional.
- Se corrigió el color del desplegable de "Emoción principal" para que las opciones se lean bien al tocarlo.
- Se ajustaron textos para hablar de "patrones de pensamiento" en vez de "distorsiones" cuando aparece en la interfaz.


## Corrección v4.3

- Se eliminó la lógica que mostraba palabras sueltas repetidas como si fueran patrones.
- La sección pasó de "Patrones dinámicos" a "Patrones útiles".
- La app ahora exige al menos 3 registros para mostrar patrones.
- Ahora prioriza:
  - ciclos recurrentes: emoción + patrón de pensamiento + tema;
  - patrones de pensamiento repetidos;
  - pensamientos realmente parecidos;
  - frases significativas.
- Se agregaron filtros para evitar ruido como "venía", "estaba", "pasó", etc.


## Versión 5 — Respuestas más humanas

Cambios principales:

- La IA ya no está obligada a responder siempre con la misma estructura.
- Se agregó selector de necesidad:
  - que la app elija,
  - contención primero,
  - análisis claro,
  - acción concreta,
  - conversar antes de resolver.
- Se agregó selector de tono:
  - acompañamiento,
  - suave,
  - directo.
- La respuesta ahora prioriza:
  - conexión emocional inicial,
  - miedo de fondo,
  - dato vs película mental,
  - frases que la persona pueda creer,
  - acción concreta,
  - mensaje sugerido cuando corresponde,
  - uso más humano del historial.
- El modo demo también fue reescrito para sonar menos automático.

La intención de esta versión es que la app no se sienta como una plantilla, sino como una guía que acompaña y ayuda a resolver.


## Versión 6 — Más simple, menos estresante

Cambios principales:

- Se reemplazó el "Mapa de pensamiento" por un "Resumen simple".
- El resumen ya no muestra ciclos largos ni flechas; solo muestra una lectura breve y fácil.
- Se agregó una sección "Ayuda en Uruguay" con teléfonos de apoyo.
- Se agregó una conversación libre: "Charlar sobre cómo me siento".
- La persona puede conversar sin completar el formulario del ejercicio.
- Se agregaron más estados de ánimo, incluyendo felicidad, alegría, calma, entusiasmo, orgullo, gratitud y esperanza.
- La app ya no asume que todo es ansiedad: una emoción positiva también puede traer pensamientos exagerados o impulsivos.

Fuentes de líneas de ayuda incluidas:
- Ministerio de Salud Pública: salud mental, líneas de emergencia.
- ASSE: Línea de Prevención del Suicidio.
- Ministerio del Interior: Emergencia 9-1-1.


## Corrección v6.1

- Se corrigió la detección de crisis para que no active el mensaje urgente cuando la persona niega el riesgo.
- Ejemplos que ya no deberían activar crisis:
  - "No quiero hacerme daño".
  - "No quería atentar contra mi vida".
  - "No tengo ideas suicidas".
- La app sigue activando el mensaje de ayuda si hay una afirmación directa de riesgo.


## Corrección v6.2

- Se reorganizó el flujo principal.
- La sección "Desarme del pensamiento" ahora queda inmediatamente debajo del formulario.
- Al tocar "Analizar pensamiento", la página baja automáticamente hasta la respuesta.
- El botón muestra "Analizando…" mientras se procesa.
- La conversación libre y el resumen simple quedan después de la respuesta principal para no interrumpir el flujo.
