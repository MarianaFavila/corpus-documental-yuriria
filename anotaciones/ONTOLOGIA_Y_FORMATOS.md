# Clases, etiquetas y formatos de anotación

Los archivos `annotations-legend.json` identifican los códigos utilizados por cada exportación. Son leyendas de etiquetas de trabajo. Esta carpeta conserva **tres leyendas distintas**: una para los once pares del AGN, otra para los tres del AGI y una tercera para cuatro fuentes asociadas con la Biblioteca del Palacio Real, la BNE y la Newberry Library, cuya identificación archivística requiere cotejo. Su contenido no debe interpretarse como una ontología formal única ni como prueba de que se aplicaron todas las clases posibles en cada texto.

## Esquema del AGN

`AGN/annotations-legend.json`, denominado `Yuriria_especificos`, define **19 clases** (`e_1` a `e_19`). Algunas admiten campos o etiquetas más precisos (`f_…`). La tabla resume la lista de clases y los campos nombrados en esa leyenda; el JSON conserva también códigos internos para casos sin campo adicional (`f_WOF_…`).

| Código | Clase | Campos nombrados en la leyenda |
|---|---|---|
| `e_1` | Persona | Nombre, Mujer, Hombre, Título, Profesión, Santo, Deidad, Cuerpo |
| `e_2` | Fecha | Mes, Año |
| `e_3` | Institución | Civil, Eclesiástica |
| `e_4` | Localización | Tipo de asentamiento, Rasgo geográfico, Topónimo, Imaginario, Jurisdicción eclesiástica, Jurisdicción civil |
| `e_5` | Animal | Insecto, Mamífero, Reptil, Ave, Anfibio, Domesticado, Acuático |
| `e_6` | Actividad | Agricultura, Guerra, Economía, Minería, Doméstica, Ritual, Social, Civil, Política, Náutica |
| `e_7` | Planta | Sin campos adicionales nombrados |
| `e_8` | Comida | Sin campos adicionales nombrados |
| `e_9` | Recurso natural | Sin campos adicionales nombrados |
| `e_10` | Artefacto cultural | Bien doméstico, Mercancía, Ropa, Armamento, Herramienta, Ritual, Vehículo terrestre, Náutico |
| `e_11` | Arquitectura | Religiosa, Civil, Doméstica, Naval |
| `e_12` | Salud | Enfermedad, Remedio |
| `e_13` | Movilidad | Terrestre, Acuática |
| `e_14` | Clima | Sin campos adicionales nombrados |
| `e_15` | Etnia | Sin campos adicionales nombrados |
| `e_16` | Grupo social | Sin campos adicionales nombrados |
| `e_17` | Idioma | Sin campos adicionales nombrados |
| `e_18` | Medida | Precio, Peso, Población, Distancia, Tamaño, Capacidad, Cantidad |
| `e_19` | Embarcación | Nombre, Tipo, Función |

Los nombres de la tabla se presentan con espacios y sin caracteres de retorno para facilitar la lectura. Los códigos y rótulos originales permanecen sin modificar en el JSON. **La propia leyenda del AGN asigna `f_18` tanto a «Cuerpo» bajo `e_1` como a «Insecto» bajo `e_5`.** Por ello, un campo no puede interpretarse a partir de su código aislado; se debe examinar la clase del registro, la leyenda original y, cuando sea necesario, el fragmento anotado. Otras etiquetas, como «Civil» y «Ritual», también aparecen bajo clases distintas, pero con códigos diferentes.

Los archivos `AGN/*.ann.json` son listas JSON. Cada registro conserva el fragmento en `text`, una referencia de párrafo en `paragraph`, posiciones `start` y `end`, un código principal en `firstEntityCode` y los posibles subcampos en `fieldsFirstEntity`. Algunos registros añaden un segundo código y sus campos en `secondEntityCode` y `fieldsSecondEntity`. El `.txt` del mismo nombre base es el texto asociado a ese archivo; los identificadores internos de párrafo no aparecen señalados como elementos HTML en él. Para recuperar posiciones sobre el texto debe comprobarse la segmentación de la exportación. No se deben aplicar las posiciones directamente al TXT principal de `transcripciones/`.

## Esquema del AGI

`AGI/annotations-legend.json` tiene otra estructura: es un diccionario plano de códigos y nombres. Enumera **31 códigos de clase**. Los primeros 19 (`e_1` a `e_19`) están nombrados en español con categorías comparables a las de AGN; los restantes son los siguientes rótulos en inglés tal como aparecen en la exportación:

| Código | Rótulo | Código | Rótulo |
|---|---|---|---|
| `e_20` | Location | `e_26` | Ethnic_Group |
| `e_21` | Person | `e_27` | Plant |
| `e_22` | Cultural_Artefact | `e_28` | Measurement |
| `e_23` | Architecture | `e_29` | Animal |
| `e_24` | Institution | `e_30` | Activity |
| `e_25` | Language | `e_31` | Date |

El diccionario incluye asimismo códigos de campo (`f_…`) que dan nombres a etiquetas como «Topónimo», «Acuática» o «Náutica». No agrupa explícitamente esos campos bajo clases. Tampoco coincide sin reservas con la leyenda del AGN: por ejemplo, `f_18` figura como «Insecto» en el diccionario del AGI, mientras que la leyenda del AGN lo utiliza con dos rótulos. El inventario conserva cada leyenda para consultar su exportación en contexto.

