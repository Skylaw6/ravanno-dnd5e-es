# Guía de traducción — Foundry D&D5e

Esta guía reúne las decisiones de estilo y formato implementadas en la traducción del proyecto. Su objetivo es mantener la coherencia entre las distintas personas que puedan colaborar en las traducciones.

## Fuente de la traducción

- Usar la **traducción oficial del SRD en español** como base siempre que esté disponible.
- Adaptarla únicamente cuando sea necesario para el formato HTML o las funciones de Foundry.
- Mantener los nombres y la terminología tal como aparecen en la SRD.

## Formato HTML

- Eliminar las etiquetas `<div>` por defecto.
- Mantener los párrafos mediante `<p>...</p>`.
- Conservar cualquier código o sintaxis necesaria para los enriquecimientos de Foundry.

## Medidas

Cuando el texto original use medidas imperiales, conservar la medida original y añadir su equivalente métrico entre paréntesis.

Ejemplos:

```text
30 pies (9 metros)
300 pies (90 metros)
5 pies (1,5 metros)
10 pies (3 metros)
```

Usar valores métricos redondeados de forma natural, siguiendo el estilo habitual de D&D.

## Conceptos mecánicos del juego

### Cuando existe una Reference

Si el concepto tiene una referencia interna confirmada de Foundry, utilizarla.

```html
&amp;Reference[Truesight]
```

Ejemplos:

```html
&amp;Reference[Truesight]
&amp;Reference[Charmed apply=false]
&amp;Reference[Frightened apply=false]
```

Los identificadores internos no se traducen.

### Cuando no existe una Reference

Usar mayúscula inicial y negritas para destacar conceptos mecánicos.

```html
<strong>Ventaja</strong>
<strong>Desventaja</strong>
<strong>Tiradas de Ataque</strong>
<strong>Tirada de Salvación</strong>
<strong>Acción de Magia</strong>
```

## Tipos de criatura

Los tipos de criatura pueden utilizar `Reference` cuando el ID esté confirmado.

Ejemplo:

```html
&amp;Reference[aberration]
```

IDs confirmados:

```text
aberration
beast
celestial
construct
dragon
elemental
fey
fiend
giant
humanoid
monstrosity
ooze
plant
undead
```

## Daño

Cuando aparezca una cantidad de daño concreta, utilizar el enriquecimiento de Foundry:

```text
[[/damage 4d8 force]]
```

El tipo de daño dentro del comando se mantiene en inglés porque forma parte de la sintaxis interna.

Debido a cómo Foundry muestra actualmente el resultado, adaptar la redacción alrededor del enriquecimiento para que se lea correctamente.

Forma preferida:

```html
recibe [[/damage 4d8 force]] de daño
```

## Tiradas de Salvación

Es importante distinguir entre el concepto general y una tirada concreta.

### Como concepto general

```html
<strong>Tirada de Salvación</strong>
```

### Como tirada concreta

Usar el enriquecimiento de Foundry:

```text
[[/save str]]
```

Si incluye una CD:

```text
[[/save str 15]]
```

Estos enrichers se utilizan únicamente cuando una criatura debe realizar una tirada concreta.

## Regla general para enrichers

Usar enrichers cuando:

- La sintaxis y el ID estén confirmados.
- Aporten interactividad o información útil.
- No dificulten la lectura del texto.

Los tipos de criatura pueden usar referencias incluso en listas cuando el resultado visual sea legible.

## Importante

- Priorizar la traducción oficial del SRD.
- Adaptar el texto cuando sea necesario para que los elementos enriquecidos se lean correctamente dentro de Foundry.
