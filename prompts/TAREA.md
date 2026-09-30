# Tarea: Mi prompt avanzado

## Tarea elegida
 generar casos de prueba para un registro de usuarios

## Version 1: prompt basico
```text
 genera casos de prueba para un registro de usuarios
```

## Version 2
```text
    Actúa como un Ingeniero de QA Senior. Genera una lista completa y bien estructurada de casos de prueba para el flujo de "Registro de Usuarios" de un sistema web.

    Organiza los casos de prueba por categorías (Casos Positivos, Casos Negativos/Validaciones, Casos de Límite y Casos de Seguridad).

    Presenta el resultado en una tabla estructurada con las siguientes columnas:
    - ID del Caso
    - Categoría
    - Descripción / Objetivo
    - Pasos
    - Resultado Esperado

Responde únicamente "LEÍDO" si entendiste la instrucción.
```
Técnicas agregadas, justificación y mejoras (Versión 2)

Técnica 1: Role Prompting : 
 Al ordenarle a la IA actuar como un Ingenioro de QA Senior, obligamos al modelo a activar conocimiento técnico especializado en testing de software.

¿Qué mejoró?: La IA deja de dar respuestas superficiales (como "probar que el botón funcione") y empieza a incluir vocabulario técnico y coberturas reales (validaciones de formato, casos de seguridad, límites).

Técnica 2: Prompt Estructurado : El prompt original era una sola línea continua. Al dividir la orden en contexto, categorías solicitadas y especificación del formato final (tabla con columnas explícitas), eliminamos la ambigüedad.

¿Qué mejoró?: La respuesta no sale como un bloque de texto desordenado o una lista informal; entrega una matriz de pruebas lista para copiar a Jira, TestRail o Excel.

## Version 3: prompt final
```text
Actúa como un Ingeniero de QA Senior. Genera una lista completa y bien estructurada de casos de prueba para el flujo de "Registro de Usuarios" de una aplicación web/móvil (campos: Nombre, Correo, Contraseña, Confirmación de Contraseña).

Estructura el alcance de las pruebas en 4 categorías explícitas:
1. Casos Positivos
2. Casos Negativos / Validaciones
3. Casos de Límite
4. Casos de Seguridad

Sigue el estilo, nivel de detalle y formato exacto de los siguientes ejemplos:

---
EJEMPLOS DE REFERENCIA:

ID: CP-POS-01
Categoría: Caso Positivo
Descripción: Registro exitoso con todos los campos válidos.
Pasos: 1. Ingresar nombre válido. 2. Ingresar correo no registrado. 3. Ingresar contraseña segura. 4. Confirmar contraseña. 5. Clic en "Registrar".
Resultado Esperado: Usuario creado en base de datos y mensaje de confirmación/redirección al dashboard.

ID: CP-NEG-01
Categoría: Caso Negativo
Descripción: Intento de registro con correo ya existente.
Pasos: 1. Ingresar correo previamente registrado. 2. Completar demás campos válidos. 3. Clic en "Registrar".
Resultado Esperado: El sistema bloquea el envío y muestra mensaje de error: "El correo electrónico ya se encuentra registrado".
---

Entrega los casos de prueba en una tabla con las columnas: ID, Categoría, Descripción, Pasos, Resultado Esperado.

```
Técnicas agregadas, justificación y mejoras (Versión 3)
Tecnica 3 :Few-Shot Prompting : Le da al modelo patrones claros y concisos de cómo redactar los pasos y resultados esperados.

¿Qué mejoró?: Garantiza la consistencia en el nivel de detalle de cada fila (evita que algunos casos queden redactados de forma abstracta y otros muy detallados).

## Tecnicas usadas en el .prompt final
1) Role Prompting
2) Prompt Estructurado
3) Few-Shot Prompting

## Evaluacion del resultado


| Criterio | Prompt Básico | Versión 2 (Intermedia) | Versión Final (3 Técnicas) |
| :--- | :--- | :--- | :--- |
| **Técnicas Aplicadas** | Ninguna *(Instrucción directa)* | • Role Prompting<br>• Prompt Estructurado | • Role Prompting<br>• Prompt Estructurado<br>• Few-Shot Prompting |
| **Formato de Salida** | Lista simple o viñetas genéricas desordenadas. | Tabla organizada con columnas estándar. | Tabla estandarizada con formato e instructivos idénticos a los ejemplos. |
| **Nivel de Cobertura** | 3 a 5 casos genéricos (*"Happy path"* o comprobaciones obvias). | Cobertura en 4 categorías explícitas *(positivos, negativos, límites, seguridad)*. | Cobertura profunda en las 4 categorías con validaciones concretas. |
| **Calidad del Resultado Esperado** | Vago *(ej. "Muestra error")*. | Técnico *(ej. "El sistema no permite el registro")*. | Preciso e inline *(ej. "Mensaje de error: El correo electrónico ya se encuentra registrado")*. |
| **Usabilidad Profesional** | **10%** *(Requiere reescribir casi todo para usarlo en producción)*. | **70%** *(Estructura útil, requiere pulir detalles específicos)*. | **95%** *(Listo para copiar y pegar en Jira, TestRail o Excel)*. |

---

## Por que elegi estas tecnicas

Dan conexto sobre lo deseado a la Ia y mantien una estructura ordena y facil de seguir y ejecutar.
