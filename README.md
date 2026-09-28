# Corpus documental de Yuririapúndaro y Michoacán

Repositorio **privado de trabajo**, preparado a partir de las carpetas `AGN_Documentos`, `Manuscritos` y `Corpus_anotado` de Proyecto YURIRIA. Reúne transcripciones principales y documentos con anotaciones. Los inventarios permiten localizar su procedencia y distinguir las versiones de un mismo texto. Su preparación no autoriza todavía una publicación abierta. Inventarios de origen: 27 de septiembre de 2026; metadatos de autoría y método actualizados el 28 de septiembre.

## Alcance de esta selección

| Procedencia | Unidades de trabajo | TXT seleccionados |
|---|---:|---:|
| AGN, Tierras | 12 expedientes | 12 |
| AGN, Indios | 11 expedientes | 11 |
| AGN, General de Parte | 8 expedientes | 8 |
| AGN, Mercedes, volumen 16 | 5 expedientes | 5 |
| AGN, Mercedes, volumen 13 | 19 piezas identificadas en un volumen | 1 TXT conjunto |
| Archivo General de Indias | 3 relaciones agustinas | 3 |
| Archivo Histórico Nacional | 1 carta episcopal | 1 |
| Biblioteca Nacional de España | 1 descripción, ms. 3047 | 1 |
| **Total** | **36 expedientes del AGN, 19 piezas del volumen 13 y 5 fuentes de otros archivos** | **42 TXT** |

Los 42 TXT son archivos seleccionados para consulta y revisión. Un archivo puede contener varias piezas históricas, como sucede con Mercedes, volumen 13. La presencia de un TXT tampoco indica que su lectura haya sido cotejada con el original: el estado de cada texto se consigna en `inventario.csv`.

## Responsables del trabajo

Las **42 transcripciones principales** del AGN, AGI, AHN y BNE fueron trabajadas en **Transkribus** por **Mariana Favila Vázquez (MFV) y Francisco Cruz Ríos (FCR)**, según confirmación del proyecto. **Rodrigo Vega Sánchez** es el autor de las anotaciones reunidas en los 18 pares de `anotaciones/`. Esta atribución no implica que cada transcripción o etiqueta se haya cotejado íntegramente con la imagen original; el estado de revisión se registra por separado.

## Corpus anotado

La carpeta [`anotaciones/`](anotaciones/README.md) reúne **18 pares de texto y archivo de anotaciones**: once expedientes del AGN (946 registros), tres relaciones del AGI (460) y cuatro documentos de la exportación `Yuriria_generales` (14,628). Suman **16,034 registros de anotación**. Cada par conserva el TXT o HTML sobre el que se marcaron los fragmentos, sus anotaciones y la leyenda de la exportación. Los 18 pares y las tres leyendas representan 39 archivos de origen. El archivo de anotaciones de la demarcación de Ysassy se distribuye como `.ann.json.gz`, una compresión sin pérdida del JSON original para facilitar su carga en GitHub; los otros 17 se distribuyen como `.ann.json`. El [inventario de anotaciones](anotaciones/inventario_anotaciones.csv) describe los pares y su relación con las transcripciones principales; las categorías, los formatos y las instrucciones para recuperar el JSON se explican en [anotaciones/README.md](anotaciones/README.md) y [ONTOLOGIA_Y_FORMATOS.md](anotaciones/ONTOLOGIA_Y_FORMATOS.md).

Los once pares del AGN y los tres del AGI corresponden a fuentes presentes entre las 42 transcripciones principales. También parece corresponder a la fuente BNE ms. 3047 uno de los cuatro pares de `Yuriria_generales`; su correspondencia textual con la versión principal requiere cotejo. Los otros tres documentos de esta exportación, una carta vinculada con la Biblioteca del Palacio Real y dos relaciones vinculadas con la Newberry Library, amplían las fuentes representadas en las anotaciones respecto de la selección de transcripciones principales; la referencia a Ayer MS 1106 está identificada a nivel de colección; faltan las fojas y el cotejo de las piezas. Los once TXT de `anotaciones/AGN/` son **versiones asociadas al trabajo de anotación**, no once expedientes adicionales. En el repositorio hay 53 archivos TXT (42 principales y once acompañantes de anotación) y siete HTML acompañantes. Las posiciones de los JSON se refieren exclusivamente al texto de su propio par. El recuento de registros no acredita que los documentos estén anotados por completo ni que la pertinencia de las etiquetas haya sido revisada.

