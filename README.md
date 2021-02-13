# Repo for Ramus & Long (In Review)
`Addititive partion of seaweed biodiversity effects across trophic levels`
This repository contains the data and code used to replicate the analysis and figures presented in

Ramus AP, Long ZT (In Review) Effects of macroalgal species identity and richness on secondary production in benthic marine communities. *Journal* Issue:Page-Range. [doi link]

`The authors request that you cite the above article when using these data or modified code to prepare a publication.`

The files contained by this repository are numbered sequentially in the order they appear in our data analysis and figure generation workflow, each of which is described below. To use our code, you will need R installed with the `cowplot`, `dplyr`, `ecodist`, `egg`, `ggplot2`, `MASS`, `plyr`, `reshape2`, and `vegan` libraries, including their dependencies. 


## `1-ramus-thesis-data-cleaned.csv’

The dataset used to generate all analyses and figures presented in the paper. 

For complete methodology,
see the corresponding article named above or 


In summary:
The experiment was carried out on intertidal mud and sandflats located within the Zeke’s Island National Estuarine Research Reserve (33.95 N, 77.94 W), North Carolina, USA.
These data represent the yields of individual macroalgal species in treatment plots 
Measured weekly in each treatment block (plot) 
Of a 12 week experiment conducted in situ along 

We followed the development of consumer communities in each treatment for 12 weeks in situ. 

time-averaged value of each variable measured monthly in each plot over the course of a 10 month experiment carried out on intertidal mud and sandflats located within the Zeke’s Island National Estuarine Research Reserve (33.95 N, 77.94 W), North Carolina, USA.

Similar to our earlier work in this system, these data represent the yield of each variable 
Yield of individual species in mixtures, plot-level data, multitrophic

time-averaged value of each variable measured monthly in each plot over the course of the 10 month experiment. 

For complete methodology, see the corresponding article named above or `Ramus AP, Long ZT (2016) Producer diversity enhances consumer stability in a benthic marine community. *Journal of Ecology* 104:572-579. https://doi.org/10.1111/1365-2745.12509`. 

