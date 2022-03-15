---
id: 1KLIQ2IZ68QFd1W10xMrG
title: Day03
desc: ''
updated: 1645430121255
created: 1645429958766
---
# Practice session: Linkage desequilibrium

1. Ir a https://www.ncbi.nlm.nih.gov/gene

    Este sitio nos permite obtener informaciones de un gen, como por ejemplo, su localización cromosómica, sus posibles funciones, los fenotipos asociados, y nos da una reseña de la literatura, entre otras cosas. Esta base de datos contiene información génica sobre múltiples especies.

    Buscar *MC1R*.

    En Search results hacer clic en *MC1R* correspondiente a Homo sapiens. Va a aparecer información básica sobre el gen y lo que se conoce de sus funciones.

    En Genomic context, Location, verificar la ubicación cromosómica del gen según el ensamblado (Assembly) GRCh37.p13. ¿En qué cromosoma, banda y posición específica está ubicado? Anotar la ubicación del gen para usarla en la parte 4.

    > Answer: NC_000016.9 (89985270..89987380)
    Chromosome 16, q band

2. Ir a www.internationalgenome.org  

    El International Genome Sample Resource (IGSR) se basa en muestras colectadas por el proyecto 1000 Genomas, a las que incorporó nuevas muestras. El objetivo del proyecto 1000 Genomas y, por ende, del IGSR, es catalogar la variación genética humana secuenciando muestras de individuos auto-declarados sanos.

    Hacer clic en Data, luego en Browse the 1000 Genomes Project phase three call set on GRCh37 bajo el titulo View variants in genomic context in EnsEMBL.

    Hacer clic en Go to e! GRCh37.

    En la casilla de búsqueda colocar *MC1R* y seleccionar la especie Human.

    Hacer clic en el primer gen que aparece listado.

    En la siguiente página hacer clic en el enlace que aparece en Location.

    Inspeccionar las características de la región génica en la que se encuentra *MC1R*.

    Listar algunos de los genes vecinos a *MC1R* (zoom out).

    > Answer: *TUBB3*, *TCF25*,*DEF8*, *AFG3L1P*.

3. Ahora vamos a explorar el desequilibrio de ligamiento presente en la región génica del *MC1R*.

    Ir al enlace Linkage data que aparece a la izquierda.

    También a la izquierda, pero más abajo, hacer clic en Select populations.

    Seleccionar CEU (individuos residentes en USA con ancestría del norte y occidente de Europa, N=99), CLM (colombianos de Medellín, N=94) y YRI (Yorubas de Nigeria, N=108). Cerrar la ventana.

    > Population selected: CLM, YRI

    En la parte inferior de la página observar los patrones de desequilibrio de ligamiento (LD) en las 3 poblaciones, medidos tanto con D’ como con r2. ¿Qué diferencias se aprecian?
    
    > CLM: 81 SNPs
    > YRI: r<sup>2</sup> 100 SNPs | D': 100 SNPs

    Hacer clic en algunos SNPs para ver información sobre ellos.

4. Vamos a utilizar estos datos para examinar en mayor detalle los SNPs presentes en el MC1R y el desequilibrio de ligamiento entre ellos en diferentes poblaciones. Para ello descargaremos la información desde el IGSR correspondiente a nuestras dos poblaciones de interés, CEU y CLM.

    Ir a http://grch37.ensembl.org/Homo_sapiens/Tools/VcftoPed
    
    Darle un nombre al trabajo.

    Colocar la ubicación del gen, en el formato cromosoma: comienzo – fin (obtenida en la parte 1), en la casilla correspondiente a la región.
    
    Seleccionar CEU y CLM en poblaciones.

    En Base format marcar Bases y marcar la casilla de Biallelic only.
    
    Correr y esperar hasta que aparece Done. Descargar el Marker Information file y el Pedigree file y luego extraer el archivo compactado ped.gz.

    Los archivos descargados anteriormente ya están incluidos en el material de la práctica.
    
    Abrir Haploview.
    
    En Data file cargar el archivo .ped provisto para cada población.
    
    En Locus Information file cargar el archivo .info provisto, con la información de los SNPs en *MC1R*.
    
    Dar OK.

    En la sección Check markers tomar nota de cuantos individuos y cuantos SNPs hay en cada población. En Minimum minor allele freq. colocar 0.01 y hacer clic en Rescore Markers. ¿Cuántos SNPs quedaron para ser usados?

    > CLM: 22, 13

    Ir a LD Plot. En Display seleccionar Show LD values, R-squared y en LD color scheme select GOLD heatmap. En Analysis, Define Blocks, seleccionar Solid Spine of LD. ¿Cuántos bloques hay en cada población?

    > CLM: 2 blocks

    Ir a Haplotypes. Examinar los bloques generados y los haplotipos presentes. Para ver todos los haplotipos colocar 0 en la casilla Examine haplotypes above. ¿Cuántos haplotipos hay en cada bloque?

    > Block 1: 13
    > Block 2: 5

    Ir a Tagger, Configuration. Seleccionar la casilla Exclude A/T & C/G SNPs.

    Nota: A/T & C/G son SNPs palindrómicos o ambiguos, es decir que sus alelos están representados por el mismo par de letras en las dos hebras de ADN (forward and reverse), lo que puede introducir ambigüedad en la identidad del alelo que estamos considerando. 

    Hacer clic en Run Tagger. Inspeccionar los resultados. ¿Cuántos SNPs son tag SNPs en cada población?

    > 11
    
    Nota: tag SNPs son polimorfismos en una región del genoma con un alto desequilibrio de ligamiento que representan a un haplotipo. Permiten describir la variación genética de la región y su asociación con fenotipos de interés sin necesidad de genotipar cada SNP de una región cromosómica. Esto reduce el gasto y el tiempo de mapeo de áreas del genoma asociadas a enfermedades, ya que elimina la necesidad de estudiar cada uno de los SNP presentes.

    Salvar los tag SNPs haciendo clic en la opción Dump Tags File.

    Comparar los tag SNPs entre CEU y CLM. ¿Qué diferencias se observan?

5. Ahora vamos a buscar información especifica sobre cada tag SNP.

    Hallar el rs id para cada tag SNP.

    Ir a dbSNP: https://www.ncbi.nlm.nih.gov/snp/

    Buscar cada tag SNP colocando su localización (ej. 16: 89986760) en la casilla de búsqueda. Crear una planilla de Excel con la posición de cada SNP y el rs correspondiente.

    - CLM
    16:89986632, rs3212368 | rs1343469836

    16:89986091, rs11547464

    16:89985844, rs1805005 | rs1364964334

    16:89986252, rs3212366

    16:89986760, rs3212369

    16:89985940, rs2228479 | rs1182978562 | rs1241199222

    16:89986154, rs885479 | rs889248756 | rs2045698175

    16:89986608, rs2228478 | rs573362333

    16:89987201, rs3212371
    
    16:89986117, rs1805007

6. Usando el código rs averiguar más información sobre los tag SNPs. Por ej., entrar el código rs la casilla de búsqueda de Phenoscanner (http://www.phenoscanner.medschl.cam.ac.uk/) y anotar en la planilla el fenotipo (diseases&traits) con asociación más fuerte con cada tag SNP.

    ¿Qué observamos?
