# permanent-transitory-decomposition-replication
## Replication package for "Permanent-Transitory decomposition of cointegrated time series via Dynamic Factor Models" by Chiara Casoli and Riccardo Lucchetti (The Econometrics Journal, 2022).


This repository contains the material to replicate the Monte Carlo experiments and the empirical application described in the article. All scripts are written in gretl and require version 2021a or later.
Directory Structure

The replication material is organized into two main directories:
1. Sec3-MonteCarlo

Contains scripts to replicate the Monte Carlo experiment in Section 3:

    functions.inp: Functions used in the main script.

    main.inp: Runs individual Monte Carlo experiments and saves results as gretl data files.

    stats.inp: Generates result tables from the data files produced by main.inp.

    Required packages: DFM.gfn, extra.gfn.

2. Sec4-Commodities

Contains scripts and data for the empirical application in Section 4:

    commod_data.gdt / commod_data.csv: Dataset in gretl and csv formats.

    part1.inp: Performs cointegration analysis (reproduces Table 3).

    part2.inp: Performs Kasa decomposition and estimates the DFM.

    part3.inp: Robustness check comparing factor extraction techniques (EM vs PC).

    Required packages: DFM.gfn, staticfactor.gfn.

Data Availability and Provenance

The data used in Section 4 are publicly available from the following sources:

    Commodity Prices: IMF Primary commodity prices database.

    Consumer Price Index (CPI): FRED, Federal Reserve Bank of St. Louis (used to deflate nominal prices).

Real prices were calculated with a basis of January 2000=100. The processed dataset is provided in both .csv and .gdt formats within the Sec4-Commodities folder.
Computational Requirements

    Software: gretl (last run with version 2021c).

    Hardware: Code was tested on a 2-core Intel-based laptop with Windows 10 Pro.

    Runtime:

        Empirical Analysis: A few minutes.

        Monte Carlo: Ranges from 2 to 25 minutes per experiment depending on the system size (n, T, B, r) and hardware.

Instructions to Replicators
Section 3: Monte Carlo

    Open main.inp and adjust the working directory.

    In the "simulation set up" section, select the parameters for the specific row of Table 1 or 2 you wish to replicate.

    Run the script to produce a .gdt file named after the DGP.

    Open stats.inp, ensure the correct file name is set in the open command.

    Set PRINT_FULL:

        0: Produces only the specific row for Table 1 or 2.

        1: Produces full output including mean, standard deviation, and median for Online Supplement tables.

Section 4: Commodities

    Table 3: Run part1.inp.


    Kasa Decomposition: Run part2.inp.

        Note: Set TO_DISPLAY = 1 on line 5 to see graphs on screen; otherwise, they are saved as EPS files.

    Robustness Check: Run part3.inp to generate comparison plots between EM and PC techniques.

## DOI

This replication package is archived at Zenodo:

[10.5281/zenodo.18592832](https://doi.org/10.5281/zenodo.18592832)