Los archivos `AGI/*.ann.json` son objetos JSON cuya clave `entities` contiene los registros. Cada entidad tiene `classId`, `part`, `offsets` y, cuando corresponde, `fields`. `part` remite a un identificador de párrafo del archivo `.plain.html` acompañante, por ejemplo `s1p2`, y `offsets` da el inicio y el texto del fragmento dentro de esa parte. El HTML conserva párrafos con el atributo `id` correspondiente. La posición es propia de ese HTML y no equivale por defecto a una posición en el TXT seleccionado en `transcripciones/AGI/`.

## Esquema de `Yuriria_generales/`

`Yuriria_generales/annotations-legend.json` define **37 clases**: las primeras 19 están nombradas en español y las 18 restantes en inglés. Las clases españolas abarcan, entre otras, Persona, Localización, Actividad, Movilidad, Medida y Embarcación. Esta leyenda tiene una estructura de objetos con campos, como la del AGN, pero forma parte de otra exportación. Sus clases adicionales son las siguientes:

| Código | Rótulo | Código | Rótulo |
|---|---|---|---|
| `e_20` | Person | `e_29` | Architecture |
| `e_21` | Location | `e_30` | Institution |
| `e_22` | Date | `e_31` | Natural_Resource |
| `e_23` | Activity | `e_32` | Health |
| `e_24` | Animal | `e_33` | Social_Group |
| `e_25` | Mobility | `e_34` | Climate |
| `e_26` | Food | `e_35` | Ethnic_Group |
| `e_27` | Cultural_Artefact | `e_36` | Plant |
| `e_28` | Measurement | `e_37` | Language |

**Los códigos ingleses difieren entre las dos leyendas:** en el AGI `e_20` es `Location` y `e_21` es `Person`, mientras que aquí corresponden a `Person` y `Location`, respectivamente. Una rutina de análisis debe usar la leyenda propia del par y registrar explícitamente cualquier equivalencia entre clases. La leyenda original incluye campos adicionales, cuyos nombres deben comprobarse antes de agregarlos por código.

Los cuatro archivos de anotaciones de `Yuriria_generales/` son objetos JSON con la clave `entities`, como los del AGI. Tres se distribuyen como `.ann.json`; el de Ysassy, `1649_Demarcación_YSASSY.ann.json.gz`, contiene el JSON original comprimido sin pérdida y debe descomprimirse antes de procesarlo como JSON. Cada registro conserva `classId`, `part`, `offsets` y `fields`, y el `part` identifica un párrafo del `.plain.html` que acompaña al archivo de anotaciones. Se comprobó que los **14,628 fragmentos y posiciones** coinciden con esos HTML. Las anotaciones están ancladas en los cuatro HTML, no en los TXT situados originalmente junto a la exportación ni en la transcripción principal de la BNE. Las cuatro parejas contienen 2,749 registros en la carta de Covarrubias, 578 en la descripción de García de Ávalos, 1,669 en la relación de Ortega Valdivia y 9,632 en la demarcación de Ysassy. La descripción de García de Ávalos se refiere a la obra BNE, ms. 3047, ya incluida entre las transcripciones principales; la equivalencia de sus dos versiones textuales no se ha cotejado. Los otros tres textos amplían las fuentes representadas en el repositorio. Véase la [guía de lectura y recuperación](README.md#anotaciones-comprimidas-de-ysassy), incluida la huella SHA-256 del JSON original.

El HTML asociado con Covarrubias contiene siete caracteres de salto de página (`U+000C`). Se conserva tal como fue exportado. Para procesarlo conviene usar un lector de HTML que tolere esos caracteres; una lectura como XML estricto puede fallar.

## Uso de los metadatos y revisión

`inventario_anotaciones.csv` tiene una fila por par y los siguientes campos:

| Campo | Contenido |
|---|---|
| `id_documento`, `institucion`, `signatura`, `fecha_documento`, `fojas` | Identificación y metadatos disponibles de la fuente, sujetos a cotejo. |
| `archivo_texto_anotado`, `archivo_anotaciones`, `archivo_leyenda` | Rutas relativas de los tres componentes necesarios para leer el par. `archivo_anotaciones` termina en `.ann.json.gz` para Ysassy; se descomprime antes de leer el JSON. |
| `registros_anotacion`, `formato_exportacion` | Recuento de registros y estructura del par. |
| `transcripcion_principal`, `relacion_con_transcripcion` | Correspondencia propuesta con el corpus de transcripciones y resultado de la comparación textual disponible. |
| `estado_revision`, `estado_derechos` | Comprobaciones pendientes para uso, cita y eventual difusión. |
| `ruta_origen_relativa`, `observaciones` | Ubicación de la exportación en las carpetas de trabajo y notas de selección. |

El corpus permite estudiar expresiones identificadas en los textos y explorar relaciones entre temas y lugares. Para convertirlo en una base comparativa se necesitaría comprobar los límites de los fragmentos, armonizar las tres leyendas con decisiones explícitas, evaluar los textos fuente y documentar el procedimiento de anotación y revisión. El total de 16,034 registros corresponde a la exportación actual y no constituye una medida de cobertura ni de exactitud.
