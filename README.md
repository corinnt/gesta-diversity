# Work in progress: Diversity in Gesta

Gesta is a leading peer-reviewed academic journal in the area of medieval art.

Target functionality: Generate visualizations of trends in gender and region of origin of Gesta-published authors.

Current functionality: Maps the locations of institutions with which Gesta-published authors are affiliated.

Note: Script can be used to analyze other journals via commandline; Gesta is the motivating example and set as default. 

*example to generate maps of publications in Gesta starting in 1999:*
    
    python diversity.py your-email@gmail.com -v -m --start_year 1999

## Use Instructions

In terminal and from directory `gesta-diversity`

### 0. For first time set-up, build the conda environment to access the necessary packages:
<!--- Make code --->
     conda env create -f journal-diversity.yml

### 1. Activate the environment:
<!--- Make code --->
    conda activate journal-diversity

### 2. Run the program:

#### use in terminal:
<!--- Make code --->
    python diversity.py email [-h] [-v] [-n JOURNAL_NAME] [-i ID] [-c] [-m] [--start_year START_YEAR] [--end_year END_YEAR] 

#### positional arguments:
  `email`                   the reply-to email for OpenAlex API calls

#### options:

  `-h`, `--help`            show this help message and exit

  `-v`, `--verbose`         include to print progress messages

  `-c`, `--write_csv`       include to write csv of data

  `-m`, `--write_maps`      include to plot locations of affiliated institutions

  `-g`, `--predict_genders` include to predict genders of all authors and write to csv

  `--start_year START_YEAR` 
                            filter publications by this earliest year (inclusive)

  `--end_year END_YEAR`     filter publications by this latest year (inclusive)

  `-n JOURNAL_NAME`, `--journal_name JOURNAL_NAME`
                            name of journal or source to search for


Thank you to OpenAlex:

    Priem, J., Piwowar, H., & Orr, R. (2022). OpenAlex: A fully-open index of scholarly works, authors, venues, institutions, and concepts. ArXiv. https://arxiv.org/abs/2205.01833

And to PyGMT:

    Wessel, P., Luis, J. F., Uieda, L., Scharroo, R., Wobbe, F., Smith, W. H. F., & Tian, D. (2019). The Generic Mapping Tools version 6. Geochemistry, Geophysics, Geosystems, 20, 5556– 5564. https://doi.org/10.1029/2019GC008515

## To-Do

-  make protocol for what fields to query to get locations if they don't have the coordinates?
    ie get institution ID, else get institution name and country, else get author name and country and year?
- look into Genderize API to get gender stats
- swap print statements for progress bar


<!--- NOTES --->
<!---- issn_l = "0016-920X" --->
<!---- source_query = "https://api.openalex.org/sources/" + args.id --->