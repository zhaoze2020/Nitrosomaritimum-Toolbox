# Nitrosomaritimum-Toolbox
**An integrated framework for detection and quantification of Nitrosomaritimum AOA.**

# 1. Refined SILVA classifier for QIIME2

The SILVA classifier trained with the refined SILVA taxonomy enables identification of *Nitrosomaritimum* from 16S rRNA gene amplicon data using the QIIME2 pipeline.

The provided reference sequence file (refined-silva-138.2-ssu-nr99-derep-uniq.qza) and taxonomy file (refined-silva-138.2-ssu-nr99-tax.qza) can be used to train feature classifiers using  the "q2-feature-classifier" plugin in QIIME2.

Additionally, two pre-trained Naive Bays classifiers are included:

- The " " classifier trained on the original refined SILVA database.
- The "refined-silva-138.2-ssu-nr99-V4V5-classifier.qza" classifier was trained on the V4V5 region of the 16S rRNA gene to ensure accurate taxonomic classification of amplicon reads generated with the primers 515F (5'-GTGYCAGCMGCCGCGGTAA-3') and 926R (5'-CCGYCAATTYMTTTRAGTTT-3').
- The "refined-silva-138.2-ssu-nr99-V4V5-classifier.qza" classifier was trained on the V4 region of the 16S rRNA gene to ensure accurate taxonomic classification of amplicon reads generated with the primers 515F (5'-GTGYCAGCMGCCGCGGTAA-3') and 806R (5'-GGACTACNVGGGTWTCTAAT-3').

```bash
# Taxonomic classification of the ASVs/OTUs with the newly SILVA classifer
qiime feature-classifier classify-sklearn --i-classifier refined-silva-138.2-ssu-nr99-V4V5-classifier.qza --i-reads representive-sequences.qza --o-classification taxonomy.qza --p-n-jobs 1 
```



# 2. Global amoA gene classifier for QIIME2



 
