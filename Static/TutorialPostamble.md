

# Customise the tutorial and explore your own data

Final thoughts; behind this **`Rmarkdown`** file is a modest amount of **`R code`** - please explore the **`Rmarkdown`** template; modify it, and run with your own samples.

The **`Nanopore_SumStatQC_Tutorial.Rmd`** script contains the R code to perform the QC analysis. This Rmarkdown script will first import the **`config.yaml`** configuration file to load the appropriate sequence summary file. Please edit the **`config.yaml`** file to point to your own summary file. As a recommended best practice, place the summary file into the **`RawData`** folder within your project directory. The summary file may be compressed  (compress with either **`.gz`** or **`.bz2`**).

The **`config.yaml`** and **`Nanopore_SumStatQC_Tutorial.Rmd`** files can both be edited directly in Rstudio. The code below shows the command to open the configuration file with the **`Rstudio`** software.

```
rstudio config.yaml
```

The figure below shows a screenshot of the **`config.yaml`** file. Change the values in the fields **`inputFile`**, **`barcodeFile`**, and **`flowcellId`** to reflect the details of your own sequencing run. **`inputFile`** should correspond to the `sequencing_summary.txt` file from the basecaller. **`barcodeFile`** should contain the barcode assignments from the demultiplexing step - if you do not have a `barcodeFile` (your library was not multiplexed, or demultiplexing was performed using e.g. Albacore) then please leave this field blank.

Change the value of **`tutorialText`** to `FALSE` and the texts relating to the installation, configuration and customisation of the tutorial will be hidden.

If base-calling was performed in MinKNOW and you have hundreds of numbered sequencing_summary files, copy all files into your **`RawData`** folder and concatenate into a single file with the command

```
cat sequencing_summary_*.txt > merged_sequence_summary.txt
```

Use (for example) this `merged_sequence_summary.txt` filename for `inputFile` in your `config.yaml`.

![](Static/Images/sumstatEditParams.png)


To extract the whole set of **`R code`** from the **`Rmarkdown`**, use the **`purl`** command - this will extract the R code into its own file.

```
knitr::purl("Nanopore_cDNA_Tutorial.Rmd", quiet=TRUE)
```


\pagebreak



# References and citations

