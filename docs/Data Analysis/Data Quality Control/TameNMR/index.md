# Tame NMR

Author: Computational Biology Facility
Revision Date: July 2017

Developed by the University of Liverpool Computational Biology Facility as an open source tool to analyse metabolomics data (clearly and reproducibly).

Dr Arturas Grauslys (funded by A Jones - TRDF) has built a server-based analytical platform in the Galaxy framework that supports tools employed by MS metabolomics and proteomics as part of the COSMOS consortium.

The tool aims to streamline and pipe multiple NMR metabolomics analytical modules that can then be used to reproduce analyses and visualise the data as it is manipulated. An alpha test is available within the university of Liverpool with plans to open up the server to www in Autumn 2017.

One particular feature that has been useful for curration of datasets for deposition is the ability to visualise the pattern file (i.e. the bucket boundaries and their annotations) overtop the spectra. The following instructions describe how this can be done using TameNMR. 



## Prepare NMR Spectra

In order to overlay the pattern with the spectra the spectra must be converted into a recognisable format. We can use AMIX to export the spectra as a matrix of numbers but we need the narrowest bucket width possible (essentially ppm per point) to see true resolution. An alternative approach would be to export 1Ds as jcamp however this would need to be done for each spectrum individually (no way to process as a batch unlike AMIX).

- Open topspin and load dataset 

- Check number of points in processed spectrum 

>  This can be found in Topspin under procPars tab SI e.g. 131072 

- Check the HzpPT

> Hertz per point – also under procPars tab e.g. 0.091699

- Divide that by field strength to get ppm per point 
> e.g. 0.091699/600.1299368=0.000153ppm per point


## Export Spectra as csv file
Follow general bucketing protocol for AMIX however set bucket width to per point value. 

- Launch AMIX and carry out bucketing procedure with the following options 
- Simple rectangular buckets
- No scaling
- Sum of intensities
- Set bucket widths to 0.000153 (or whatever value was calculated in 1.)
- Export bucket table as csv with:
- Tab separations
- Spectra in columns

## Upload csv spectra file to galaxy
Galaxy server can be accessed from anywhere within the University (or via VPN).

- Open galaxy in browser: [galaxy.liv.ac.uk](galaxy.liv.ac.uk)
- Go to Get Data (Left hand) 
  - Upload File (can drag and drop into upload window)
- Leave type as Auto-detect and click Start
- Wait for it to upload (this may take some time – worth carrying out analysis on SUBSET of spectra)

## Upload Patter file
### Upload the Bruker format pattern file
The pattern file is a Bruker formatted text file containing the bucket boundaries and their annotations for the dataset.

- Go to Get Data (Left hand) 
  - Upload File (can drag and drop into upload window)
- Leave type as Auto-detect and click Start
- Now convert data with Import data tab
  - Prepare pattern file
- Source – bruker pattern file
- Bruker pattern file - use pattern file
- Click execute

### Upload the bruker format pattern file
The Bruker formatted text file containing the bucket boundaries and their annotations can be converted into a 3 column (tab separated) csv file and thus used directly in Galaxy without import/conversion. The 3 columns must be left bound (in ppm), right bound (in ppm) and annotation.

## Plot the Overlay
Provided actions 2, 3 and 4 yielded no errors (red crosses on the right hand pane) the pattern and spectra may now be plotted in Galaxy. Be aware that the visualisation zoom is fixed therefore it is recommended to plot 1 to 2ppm ranges of spectra to be able to see the annotations effectively. Also the height of the spectra are auto-scaled to maximum peak in visualisation range (so avoid plotting water or large peaks when trying to observed peaks near the baseline. 

- Go to Plots 
  -  Plot NMR 
- NMR Spectra (the csv of your spectra prepared in 2.)
- Interval is the region to show 
  - plot bins
- Select bin table as in 4.
- Click Execute
- Wait (if using more than 20 spectra this could take some time)
- Click on eye icon once NMR Plot action (right hand panel) turns green

## Trouble-shooting

- If at any point the action panel on the right hand side has yellow actions these are in progress (need to wait for them to finish).
- Once finished any failed processes are indicated in red – processes typically fail because the data is incorrectly formatted – check input data for correct dimensions and number of columns!
