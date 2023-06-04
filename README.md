# Analysis scripts for Li, et. al.
[![DOI](https://zenodo.org/badge/318900139.svg)](https://zenodo.org/badge/latestdoi/318900139)

### Figure Legends
Microarray expression values were z-score scaled. Samples were clustered via calculating the Euclidean distance between centroids. See ([1](https://doi.org/10.1016/j.cmet.2019.11.002)) for raw data curation and ([2](https://github.com/j-berg/summers_2020)) for the associated analysis code for this manuscript. The data was originally generated as part of ([3](https://doi.org/10.1371/journal.pone.0013091)) and ([4](https://doi.org/10.1158/1541-7786.mcr-07-0267)) and can be accessed using the GEO identifiers [GSE20916](http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE20916) and [GSE8671](http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE8671) ([5](https://www.ncbi.nlm.nih.gov/geo/)).


### Methods
Microarray expression data were accessed and analyzed as described in ([1](https://doi.org/10.1016/j.cmet.2019.11.002)). Briefly, human microarray data were accessed from the GEO database [GSE20916](http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE20916) and [GSE8671](http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE8671) ([5](https://www.ncbi.nlm.nih.gov/geo/)) under the inclusion parameters of "normal" tissue and non-cancer "adenoma" tissue. Multimapping probes were dropped and probe sets mapping to the same gene were collapsed and averaged. Heatmaps were generated using XPRESSplot (v0.2.5) ([6](https://doi.org/10.1371/journal.pcbi.1007625)). GEO datasets were parsed using the GEOparse package (v2.0.3) ([https://pypi.org/project/GEOparse/](https://pypi.org/project/GEOparse/)). Gene set normalization was performed using scikit-learn (v1.2.2) (7). Benjamini-Hochberg (8) corrected p-values were calculated using SciPy (v1.10.1) (9) and statsmodels (v0.14.0) (10).

Statistics and figures related to processing the heatmaps and GEO database datasets were performed in Python. Data processing and analyses can be interactively replicated using Jupyter Notebook ([https://jupyter.org](https://jupyter.org)) at ([12](https://zenodo.org/record/4567545)).

### References
[1] Bensard CL, Wisidagama DR, Olson KA, Berg JA, Krah NM, Schell JC, Nowinski SM, Fogarty S, Bott AJ, Wei P, Dove KK, Tanner JM, Panic V, Cluntun A, Lettlova S, Earl CS, Namnath DF, Vázquez-Arreguín K, Villanueva CJ, Tantin D, Murtaugh LC, Evason KJ, Ducker GS, Thummel CS, Rutter J. Regulation of Tumor Initiation by the Mitochondrial Pyruvate Carrier. Cell Metab. 2020 Feb 4;31(2):284-300.e7. doi: 10.1016/j.cmet.2019.11.002.
[2] [https://github.com/j-berg/li_2021](https://github.com/j-berg/li_2021)
[3] [https://doi.org/10.1371/journal.pone.0013091](https://doi.org/10.1371/journal.pone.0013091)
[4] [https://doi.org/10.1158/1541-7786.mcr-07-0267](https://doi.org/10.1158/1541-7786.mcr-07-0267)
[5] [https://www.ncbi.nlm.nih.gov/geo/](https://www.ncbi.nlm.nih.gov/geo/)
[6] Berg JA, Belyeu JR, Morgan JT, Ouyang Y, Bott AJ, Quinlan AR, Gertz J, Rutter J. XPRESSyourself: Enhancing, standardizing, and automating ribosome profiling computational analyses yields improved insight into data. PLoS Comput Biol. 2020 Jan 31;16(1):e1007625. doi: 10.1371/journal.pcbi.1007625.
[7] Pedregosa, F., Varoquaux, G., Gramfort, A., Michel, V., Thirion, B., Grisel, O., Blondel, M., Prettenhofer, P., Weiss, R., Dubourg, V., Vanderplas, J., Passos, A., Cournapeau, D., Brucher, M., Perrot, M., Duchesnay, E. Scikit-learn: Machine Learning in Python (2011). Journal of Machine Learning Research, vol 12.
[8] Yoav Benjamini and Daniel Yekutieli. The Control of the False Discovery Rate in Multiple Testing under Dependency (2001). The Annals of Statistics, Vol. 29, No. 4. [https://www.jstor.org/stable/2674075](https://www.jstor.org/stable/2674075)
[9] Pauli Virtanen, Ralf Gommers, Travis E. Oliphant, Matt Haberland, Tyler Reddy, David Cournapeau, Evgeni Burovski, Pearu Peterson, Warren Weckesser, Jonathan Bright, Stéfan J. van der Walt, Matthew Brett, Joshua Wilson, K. Jarrod Millman, Nikolay Mayorov, Andrew R. J. Nelson, Eric Jones, Robert Kern, Eric Larson, CJ Carey, İlhan Polat, Yu Feng, Eric W. Moore, Jake VanderPlas, Denis Laxalde, Josef Perktold, Robert Cimrman, Ian Henriksen, E.A. Quintero, Charles R Harris, Anne M. Archibald, Antônio H. Ribeiro, Fabian Pedregosa, Paul van Mulbregt, and SciPy 1.0 Contributors. (2020) SciPy 1.0: Fundamental Algorithms for Scientific Computing in Python. Nature Methods, 17(3), 261-272.
[10] Seabold, Skipper, and Josef Perktold. “statsmodels: Econometric and statistical modeling with python.” Proceedings of the 9th Python in Science Conference. 2010.
[11] Cohen, Jacob (1988). Statistical Power Analysis for the Behavioral Sciences. Routledge. ISBN 978-1-134-74270-7.
[12] [https://doi.org/10.5281/zenodo.4567545](https://zenodo.org/record/4567545)

### To reproduce the analyses from these scripts:
The following example will show  how to install and run the analyses on a *nix OS.

1. Download [Conda](https://conda.io/projects/conda/en/latest/user-guide/install/index.html) and install.
2. Download [this repository](https://github.com/j-berg/li_2023/archive/main.zip).
3. Unzip the folder and navigate to the folder using the command line. For example, if you downloaded the zip file to your Desktop:
```bash
cd ~/Desktop/
unzip li_2023-main.zip
cd li_2023-main
```
4. Create a conda environment:
```bash
conda create -n li_analysis
conda activate li_analysis
conda install python jupyter
pip install -r requirements
git clone https://github.com/XPRESSyourself/XPRESSplot.git
cd XPRESSplot
python setup.py install
```

5. Launch Juypter Notebook (from within the `li_2023-main` directory):
```bash
jupyter notebook
```
