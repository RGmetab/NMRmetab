# A selection of statistical analyses in MetaboAnalyst

Authors: Marie Phelan & Eva Caamaño-Gutiérrez
Revision Date: 2 November 2017

## Part 1 Submitting Data

Open MetaboAnalyst at www.metaboanalyst.ca 

1. Click on “click here to start”
2. Upload data for Statistical Analysis
   1. Peak intensity table works for AMIX exported bucket tables
   2. Upload your file here in .csv format
   3. Submit- errors will appear if file is not correctly formatted **Edit the .csv file output from AMIX for correct upload to MetaboAnalyst.**

 Some of the editing needed to make the file compatible with MetaboAnalyst involves the incorporation of some key information for the analysis, for example:

- Open bucket file in spreadsheet software.
- Add a new column after the name of each spectrum (See example spreadsheet on Metaboanalyst). The first column (name) corresponds to the sample identity kept from the spectrometer. The second column (group) contains the key information for future grouping and testing.

3. Data check

   Once you have uploaded your file the data integrity check screen will appear. In this step you can decide how to deal with missing values if applicable. There is functionality to choose to ignore variables with over a percentage of samples missing or to use an algorithm to estimate those missing values. However, most of the data produced via the tools presented in this workshop will not require this step and we can click “skip”. 

4. Data filtering

   This functionality is paramount when trying to reduce dimensionality of the data for computational purposes (many variables=longer computational time) and to reduce unwanted variance, specially remove outliers. However, if you have less than 2000 variables/bucket/metabolites and you are unsure on how to filter your data, you can choose to not filter your data (“none).

