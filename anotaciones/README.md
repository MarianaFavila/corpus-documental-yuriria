# Corpus anotado de Yuririapúndaro y Michoacán

Esta carpeta reúne una selección de archivos de la carpeta `Corpus_anotado` del Proyecto YURIRIA. Comprende **18 pares de texto y anotaciones**: once expedientes del Archivo General de la Nación (AGN), tres relaciones del Archivo General de Indias (AGI) y cuatro documentos de una tercera exportación, cuya identificación archivística debe completarse. Las exportaciones contienen **16,034 registros de anotación** en total: 946 del AGN, 460 del AGI y 14,628 de los cuatro documentos adicionales. Son recuentos de los registros presentes en los archivos, no una evaluación de la exhaustividad o calidad de las anotaciones.

La organización se inspira en la documentación de los [corpus anotados del proyecto *Digging into Early Colonial Mexico* (DECM)](https://github.com/patymurrieta/Digging-into-Early-Colonial-Mexico/tree/master/DECM_Corpus/DECM_Machine_Annotated_Corpus), que conserva juntos los textos, los archivos de anotaciones y sus leyendas. Esta selección corresponde a fuentes y exportaciones del Proyecto YURIRIA. Sus categorías, formatos y estados de revisión se describen aquí a partir de los archivos efectivamente incorporados.

## Contenido y organización

| Carpeta | Fuentes | Texto asociado | Anotaciones | Leyenda | Registros |
|---|---:|---|---|---|---:|
| `AGN/` | 11 | `.txt` | `.ann.json` | `AGN/annotations-legend.json` | 946 |
| `AGI/` | 3 | `.plain.html` | `.ann.json` | `AGI/annotations-legend.json` | 460 |
| `Yuriria_generales/` | 4 | `.plain.html` | 3 `.ann.json` y 1 `.ann.json.gz` | `Yuriria_generales/annotations-legend.json` | 14,628 |
| **Total** | **18** | **18 archivos** | **17 `.ann.json` y 1 `.ann.json.gz`** | **3 leyendas** | **16,034** |

En cada carpeta, el texto y sus anotaciones tienen el mismo nombre base. Por ejemplo, `AGN/AGN_Indios_v006_exp44.txt` se acompaña de `AGN/AGN_Indios_v006_exp44.ann.json`. El par de Ysassy contiene `Yuriria_generales/1649_Demarcación_YSASSY.plain.html` y `Yuriria_generales/1649_Demarcación_YSASSY.ann.json.gz`. La relación de cada par, sus metadatos disponibles y el número de registros aparecen en [`inventario_anotaciones.csv`](inventario_anotaciones.csv). Las leyendas identifican las clases y etiquetas de cada exportación; los detalles de los formatos se explican en [`ONTOLOGIA_Y_FORMATOS.md`](ONTOLOGIA_Y_FORMATOS.md).

Esta selección conserva los textos que acompañan a las anotaciones porque sus archivos JSON remiten a esos textos. De los 14 pares del AGN y AGI, **trece textos acompañantes difieren a nivel de bytes de la transcripción principal de su fuente en `transcripciones/`; uno coincide exactamente**. Entre los cuatro pares de `Yuriria_generales/`, el atribuido a García de Ávalos corresponde a la obra conservada como BNE, ms. 3047, ya presente entre las 42 transcripciones principales. Su HTML anotado se relaciona con otra versión legible del texto localizada en la raíz de `Manuscritos`; su equivalencia con el TXT principal del repositorio no se ha cotejado. Los otros tres, atribuidos a Covarrubias, Ortega Valdivia y Ysassy, amplían la selección de fuentes y tienen su texto acompañante en esta carpeta. En conjunto, **15 pares se vinculan con fuentes de las 42 transcripciones principales y tres pares corresponden a fuentes añadidas**. La identificación de una fuente común por título o signatura no basta para trasladar las posiciones de anotación a otra versión del texto. Las correspondencias propuestas y el estado de su cotejo figuran en el inventario.

| Texto de la tercera exportación | Registros | Relación con las 42 transcripciones principales |
|---|---:|---|
| Carta de Baltasar de Covarrubias (1619) | 2,749 | Fuente añadida; procedencia de la versión por comprobar. |
| Descripción de García de Ávalos (1638) | 578 | Misma obra que BNE, ms. 3047; equivalencia con el TXT principal sin cotejar. |
| Relación de Ortega Valdivia (1639) | 1,669 | Fuente añadida; procedencia de la versión por comprobar. |
| Demarcación de Ysassy (1649) | 9,632 | Fuente añadida; procedencia de la versión por comprobar. |

## Cómo consultar los archivos

1. Busca la fuente en `inventario_anotaciones.csv` y abre la ruta indicada en `archivo_texto_anotado`.
2. Abre el archivo emparejado en `archivo_anotaciones` y consulta `archivo_leyenda` para interpretar los códigos de clase y campo. Conserva juntos los dos archivos de cada par. Para Ysassy, primero lee o descomprime el `.ann.json.gz` según las instrucciones de abajo.
3. Revisa `formato_exportacion` antes de procesar el contenido JSON. En AGN, el archivo es una **lista** de registros con campos como `text`, `paragraph`, `start`, `end` y `firstEntityCode`; algunos registros también tienen `secondEntityCode`. Tanto en AGI como en la tercera exportación, es un **objeto** con la clave `entities`; cada registro emplea `classId`, `part` y `offsets`. Los identificadores de párrafo aparecen en los archivos `.plain.html`; el TXT del AGN no los marca de la misma manera.

En consecuencia, las posiciones deben interpretarse dentro del formato de exportación correspondiente. Para un análisis automatizado conviene comprobar sobre el texto asociado tanto los fragmentos como su segmentación. El número de registros no equivale necesariamente al número de personas, lugares u otras entidades distintas.

### Anotaciones comprimidas de Ysassy

El archivo `Yuriria_generales/1649_Demarcación_YSASSY.ann.json.gz` contiene el JSON original comprimido **sin pérdida** para facilitar su carga en GitHub. La exportación original sigue en la carpeta de trabajo `Corpus_anotado` de Dropbox. De los 39 archivos de origen representados en `anotaciones/`, 38 se copiaron byte por byte y este JSON se almacena comprimido. El inventario apunta al archivo `.gz` disponible en el repositorio; la compresión no cambia los **9,632 registros** de este par ni el total de **16,034**.

Para leer los registros directamente con Python, sin crear otra copia:

```python
import gzip
import json

ruta = "anotaciones/Yuriria_generales/1649_Demarcación_YSASSY.ann.json.gz"
with gzip.open(ruta, "rt", encoding="utf-8") as archivo:
    datos = json.load(archivo)
registros = datos["entities"]
```

Para recuperar el archivo original desde la raíz del repositorio y comprobar su identidad:

```bash
gunzip -c 'anotaciones/Yuriria_generales/1649_Demarcación_YSASSY.ann.json.gz' > '1649_Demarcación_YSASSY.ann.json'
sha256sum '1649_Demarcación_YSASSY.ann.json'
```

El JSON recuperado tiene **1,337,918 bytes** y SHA-256 **`9ccc3a081c1740f6893e5c2a5ce165e265f085a9bc669aab247035ae8c9b770e`**. La copia recuperada se crea en el directorio actual, sin alterar el archivo comprimido del repositorio. `SHA256SUMS.txt` registra la huella del `.gz` que se distribuye, mientras que la huella anterior corresponde al JSON original.

## Alcance y pendientes

El esquema de AGN incluye 19 clases de anotación con posibles campos más específicos, entre ellos persona, localización, actividad, movilidad y embarcación. La leyenda de AGI enumera 31 códigos de clase: 19 nombres en español y 12 en inglés. La tercera leyenda, `Yuriria_generales`, define 37 códigos de clase, con 19 nombres en español y 18 en inglés. **Los tres esquemas deben leerse por separado**, incluso cuando los códigos se parecen. La descripción completa y las inconsistencias detectadas se encuentran en `ONTOLOGIA_Y_FORMATOS.md`.

No se ha verificado aquí si cada documento fue anotado por completo, cómo se hicieron las anotaciones, quién las revisó ni su posible uso como conjunto de referencia para aprendizaje automático. Las signaturas, transcripciones y condiciones para difundir públicamente los archivos siguen sujetas a la revisión indicada en los inventarios y en [`DERECHOS_Y_PROCEDENCIA.md`](../DERECHOS_Y_PROCEDENCIA.md). El repositorio se mantiene privado durante esa revisión.

Estos archivos pueden servir para búsquedas temáticas, análisis cualitativos y cuantitativos, minería de textos y análisis geográfico del lenguaje, siempre que se tengan presentes las variantes textuales, las diferencias de formato y el estado de revisión de cada fuente.
