# Selección y tratamiento de las transcripciones

## Punto de partida

La selección se apoya en los inventarios realizados el 27 de septiembre de 2026 de `AGN_Documentos` y `Manuscritos`, dentro de Proyecto YURIRIA. Se identificaron 45 unidades con signatura en el AGN; 36 tenían al menos un TXT. En la carpeta de Mercedes, volumen 13, se identificaron 19 piezas y una exportación TXT conjunta. La carpeta `Manuscritos` contenía 85 archivos TXT, de los cuales 80 tienen contenido y cinco son bitácoras; para este repositorio se eligieron cinco exportaciones de AGI, AHN y BNE.

El criterio de incorporación inicial es disponer de una transcripción principal localizable y de una procedencia archivística suficientemente clara para continuar su verificación. Los datos extraídos del inventario, incluidos fechas, fojas y asuntos, son descriptivos y pueden requerir cotejo con el documento. Las discrepancias entre una ficha, la imagen y el TXT se resolverán por unidad y quedarán anotadas en el inventario.

## Elección de versiones

1. **AGN.** Se selecciona un TXT de conjunto por cada uno de los 36 expedientes con transcripción, más la exportación conjunta del volumen 13 de Mercedes. La extensión efectivamente transcrita de cada expediente queda pendiente de cotejo. Los archivos por foja y las variantes siguen disponibles en las carpetas de origen.
2. **AGI.** Se elige la exportación de Transkribus de cada relación agustina de Yuririapúndaro, Guayangareo y Cuitzeo. Sus versiones HTR adicionales y modernizadas permanecen registradas como variantes en las carpetas originales.
3. **AHN.** Se selecciona la exportación titulada como visita de 1636. El inventario la describe como una carta episcopal; debe verificarse su signatura y caracterización en la fuente archivística.
4. **BNE.** Se elige la exportación de Transkribus del manuscrito 3047. La versión legible situada en la raíz de `Manuscritos` permanece pendiente de cotejo y de atribución del trabajo editorial.

La copia de cada texto se conserva como transcripción de trabajo. La selección de un archivo principal no equivale a una revisión paleográfica ni prueba que las versiones alternativas sean intercambiables. Las intervenciones futuras sobre grafías, abreviaturas, segmentación, marcas de foja o errores de reconocimiento se documentarán de modo que puedan distinguirse de la lectura inicial.

## Inventario curado

`inventario.csv` tiene una fila por TXT principal y utiliza estos campos:

| Campo | Uso |
|---|---|
| `id` | Identificador estable de la unidad de trabajo. |
| `archivo_repo` | Ruta relativa del TXT dentro del repositorio. |
| `ruta_origen_relativa` | Ubicación relativa en las carpetas de origen; omite rutas de usuario e identificadores internos de Dropbox. |
| `institucion` | Archivo o biblioteca que conserva el testimonio. |
| `fondo_serie` | Ramo, fondo o colección cuando se conoce. |
| `signatura` | Volumen, expediente, manuscrito u otra referencia disponible, pendiente de cotejo cuando proceda. |
| `fecha_documento` | Fecha atribuida al documento; puede quedar vacía o con incertidumbre indicada. |
| `fojas` | Foliación del documento cuando consta en el inventario. |
| `titulo_asunto` | Título breve o descripción del contenido. |
| `metodo_version` | Exportación, HTR u otra condición observable del archivo elegido. |
| `estado_cotejo` | Estado comprobado de revisión; «no verificado en esta selección» evita inferir el trabajo previo sobre cada texto. |
| `estado_derechos` | Estado de la revisión de condiciones de reutilización y publicación. |
| `fuente_en_linea` | Enlace institucional estable, cuando se haya verificado. |
| `transcriptor` | Autoría del trabajo de transcripción cuando se haya comprobado. |
| `observaciones` | Dudas de identificación, fechas, versiones y decisiones de tratamiento. |

`indice_mercedes_vol13.csv` describe las 19 piezas contenidas en un solo TXT. Cada fila debe permitir identificar al menos la pieza y sus fojas, y conservar las fechas y observaciones que consten en el inventario. `pendientes_de_revision.csv` conserva la pista de los materiales que no se copiaron a `transcripciones/` y de las condiciones necesarias para reconsiderarlos.

## Revisión posterior

Antes de una difusión pública deben comprobarse la signatura y las fojas de cada unidad, el contenido y alcance de la transcripción, la autoría del trabajo editorial y las condiciones de consulta y reproducción de la institución correspondiente. Las correcciones se registrarán en el historial del repositorio y se reflejarán en `inventario.csv`. Hasta entonces, las lagunas del registro se dejan visibles.
