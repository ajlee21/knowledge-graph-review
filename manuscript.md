---
author-meta:
- David Nicholson
- Jane Roe
date-meta: '2019-12-26'
keywords:
- knowledge-graphs
- network-embeddings
- text-mining
- natural-language-processing
- deep-learning
- machine-learning
- literature-review
lang: en-US
title: Constructing Knowledge Graphs and Their Biomedical Applications
...






<small><em>
This manuscript
([permalink](https://greenelab.github.io/knowledge-graph-review/v/d1d51c8c00e0d61240e8ecd0a715144c67763e76/))
was automatically generated
from [greenelab/knowledge-graph-review@d1d51c8](https://github.com/greenelab/knowledge-graph-review/tree/d1d51c8c00e0d61240e8ecd0a715144c67763e76)
on December 26, 2019.
</em></small>

## Authors



+ **David Nicholson**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [0000-0003-0002-5761](https://orcid.org/0000-0003-0002-5761)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [danich1](https://github.com/danich1)<br>
  <small>
     Department of Systems Pharmacology and Translational Therapeutics, University of Pennsylvania
     · Funded by GBMF4552 and T32 HG000046
  </small>

+ **Jane Roe**<br>
    ![ORCID icon](images/orcid.svg){.inline_icon}
    [XXXX-XXXX-XXXX-XXXX](https://orcid.org/XXXX-XXXX-XXXX-XXXX)
    · ![GitHub icon](images/github.svg){.inline_icon}
    [janeroe](https://github.com/janeroe)<br>
  <small>
     Department of Something, University of Whatever; Department of Whatever, University of Something
  </small>



## Abstract {.page_break_before}

1. Give high level description of review as it pertains to knowledge graphs (creation and application)


## Introduction

Knowledge graphs are a practical resource for many real world applications.
They have been used in social medial mining to classify nodes [@IexVJgDF] or to create a recommendation system [@Eqbsazq5].
Knowledge graphs have also been used to understand natural language via interpreting simple questions and using relational information to provide answers [@N0gUhlt9; @s8ydThMc].
In a biomedical setting these graphs have been used to prioritize genes relevant to disease [@GI2y7kMc; @Oi5yRd0v; @15k4Xz0i3; @1D9FTzRBg], perform drug repurposing [@O21tn8vf] and identify drug-target interactions [@15GxqZyO8].

Despite their utility, precisely defining a knowledge graph is a difficult task because there are multiple conflicting definitions [@V9M93in].
For this review, we define a knowledge graph as the following: a resource that integrates single or multiple sources of information into the form of a graph.
This graph allows for the capacity to make semantic interpretation, continuously incorporate new information and uncover novel hidden knowledge through computational techniques and algorithms.
Based on this definition resources like Hetionet [@O21tn8vf] would be considered a knowledge graph.
Hetionet integrates multiple sources of information into the form of a graph (example shown in Figure {@fig:hetionet_schema}) and was used to derive novel information concerning unique drug treatments [@O21tn8vf].
We do not consider databases like DISEASES [@5gG8hwv7] and DrugBank [@1FI8iuYiQ] to be knowledge graphs.
These resources contain essential information, but do not represent their data in graph form.

Knowledge graphs are often constructed from manually curated databases [@O21tn8vf; 10.1371/journal.pcbi.1002574; @kBHNhSma; @tIGJl1ES;  @BTEcMH0X].
These sources provide previously established information that can be incorporated into a graph.
For example, a graph using DISEASES [@5gG8hwv7] as a resource would have genes and diseases as nodes, while edges would be added between nodes that have an association.
This example shows a single type of relationship; however, there are graphs that use databases with multiple relationships.
Other approaches have used natural language processing techniques to build knowledge graphs [@gddb9uXr; @rxaBUglG].
One example used a text mining system to extract sentences that indicated a protein interacting with another protein [@ibJfUvEe].
Once these sentences have been identified, they are incorporated as evidence for establishing edges in a knowledge graph.

In this review we describe various approaches for constructing and applying knowledge graphs in a biomedical setting.
We discuss the pros and cons of constructing a knowledge graph via manually curated  databases and via text mining systems.
We also compare assorted approaches for applying knowledge graphs to solve biomedical problems.
Lastly, we conclude on the practicality of knowledge graphs and point out future applications that have yet to be explored.

![
A metagraph (schema) of the heterogeneous network used in the Rephetio project [@O21tn8vf].
This undirected network depicts pharmacological and biomedical information.
The nodes (circles) represent entities and edges (lines) depict  relational information between two entities.
](https://raw.githubusercontent.com/dhimmel/rephetio/f02d44fde7eeef0ffdca0800e0b43c48d800c86d/figure/metagraph.png){#fig:hetionet_schema}


## Building Biomedical Knowledge Graphs

Knowledge graphs can be constructed in many ways using resources such as text or pre-existing databases. 
Usually, knowledge graphs are constructed using pre-existing databases.
These databases are constructed by domain experts using approaches ranging from manual curation to automated techniques, such as text mining systems.
Manual curation is a process that involves extensive use of domain experts to read papers and detect sentences that assert a relationship.
Automated approaches involve the use of machine learning or natural language processing techniques to rapidly detect sentences of interest.
We categorize these automated approaches into the following groups: rule-based extraction, unsupervised machine learning, and supervised machine learning.
We discuss examples of each type of approach and synthesize the strengths and weaknesses of each.

### Constructing Databases and Manual Curation

Database construction can date back all the way to 1956 where the first database contained a protein sequence of the insulin molecule [@GjM2NbnC].
This process involves gathering relevant text such as journal articles, abstracts, or web-based text.
At this point curators can read gathered text and detect relationship asserting sentences (i.e. relationship extraction).
An alternative to use a text mining system to filter out extraneous sentences, then incorporate curators to perfect the system's findings. 
This semi-automatic approach is way to augment curators throughout the curation process.
We discuss the pros and cons of using manual curation for relationship extraction and mention databases that use this method to populate their fields.

Notable databases have been constructed via manual curation (Table {@tbl:manual-curated-databases}).
For example, COSMIC [@pfquADl5] was constructed via a group of domain experts scanning the literature for key cancer related genes.
This database has reached close to 35M entries in 2016 [@pfquADl5] and grew to a total of 45M entiries in 2019 [@1E72FZcIm].
Studies have shown that these databases contain relatively precise data, but in low quantities [@5TLcy6Yl; @1BnoByjXH; @OELNNm08; @yjdNa04s; @d3rG3TXb; @16P0HRKom; @UdzvLgBM].
This happens because the high publication rate is too much for curators to keep up [@vYYWSlK2].
This findings highlight a critical need for future approaches to be fast enough to compete with an increasing publication rate.

Semi-automatic methods are a way to augment curators during the curation process [@17LLVYRDg; @iJxqfYog; @us6gXxVp; @kHKmKy23; @17KVV4Pum; @d3rG3TXb; @SHPz84Z7].
First step in this context is to use an automatic system to initally extract sentences from text.
This process filters out irrelevant sentences, which means less text for  curators to sift through.
After the pre-filtering step curators can approve or remove the identified sentences.
This semi-automatic process was found to speed up the curation process compared to manual approach [@17LLVYRDg; @KX7N360G]. 
Curators in [@KX7N360G] saved an average of 2.8 hours of overall time while curators in [@17LLVYRDg] saved about the same amount of time (2 hours). 
Despite the speed up, this process is prone to produce bias results.
As automated systems excel in identifying sentences for commonly occurring relationships, they miss out on lessor known relationships [@17LLVYRDg].
Plus, these systems have a hard time parsing ambiguous sentences that naturally occur in text.
This complication results in curators have a difficult time correcting these systems [@17LLVYRDg].
Given these caveats, a future direction would be using or creating approaches that can mitigate the relationship bias.
Furthermore, future approaches should look into using techniques that simplify sentences to solve the ambiguity issue [@umenx8Nh; @aJL1tPyy].

Despite the negatives of manual curation, it is still an essential process for relationship extraction approaches.
This process can be used to generate gold standard datasets that automated systems use for validation [@Y2DcwTrA; @YWh6tPj].
Furthermore, manual curation can be used during the training process of  automated systems (i.e. active learning) [@MTIt6gSA].
It is important to remember that manual curation alone is precise, but results in low recall rates [@UdzvLgBM].
Future databases should consider initially relying on automated methods to obtain sentences at an acceptable recall level, then incorporate manual curation as a way to fix or remove irrelevant results.

| Database [Reference] | Short Description | Number of Entries | Entity  Types | Relationship Types | Method of Population |
| --- | --- | --- | --- | --- | --- |
| Entrez-Gene [@u7vVtngU] | NCBI's Gene annotation database that contains information pertaining to genes, gene's organism source, phenotypes etc. | 7,883,114 | Genes, Species and Phenotypes | Gene-Phenotypes and Genes-Species mappings | Semi-automated curation |
| UniProt [@1ZE22clL] | A protein protein interaction database that contains proteomic information. | 560,823 | Proteins, Protein sequences | Protein-Protein interactions | Manual and Automated Curation | 
| PharmGKB [@qbo1ouMs] | A database that contains genetic, phenotypic, and clinical information related to pharmacogenomic studies. | 43,112 | Drugs, Genes, Phenotypes, Variants, Pathways | Gene-Phenotypes, Pathway-Drugs, Gene-Variants, Gene-Pathways | Manual Curation and Automated Methods |
| COSMIC [@pfquADl5] | A database that contains high resolution human cancer genetic information. | 35,946,704 | Genes, Variants, Tumor Types| Gene-Variant Mappings | Manual Curation | 
| BioGrid [@kFAyvOpe] | A database for major model organisms. It contains genetic and proteomic information.| 572,084 | Genes, Proteins| Protein-Protein interactions | Semi-automatic methods |
| Comparative Toxicogenomics Database [@axd6eJec] | A database that contains manually curated chemical-gene-disease interactions and  relationships. | 2,429,689 | Chemicals (Drugs), Genes, Diseases | Drug-Genes, Drug-Disease, Disease-Gene mappings | Manual curation and Automated systems |
| Comprehensive Antibiotic Resistance Database [@1ByMfX8Y1] | Manually curated database that contains information about the molecular basis of antimicrobial resistance. | 174,443 | Drugs, Genes, Variants | Drug-Gene, Drug-Variant mappings | Manual curation |
| OMIM [@1FZWpEoss] | A database that contains phenotype and genotype information | 25,153 | Genes, Phenotypes | Gene-Phenotype mappings | Manual Curation |
Table. A table of databases that used a form of manual curation to populate entries. 
Reported number of entities and relationships are relative to time of publication.
{#tbl:manual-curated-databases}

### Text Mining for Relationship Extraction

#### Rule-Based Natural Language Processing

1. Mention papers on hand written rules and expressions

#### Extracting Relationships Without Labels

Unsupervised methods of extraction involve drawing inferences from data without the use of labels.
These methods involve some form of clustering or statistical calculations.
In this section we discuss methods that use unsupervised learning to detect relationship asserting sentences from text.

An unsupervised method to extract relationships exploits the fact that two entities can appear together in text. 
This kind of event is called co-occurrence and studies that use this phenomenon can be found in table {@tbl:unsupervised-methods-text-mining}.
Two databases DISEASES [@5gG8hwv7] and STRING [@iihNCsNX] were populated using a co-occurrence scoring method on PubMed abstracts.
Both databases used the same scoring method that measured the frequency of co-mention pairs within individual sentences as well as the abstracts themselves.
This method assumes independence between each individual occurrence.
Under this assumption mention pairs that occur more than expected were presumed to indicate the presence of an association or interaction.
This approach was able to identify 543,405 disease gene associations [@5gG8hwv7] and 792,730 high confidence protein protein interactions [@iihNCsNX], but is limited to only using PubMed abstracts.

Full text articles are able to drastically amplify text mining power to detect relationships [@DGlWGDEt; @pLAIFXqP].
Westergaard et al. used a co-occurrence approach, similar to DISEASES [@5gG8hwv7] and STRING [@iihNCsNX], to mine full articles for protein-protein interactions and other protein related information [@DGlWGDEt].
The authors discovered that full text provided better prediction power than using abstracts alone.
This improvement suggests that future text mining approaches should consider using full text to increase detection power.

Unsupervised methods have been focused on treating multiple biomedical relationships as multiple isolated problems.
These methods repeatedly use the same model for each biomedical relationship type.
An alternative to this persepctive is to capture all different relationship types at once.
Clustering is an approach that accomplish this concept of simultaneous extraction.
Percha et al. used a biclustering algorithm on generated dependency parse trees to group PubMed abstract sentences [@CSiMoOrI].
Each cluster was manually curated to determine which relationship they represented.
This approach captured 4,451,661 dependency paths for 36 different groups [@CSiMoOrI].
Despite the success, this approach suffered from technical issues such as dependency tree parsing errors.
This type of error resulted in sentences not being grouped by the clustering algorithm [@CSiMoOrI].
Future clustering approaches should consider simplifying sentences to prevent this type of issue.

Overall unsupervised methods provide a means to rapidly find relationship asserting sentences without the need of annotated text.
Approaches in this category range from using co-occurrence scores to clustering sentences.
These methods provide a generalizable framework that can be used on large repositories of text.
Future methods can improve detection power by considering the use of  methods that simplify sentences and use datasets that include full text articles.

| Study | Relationship of Interest | 
| --- | --- | 
| [@IGXdryzB] | Protein-Protein Interactions, Disease-Gene and Tissue-Gene Associations |
| [@ETC6lm7S] | Drug Disease Treatments |
| [@AdKPf5EO] | Drug, Gene and Disease interactions |
| [@DGlWGDEt]| Protein-Protein Interactions |
| [@5gG8hwv7] | Disease-Gene associations|
| [@q9Fhy8eq]| Protein-Protein Interactions |
| [@10tWTMIaV] | Genotype-Phenotype Relationships |

Table: Table of approaches that mainly use a form of co-occurrence. {#tbl:unsupervised-methods-text-mining}

#### Supervised Machine Learning

1. Mention the availablility of publically available data
	1. PPI - 5 datasets 
	   1. 10.1016/j.artmed.2004.07.016 
	   2. 10.1186/1471-2105-8-50 
	   3. Learning language in logic - genic interaction extraction challenge
	   4. 10.1093/bioinformatics/btl616 
	   5. http://helix-web.stanford.edu/psb02/ding.pdf
	2. DaG - 3 datasets
	   1. 10.1016/j.jbi.2012.04.004 
	   2. 10.1186/s12859-015-0472-9
	   3. 10.1186/1471-2105-14-323 
	   4. 10.1186/1471-2105-13-161
	3. CiD 
	  1. 10.1093/database/baw068 
	4. CbG 
	  1. Biocreative VI track 5 - raw citation
	5. more if exists talk about deep learning methods
2. Mention the use of Support Vector Machines and other non deep learning classifiers
   1. Will have to mention that field has moved to deep learning.
   2. 10.1186/s13326-017-0168-3
   3. 10.1371/journal.pcbi.1004630
3. Mention deep learning methods
   1. 1901.06103v1
   2. 10.1016/j.knosys.2018.11.020
   3. 10.1177/0165551516673485
   4. 1706.01556v2
   5. ^^ A few papers here but a lot more will be put into place 
   6. Mention caveat which is the need for large annotated datasets
   7. Mention a direction the field is moving to which is weak supervision and more that info that will come in time.


## Applying Knowledge Graphs to Biomedical Challenges

1. Mention that these graphs can be used for discovery
2. Mention representation learning (aka representing a graph as dense vectors for nodes and/or edges)
3. 

### Unifying Techniques

1. Set up the problem that maps a knowledge graph into a low dimensional space

#### Matrix Factorization

1. Mention techniques for these with some papers

#### Deep Learning

1. Define node neighborhoods
2. Talk about random walks 
3. Talk about auto encoders random walk independent approaches 

### Unifying Applications

1. Mention how the previous section is used in a biomedical setting

#### Disease and Gene Interactions

1. Mention disease gene prioritization
2. Mention Disease gene associations

#### Protein Protein Interactions

1. Mention predicting genes interacting genes

#### Drug Interactions

1. Talk about drug side effects
2. Drug repurposing
3. Drug-Disease Interations

#### Clinical applications

1. Can mention EHR use and other related applications
2. Mention Tiffany's work on private data embeddings


## Conclusion
1. Summarize discussed positives and pitfalls
2. Leave some open ended questions yet to be explored
  1. Will come into play as I write this review paper


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>