# sars2-mts-saliva-comp
"The Comparison Between Saliva and Mid-Turbinate Swabs in the Detection of COVID-19", Jianyu Lai, Jennifer German, Filbert Hong, S.-H. Sheldon Tai, Donald K. Milton, for the University of Maryland StopCOVID Research Group*

Overview:
Source data (participant demographics and symptoms, PCR data) are cleaned and merged in salivaswab_source_final.Rmd.
Resulting datasets are analyzed in figure and table scripts in data_analysis/scripts and outputted to data_analysis/output

The source data for these analyses come from the StopCOVID study, which are elaborated on at the public github https://phablab-umd.github.io/sars2-shedding/

## Source files:
1. ncovPCRtempsxresults1_210805.csv - PCR experiment information (merged with some clinical data: temp, sx) - version pulled on 8/5/2021
2. StopCOVIDsamples_210804.csv- LIMS sample information - version pulled on 8/4/2021
3. cov_pcr_sera_20210803.RDS - R object containing quantitative PCR data for shedding subjects but primarily used just for demographic data
(refer to previous github)

## Primary merging:

1. Script: source/salivaswab_source_final.Rmd  
Inputs: source/files as described above.
Outputs: data_analysis/data/demohist_salivaswab_1.RDS, data_analysis/pcr_screen_salivaswab_1.csv, data_analysis/qpcr_salivaswab_withimputes_1.csv
Notes: 

## Table and Figure scripts
All files are in data_analysis; all scripts are in data_analysis/scripts.

---
Script: figure_1_scatter_bland_altman_plot.Rmd
Inputs: data/pcr_screen_salivaswab_1.csv
Outputs: output/figure_1_scatter_bland_altman.png

Script: figure_2_plot_ct_probability_symptom_onset.Rmd
Inputs: data/pcr_screen_salivaswab_1.csv, data/demohist_salivaswab_1.RDS, data/qpcr_salivaswab_withimputes_1.csv
Outputs: output/figure_2_plot_ct_probability_symptom_onset.png

Script: figure_s1_ct_plot_by_sample_type.Rmd
Inputs: data/pcr_screen_salivaswab_1.csv
Outputs: output/figure_s1_ct_plot_by_sample_type.png

Script: table_1_table_s2_s4.Rmd
Inputs: data/pcr_screen_salivaswab_1.csv, data/demohist_salivaswab_1.RDS
Outputs: output/table_1_study_population.csv, output/table_1_comparison_values.csv, output/table_s2_numsamples.csv, output/table_s4_asympt_pos_participant.csv, output/text_febrile_cases.txt

Script: table_3_figure_s2.Rmd
Inputs: data/pcr_screen_salivaswab_1.csv, data/demohist_salivaswab_1.RDS
Outputs: output/figure_s2_samples_days_onset.png, output/table_3a_rel_odds_onset.csv

Script: viral_load_analysis.Rmd
Inputs: data/qpcr_salivaswab_withimputes_1.csv, data/demohist_salivaswab_1.RDS
Outputs: output/total_58_viral_gm_gsd.csv, output/tables2b_total_14_viral_gm_gsd.csv, output/total_13_viral_gm_gsd.csv, output/tables2c_positive_samples_14_viral_gm_gsd.csv, output/table_3b_viral_load_estimates.csv

