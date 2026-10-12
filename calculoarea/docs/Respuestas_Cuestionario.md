# CUESTIONARIO TÉCNICO DE CONTROL - RESPUESTAS

## Pregunta 1: El Prototipo de la Función

**Pregunta:** Si borráramos la línea 15 (`double calcularAreaCirculo(double radio);`), ¿por qué creés que el compilador no sabría qué hacer cuando intente leer la función main?

**Respuesta:**
El compilador de C++ lee el código de arriba hacia abajo, secuencialmente. Cuando encuentra la llamada a `calcularAreaCirculo()` dentro de `main()`, necesita saber previamente:
- Que la función existe
- Qué tipo de dato devuelve (en este caso `double`)
- Qué parámetros recibe (en este caso un `double`)

Sin el prototipo, el compilador no tiene esta información y genera un error de compilación porque no puede verificar si la llamada a la función es correcta. El prototipo actúa como una "declaración anticipada" que le avisa al compilador sobre la existencia y características de la función antes de que se use.

---

## Pregunta 2: El Filtro de Consistencia

**Pregunta:** ¿Qué problema físico o geométrico ocurriría si intentáramos calcular el área de un círculo con un radio de 0 cm o de -5 cm? ¿Por qué es importante controlar esto?

**Respuesta:**
- **Radio = 0:** Un círculo con radio 0 no existe geométricamente, sería un punto sin dimensión. El área sería 0, lo cual no tiene sentido práctico.
- **Radio negativo (-5):** El radio es una medida de distancia y por definición no puede ser negativo. Un radio negativo es un error conceptual.

Si no controlamos esto:
1. Podríamos obtener resultados matemáticamente "válidos" pero físicamente imposibles (ej: área positiva con radio negativo al elevarlo al cuadrado)
2. El programa podría usarse incorrectamente en aplicaciones reales
3. Se pierde la confianza en los resultados del programa

El filtro de consistencia garantiza que solo se procesen datos válidos y técnicamente correctos.

---

## Pregunta 3: Proteger Constantes en RAM

**Pregunta:** ¿Por qué considerás que es más seguro para un sistema crítico (como el software de un avión o un sistema médico) declarar valores como "inmutables" (const) en lugar de usar variables comunes?

**Respuesta:**
En sistemas críticos, la seguridad es primordial. Usar `const` ofrece varias ventajas:

1. **Prevención de errores accidentales:** Si el valor de PI se modifica por error en cualquier parte del programa, el compilador lo detecta y detiene la compilación. En un sistema médico, un cambio accidental en un valor constante podría tener consecuencias fatales.

2. **Documentación del código:** Declarar un valor como `const` le indica a otros programadores que ese valor NO debe modificarse, mejorando la legibilidad y mantenibilidad.

3. **Optimización del compilador:** El compilador puede hacer optimizaciones adicionales sabiendo que el valor no cambiará.

4. **Protección de integridad:** En sistemas de aviónica o médicos, los valores constantes (como factores de conversión, límites de seguridad, etc.) deben permanecer inalterables durante toda la ejecución para garantizar la seguridad del sistema.

5. **Depuración más simple:** Si un valor `const` aparece en un error, sabemos que no fue modificado, reduciendo las posibles causas del problema.
