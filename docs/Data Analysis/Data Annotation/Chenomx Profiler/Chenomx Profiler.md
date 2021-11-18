# Chenomx Profiler Metabolite Identification - Quick Guide

Author: Rudi Grosman & Marie Phenlan
Revision Date: 2 November 2017

Chenomx is a commercial software package for which we have two 'standard' licenses and one 'professional' license. Software may also be used as 'evaluation' which allows metabolite identification but you cannot save your results. All licensed versions enable saving and the professional version allows import and build of new molecules for the library. Book the appropriate hot-desk as required:

- METAB4 Chenomx Professional 
- METAB1 Chenomx Standard 
- METAB2 Chenomx Standard

Chenomx works ideally with spectra acquired at 25&deg;C and around 7.0 pH.

1) **Launch Chenomx** 

   Launch Chenomx from the desktop icon or the panel shortcut (select profiler if prompted):

   When launched Chenomx will ask for a licenses (on METAB3, TD, LNX7 and LNX6).

   Click on **Evaluate**.

   The software launches with a message offering the option to analyse a sample spectrum. Click on ‘No’. 

   

2) **Opening a spectrum in Chenomx** 

   On the menubar click on File and select Open to proceed to the open dialogue. NMR spectra (Bruker format) are saved in a file called “1r” which are typically located in a nested file directory structure (<span style="color:fuchsia">replace pink text with relevant information</span>): /home/<span style="color:fuchsia">[USER NAME]</span>/data/<span style="color:fuchsia">[DATA NAME]</span>/nmr/<span style="color:fuchsia">[EXPERIMENT NUMBER]</span>/pdata/1/1r and click ‘Open’. 

   

3) **Calibrate & Process spectra**

   An import screen will request sample details in order to calibrate the built-in metabolite library for analysis.

   ​	**Calibration:**

   ​		In most biofluids (not blood, SF or CSF) samples will have an internal standard (Chemical Shape Indicator (CSI) in Chenomx). The most common standard is TSP, but this may be different in certain cases. Refer to the sample preparation documents if unsure.

   ​		Once selected enter the final concentration of the standard TSP in the sample. This information will be used for identification and quantification of metabolites.

   ​		Uncheck the “Sample contains one or more pH Indicators” box and enter the sample pH value (7.4) followed by +/- value for adjustment. Metabolites will have shifted signals at different pHs - this information will calibrate the shifts of metabolites for analysis.

   ​	**Processing:**

   ​		In metabolomics the spectra is automatically processed immediately after acquisition therefore no extra processing *should* be required (leave this unchecked).

   Click **OK**.

   Chenomx will now load the selected spectrum for analysis.

   

4) **Spectrum Manipulation**

   ​	After the spectrum is loaded the analysis screen opens. Spectra can be scaled (y axis) up and down via scrolling mouse wheel down and up (respectively). Zoom in / out (x axis) via pressing shift + scrolling mouse wheel. 

   

5) **Tools for analysis**

   The left hand panel provides 5 tabs to aid with analysis:

   **Reference Card:** Reference cards give information and links on selected metabolites.

   **Compound Sets:** Chenomx allows the use of in-house metabolite libraries, from this tab an in-house library may be selected (if available).

   **Spectrum Details:** Displays details of current spectrum (instrument, field strength, experiments, etc.).

   **Legend:** Provides control to work on layers of spectra, as well as to create digital spectrum via summing or subtracting spectrum digitally.

   **Files:** File browser to swap between spectrum quickly.

   

6) **Manual Metabolite analysis**

   To start analysis, select a metabolite from the compound list. When selected, the compound spectrum will be overlaid in blue on your sample spectrum.

   

   Dashed blue lines shows the shifts of the peaks for the selected metabolite. On the upper left corner right under the compound name. All peaks of the compound are listed and when clicked it will automatically zoom in to that region allowing finer adjustments for your analysis.

   

7) **Automated Metabolite Analysis**

   

   What makes Chenomx a faster streamlined metabolite identifier is the feature that automatically fits multiple compounds via recreating your spectrum with the built-in library through a series of algorithms (this is why upon importing it is very important to provide the correct standard (as well as its concentration) and pH value).

   

   Select the entire range of metabolites listed below the spectrum panel by clicking on the panel and typing ctrl+A . Alternatively select a subset of metabolites using the mouse and shift key (individual metabolites can be added and taken out via control+click).

   

   Right click on your selection and click on “Fit Automatically”.

   

   After Chenomx finishes compound fitting, depending on the metabolites selected you will encounter two info messages.

   

   If metabolites were matched, Click **OK** and proceed to manual verification.

   

   If no compounds were matched click **OK** and either try another set of compounds or a different spectrum (the import options may require adjustment). 

   

8) **Automated Metabolite Analysis Appraisal**

   Matched compounds will now be shown in bold letters in the compound list and they will also be quantified. At this point metabolite fits should be appraised.

   

   The <span style="color:black">black </span> spectrum is your original spectrum.

   The <span style="color:red">red </span>spectrum is a digitally created spectrum from the fitted compounds.

   <span style="color:blue">Blue </span> arrows shows the peaks of the currently selected compound (you can switch to reference card tabs to obtain more information about your compounds).

   

   On the upper left corner just below the compound name in the spectrum window there is only one value “2.4” which show the corresponding peak of the compound. This value can appear in two conditions:

   - Green: The peak is fitted to the original spectrum.
   - Black: The peak might fit but requires fine tuning.

   

   NMR provides unique characteristic spectrum for each molecule although their location on a spectrum might change slightly depending on conditions (i.e temperature, pH, other compounds in the solution) the overall fingerprint is always the same. This is why when Chenomx flags a peak that is not green it you can adjust the intensity and shift within a certain margin of error. Click the peak in question then hold down left mouse button over the blue shaded area and drag the peak to change height and or shift.

   

   > For a molecule with multiple peaks the relative height volume is fixed therefore be mindful when adjusting one signal that **all** signals corresponding to that molecule will change.

    

9) **Peak Matching**

   When a compound is fitted but peaks are not matching, click on the peaks that are in black below the compound name.

   

   This will zoom in to that peak region where you can move the peak around with in the given margin.

   

   When you are out of range your peak indicator will turn red.

   

   When you fit the peak it will turn green.

   

   Some peaks may not turn green because they will under the other peaks or noise, that is why you need to verify each match given by chenomx.

   

   When you are done with your verification, select another metabolite and you will be seeing its projection on your spectrum. Here you can clearly see that NADP+ is in the spectrum but all peaks appear to be black.

   

   After adjustment even though all the peaks are not green the fit is clear and the metabolite is identified. 





