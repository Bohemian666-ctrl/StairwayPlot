# StairwayPlot
Pipeline reproducible para el procesamiento de datos GBS en moluscos del género Pomacea, desde archivos VCF generados con ipyrad hasta la construcción del Site Frequency Spectrum (SFS). Incluye control de calidad del VCF, filtrado con bcftools, generación de SFS con easySFS y preparación de blueprints para Stairway Plot.
# GBS to Stairway Plot pipeline for Pomacea

Este repositorio contiene un pipeline reproducible para analizar datos de genotyping-by-sequencing (GBS) en especies del género *Pomacea*, desde archivos VCF generados con ipyrad hasta la inferencia de historia demográfica usando Stairway Plot.

## Flujo general del análisis

1. Diagnóstico del archivo VCF y control de calidad.
2. Filtrado de SNPs con bcftools:
   - Solo variantes bialélicas.
   - Filtrado por profundidad mínima.
   - Eliminación de loci con alto porcentaje de datos faltantes.
   - Pruning: un SNP por locus.
3. Generación automática del archivo popfile.
4. Construcción del Site Frequency Spectrum (SFS) con easySFS.
5. Conversión del SFS al formato requerido por Stairway Plot.
6. Ejecución de Stairway Plot usando blueprints personalizados.

## Requisitos

- Python ≥ 3.8
- bcftools
- vcftools
- Java (para Stairway Plot)
- easySFS
- stairway_plot_v2.x

Las dependencias de Python pueden instalarse con:

```bash
pip install -r requirements.txt