In brief: The experiment was carried out adjacent to the rock revetment located within Zeke’s Island National Estuarine Research Reserve ([33.95, -77.94] https://goo.gl/maps/T1XRRBfyCFSUjCWC8) in North Carolina, USA.

 We manipulated macroalgal identity and richness in seven treatments 
 
These data represent the yields of individual macroalgal species in treatment plots 
Measured weekly in each treatment block (plot) 
Both the individual species component 
Plot-level sum
Of a 12 week experiment conducted in situ along 
2012-06-14 to 2012-09-06

A brief description of each variable is given below. 

Field | Variable | Description 
--- | --- | --- 
1 | Data | Distinguishes whether sample is plot-level ‘sum’ of its component ‘parts’ in mixtures (used for subsetting)
2 | Species | Macroalgal species ‘sown’ in treatment | Abbreviated names Codium fragile, 
3 | ProBiomassInitial | Initial starting wet mass of macroalgae sown 
4 | Deployed | Date component was deployed
5 | Sampled | Date compenent was sampled
6 |Quadrant | The quadrant (1-4) sampled within each block
7 |Week | Experimental duration in weeks (1-12)
8 |Block | Block identification number (1-35)
9 |Location | Location of block (1-35) within a randomized line, with 1 being the farthest South
10 |ProDivTrtType | Producer diversity treatment type (Mono or Poly)
11 |ProDivTrtRich | Producer diversity treatment richness, the number of producer species (1, 3, or 4)
12 |ProDivTrtID | Producer diversity treatment identifier (Cf, Gt, Gv, Gg, NM, IM, or CM)
13 | CfBiomass | Wet biomass of *Codium fragile* in grams
14 | GtBiomass | Wet biomass of *Gracilaria tikvahiae* in grams
15 | GvBiomass | Wet biomass of *Gracilaria vermiculophylla* in grams
16 | GgBiomass | Wet biomass of *Gymnogongrus griffithsiae* in grams
17 | ProBiomass | Total wet biomass of macroalgae in grams (sum of fields 10-13)
18 | Amphipods | Abundance of gammaridean amphipod crustaceans
19 | Bivalves | Abundance of bivalve molluscs
20 | Caprellids | Abundance of caprellid amphipod crustaceans
21 | Gastropods | Abundance of gastropod molluscs
22 | Isopods | Abundance of isopod crustaceans
23 | Megalopae | Abundance of decapod crustacean megalopae
24 | NonXanthids | Abundance of crab-like decapod crustaceans not belonging to the Xanthidae
25 | Polychaetes | Abundance of polychaete annelids
26 | Pycnogonids | Abundance of pycnogonid pantopod crustaceans
27 | Shrimps | Abundance of palaemonid and penaeid decapod crustaceans
28 | Xanthids | Abundance of xanthid decapod crustaceans
29 | Others | Abundance of ‘other’ heterotrophs that either were unidentifiable or did not belong to any of the aforementioned taxonomic groups (fields 15-25)
30 | ConAbund | Consumer abundance, the total number of individual consumers (sum of fields 15-26)
31 |ConBiomass | Consumer biomass, the total dry mass of consumers in grams
32 |ConDivRich | Consumer richness, the total number of unique consumer taxa present in fields 15-26


## `2 supplementary code.R `

Code to replicate the primary analysis of ecosystem multifunctionality as presented in Ramus et al. (2017) PNAS. This code calculates multifunctionaity, fits candidate models using nonlinear least squares for each function individually, and generates the model selection table and corresponding figure presented in the paper.

Here we focus on our most resolved data from the final 12 weeks of the experiment. Following the partition of Loreau & Hector (2001) *Nature*.


## `3 nlsTab.R `

Code to generate a model selection table for fitted nls models. This code works as a 'manual loop' for lack of a better description. Much of it is dedicated to combining and reorganizing information, although there are a few calculations.


## `4 model selection table.csv`

Model selection table of fitted nls models generated by the code.


## `5 figure.png`

Figure generated by the code. Corresponds to Fig. 2 presented in the paper.

![5%20figure](5%20figure.png)


## Notes

The are a number of metrics that quantify the biodiversity-ecosystem funtioning and the most common the effect of biodiversity on plant productivity in terms of ‘relative yield’ – i.e. the ratio of species‐level productivity observed in a multi‐species mixture, relative to that in monoculture. Observed relative yield is then compared to a expected relative yield, in which the relative yield is proportional to the initial relative species abundance. Then, if the observed exceeds the expected, one can conclude that productivity per unit area is higher in mixtures than in average monocultures.

A major advantage of 'relative yield' related metrics is that one can partition them into different components and then use these components to summarize different characteristics of the relationship between biodiversity and ecosystem functioning (**Loreau & Hector, 2001, Isbell et al., 2018**). The most common used of these metrics, is the *Loreau and Hector partition* that groups deviations between observed and expected yield into two componentsthe *‘selection effect’* and the *‘complementarity effect’* (**Loreau & Hector, 2001**). In *selection effect*, the presence of highly productive species species is responsible for higher productivity with greater diversity (**Aarssen 1997, Gorssman et al. 2017**). In other words, the biodiversity-productive relationship emerge just because sample plots have highly productive species (irrespective of plot diversity), and that the most productive species had more chance (*to be sampled*) of being included in the more diverse plots than in the less diverse plots. In *complementary effect*, complementary interaction between species related to functional differences are driving the biodiversity-productivity relationship (**Loreau & Hector, 2001, Gorssman et al. 2017**). 

"Over the last two decades, empirical work has established that higher biodiversity can lead to greater primary productivity; however, the importance of different aspects of biodiversity in contributing to such relationships is rarely elucidated" (**Gorssman et al. 2017**).


