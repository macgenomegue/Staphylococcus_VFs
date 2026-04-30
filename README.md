Staphylococcus Virulence Factors Database

Overview
This repository contains a curated FASTA database of virulence factors associated with Staphylococcus aureus and related species.
The database is designed to support genomic screening of virulence determinants, with particular relevance for food safety, clinical microbiology, and epidemiological investigations. Virulence profiling is essential for risk characterisation, especially for enterotoxigenic strains where toxin gene carriage determines pathogenic potential.

Contents
- Staphylococcus_VFs.fasta: curated nucleotide sequences of Staphylococcus virulence factors

Intended Use
This database is designed for:

- Whole genome sequencing (WGS) analysis
- Screening using BLAST+ or ABRicate
- Detection of virulence-associated genes, including toxins, adhesins, immune evasion factors, and exoenzymes

Recommended Tools
- BLAST+ (blastn)
- ABRicate

Recommended Parameters
- Minimum identity: 80%
- Minimum coverage: 95%

These thresholds provide a balance between sensitivity and specificity for detecting virulence genes across diverse Staphylococcus genomes.

Example Usage

BLAST+
makeblastdb -in Staphylococcus_VFs.fasta -dbtype nucl -out VF_db

blastn -query genome.fasta 
-db VF_db 
-out results.txt 
-outfmt “6 qseqid sseqid pident length qcovs evalue bitscore” 
-perc_identity 80

Filter results for coverage >=95%.

ABRicate

abricate –db Staphylococcus_VFs genome.fasta > report.tab

Ensure the database is installed in the ABRicate database directory.

Interpretation

Detection of virulence factor genes indicates the genetic potential of a strain to express specific pathogenic traits. This includes toxins, adhesion factors, and immune evasion mechanisms.

Detection of a gene does not confirm expression, protein production, or phenotypic activity. Results must be interpreted in the context of strain background, environmental conditions, and, where relevant, laboratory confirmation.

Limitations

- Database is limited to currently curated virulence genes
- Novel or highly divergent virulence factors may not be detected
- Results depend on genome assembly quality and completeness
- Gene presence does not equate to pathogenicity or clinical outcome

Curation

Sequences were compiled from public databases and peer-reviewed literature, with a focus on well-characterised Staphylococcus virulence determinants. Expansion and updates should follow transparent inclusion criteria.

Versioning

Version: 1.0
Date: 2026-04-26

Citation

If you use this database, cite both the associated publication and this repository.

Publication:
Macori G, Bellio A, Bianchi DM, Chiesa F, Gallina S, Romano A, Zuccon F, Cabrera-Rubio R, Cauquil A, Merda D, Auvray F. Genome-wide profiling of enterotoxigenic Staphylococcus aureus strains used for the production of naturally contaminated cheeses. Genes. 2019 Dec 27;11(1):33.

Database:
Staphylococcus Virulence Factors Database. GitHub repository. Available at: https://github.com/macgenomegue/Staphylococcus_VFs

Suggested citation format:
Staphylococcus Virulence Factors Database (version 1.0). Available at: https://github.com/macgenomegue/Staphylococcus_VFs

Contact

Maintainer: [Guerrino Macori]
Institution: [University College Dublin]

License
CC BY 4.0
