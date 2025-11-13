# Nitrosomaritimum-Toolbox
**An integrated framework for detection and quantification of Nitrosomaritimum AOA.**

# 1. Refined SILVA classifier for QIIME2

The SILVA classifier trained with the refined SILVA taxonomy enables identification of *Nitrosomaritimum* from 16S rRNA gene amplicon data using the QIIME2 pipeline.

The provided reference sequence file (refined-silva-138.2-ssu-nr99-derep-uniq.qza) and taxonomy file (refined-silva-138.2-ssu-nr99-tax.qza) can be used to train feature classifiers using  the "q2-feature-classifier" plugin in QIIME2.

Additionally, two pre-trained Naive Bays classifiers are included:

- The " " classifier trained on the original refined SILVA database.
- The "refined-silva-138.2-ssu-nr99-V4V5-classifier.qza" classifier was trained on the V4V5 region of the 16S rRNA gene to ensure accurate taxonomic classification of amplicon reads generated with the primers 515F () and 926R ().

 
