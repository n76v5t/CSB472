java c
CSB472
Phylogenetics Tutorial
In this   phylogenetics tutorial, you will:
.          Gain experience with   multiple   phylogenetic   methods.
.          Investigate how the   different   MSA   approaches   and   parameters   influence   the   inferred   evolutionary histories.
.          Investigate how   using   an   evolutionary   substitution   model   influences the   inferred   history   vs.   no   evolutionary model.
.          Investigate how   phylogenetic trees   produced from   aligned   DNA   sequences   differ from   those   produced from aligned   protein sequences.
We will   be   using   MEGA11 for this   lab,   but there are   many other phylogenetics tools available. As   a reminder, you can access   MEGA from https://www.megasoftware.net/. Note   that   there   are   some   notable changes to the tree viewer in   MEGA11   relative to earlier   versions.   I   have   also   listed   a   number   of alternative tools in Appendix   3.
Important - the quiz   is different for this   lab. You will   be asked to   upload   a   short   summary   of your   analysis   results. This   is explained at the end of the lab   and   on   the   class website.
CASE   1:   Exploring the   Impact of Alignment   Parameters
Biological   Plausibility vs.   Phylogenetic Support and the   Impact of Alignment   Methods    Parameters
Let's first look at the   impact of using a   codon-based   alignment   approach when   aligning   coding sequencing.   Recall, when you align a coding sequence you can   either   align the   DNA   sequence   directly,   or you can translate the   DNA to the corresponding   protein sequence,   perform. the   amino   acid-based   alignment, and then   back-translate the alignment to the   DNA sequence.   Doing this   imposes   a   degree of   biological   plausibility since   insertions and deletions that change the coding   sequence will   almost   always   result   in a   premature stop codon (i.e., a   nonsense   mutation).   Since these   mutations   create   truncated   proteins, they should   be strongly selected against, and therefore,   rapidly   culled from   the   population   by   natural selection. Given this, we   prefer to   perform. codon-based alignments, when   possible,   but you need to   recognize that doing this imposes constraints on   where   gaps   can   be   inserted. Also,   I   need   to emphasize that this   is only appropriate when working with a coding sequence.   Let's   see   how   these constraints   impact our phylogenetic analysis. We will also examine   how   different   alignment   approaches   and   parameters   influence   phylogenetic   results.
We will   use a dataset of HopM1 type   III effector   proteins from   the   plant   pathogenic   bacterium   Pseudomonas syringae. As discussed   previously, type   III effectors are translocated directly from   the   bacterial cell to the   host cell via a type   III secretion   system.   They   have   evolved   in   order to   promote   bacterial fitness (virulence   in this context)   but can also trigger   the   host   immune   response   if the   host   has   the appropriate   immune   receptors.   I have   provided two alignments. You will   primarily work with
HopM1_clustal_10_0.1_codon.fas, while   most   of   the   analysis   for   HopM1_clustal      1      1.fas   will   be provided to you for comparison purposes.
1.       Quickly examine these alignments   in Jalview to get   an   overview.
2.       Open   HopM1_clustal_10_0.1_codon.fas   in   MEGA   for   phylogenetic   analysis. You   can   do   this using the file   menu or by drag-and-drop. You will   need to click   through   a   few   prompts:
.          Analyze   or   Align   File   = Analyze
.          Input   Data   Options   =   Nucleotide   Sequences
.          Protein-coding   nucleotide sequence   data   = Yes
.          Select   Genetic   Code   =   Standard
3.       Build   a   Neighbor-Joining   (NJ) tree.
.          Use   Phylogeny / Construct/Test   Neighbor-Joining Tree. You   may   be   asked   if you   want to use the   current data   file.   Select Yes.
.            Use the following analysis parameters
.   Test of Phylogeny =   Bootstrap   method
.   No. of   Bootstrap   Replications   =   100
o   Normally   I   would   use   500 or   1000   bootstrap   replicates,   but   you   can   use
100 for   the   lab   to   speed   things   up.
.   Substitution   Model = Maximum Composite   Likelihood
o   If you are doing a   protein analysis,   I suggest you   use Jones-Taylor-   Thornton.
.   Rates =   Uniform
.   Gaps/Missing   Data Treatment =   Pairwise deletion
4.         After you   build your tree, a Tree   Explorer window will automatically open. This window   provides   many options for manipulating and viewing your tree.   It   also   provides the   option   for   a   caption that   provides the details of how the tree was   built. The   information   presented   in this   caption   is   the type of information you will want to   present   in a   methods section   or figure   legend   if you publish your   results.   
5.       Try   using some of the tree   manipulation tools available through the   menus on   the   left   side   of the   window. These give you great flexibility is   how you view   and   present   your   tree.   For   example,   you   re-root your tree on a   specific   branch or midpoint   root   it. You   can   collapse   and   expand   nodes. You can change the size of the tree   and   the   fonts.
.          For example, show   only   bootstrap values   greater than   or   equal   to   70
.   Statistics/Frequency/Info
.   Frequency
.   Hide   Values   Lower   Than   =   70
.          If you want to   rescale your tree   to   better fit   in   the window
.   Layout
.   Auto-size Tree
.            If you want to   root the tree on a   specific   branch
.   Subtree
.   Root Tree
.   Use your mouse to click on the   branch   and   position   you   want   to   be   the   new   root
.          To   midpoint   root   your   tree
.   Layout
.   Root on   Midpoint
.          Change the   layout of the tree   to   circular   or   radial format
.   Layout
.   Tree Style
.   Circle or   Radiation
6.       Save the tree for later comparison. You can   use the   File   menu   to   save   an   analysis   session,
which will allow you to go directly back   to where   you   are   now,   or you   can   export   the   tree   in   Newick format. There are also   many other output formats that you   might find   useful   for   specific   analyses.   Finally, you can save the tree   image   in different formats through the   Image   menu. For this   lab   I suggest you   Image / Copy to Clipboard and   paste   into   a Word   document   so   you   can compare trees from different analyses.   Don’t forget to   record   notes on   how you   generated      the alignment and   tree.
Impact of Substitution   Model
We will examine the   impact of the substitution model   and   then   use   some   tools   to   identify   the   best model.   Remember that substitution models are   meant to correct for   both   biases   in   the   substitution patterns as well as   mutational saturation. You can find out   more   about the   substitution   models   through MEGA   help. Wikipedia also   has a   nice summary of the different   models:
https://en.wikipedia.org/wiki/Models      of    DNA_evolution
7.       Generate the   nucleotide substitution matrix used for a   particular   evolutionary   model.
.          Use   HopM1_clustal_10_0.1.fas
.          Models /   Estimate   Substitution   Matrix   (ML).
.            Model/Method = Jukes-Cantor
.          Leave   all   other   parameters   to   their   defaults.
8.       Compare the   nucleotide substitution matrix used for the   Jukes-Cantor   model vs.   the   Tamura   3-   parameter model.
.          Perform. the same analysis   as   described   above  代 写CSB472 Phylogenetics TutorialMatlab
代做程序编程语言 but   select   Tamura   3-Paramter.   Note   that the   results window should stay open from prior analyses   so   it   is   easy   to   compare   results.
.          The   matrix shows the   pairwise   probability of substitution.   Pay particular   attention   to   the   legend   below the table, which gives important   information, such as the   observed nucleotide frequencies for your data.
.          Note, the example substitution   matrices   shown   below were   generated from   the   HopM1_clustal_1_1.fas   dataset.
9.       Compare   HopM1_clustal_10_0.1.fas   Neighbor-Joining   trees   derived   using   different substitution models.
.          Use   parameters as   before,   except   modify the   Model/Method
.          Compare the   Maximum Composite   Likelihood to Jukes-Cantor to   p-distance
.          Look at the scale   of the tree   and   the   total   branch   length   (found   in   the   legend).
10. Determine the   best evolutionary   model.   MEGA   provides a means to   identify   the   best
evolutionary   model   based on a   maximum   likelihood analysis of the data. This   is a   very   useful   tool and   I   recommend   using   it for selecting the   best   model.
.          Calculate the   best   model via   Models /   Find   Best   DNA/Protein   Models (ML)
.          Examine the   NOTE at the   bottom   of the table.   There   is   a   lot   of   information   here,
including information about   how to   interpret the table and what   criteria   are   used to   select   the   best   model.
.          Note, the example   analysis   shown   below was   generated from   the   HopM1_clustal_1_1.fas   dataset.
Impact of Phylogenetic   Method
Now,   let’s examine   how   using different   phylogenetic   methods   impacts your results.
11. Compare   trees.
.          Compare   HopM1_clustal_10_0.1_codon.fas   trees   produced   by   Neighbor-Joining,   Maximum   Likelihood,   Parsimony, and   UPGMA.
.   I   have   provided   trees   for   the   latter   in   Appendix   1.
.   The analysis   parameters   used for each tree are presented   in the figure   legends.
.   Note   1,   I   reduced   the   number   of   bootstrap   replicates   to   20 simply   to   speed   up   the analysis.   In   reality,   I   would   never   use   less   than   100, and   500 or   1000 would   be strongly   preferred.
.   Note   2,   I   only   show   bootstrap   scores   greater   than   50   in   each   tree.   When
comparing the trees,   pay   particular attention to the clade structure of the tree   and   the   bootstrap support for the   nodes.
.          Compare   HopM1_clustal_10_0.1_codon.fas   trees   to   HopM1_clustal_1_1.fas   trees.
.   I   have   provided trees for the latter in Appendix   2.
.   Everything else   mentioned above applies   here as well.
CASE 2: Species Trees, Gene Trees, and   Domain   Trees
Let's   integrate the skills you   have   learned over the   past few weeks. The goal will   be to   compare   phylogenies produced at three different levels: species,   full   gene,   and   conserved   domain.
The species   phylogeny we will   use   is the   internal transcribed spacer sequence   ITS-1.   ITS-1 sits   between   the   18S   and   5.8S   rRNA   genes   and   is   a   commonly   used   molecular   marker   to   identify   species.   The gene tree will   be created from the coding sequence of   a   gene   encoding   a   receptor-like   kinase   (RLK). The domain tree will   be   made from the   protein sequence of the conserved   kinase   domain   encoded   by each gene.
Species   Phylogeny
I   have   collected   ITS-1 sequences   (ITS1.fas) from   the   ITSoneDB   (http://itsonedb.cloud.ba.infn.it) for   the following species:
.          Arabidopsis thaliana
.            Raphanus sativus (radish)
.            Camelina sativa (camelina, or wild flax)
.            Nicotiana tabacum   (tobacco)
.            Solanum lycopersicum (tomato)
.            Phaseolus   vulgaris (bean)
.            Glycine max (soybean)
.            Citrus sinensis   (orange)
.            Zea mays   (corn)
1.         Align   the   ITS-1 sequences   from   each   of   these   species   (sequences   found   in   the   file   ITS1.fas)   using methods and   parameters that you feel will give you the   best   results
2.       Create a   bootstrapped   Neighbor-Joining   phylogenetic tree from the   ITS sequences.
Gene Tree
I   have   identified   homologs   of   the   A. thaliana   RLK   locus   NM_124768 encoding   the   PSKR2   protein   from these species above.   Note that   I   purposefully did   not   pick the top   BLAST   hits, so while these   are   all homologous sequences, many   may   not   be orthologs.
Accession
Species
NM_124768
Arabidopsis thaliana
XM_018635947
Raphanus sativus
XM_010417671
Camelina sativa
XM_016612518
Nicotiana tabacum
NM_001309251
Solanum lycopersicum
XM_007140778
Phaseolus   vulgaris
XM_006581242
Glycine max
XM_015530716
Citrus sinensis
XM_008654299
Zea mays
3.       Identify and download the coding sequences   of each   RLK   gene   from   NCBI.
4.         Align the   RLK coding sequences using   methods and   parameters that you feel   will   give   you   the   best   results.
5.       Create a   bootstrapped   Neighbor-Joining   phylogenetic tree of the   RLK genes.
Domain Tree
6.       Identify the conserved kinase domain   from   the A.   thaliana   PSKR2   protein.   Remember that   even   if   the domain of interest   is   not   listed as a feature   in the   NCBI   accession, you   can   easily   find   conserved domains   using the   NCBI Conserved   Domain   Database as discussed   in step   20   of the   NCBI   lab. You can directly access this database from any   NCBI   accession   by   selecting   Identify   Conserved   Domains from the Analyze this sequence   menu on the   right side of the   page.   Don’t      forget that you   many   have to change the Conserved   Domain View from the default   Concise   Results to the   more complete Standard   Results.
7.       Based on the domain   information from the   PSKR2   protein   and your   MSA,   identify   the   homologous   kinase domains from the   protein   sequences of the eight other species.
8.       Extract   the   aligned   conserved   kinase   domain.
.          Try to figure out   how to block   off the   appropriate   region   in   Jalview.   Hint,   once   columns   are   hidden you can save the unhidden   alignment   to   a   new   file
9.       Realign   this   domain.
10. Create a   bootstrapped   Neighbor-Joining   phylogenetic tree.
Comparative Analysis
11. Finally, compare   the   ITS-1 species   tree, the   PSKR2 gene   tree,   and   the   PSKR2   kinase   domain   tree.   This comparison   is your   quiz.
Your quiz will   be a summary of the analysis results from   CASE   2:   Species   Trees,   Gene   Trees,   and   Domain   Trees.   Record   your   results   in   a   file   (Word   or   pdf)   and   upload   it   to   Lab   6   Quiz:
Phylogenetics   2.
Minimally, you should show the following:
.          The   phylogenetic   analyses:
o   ITS-1 species   tree
o   PSKR2 gene   tree
o   PSKR2   kinase domain tree
.          Summary   information on   how you   performed each analysis.   Enough   information   should   be   presented to recreate your work.   In addition to explaining the approach   and   choice   of
parameters for the   phylogenetic analysis, don't forget to explain your alignment and   model   selection.
.          Very short discussion / analysis of the similarities   and   differences   between these   trees   and   explanation.
.          Keep this report tightly focused   on what   analyses   you   did, why   you   selected   the   analyses   and   parameters, and a basic comparative   analysis   of the   results.
   


         
加QQ：99515681  WX：codinghelp
