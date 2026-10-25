# Candidate biallelic BUB1B variants in mosaic variegated aneuploidy

Team: Checkpoint Genomics. Track 1, model 1: phenotype-guided BUB1B candidate-pair prioritization. Proband: WGS_EX2312012. Reference assembly: GRCh38. Repository: https://github.com/irvingReyes02/checkpoint-genomics-mva-track1.

## Abstract

A phenotype-guided analysis prioritized a candidate pair of heterozygous BUB1B variants in a child reported to have mosaic variegated aneuploidy, rhabdomyosarcoma and prenatal-onset growth restriction. The submitted prediction combines chr15:40209701 T>G, annotated as c.2210T>G (p.Leu737Ter), with chr15:40220612 T>G, annotated as c.3006T>G (p.Asn1002Lys). The truncating variant has a pathogenic ClinVar assertion for mosaic variegated aneuploidy syndrome 1. The missense variant is a candidate damaging allele on the basis of computational annotations reported in the original analysis; its clinical pathogenicity is not established by those predictions alone. The pair is submitted as one primary candidate with a subjective EPCR of 0.95. Phase remains unresolved, and compound heterozygosity is therefore proposed rather than demonstrated. The principal strengths are phenotype-directed prioritization and explicit modeling of a recessive pair. Limitations include a narrow gene search, missing parental phase information, lack of functional validation of the missense variant, and unavailable raw analysis artifacts for independent verification during report preparation.

## Data provenance and computational approach

This report revises the supplied TEAM_track1_report.md and TEAM_bub1b-comphet-vep.csv. The original VCF, alignment files, scripts, annotation responses and structural-analysis outputs were not supplied for this revision. Read counts, predictor scores and pipeline descriptions below are consequently attributed to the original analysis rather than presented as independently reproduced results.

The original report describes a single-sample GATK 4.2.4 HaplotypeCaller VCF on GRCh38 with decoy sequences. It reports extraction with pysam 0.24 of BUB1B, TRIP13 and CEP57 gene intervals with 10 kb flanks, retention of non-reference genotypes, and Ensembl VEP REST annotation. Reported filters were FILTER=PASS, population allele frequency below 0.001, and a protein-altering consequence or splice-region consequence with SpliceAI at least 0.2. Recessive candidates included biallelic calls or pairs of heterozygous variants in the same gene. Detection of two heterozygous variants was used for candidate generation and does not establish their phase.

The original annotation sources included ClinVar, gnomAD v4, CADD v1.7, SpliceAI, AlphaMissense and REVEL. Exact database snapshots, the Ensembl release, transcript version used in the original run, API requests and per-variant annotation responses were not available. These details must be retained in the analysis repository for full reproducibility. The current ClinVar record for the truncating variant uses NM_001211.6. No new alignment, variant calling, genome-wide prioritization or structural analysis was performed for this revision.

## Candidate evidence and biological rationale

The submitted coordinates are chr15:40209701 T>G and chr15:40220612 T>G on GRCh38. The original report gives heterozygous reference/alternate read counts of 21/25 and 15/13, respectively, with PASS filters. These reported counts are compatible with heterozygous calls but have not been checked against the original reads. ClinVar independently supports the first variant's GRCh38 coordinate and NM_001211.6:c.2210T>G, p.Leu737Ter annotation. The second coordinate-to-transcript mapping is retained from the supplied analysis.

ClinVar RCV000641226.9 records p.Leu737Ter as pathogenic for mosaic variegated aneuploidy syndrome 1, with criteria supplied by a single submitter and an evaluation date of October 9, 2024. The submitter also warns that population frequency information is unreliable because of poor site-level quality in gnomAD. Accordingly, the original reported frequency of 3.3e-5 is not used here as firm evidence of rarity. A premature stop supports a loss-of-function hypothesis, but transcript-specific nonsense-mediated decay was not independently evaluated.

For p.Asn1002Lys, the original analysis reports absence from gnomAD, CADD 24.5 and AlphaMissense 0.92. Population absence requires confirmation of dataset version, coverage and allele number. AlphaMissense is a computational prediction, not a calibrated probability that the variant causes the patient's phenotype and not a clinical ACMG/AMP classification. No formal pathogenic or likely pathogenic classification is assigned to this missense variant in this report.

