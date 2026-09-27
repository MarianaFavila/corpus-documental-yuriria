# Selección y tratamiento de las transcripciones y anotaciones

## Punto de partida

La selección se apoya en los inventarios realizados el 27 de septiembre de 2026 de `AGN_Documentos` y `Manuscritos`, dentro de Proyecto YURIRIA. Se identificaron 45 unidades con signatura en el AGN; 36 tenían al menos un TXT. En la carpeta de Mercedes, volumen 13, se identificaron 19 piezas y una exportación TXT conjunta. La carpeta `Manuscritos` contenía 85 archivos TXT, de los cuales 80 tienen contenido y cinco son bitácoras; para este repositorio se eligieron cinco exportaciones de AGI, AHN y BNE.

El criterio de incorporación inicial es disponer de una transcripción principal localizable y de una procedencia archivística suficientemente clara para continuar su verificación. Los datos extraídos del inventario, incluidos fechas, fojas y asuntos, son descriptivos y pueden requerir cotejo con el documento. Las discrepancias entre una ficha, la imagen y el TXT se resolverán por unidad y quedarán anotadas en el inventario.

## Elección de versiones

1. **AGN.** Se selecciona un TXT de conjunto por cada uno de los 36 expedientes con transcripción, más la exportación conjunta del volumen 13 de Mercedes. La extensión efectivamente transcrita de cada expediente queda pendiente de cotejo. Los archivos por foja y las variantes siguen disponibles en las carpetas de origen.
2. **AGI.** Se elige la exportación de Transkribus de cada relación agustina de Yuririapúndaro, Guayangareo y Cuitzeo. Sus versiones HTR adicionales y modernizadas permanecen registradas como variantes en las carpetas originales.
3. **AHN.** Se selecciona la exportación titulada como visita de 1636. El inventario la describe como una carta episcopal; debe verificarse su signatura y caracterización en la fuente archivística.
4. **BNE.** Se elige la exportación de Transkribus del manuscrito 3047. La versión legible situada en la raíz de `Manuscritos` permanece pendiente de cotejo y de atribución del trabajo editorial.

La copia de cada texto se conserva como transcripción de trabajo. La selección de un archivo principal no equivale a una revisión paleográfica ni prueba que las versiones alternativas sean intercambiables. Las intervenciones futuras sobre grafías, abreviaturas, segmentación, marcas de foja o errores de reconocimiento se documentarán de modo que puedan distinguirse de la lectura inicial.

## Selección y correspondencia de las anotaciones

En `Corpus_anotado` se identificaron tres exportaciones y se incorporaron sus **18 pares** y tres leyendas: once pares del AGN con `.txt` y `.ann.json` (946 registros), tres del AGI con `.plain.html` y `.ann.json` (460), y cuatro de `Yuriria_generales` con `.plain.html` y anotaciones en JSON (14,628). En conjunto son **16,034 registros de anotación** y 39 archivos de origen. De esos 39, 38 se conservaron byte por byte; por el límite de carga de GitHub, el archivo de anotaciones de Ysassy se guardó como `1649_Demarcación_YSASSY.ann.json.gz`. La compresión no altera el contenido: al descomprimirlo se recupera el JSON original de 1,337,918 bytes, con SHA-256 `9ccc3a081c1740f6893e5c2a5ce165e265f085a9bc669aab247035ae8c9b770e`. Los cuatro JSON de `Yuriria_generales` contienen anotaciones y se conservan junto con los HTML de su exportación actual.

Cada anotación debe leerse junto al texto de su propia exportación. Entre los catorce pares del AGN y el AGI, en trece el texto acompañante no coincide byte por byte con la transcripción principal de la misma fuente; en uno sí. En General de Parte, volumen 63, expediente 262, el texto anotado desarrolla abreviaturas que aparecen abreviadas en el TXT principal. En las relaciones del AGI también hay diferencias de grafía y segmentación. Los cuatro pares de `Yuriria_generales` corresponden a una carta vinculada con la Biblioteca del Palacio Real, dos relaciones vinculadas con la Newberry Library y una descripción asociada con la BNE ms. 3047; las tres primeras no están entre los 42 TXT principales, y la última requiere cotejo textual con el TXT principal de la BNE. La identificación de un mismo documento por título o signatura no hace equivalentes las posiciones de dos versiones. `anotaciones/inventario_anotaciones.csv` registra estas relaciones y las rutas disponibles.

Se comprobaron técnicamente los 16,034 fragmentos anotados contra sus textos acompañantes: los anclajes remiten al fragmento indicado. Esto comprueba la integridad de los pares descargados, pero no determina si las clases son históricamente adecuadas, si se anotó todo el documento o quién efectuó y revisó el trabajo. Las tres exportaciones tienen leyendas propias y los JSON presentan estructuras distintas; [`anotaciones/ONTOLOGIA_Y_FORMATOS.md`](anotaciones/ONTOLOGIA_Y_FORMATOS.md) explica cómo interpretarlas. Las categorías no se unificaron automáticamente.

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

`anotaciones/inventario_anotaciones.csv` registra una fila por par de texto y anotaciones, especifica su leyenda y número de registros, e indica la relación identificada con una transcripción principal cuando existe. El campo `archivo_anotaciones` señala directamente el archivo disponible; la ruta que termina en `.ann.json.gz` se debe descomprimir antes de tratar su contenido como JSON. Los 42 TXT principales y los once TXT acompañantes del AGN son archivos distintos; las siete exportaciones HTML se mantienen como textos acompañantes de los otros siete archivos de anotaciones. La suma de archivos de texto del repositorio es, por tanto, 53 TXT y siete HTML, sin equiparar esas copias a nuevas fuentes históricas.

## Revisión posterior

Antes de una difusión pública deben comprobarse la signatura y las fojas de cada unidad, el contenido y alcance de la transcripción, la autoría del trabajo editorial y las condiciones de consulta y reproducción de la institución correspondiente. Las correcciones se registrarán en el historial del repositorio y se reflejarán en `inventario.csv`. Hasta entonces, las lagunas del registro se dejan visibles.
