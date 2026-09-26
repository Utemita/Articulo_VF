# Revisión COMROB: notas nuevas y autores

Esta carpeta es una revisión nueva. No sustituye los PDF anotados ni los archivos de las entregas anteriores.

## Qué abrir

- `articulo_semilla12.pdf`: artículo de seis páginas con Adriana Elorza-Ramos como primera autora, afiliaciones en español y los cuatro ORCID confirmados.
- `articulo_revision_ciega.pdf`: mismo contenido científico, sin datos de autoría, para la etapa de evaluación de COMROB.
- `fuentes_latex_Overleaf.zip`: proyecto LaTeX completo, con clase IEEEtran y figuras. No requiere ejecutar la optimización.
- `RESPUESTA_NOTAS.md`: respuesta a las 15 anotaciones y explicación de la revisión de pesos.
- `VERIFICACION.json`: comprobaciones automáticas de páginas, citas y conservación de resultados.

El congreso solicita PDF para el envío, no un ensamble de SolidWorks. LaTeX se edita en Overleaf, TeXstudio o VS Code con una distribución TeX; SolidWorks no abre `.tex` como artículo ni lo convierte en piezas CAD.

## Abrir en Overleaf

1. Crear un proyecto mediante **Upload Project / Subir proyecto** y seleccionar `fuentes_latex_Overleaf.zip`.
2. Elegir **pdfLaTeX** como compilador.
3. Usar `articulo_semilla12.tex` como documento principal para la versión con autores, o `articulo_revision_ciega.tex` para la anónima.
4. Recompilar. Los archivos de dimensiones, referencias, autores y figuras ya están incluidos.

Para compilar localmente, abrir una terminal en la carpeta `latex` y ejecutar dos veces el comando correspondiente:

```text
pdflatex articulo_semilla12.tex
pdflatex articulo_revision_ciega.tex
```

Los autores se editan en `latex/autores.tex`; la bibliografía, en `latex/referencias_conservadas.tex`. No hay dependencia de BibTeX.

## Formato y etapa del envío

Se utiliza `IEEEtran` en modo `conference,letterpaper`: papel carta, dos columnas, cuerpo de 10 puntos, sin modificar márgenes para forzar el límite. Las tablas conservan títulos encima y las figuras, pies debajo. Se conservan las cuatro figuras y las cinco tablas, incluida la comparación de dimensiones. La figura 3 solo cambia la posición del texto del detalle IFD para que no cruce la curva; no se han desplazado ni exagerado los datos.

COMROB 2026 exige un máximo de seis páginas y **no incluir autores ni instituciones durante la revisión ciega**. La versión con autores corresponde a la versión final, una vez aceptado el trabajo. Para evaluar se envía únicamente el PDF ciego, no este paquete completo, que sí contiene nombres y documentos originales.

Fuente oficial consultada: https://mecatronica.ibero.mx/comrob2026/info-autores.html

El PDF entregado con el nombre `IEEE-conference-template-062824.pdf` contiene el artículo original de siete páginas, no una plantilla vacía. Se utilizó como referencia de estructura y estilo; la clase IEEEtran y las indicaciones oficiales de COMROB determinan el formato de esta revisión.

## Datos de los autores

| Orden | Nombre | Afiliación aportada | ORCID |
|---|---|---|---|
| 1 | Adriana Elorza-Ramos | 2, División de Estudios de Posgrado | 0009-0008-8398-3191 |
| 2 | Pavel Palma-Nicolás | 1, Instituto de Electrónica y Mecatrónica | 0009-0005-9704-9867 |
| 3 | Manuel Arias-Montiel | 1, Instituto de Electrónica y Mecatrónica | 0000-0003-4534-9401 |
| 4 | Esther Lugo-González | 1, Instituto de Electrónica y Mecatrónica | 0000-0002-7374-3425 |

Ambas unidades pertenecen a la Universidad Tecnológica de la Mixteca, Huajuapan de León, Oaxaca, México. Se emplean los marcadores de afiliación de IEEEtran, conservando estas asociaciones. No se añade un código postal, innecesario para el bloque IEEE.

Los cuatro ORCID pasan la comprobación de su dígito de control. Esta comprobación detecta errores de transcripción; no demuestra por sí sola la titularidad del perfil. La asociación de nombres e identificadores fue confirmada por Adriana. Los registros públicos de ORCID no pudieron leerse íntegramente con la herramienta de consulta, por lo que no se declara una verificación independiente de los cuatro perfiles.

## Qué se conserva

No se ejecutó otra optimización ni se cambió el mecanismo. Se mantienen los códigos de optimización, los CSV, las 40 ejecuciones guardadas, ED semilla 12, AG semilla 7, las dimensiones y las métricas CAD-modelo. La revisión independiente recalculó el objetivo de los 40 diseños sin encontrar diferencias. El único cambio en `codigo/validar_semilla12.py` es la colocación de un rótulo en la figura 3.

- `codigo/comparar_ED_AG.py`: comparación multisemilla, ED y AG.
- `codigo/estudio_parcial.py`: parametrización, referencia, función objetivo y verificación geométrica.
- `codigo/modelo_ED_original.py`: ecuaciones cinemáticas reutilizadas por el modelo parcial.
- `codigo/validar_semilla12.py`: evaluación del CAD y generación de tablas y gráficas; no optimiza.
- `codigo/verificar_semilla12.py`: comprobaciones del modelo y los resultados guardados.
- `datos/referencia_angular.csv`: los mismos 120 registros del archivo proporcionado.
- `datos/L1.csv`, `IFP.csv`, `IFD.csv`: rutas del ensamble de la semilla 12.
- `resultados/comparacion/`: diseños y evolución de cada ejecución.

Para validar de nuevo desde esta carpeta, después de instalar `codigo/requirements.txt`:

```text
python codigo/validar_semilla12.py
python codigo/verificar_semilla12.py
```

El primer comando reescribe las figuras y los resultados de validación de ESTA copia. No es necesario ejecutarlo para abrir el artículo ni para compilar LaTeX.

## Limitación importante antes de enviar

Se conserva la finalidad del dispositivo: el estudio de pinza fina. Sin embargo, `mocap_pinza_fina_120pts.csv` no contiene los identificadores del sujeto, movimiento o repetición. El rastreo disponible no permitió vincularlo de forma verificable con un agarre concreto de la base original. El artículo distingue esta limitación de la comparación CAD-modelo, cuyos cálculos sí se conservan y se han comprobado.

Por eso no se presenta como hecho demostrado que los 120 registros correspondan a una pinza fina real. Esta condición sigue pendiente antes de defender esa afirmación ante revisores. No se sustituyó la referencia angular por otro agarre ni se alteraron resultados para ocultarlo.

Se retiró únicamente la cita de la copia de Zenodo solicitada por Adriana. Se mantienen las otras 18 referencias, ordenadas por primera aparición; la publicación de la base original sigue citada. Las citas se ubican en el cuerpo del artículo, no en el resumen.
