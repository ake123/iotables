
<!-- README.md is generated from README.Rmd. Please edit that file -->
iotables <img src="man/figures/logo.png" align="right" height="205 width="205"/>
================================================================================

The symmetric input-output tables (SIOTs) are complex statistical products that present inter-related statistics in a predefined structure. They are often found in spreadsheets that follow this structure, or in the case Eurostat in a data repository. In both cases they in reproducible research must be downloaded and restructured to programmatically accessible form. Often these highly structured statistics need to be analyzed together with other data, for example, when employment effects and multipliers are calculated. In this case processing the employment data to SIOT conforming format is a significant preprocessing challenge.

The iotables are exactly designed for these tasks. Currently the package downloads and processes standardized European SIOTs conforming to the latest statistical regulations, i.e. SIOTs starting from the year 2010.

The aim of this introduction is not to introduce input-output economics, or SIOTs in detail. The [Eurostat Manual of Supply, Use and Input-Output Tables](http://ec.europa.eu/eurostat/documents/3859598/5902113/KS-RA-07-013-EN.PDF/b0b3d71e-3930-4442-94be-70b36cea9b39?version=1.0) and the [Eurostat tematic page](http://ec.europa.eu/eurostat/web/esa-supply-use-input-tables/methodology/symmetric-input-output-tables) \[Eurostat Manual\] in the documentation should be consulted for further information about the data and the metadata.

In order to test the analytical functions of the package and to have a manageable sized example data set, we use the real-life data from the Eurostat manual. The `germany_1990` dataset is a simplified 6x6 sized SIOT taken from the Eurostat SIOT manual (page 481). The package function examples can be checked against [publisehd results from Jörg Beutel](http://ec.europa.eu/eurostat/documents/3859598/5902113/KS-RA-07-013-EN.PDF/b0b3d71e-3930-4442-94be-70b36cea9b39?version=1.0). These calculations can be followed in the [Germany 1990 vignette](http://iotables.ceemid.eu/articles/germany_1990.html).

The calculation of induced effects (Type-II multipliers) are following the [Input-Output Multipliers Specification Sheet and Supporting Material, Spicosa Project Report](http://www.coastal-saf.eu/output-step/pdf/Specification%20sheet%20I_O_final.pdf). The analytical functions are tested against this example, too.

Installation
------------

You can install iotools from CRAN or the latest development version with github:

``` r
install.packages("iotables")
devtools::install_github("rOpenGov/iotables")

#with vignettes:
#devtools::install_github("rOpenGov/iotables", build_vignettes = TRUE)
```

You can follow changes on the NEWS.md file.

Acquiring data
--------------

Eurostat's data can be downloaded in several tidy, long-form, files, and a lot of filtering is needeed to start working with it.

Currently the following Eurostat SIOTs can be used:

-   product x product SIOTs `naio_10_cp1700` or `naio_10_pyp1700`;

-   industry x industry SIOTs `naio_10_cp1750` or`naio_10_pyp1750`;

-   use tables at basic prices `naio_10_cp1620` or `naio_10_pyp1610`;

-   trade and transport margins `naio_10_cp1620` or `naio_10_pyp1620`;

-   net taxes less subsidies `naio_10_cp1630` or `naio_10_pyp1630`;

-   Supply table at basic prices incl. transformation into purchasers' prices (naio\_10\_cp15) and Use table at purchasers' prices (naio\_10\_cp16).

The `cp` element refers to basic prices and the `pyp` to previous years' prices.

Vignettes
---------

Given the complexity of the data used by the package, probably the use of the vignettes is needed to get a start.

The [Germany 1990](http://iotables.ceemid.eu/articles/germany_1990.html) vignette presentes most of the examples of the [Eurostat Manual of Supply, Use and Input-Output Tables](http://ec.europa.eu/eurostat/documents/3859598/5902113/KS-RA-07-013-EN.PDF/b0b3d71e-3930-4442-94be-70b36cea9b39?version=1.0) (Eurostat Manual, Chapter 15.) This is a good introduction to understand what will the functions do, and to check that they work correctly. The `testthat` infrastructure of the package checks the proper working of the functions against the published results from the Eurostat Manual.

The [Working with Eurostat Data](http://iotables.ceemid.eu/articles/working_with_eurostat.html) vignette shows how you can download, pre-process and use real data from Eurostat.

The [United Kingdom Input-Output Analytical Tables 2010](https://webarchive.nationalarchives.gov.uk/20160114044923/http://www.ons.gov.uk/ons/rel/input-output/input-output-analytical-tables/2010/index.html) are used for testing the `iotables` package, because they are well-documented and detailed, organized data is available with them. These calculations can be followed in the [United Kingdom Input-Output Analyitcal Tables](http://iotables.ceemid.eu/articles/united_kingdom_2010.html) vignette.
