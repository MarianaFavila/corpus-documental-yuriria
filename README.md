# Transcripciones documentales de Yuririapúndaro y Michoacán

Repositorio **privado de trabajo**, preparado a partir de las carpetas `AGN_Documentos` y `Manuscritos` de Proyecto YURIRIA. La selección reúne una transcripción principal en TXT por unidad de trabajo y un inventario que permite localizar su procedencia. Su preparación no autoriza todavía una publicación abierta. Fecha del inventario de origen: 27 de septiembre de 2026.

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

## Organización

```text
inventario.csv
indice_mercedes_vol13.csv
pendientes_de_revision.csv
SHA256SUMS.txt
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
CITATION.cff
```

`inventario.csv` contiene una fila por TXT principal. `indice_mercedes_vol13.csv` registra las 19 piezas localizadas dentro de la transcripción conjunta del volumen. `pendientes_de_revision.csv` documenta materiales apartados de esta selección, junto con el motivo de la revisión pendiente. El nombre de cada TXT facilita su localización; para citarlo debe usarse la signatura verificada y, cuando corresponda, la foja.

`SHA256SUMS.txt` registra la huella de cada archivo de este paquete, excepto la suya propia. Los TXT se copiaron sin editar y se verificaron contra los tamaños y huellas de Dropbox al preparar la selección.

El inventario amplio de Dropbox registra más archivos porque comprende exportaciones por página, variantes HTR y modernizadas, bitácoras e imágenes. Este repositorio contiene una selección de transcripciones. Las cifras de imágenes conservadas en Dropbox no acreditan por sí solas cuántas se procesaron en Transkribus.

## Materiales en revisión

Esta primera selección deja pendientes las *Relaciones geográficas de Michoacán* en la edición de René Acuña, los fragmentos OCR de la obra de Diego Basalenque alojada por UANL y los TXT situados en la raíz de `Manuscritos` vinculados con la Biblioteca del Palacio Real y la Newberry Library. También quedan fuera de la selección principal las versiones alternativas de las relaciones del AGI y la versión legible de la descripción de la BNE situada en la raíz. Su procedencia, autoría editorial y condiciones de uso requieren una revisión individual antes de incorporarlas.

## Consulta, revisión y cita

La selección documental y las decisiones sobre variantes se explican en [METODOLOGIA.md](METODOLOGIA.md). Los puntos que requieren aclaración antes de publicar se registran en [DERECHOS_Y_PROCEDENCIA.md](DERECHOS_Y_PROCEDENCIA.md). La ficha [CITATION.cff](CITATION.cff) es provisional: las citas de fuentes históricas deben incluir además archivo, ramo o colección, signatura y fojas comprobadas. No se ha asignado una licencia pública ni un DOI a esta versión privada.
