# Nitrosomaritimum-Toolbox
**An integrated framework for detection and quantification of *Nitrosomaritimum* AOA.**

# 1. Refined SILVA classifier for QIIME2

The SILVA classifier trained with the refined SILVA taxonomy enables identification of *Nitrosomaritimum* from 16S rRNA gene amplicon data using the QIIME2 pipeline.

The provided reference sequence file (refined-silva-138.2-ssu-nr99-derep-uniq.qza) and taxonomy file (refined-silva-138.2-ssu-nr99-tax.qza) can be used to train feature classifiers using  the "q2-feature-classifier" plugin in QIIME2.

Additionally, three pre-trained Naive Bays classifiers are included:

- The "refined-silva-138.2-ssu-nr99-classifier.qza" classifier was trained on the original refined SILVA database.
- The "refined-silva-138.2-ssu-nr99-V4V5-classifier.qza" classifier was trained on the V4V5 region of the 16S rRNA genes to ensure accurate taxonomic classification of amplicon reads generated with the primers 515F (5'-GTGYCAGCMGCCGCGGTAA-3') and 926R (5'-CCGYCAATTYMTTTRAGTTT-3').
- The "refined-silva-138.2-ssu-nr99-V4-classifier.qza" classifier was trained on the V4 region of the 16S rRNA genes to ensure accurate taxonomic classification of amplicon reads generated with the primers 515F (5'-GTGYCAGCMGCCGCGGTAA-3') and 806R (5'-GGACTACNVGGGTWTCTAAT-3').

```bash
# Taxonomic classification of representative ASVs/OTUs from 16S rRNA gene amplicon data using the SILVA classifer
qiime feature-classifier classify-sklearn --i-classifier refined-silva-138.2-ssu-nr99-V4V5-classifier.qza --i-reads representive-sequences.qza --o-classification taxonomy.qza --p-n-jobs 10
```



# 2. Global *amoA* gene classifier for QIIME2

The global *amoA* gene classifier includes a reference sequence file (amoA-db-rep-seqs.qza) and a taxonomy file (amoA-db-taxonomy.qza) derived from the global *amoA* gene database. These files can be used to classify amplicon reads generated from *amoA* gene amplicon sequencing. We suggest using the primers AOA83F64 (5’-GGWGAYTAYATNTTCTAYAC-3’) and AOA518R64 (5’-GGRCTRTTRTAGAAYTTNCC-3’) for *amoA* gene amplicon sequencing.

```bash
# Taxonomic classification of representative ASVs/OTUs from amoA gene amplicon data using the amoA gene classifier
qiime feature-classifier classify-consensus-vsearch --i-query representative-sequences.qza --i-reference-reads amoA-db-rep-seqs.qza --i-reference-taxonomy amoA-db-taxonomy.qza --p-threads 10 --output-dir output-directory
```

# 3. Specific qPCR primer set AOAnm3bF-AOAnm3aR targeting *Nitrosomaritimum* *amoA* genes

Primer AOAnm3bF: 5’-TGGGCTTGGACATCGTTTAC-3’

Primer AOAnm3aR: 5’-AACTGTCATGATRAGGCMGT-3’

The thermal cycling program included an initial denaturation at 95℃ for 30s, followed by 40 cycles of 95℃ for 5 s and 50℃ for 30 s.
