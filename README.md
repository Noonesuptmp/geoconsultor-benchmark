# GeoConsultor AI-MineSafe: benchmark de verificación técnica (15 preguntas)

Este repositorio contiene el benchmark manual de 15 preguntas técnico-cuantificables usado para evaluar **GeoConsultor AI-MineSafe**, un sistema que combina recuperación híbrida (RAG) y modelos de lenguaje ajustados con QLoRA para responder consultas sobre la normativa geotécnica de depósitos de relaves en Chile.

El benchmark acompaña al artículo:

> M. Díaz-Véliz, G. Hermosilla, G. Olmos, G. Villavicencio y G. Cocca-Guardia, "GeoConsultor AI-MineSafe: RAG and Fine-Tuning of Local LLMs for Geotechnical Regulations in Chilean Mining", *XVI Latin-American Congress on Electricity Generation and Transmission (CLAGTEE 2026)*, Santiago, Chile, 2026.

## Contenido

`benchmark_15_preguntas.csv` (UTF-8, separado por comas) tiene una fila por pregunta y estas columnas:

| Columna | Descripción |
|---|---|
| `id` | Número de la pregunta (1 a 15) |
| `documento` | Nombre abreviado del documento de origen |
| `documento_completo` | Título completo del documento de origen |
| `pregunta` | Pregunta planteada al sistema |
| `ground_truth` | Respuesta de referencia, verificada manualmente contra el documento |
| `pagina` | Página del documento donde se encuentra la respuesta |
| `seccion` | Sección, tabla o ecuación de referencia dentro del documento |
| `incluida_en_em` | Indica si la pregunta entra en el cálculo de Exact Match (EM) |
| `nota` | Observaciones sobre el cálculo de EM, cuando corresponde |

## Documentos de origen

| Abreviatura | Documento | Preguntas |
|---|---|---|
| GISTM | *Global Industry Standard on Tailings Management*, ICMM, UNEP y PRI, agosto de 2020. https://www.icmm.com/our-principles/gistm | 1 a 5 |
| Guía EF | *Guía Metodológica para la Evaluación de la Estabilidad Física de Depósitos de Relaves*, SERNAGEOMIN. | 6 a 10 |
| Guía Cierre | *Guía Metodológica de Evaluación de Riesgos para el Cierre de Faenas Mineras*, SERNAGEOMIN, versión 01, marzo de 2014. https://www.sernageomin.cl/wp-content/uploads/2017/11/14.03.24-GuiadeEvaluaciondeRiesgosparaelCierreFaenasMineras.pdf | 11 a 15 |

## Notas sobre el Exact Match

La variante de Exact Match usada en el artículo cuenta un acierto cuando la respuesta del modelo reproduce todos los valores numéricos del ground truth. Por eso:

- **La pregunta 15 queda excluida**, porque su respuesta de referencia es una expresión simbólica sin valores numéricos y la métrica queda indefinida. El EM se calcula sobre 14 preguntas.
- **Las preguntas 13 y 14 se incluyen**, pero sus valores numéricos no son magnitudes técnicas: en la 13 son años de publicación y en la 14 es el subíndice del nombre de la variable IMC2.

## Licencia

El contenido de este repositorio se publica bajo la licencia [Creative Commons Atribución 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.es). Las preguntas y respuestas de referencia citan documentos normativos de terceros, que conservan sus propias condiciones de uso.

## Financiamiento

Proyecto FONDECYT Regular N.º 1240573, "AI-MineSafe: Safety in Mining Waste Management through Artificial Intelligence" (ANID, Chile).