Biallelic BUB1B variants are an established cause of mosaic variegated aneuploidy, and truncating and missense variants have been described in affected families that included children with embryonal rhabdomyosarcoma. This provides a strong gene-level rationale for prioritizing the pair. The original structural interpretation placed Asn1002 in the C-terminal kinase-like region and proposed destabilization. Because the structural outputs were unavailable and no variant-specific functional assay was supplied, this remains a mechanistic hypothesis. It does not demonstrate reduced protein abundance or hypomorphic activity for p.Asn1002Lys.

## Prediction format, curation and secondary findings

The submission is a downstream-curated candidate file rather than an unmodified automated output. It contains one primary row representing the proposed pair, using the competition's CSV columns. EPCR 0.95 preserves the original analysis's subjective confidence and ranking; it was not calibrated against a validation cohort or inferred from a predictor score. The two original singleton fallback rows were removed because neither was supported as an independent explanation of the proposed recessive disorder. No improvement in the competition score is assumed from this change.

The original report describes a limited additional screen of TP53, DICER1, HRAS and NF1 and identifies only the common TP53 p.Pro72Arg polymorphism. No secondary candidate is submitted. This is not an exhaustive incidental-findings assessment, and a negative limited screen does not exclude other genetic explanations.

## Limitations, scalability and validation

The variants are 10,911 bp apart. No parental segregation or validated read-based phase result was supplied. Their distance exceeds a typical individual short-read fragment but does not exclude all possible indirect phasing approaches. Phenotypic fit cannot establish trans configuration. Confirmation of both calls and segregation testing would be the most direct next steps. If both variants are in cis, this pair would not demonstrate the proposed biallelic genotype.

The reported search did not include genome-wide rare-variant analysis, copy-number or structural-variant calling, or functional validation. No qualifying TRIP13 or CEP57 variants were reported within the original filters; this is not exclusion of all disease mechanisms in those genes. A small panel is computationally economical, but its sensitivity and scalability to other phenotypes have not been benchmarked. Full reproducibility requires the original extraction and annotation scripts, configuration, software and database versions, and appropriate access to the input data.

## Public data, external information and AI disclosure

The analysis uses the competition-provided case data and public annotation resources and literature. No additional proprietary reference dataset was documented in the supplied materials; the access conditions of the competition's case data are not inferred here. During post-analysis editorial review, web search results included other public competition reports mentioning the same pair. The submitted pair and EPCR were already present in the supplied files before that search. Those reports were not used to change the candidate coordinates or ranking; this revision should not be represented as a fully blinded evaluation.

The original report attributes orchestration, scripting and drafting to Anthropic Claude via the Claude application and Cowork. The precise model, subscription plan or tier, and relevant data-handling setting were not confirmed by the submitter. This revision used OpenAI Codex for document review, source checking, CSV curation and file preparation; the account plan or tier and data-handling setting were not provided. No assertion of a no-training setting is made for either service. The organizer-requested plan and data-handling disclosures therefore remain incomplete. The original report states that variant coordinates, without the proband identifier, were sent to Ensembl VEP REST; request logs were unavailable to verify that statement.

## Runtime and cost

The original report estimates less than five minutes for extraction and approximately one minute for VEP REST on a laptop. These timings were not independently measured, and hardware specifications and logs were unavailable. No measured total cost is available; AI subscription or usage costs should not be represented as zero merely because local computation incurred no separately reported charge.

## References

Hanks S et al. Constitutional aneuploidy and cancer predisposition caused by biallelic mutations in BUB1B. Nature Genetics. 2004;36:1159–1161. https://pubmed.ncbi.nlm.nih.gov/15475955/

NCBI ClinVar. NM_001211.6(BUB1B):c.2210T>G (p.Leu737Ter) and mosaic variegated aneuploidy syndrome 1. RCV000641226.9. https://www.ncbi.nlm.nih.gov/clinvar/RCV000641226/

Richards S et al. Standards and guidelines for the interpretation of sequence variants: a joint consensus recommendation of ACMG and AMP. Genetics in Medicine. 2015;17:405–424. https://pmc.ncbi.nlm.nih.gov/articles/PMC4544753/
