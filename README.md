# Bioinformatics

Crohn’s Disease is one of the inherited disorders of the peripheral nervous system. We try to study the possible neuronal genes involved in the mutation for this disease by documenting their possible interactions and relationships. We have three interactions sources namely IID data, Bio grid, and Innate DB. Later, we perform a detailed analysis that involves the enrichment analysis associated with these genes.

The study of the biological network and its related complex dynamics is crucial to better understand human diseases. A disease represents not only a malfunction of a single gene but especially a consequence of inter-cellular network distortion. Network science simplifies the protein's interaction complexity to only two elements: the components/nodes and the interactions/edges. Using this model, the network information can be gathered to examine the underlying disease mechanism. For this reason, the study of network properties and characteristics became interesting as a reflection of biological system activity comprehension. In this report we took the gene interactomes from the previous analysis we did on Chron’s disease like Seed Gene Interactome (SGI), Interaction Interactome (I), and Union Interactome (U) and used these datasets to generate graphs using networkx python package and based on the observations we performed clustering of the genes using Louvain and MCL algorithms. Using the clustering information, we did Gene Ontology and Pathway analysis using Innate DB and put together putative disease proteins using DiAMOnD tool to conclude our analysis.

# Analysis and Observations

● There’s is considerable difference between the number of interactions returned by Bio Grid (1132) and IID (3844) datasets.

● We observed some inconsistencies between the results that we obtained in steps 3 and 4 using Bio Grid and IID data sets and the results that we saw in the Innate DB site because not all genes are present in the Ontology and Pathway analysis as we observed a different source data source (other than IID and BioGrid) which might lead to some inconsistencies in the analysis and results may be misleading as some genes which might be important for analyzing the pathological condition might be missing in the Innate DB resource 

● Some of the interactions are repeated more than once, as it is possible under the presence of a different environment.

● Using different Gene Symbol may return different interactions.

● The code and the related data are present in the corresponding folders (3,4 and 5).

● For retrieving Gene symbols for non seed genes we used a python package mygene(https://pypi.org/project/mygene/) and for retriving the Uniprot IDs for non-seed genes to be updated in 4.2.csv and 4.3.csv we used data available in this link(https://www.rcsb.org/pdb/browse/homo_sapiens_download.jsp?rows=100000&page=1&sidx=id&sord=desc). We downloaded the Gene symbol to uniport AC map available in JSON format and used it to update the uniport ids in 4.2.csv and 4.3.csv.

● Additional metadata that we used for our analysis is included in the metadata folder, which includes Gene Map.xls for mapping between Gene symbol, Uniprot ID and Gene ID.

● As per our analysis, there is similar gene set for both union interactome and intersection interactome so the results of enrichment (both Gene Ontology and Pathway) analysis will be more or less similar. 

● We observed a high degree of inter connectivity for both Union and Intersection interactome, the presence of only one Largely connected component (LCC) for both union and intersection interactome datasets reflects that. 

● We also observed that the mapping between gene id, gene name and uniport id doesn’t always result in the same output always. One common data set coupled with some standardization would be an ideal solution for these kinds of discrepancies.

● The clustering results using Louvain and MCL are not the same for each run. So we observed some randomness in the implementation of these algorithms. Eventhe DiAMOnD algorithm yielded different gene ranks after each run. 

● We faced difficulties in correlating the results of Gene Ontology and Pathway analysis from Innate DB website, so we observed that the results include other parameters as well which makes them mostly not relevant for our analysis and correlation.

● We observed that the clustering coefficient for different graphs is inversely proportional to number of nodes, so we can infer that it is difficult for a disease protein to propagate in a large network of other non-disease genes.
