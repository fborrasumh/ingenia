# IngenIA

El laboratorio de Ingeniería Genética en tu navegador: de la restrictasa al RNA-seq. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/ingenia/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

Un laboratorio de Ingeniería Genética en el navegador que sigue el temario, las prácticas y el formato de examen de la guía docente 2026-2027 de Ingeniería Genética (asignatura 1401, Grado en Biotecnología, UMH). Todo funciona sin clave de IA salvo donde se indica.

- **Restrictasas y cartografía (T2).** 35 endonucleasas de tipo II reales, cada una con su sitio, su punto de corte en cada hebra, los extremos que genera y su organismo de origen. Se corta pUC19 (GenBank M77789.2), pBR322 (J01749), la región codificante de EGFP, el ADNc y el ARNm de la insulina humana (NM_000207.3) o una secuencia pegada. El código calcula los cortes (también los que cruzan el origen de una molécula circular), los fragmentos, el gel de agarosa que saldría a cada porcentaje —con las formas superenrollada, circular abierta y lineal del plásmido sin cortar— y el mapa circular con los genes anotados. Indica qué sitios bloquearía la metilación Dam, lo que distingue MboI de Sau3AI y explica el caso inverso de DpnI. Retos de cartografía con digestión simple y doble, distintos por estudiante, que aceptan también el mapa en espejo.
- **PCR y cebadores (T2).** Siete comprobaciones por cebador (longitud, GC, Tm, pinza 3′, repeticiones, autodímero y horquilla), Tm por vecinos más próximos con los parámetros unificados de SantaLucia (1998) y corrección de sal, junto a la regla de Wallace y la fórmula del % de GC para ver cuánto difieren. El código localiza dónde hibrida cada cebador, separa la cola 5′ de la parte que hibrida, construye el producto, calcula la Ta sugerida y detecta los sitios de restricción de las colas y sus bases protectoras. Rendimiento con meseta y fidelidad por polimerasa a partir de las duplicaciones efectivas.
- **Banco de clonación (T3-T4).** Vector (pUC19 o pBR322), una o dos enzimas, inserto, desfosforilación, extremos romos y relación molar. El código calcula los extremos reales de cada pieza, su compatibilidad, si la clonación es direccional, los productos de la ligación con su proporción y el fenotipo de cada uno (AmpR/AmpS, TetR/TetS, azul o blanca) comprobando qué genes del vector quedan intactos. Después siembra la placa y muestra las colonias que saldrían con el antibiótico y el X-gal elegidos.
- **Hibridación (T5).** Southern simulado sobre un locus de 30 kb distinto por estudiante, con cuatro enzimas y tres situaciones (copia única, gen duplicado, heterocigoto para un polimorfismo) que hay que distinguir leyendo el número y la intensidad de las bandas. Caso de paternidad con seis microsatélites reales, construido para que el varón que no es el padre quede excluido en varios loci. Curvas de reasociación C₀t, incluida la del ADN humano con sus tres componentes.
- **Secuenciación (T6).** Electroferograma de Sanger generado a partir de secuencias reales, con diagnóstico de los dos errores habituales (leerlo al revés o escribir la hebra molde). Pirograma con homopolímeros. Anotación de una secuencia: composición, ORF en los seis marcos (incluidas las que cruzan el origen) y señales de consenso, con el aviso de cuántas aparecen por azar. Cobertura de secuenciación masiva con la fracción esperada sin leer.
- **Expresión génica (T7).** Curvas de qPCR simuladas por estudiante: el código calcula el Ct por interpolación en el umbral que mueve el estudiante, el ΔΔCt y el método de Pfaffl, y los compara con el cambio real simulado. Curva patrón con eficiencia a partir de la pendiente. RNA-seq con RPKM y TPM sobre dos muestras de profundidad distinta. Footprinting con DNasa I y su sitio hipersensible.
- **Laboratorio de problemas.** Catorce tipos (frecuencia de corte, cuantificación de ADN, relación molar, eficiencia de transformación, rendimiento y fidelidad de la PCR, Tm, recta patrón del gel, digestión doble, tamaño de genoteca, complejidad por C₀t, cobertura, ΔΔCt, RPKM y TPM) con datos distintos por estudiante a partir de su código. La solución la calcula el código y, si la respuesta es incorrecta, se recalcula con los errores típicos declarados para explicar el fallo.
- **Simulacro de examen.** 50 preguntas tipo test con cuatro alternativas y 8 preguntas cortas repartidas por los siete temas. El test lo corrige el código con la clave; **no pone nota ni aplica la penalización de 0,33 del examen real**. Las preguntas cortas tienen revisión de conceptos sin IA o feedback detallado con IA.
- **Casos (T2-T7).** Ocho experimentos que no salen (una digestión que no cuadra, todas las colonias azules, una PCR con dímeros, un RFLP, un gen eucariótico que no se expresa en *E. coli*, una inducción que depende del gen de referencia, una genoteca incompleta y un gen testigo que miente) con pistas graduadas y un tutor socrático.
- **Tarjetas, Mis apuntes y Progreso.** 32 tarjetas con repetición espaciada; preguntas a los apuntes propios y tarjetas generadas a partir de ellos (con IA, cita comprobada); aciertos recientes por tema y exportación a Word, CSV y JSON.

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador. No hace falta servidor. La IA solo se usa en el feedback de las preguntas cortas, el tutor de los casos y los apuntes; no calcula nada ni pone notas.

