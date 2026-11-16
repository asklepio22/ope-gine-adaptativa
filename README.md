# OPE Gine Adaptativa — versión 1.0

Aplicación web progresiva (PWA) para uso personal, instalable en Android y disponible sin conexión una vez cargada e instalada desde un sitio HTTPS.

## Datos incorporados

- **500 preguntas** transcritas automáticamente de `FEM OBSTETRICIA Y GINECOLOGIA_cas.pdf` (incluidos 17 casos clínicos con contexto compartido).
- **Plantilla de 500 entradas** de `Plantilla_consensuada_OPE_Ginecologia_500(1).pdf`, fechada el 15/11/2026.
- **492 claves provisionales** y **8 sin respuesta defendible**: 60, 109, 231, 278, 279, 285, 317 y 460.
- Bibliografía oficial consultada en `IV ANEXO_BIBLIOGRAFIA_FEM OBSTETRICIA Y GINECOLOGIA.pdf` como referencia para próximas validaciones; **no se han atribuido explicaciones específicas a libros que no se han aportado**.

**Importante:** las claves son consensuadas y no oficiales; no constituyen validación bibliográfica individual.

## Funciones

- Test adaptativo de 10 preguntas: prioriza las preguntas vencidas, los fallos y las nuevas.
- Repaso de errores.
- Simulacro aleatorio de 50 preguntas, con corrección al final (sin mostrar soluciones durante el test).
- Modo de preguntas discutidas (no puntuables).
- Estadísticas de progreso y programación de repaso por intervalos crecientes (1, 3, 7, 14, 30 días; error: repaso inmediato).
- Datos personales en `localStorage`, sin cuentas ni servidor de usuario.
- Exportación/importación JSON y borrado de progreso.
- Caché offline mediante service worker.

## Cómo instalar en Android

1. Publicar **todo el contenido** de esta carpeta en un alojamiento estático **HTTPS** (p. ej. GitHub Pages o Netlify). No basta con abrir `index.html` desde un ZIP.
2. Abrir la URL en Chrome para Android.
3. En el menú de Chrome elegir **Instalar aplicación** o **Añadir a pantalla de inicio**.
4. Abrir una vez con conexión para almacenar el banco de preguntas; luego funciona offline.

Para probar en ordenador: ejecutar `python -m http.server 8000` en esta carpeta y abrir `http://localhost:8000`. La instalación PWA y el caché offline en Android requieren HTTPS.

## Límites de esta versión

- El algoritmo es adaptativo **por historial de aciertos y calendario de repaso**, no por dificultad clínica validada ni por una estimación psicométrica IRT.
- No hay explicaciones médicas específicas por pregunta: generarlas sin verificar las fuentes sería engañoso.
- No hay clasificación temática automática, ya que no está definida en los documentos aportados.
- El progreso es local al navegador/dispositivo y puede perderse al borrar los datos del sitio. Exporta copias periódicas.
- La extracción de preguntas se ha comprobado por cantidad y estructura (500 preguntas, 4 opciones por pregunta), pero **no equivale a revisión editorial manual de cada enunciado**.

## v1.1
Memorización sin explicaciones; errores reinsertados hasta dos veces por sesión adaptativa. Repasos a 1 minuto, 10 minutos, 1, 3, 7, 14 y 30 días. Algoritmo escalonado, no FSRS calibrado.
