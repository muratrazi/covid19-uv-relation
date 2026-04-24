# covid19-uv-relation
**A Study on the Impact of Sunlight, Ultraviolet Radiation, and Temperature Variability on COVID-19 Mortality: Spatiotemporal Evidence from Small Countries and U.S. States and Territories**

**About the Project**
This repository contains the analysis code and datasets for an epidemiological study examining the relationship between COVID-19 mortality rates and environmental factors (UV index, ambient temperature, and sunlight duration). The core analysis utilizes a Distributed Lag Model (DLM) focusing on 7 to 21-day lag windows, controlling for socioeconomic and other environmental confounding variables.
You can access the related article via the following link.
https://www.mdpi.com/2673-8112/6/4/56

https://zenodo.org/records/19209481

**Repository Structure**
The repository is organized into three main components: data collection (Python), statistical analysis (MATLAB), and the raw datasets.
1. Main Analysis Scripts (MATLAB)
	•	MAIN_ANALYSIS.mlx: The backbone of the study.
	•	Standardizes environmental variables (UV, Temperature, Sunlight) using Z-scores.
	•	Fits a Fixed Effects model with a Poisson distribution, accounting for 7-21 day lags.
	•	Visualizes model fit, standardized effect sizes (via Forest Plots), and regional time-series reconstructions.
	•	Exports the final metrics and coefficients to Model_Standardized_7to21Lags.xlsx.
	•	REGION-SPECIFIC_ANALYSIS.mlx: Executes isolated, region-specific analyses for all countries and states included in the dataset to evaluate localized effects.
	•	diagnostics.mlx: Runs essential statistical assumption tests and model diagnostics for the Generalized Linear Models (GLM) after the main analysis is complete.
	•	summary.mlx: Generates descriptive statistics (Mean, Variance, Min, Max) for all raw inputs used in the study. Exports the results directly to a supplementary Excel file.
2. Data Retrieval and Preprocessing Scripts (Python)
These Jupyter Notebooks were used to download, clean, and format raw environmental and climate data from external sources (e.g., NASA) into the .xlsx formats required for the main analysis:
	•	PM25.ipynb
	•	sunshine.ipynb
	•	temp.ipynb
	•	UV.ipynb
	•	humidity.ipynb
3. Datasets
COVID-19 Mortality Data:
	•	owid-covid-data.csv: International daily cases and deaths (Our World in Data).
	•	us-states.csv: State-level mortality data for the United States.
Environmental & Climate Data (Daily Time Series):
	•	UV.xlsx, degrees.xlsx, sunshine.xlsx, humidity.xlsx, PM25.xlsx
Socioeconomic & Demographic Data (Static Confounders):
	•	diabetes.xlsx, Obesity_List.xlsx, AgerOver65.xlsx, Respiratory.xlsx, lifeexpectancy.xlsx, unemployment.xlsx
	•	population.xlsx, USA_States_Population.xlsx
How to Run
	0.	Prerequisites: You must have MATLAB installed, including the Statistics and Machine Learning Toolbox.
	0.	Working Directory: Ensure all .mlx scripts and .xlsx/.csv data files are placed in the same working directory.
	0.	Descriptive Statistics: Run summary.mlx first to generate an overview of the input data.
	0.	Main Analysis: Run MAIN_ANALYSIS.mlx from start to finish to fit the primary models, generate the core figures (Fig 1-5), and automate the Excel exports.
	0.	Diagnostics: Run diagnostics.mlx to validate the assumptions of the main models.
	0.	Regional Breakdown: Finally, execute REGION-SPECIFIC_ANALYSIS.mlx to isolate and examine the effects within specific countries or states.

 Owid data can be downloaded by the link below.
   https://ourworldindata.org/coronavirus

Author
Murat Razi
