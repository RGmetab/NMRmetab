# Pattern File Preparation Guide

Authors: Rudi Grosman & Marie Phelan
Revision Date: 1 November 2017

A pattern file can enhance the ease of analysis and identification of metabolites influencing statistical groupings. Pattern files form the basis for bucketing in AMIX enabling metabolite details to be encoded in the matrix of peak intensities taken forward for statistical analysis.

![PatternTable](.\Pattern_Table.jpg)

The format of the pattern file must be adhered to – any deviation may corrupt AMIX bucketing. Spaces and row information is critical for this Plain text document therefore it is recommended that the file is prepared using a text editor such as nedit, gedit or notepad in order to avoid undesired formatting.

## Header Section

The pattern file is made of two main sections; the header (lines 1-9, light grey) and the data (lines 10-20, dark grey).

The header must contain all the information required after the equal sign.

The ITEMS line must have the exact number of lines provided in the data section (lines 10-20) otherwise AMIX will accept the pattern file.

## Data Section

The data section contains left and right boundaries (in ppm) of the peaks and any annotations or identification for the peak.

First two columns must be left as 0.0000 and the following two columns should be the **left** and **right chemical shift positions** that define the peak.

> Shifts: Shifts (aka. Chemical shifts) are specific points on your spectrum which are
> measured in ppm (parts per million). These value can be identified interactively using TopSpin.
> Make sure that that you are reading this information in ppm and not in Hz (Hertz).

Template pattern files are available on VOCAL to ensure correct formatting.

The line has a specific outline:
	Each * represents a space character:
`**0.0000***0.0000**4.2554****4.2461****0*glyceryl backbone CH2-2`

The annotations must be unique, if not you won't be able to locate a specific peak during your
statistical analyses.

## Key Points

- Always use plain text.
- Never use a word processor (e.g MS Word, OpenOffice, etc).
- If prepared on Windows always check you file on linux text editor (e.g Nedit). Files prepared on Windows may introduce “<cr>” in your line. If this happens simply delete every <cr> and save the file before you proceed.