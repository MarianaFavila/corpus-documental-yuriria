# Estado documental y pendientes

Actualización: 28 de septiembre de 2026. Este cuadro distingue las **fuentes**, los **archivos seleccionados** y los **archivos deliberadamente excluidos**. Los números no se suman como si todos fuesen documentos históricos distintos.

| Situación | Recuento | Lectura correcta |
|---|---:|---|
| TXT principales conservados | 42 | 37 del AGN y cinco del AGI, AHN y BNE. |
| Pares con anotaciones | 18 | Once del AGN, tres del AGI y cuatro de `Yuriria_generales`; 15 se relacionan con fuentes de los TXT principales y tres amplían la selección. |
| Unidades del AGN sin TXT localizado | 9 | Expedientes con imágenes o fichas en la carpeta inventariada, pero sin TXT de conjunto en la revisión del 27 de septiembre. |
| Variantes por cotejar fuera de `transcripciones/` | 4 | TXT de la raíz de `Manuscritos` relativos a Covarrubias, Ortega Valdivia, Ysassy y García de Ávalos; estos textos tienen relación con los pares anotados. |
| Archivos excluidos por la selección | 71 | Una transcripción de la edición de Acuña, seis variantes de las relaciones del AGI y 64 fragmentos OCR de la obra de Basalenque. |
| **Registros en `pendientes_de_revision.csv`** | **84** | **9 sin TXT + 4 variantes para cotejar + 71 exclusiones; no son 84 documentos pendientes de transcribir.** |

## Datos ya documentados

- Las 42 transcripciones principales del AGN, AGI, AHN y BNE se trabajaron en **Transkribus**. Sus responsables son **Mariana Favila Vázquez (MFV)** y **Francisco Cruz Ríos (FCR)**. Esta atribución proviene de la confirmación de la autora del proyecto del 28 de septiembre de 2026.
- Las anotaciones de los 18 pares fueron realizadas por **Rodrigo Vega Sánchez**, de acuerdo con la misma confirmación. Su autoría se registra por fila en `anotaciones/inventario_anotaciones.csv`.
- Los tres TXT del AGI proceden del conjunto identificado en la carpeta del proyecto `AGI_26_Indiferente_1529N6_GTA` como **AGI, INDIFERENTE,1529,N.6**. La signatura identifica el conjunto; todavía falta fijar el folio de cada relación.
- La ficha de la BNE conservada junto al TXT identifica **MSS/3047** como el tomo 5 de la colección reunida por Juan Díez de la Calle. Los cinco archivos de imagen de la selección se rotulan 9, 9.r, 10, 10r y 11: indican el tramo, pero no permiten asignar con certeza cada recto y verso.
- La [ficha de colección de Newberry](https://collections.newberry.org/archive/-2KXJ8Z7AGOQ6.html) acredita **Ayer MS 1106** para los textos del obispado. La asignación específica de Ortega Valdivia y Ysassy al tramo C3 se apoya además en los archivos locales y debe cotejarse con el registro de las piezas.

## Cotejos concretos que siguen abiertos

1. **AGN:** comprobar si se exportaron TXT de las nueve unidades listadas como `Falta TXT`; las 64 piezas OCR de Basalenque no pertenecen a este grupo.
2. **AGN, General de Parte, vol. 1, exps. 390–391:** cotejar las imágenes y el catálogo. La ficha conservada como expediente 391 describe el pedimento de los naturales, mientras el TXT ubicado en esa carpeta trata la petición de Martín López Mellado.
3. **AGN, Tierras, vol. 2782, exp. 23:** el TXT copiado contiene diligencias fechadas en 1590; la ficha del AGN consigna 1595. Registrar por separado la fecha del tramo transcrito y la del expediente después de revisar las imágenes completas.
4. **AGN, Indios, vol. 6, 2.ª parte, exp. 389, e Indios, vol. 17, exp. 11:** verificar las discrepancias de foja entre fichas e imágenes que ya se señalan en `inventario.csv`.
5. **AGI:** fijar las fojas individuales de Yuririapúndaro, Guayangareo y Cuitzeo dentro de `INDIFERENTE,1529,N.6` y comprobar sus enlaces archivísticos.
6. **AHN:** ubicar fondo y signatura de la carta de Francisco de Ribera del 19 de febrero de 1636; la carpeta local conserva cuatro imágenes sin foliación indicada.
7. **BNE y tercera exportación anotada:** cotejar folios exactos del ms. 3047 y equivalencia textual de los TXT y HTML. Confirmar la referencia exacta y las fojas de Covarrubias en la Biblioteca del Palacio Real y de Ortega Valdivia y Ysassy en Newberry.
8. **Anotaciones:** documentar quién diseñó o adaptó cada leyenda y el alcance de la revisión de las etiquetas, que son cuestiones distintas de la autoría ya aclarada.
9. **Difusión:** establecer para cada institución y cada versión las condiciones de publicación antes de cambiar la visibilidad del repositorio. Que una transcripción se haya trabajado en Transkribus o que el manuscrito sea antiguo no resuelve por sí solo las condiciones de difusión de la reproducción o de una edición.

`fuente_en_linea` se mantiene vacío en el inventario principal cuando aún no hay un enlace directo y verificado a la unidad. No se llena con la portada general de una institución ni con un enlace a otra pieza. Las signaturas, las carpetas de procedencia y las discrepancias conocidas permiten continuar el cotejo sin inventar metadatos. Los campos de estado de revisión paleográfica se conservan separados de los datos de autoría y plataforma.