5. Normalisation Options

   The aim of **normalisation** is to make <u>samples</u> comparable (for example to reduce variation due to dilution effects, ‘pipetters’ or ). Some examples include normalisation by an internal standard e.g. a metabolite that is at constant concentration between treatments or If looking at a time series for example we could also normalise all other samples by the time zero. Some data transformations also aid in some analyses. For example log transformation is usually helpful in biological data that which distribution is skewed towards positive values. Each dataset is different and requires its own evaluation.

   **Scaling** is a way of making the <u>variables</u> in the data more similar in range. If the variables are of different scale some linear analysis methods (like PCA) will tend to be influenced more by larger variables skewing the results. *Pareto* scaling is a popular choice in metabolomics studies and is available in MetaboAnalyst.

   

   When you have finished, click Submit to view the data normalisation (see Figure below). After the transformations the data is centred around zero and is of similar scale, with not variables overweighting by solely their nature instead of the effect the treatments have on them. It is ready for further analysis, press next

   

   Click **Submit** to view the data normalisation.

   

   After the transformations the data is centred around zero and is of similar scale. It is ready for further analysis. **Submit** 

   

   The data is now prepared for application of the numerous statistical tests available in MetaboAnalyst.

   

   Different tests are available depending on how many cohorts (GROUPS) you have. In this example there are more than Two cohorts, Thus multivariate tests such as ANOVA and available and twofold tests such as T-Test and Fold Changes are not.

   

   ## Part 2 Statistical Analysis

   

   You can now explore the statistical tests MetaboAnalyst offers. Different tests are available depending on how many cohorts (CLASS/GROUP) you have. We have >2 cohorts, so multivariate tests such as ANOVA are available but not tests for only two variables such as t-test.

   

   ## Part 2a Statistical Analysis – ANOVA

   1. Choose parameters & explore data

      1. Choose a p-value threshold 
      2. Choose post hoc analysis technique (method to do cohort comparisons on significant points (both Fisher and Tukey) and correct for false positives (Tukey)). 
      3. Red data points are significantly different 
      4. Dotted line represents the p-value cut-off 
      5. Blue data points are not significantly different 
      6. Click on each data point to get a box plot showing the different in intensity of the peak at that ppm between the samples. 
      7. Clicking on the table shows the post-hoc table (see next page)
      8. Click on the paint palette to download images

   2. Post-hoc tables are available from the ANOVA

      The Table only reports those buckets that are significantly different between cohorts, in the post-hoc tests section it can be seen between which cohorts the bucket is significantly different.

      

      Clicking on each of the buckets (1.914Lys, for example) brings up a box plot of the differences of that bucket between cohorts.

      

      The table is downloadable as well as the box plots.

      

   ## Part 2b Heat maps

   Heat maps are a very useful visualisation method. For a quick overview of how the groups are different between them in relation to the bucket signal.

   ## Part 2c Statistical Analysis – PCA

   To launch PCA analysis select PCA from side menu (red arrow)

   1) In the Overview you can visualise your data to five principle components (PC's) with a pairwise score plot for each PC against every other PC

   2) Scree plot - shows % explained variance both per PC and cumulatively

   3) 2D scores plot - shows scores for annotated samples (including 95% confidence elipsoid) for specified PCs

   4) 3D scores plot - shows moveable cube with 3 PCs plotted against each other. Hover mouse over each point to get specific sample information.

   5) Loadings plot - shows metabolite bucket weightings responsible for specified PCs. Hover the mouse over individual point to obtain specific bucket weighting. Click on specific point to see a boxplot representation.

   6) Biplot – combines sample score to most influential buckets.

      

   ## Part 2d Statistical Analysis – PLS-DA and OPLS-DA

   Partial Least Squares-Discriminant Analysis (PLS-DA) and Orthogonal Projections to Latent Structures (O-PLS) are supervised multivariate analyses. Similar to PCA the PLSDA algorithm can be launched by clicking the tab. The output will be akin to PCA’s but with some key differences. Main similarities are the score plots of the PLS components and the loadings. Similarly than with PCA, latent variables arise that provide new projections (scores) and to which the original variables have certain contribution (loadings).

   

   Because <u>over-fitting</u> is a very important issue, there are main methods to try to control it implemented in MetaboAnalyst. These provide statistical insight on how many variables to choose to create the model. The algorithm implemented within MetaboAnalyst should automatically select chosen the best fit for the data.

   

   1) <u>Cross Validation</u>

   In the cross-validation tab several parameters can be selected such as the performance measure. The optimal is set to Q<sup>2</sup> , which is the cross-validated sum of squares captured by the model.

   

   Another method to control over fitting is permutation test. These rely on assessing how likely is to get the separation obtained by the model randomly. For that purpose, the labels (groups/cohorts) are randomised/unordered and the model is made again. With random labels, no significant differences should be found between groups. This process is repeated iteratively 100, 1000 or 2000 times (in MetaboAnalyst) and allows deriving the probability of separating the original groups just by chance. A low p value indicates that the chances for the grouping to be random are low. 

   

   2) <u>Importance Features</u>

   In the tab “Imp. Features”, there are two variable importance measures in PLS-DA, that can be downloaded by pressing on the little sheet icon.

   

   The first, Variable Importance in Projection (VIP), is a weighted sum of squares of the PLS loadings taking into account the amount of explained Y-variation, in each dimension this can be interpreted as a measure of the contribution <u>or importance of a variable to the model</u>. Since VIP scores are calculated for each component when more than 1 component are used to calculate the feature importance the average of the VIP scores are used.

   

   The other importance measure is based on the weighted sum of PLS-regression. The weights are a function of the reduction of the sums of squares across the number of PLS components. The coefficient of each feature will be different depending on which group you want to predict. The average of the feature coefficients are used as the overall coefficient-based importance.

   

   3) <u>OPLS-DA</u> 
   
   The last feature that has been implemented in MetaboAnalyst is OPLS. Documentation is still limited but it is note worthy the visualisation improvement that might provide with respect to PLSDA (see below, groups separation is more obvious with only two dimensions).

## Part 3 Modifying and extracting the data

1. At any time the left hand menu allows modification of the dataset under investigation. Selecting upload, processing and normalisation will return to the corresponding process. Selecting Statistics opens a list of statistical analyses available in MetaboAnalyst for the particular dataset (dependent on number of groups etc.)

## Part 4 Download

In the Download section all or part of the analysis results can be downloaded.

Clicking on the Download.zip downloads everything in one zipped file. This is sometimes a good option as MetaboAnalyst will time out after a period of inactivity require re-inputting of the data.

Logging out ends your session and the data will no longer be available so make sure you have downloaded everything you need before you do this.

## More Information

Jianguo Xia & David S Wishart “Web-based inference of biological patterns, functions and pathways from metabolomic data using MetaboAnalyst” Nature Protocols 6, 743-760 (2011) doi:[10.1038/nprot.2011.319](https://doi.org/10.1038/nprot.2011.319)