## Organización

```text
inventario.csv
indice_mercedes_vol13.csv
pendientes_de_revision.csv
SHA256SUMS.txt
anotaciones/
  README.md
  ONTOLOGIA_Y_FORMATOS.md
  inventario_anotaciones.csv
  AGN/
  AGI/
  Yuriria_generales/
transcripciones/
  AGN/
    Tierras/
    Indios/
    General_de_Parte/
    Mercedes/
  AGI/
  AHN/
  BNE/
METODOLOGIA.md
DERECHOS_Y_PROCEDENCIA.md
ESTADO_Y_PENDIENTES.md
CITATION.cff
```

`inventario.csv` contiene una fila por TXT principal. `indice_mercedes_vol13.csv` registra las 19 piezas localizadas dentro de la transcripción conjunta del volumen. `pendientes_de_revision.csv` enumera 84 registros de tres tipos: nueve unidades del AGN sin TXT localizado, cuatro variantes para cotejar y 71 archivos apartados por criterio de selección. Estos 84 registros no equivalen a 84 fuentes faltantes. La [guía del estado documental](ESTADO_Y_PENDIENTES.md) resume qué datos ya se resolvieron y cuáles requieren una consulta puntual. El nombre de cada TXT facilita su localización; para citarlo debe usarse la signatura verificada y, cuando corresponda, la foja.

`SHA256SUMS.txt` registra la huella de cada archivo de este paquete, excepto la suya propia. Los TXT se copiaron sin editar y se verificaron contra los tamaños y huellas de Dropbox al preparar la selección.

De los 39 archivos de origen del corpus anotado, 38 se copiaron sin editar. El JSON de Ysassy se comprimió sin pérdida; al descomprimirlo se recuperan exactamente sus bytes originales, cuya huella SHA-256 es `9ccc3a081c1740f6893e5c2a5ce165e265f085a9bc669aab247035ae8c9b770e`. Se comprobaron técnicamente los **16,034 anclajes** contra el TXT o HTML acompañante; esta comprobación de correspondencia no evalúa la pertinencia histórica de cada etiqueta.

El inventario amplio de Dropbox registra más archivos porque comprende exportaciones por página, variantes HTR y modernizadas, bitácoras e imágenes. Este repositorio contiene una selección de transcripciones. Las cifras de imágenes conservadas en Dropbox no acreditan por sí solas cuántas se procesaron en Transkribus.

## Materiales fuera de la selección principal

Esta primera selección de transcripciones principales deja pendientes las *Relaciones geográficas de Michoacán* en la edición de René Acuña, los fragmentos OCR de la obra de Diego Basalenque alojada por UANL y los TXT situados en la raíz de `Manuscritos` vinculados con la Biblioteca del Palacio Real y la Newberry Library. Los documentos de estas dos últimas instituciones **sí están representados en `anotaciones/Yuriria_generales/`** mediante sus propios HTML y anotaciones; aún no se han incorporado sus TXT de la raíz a `transcripciones/`. También quedan fuera de la selección principal las versiones alternativas de las relaciones del AGI y la versión legible de la descripción de la BNE situada en la raíz, aunque esta última se relaciona con otro par anotado de `Yuriria_generales`. La procedencia, autoría editorial y condiciones de uso de estas variantes requieren revisión individual.

## Consulta, revisión y cita

La selección documental y las decisiones sobre variantes se explican en [METODOLOGIA.md](METODOLOGIA.md). El [estado de las verificaciones](ESTADO_Y_PENDIENTES.md) distingue exclusiones de lagunas reales; las condiciones de difusión se registran en [DERECHOS_Y_PROCEDENCIA.md](DERECHOS_Y_PROCEDENCIA.md). La ficha [CITATION.cff](CITATION.cff) es provisional: las citas de fuentes históricas deben incluir además archivo, ramo o colección, signatura y fojas comprobadas. No se ha asignado una licencia pública ni un DOI a esta versión privada.