## Privacidad

Todo se procesa y se guarda en el navegador (IndexedDB): progreso, respuestas, apuntes y la clave de IA. Las secuencias van dentro del propio fichero, y todos los cálculos (cortes, geles, Tm, clonaciones, Southern, Ct, estadística y laboratorio) los hace el código sin red.

Solo salen datos hacia el proveedor de IA si se usan las funciones con IA: las respuestas cortas, los mensajes al tutor o los apuntes, con correos, documentos de identidad y teléfonos enmascarados y tras un aviso previo con una muestra de lo que sale. El JSON exportado no contiene la clave de API.

## Límites

- El contenido (test, preguntas cortas, tarjetas, casos) es material de repaso elaborado a partir del temario de la guía docente: puede contener errores u omisiones. Mandan el profesorado, la guía docente y los guiones de prácticas.
- El gel de agarosa es un **modelo didáctico**: la distancia es lineal con el logaritmo del tamaño dentro del intervalo de resolución de cada porcentaje y se comprime fuera de él, y las formas del plásmido se dibujan con una movilidad aparente distinta. No reproduce un gel real al milímetro.
- Las proporciones de los productos de la ligación salen de un modelo sencillo que premia los extremos cohesivos frente a los romos y aplica la relación molar elegida: son orientativas, no un rendimiento medido. Un experimento real depende además de la calidad del ADN, de la ligasa y de la competencia de las células.
- El Southern, el caso de paternidad, las curvas de qPCR, los datos de RNA-seq y el footprinting son **simulaciones didácticas** con el sentido biológico esperado, no medidas de laboratorio.
- La Tm por vecinos más próximos usa los parámetros de SantaLucia (1998) con corrección de sal; un programa comercial puede dar un valor algo distinto según sus correcciones. Las tasas de error de las polimerasas son las medidas por Cline, Braman y Hogrefe (1996) en un mismo ensayo; otras publicaciones dan valores distintos.
- Las señales (cajas −35 y −10, Shine-Dalgarno, TATA, Kozak, poliadenilación) se buscan como consensos cortos: aparecen muchas veces por azar y encontrarlas no significa que sean funcionales.
- El simulacro no pone nota ni reproduce la penalización del examen real, y sustituye los dos problemas del examen por preguntas cortas; para los problemas numéricos está el laboratorio. Si la IA cuela una calificación, el código la elimina. Su feedback solo se muestra cuando la cita literal aparece de verdad en la respuesta del estudiante.
- El tutor de los casos no recibe la solución y el código filtra sus frases, pero el filtro es una lista de términos: puede dejar pasar una formulación inesperada.

Probado con IA simulada de los tres proveedores (incluida una IA que inventa citas, cuela una nota y chiva la solución), en español, inglés y portugués, en escritorio y móvil. Los cortes se contrastaron con los mapas publicados de pUC19 y pBR322 (PvuII libera 2364 y 322 pb de pUC19; los sitios únicos del policonector coinciden con los descritos) y los cálculos del laboratorio con 14 tipos × 300 variantes en Node. **No se ha probado con una clave de API real.**

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y José Luis Micol Molina (Universidad Miguel Hernández de Elche).

Sigue el temario, las prácticas y el formato de evaluación de la guía docente 2026-2027 de Ingeniería Genética (asignatura 1401, Grado en Biotecnología, UMH), cuyo responsable es José Luis Micol Molina.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · José Luis Micol Molina [0000-0002-0396-1750](https://orcid.org/0000-0002-0396-1750)

## Cómo citar

Borrás Rocher, F. y Micol Molina, J. L. (2026). *IngenIA* (v1.0.0) [Software].

## Licencia

MIT. Véase [LICENSE](LICENSE). Las secuencias proceden de registros públicos de GenBank/RefSeq (pUC19 M77789.2, pBR322 J01749, insulina humana NM_000207.3) y de un repositorio público para la región codificante de EGFP.
