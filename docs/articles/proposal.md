# BST260 Final Project Proposal

**To: BST260 Teaching Team, Fall 2026**

## Project overview

For my final project, I propose two analyses using public health
datasets encountered in BST260. The first will investigate the
association between body mass index (BMI) and systolic blood pressure
among adults in NHANES. The second will describe patterns in reported
waterborne disease outbreaks using the CDC dataset provided in the
course package.

These analyses will apply tools from BST260 for data cleaning,
descriptive statistics, visualization, and statistical modeling. I will
present the work in two separate vignettes within the `finalproject` R
package and publish the reports through a pkgdown website.

## Analysis 1: BMI and systolic blood pressure in NHANES

### Data source and provenance

I will use the `NHANES` dataset from the NHANES R package, which
contains an educational adaptation of data from the 2009–2010 and
2011–2012 National Health and Nutrition Examination Survey cycles.
NHANES is conducted by the National Center for Health Statistics and
combines interviews with physical examinations.

I will document the package version, original data source, variable
definitions, and steps used to construct the analysis sample. Because
this dataset has been adapted for educational purposes, I will interpret
the results as an exploratory classroom analysis rather than definitive
national estimates.

### Investigative objectives

My primary question is: How is BMI associated with average systolic
blood pressure among adults aged 20 years and older?

I will also examine whether the observed association changes after
accounting for age and sex. I expect higher BMI to be associated with
higher systolic blood pressure, but the analysis will evaluate the
pattern without assuming that the relationship is causal.

### Variables and analysis plan

The primary variables will be BMI, average systolic blood pressure
(`BPSysAve`), age, and the sex variable provided in the dataset.

I will first restrict the sample to adults aged 20 years and older and
summarize missingness in the selected variables. I will report the
number of participants included and excluded at each step.

Descriptive analyses will include means, standard deviations, medians,
and interquartile ranges for continuous variables, along with counts and
percentages for categorical variables. Histograms and boxplots will show
variable distributions, and a scatterplot with a smooth curve will
describe the relationship between BMI and systolic blood pressure.

I will fit a simple linear regression of systolic blood pressure on BMI,
followed by a model adjusting for age and sex. I will report estimated
differences in systolic blood pressure per five-unit increase in BMI.
Model diagnostics will assess linearity, unusual observations, and
residual patterns. Any uncertainty estimates will be interpreted in
light of the dataset’s educational resampling.

### Anticipated limitations

This is a cross-sectional analysis, so it cannot establish temporal
order or causation. Blood pressure may also be influenced by medication
use, diet, physical activity, and other factors not included in the
primary model. Missing data may affect the composition of the analysis
sample. A future extension would use original NHANES files and
appropriate survey methods to obtain population-level estimates.

## Analysis 2: Patterns in reported waterborne disease outbreaks

### Data source and provenance

I will use the CDC waterborne illness dataset distributed as
`waterborne` in the `finalproject` package. Before analysis, I will
review its documentation and original CDC source to establish the
reporting period, unit of observation, variable definitions, and
surveillance coverage.

I will document the dataset version, source URL, available years, and
all cleaning or aggregation steps. I will also check whether each row
represents an individual outbreak or an aggregated surveillance record
before calculating summaries.

### Investigative objectives

My primary question is: How do the number of reported waterborne disease
outbreaks and their associated illness burden vary over the available
reporting years?

A secondary question is whether outbreak frequency and illness burden
differ across reported etiologies or water exposure categories,
depending on the variables available.

### Variables and analysis plan

I will examine reporting year, outbreak counts, illness counts, and
available categories describing the cause or type of water exposure.

I will begin by reviewing variable types, missing values, duplicate
records, and category labels. I will distinguish missing or unknown
values from true zeros and identify potentially incomplete reporting
years.

I will summarize reported outbreaks and illnesses by year. If
outbreak-level illness counts are available, I will also describe the
distribution of outbreak size using the median, interquartile range, and
range.

Line plots will show annual patterns, while bar charts will compare
categories. I will distinguish categories that account for many reported
outbreaks from those associated with a large total number of illnesses.
These will be descriptive comparisons; I will not calculate population
incidence rates without appropriate denominators.

### Anticipated limitations

Surveillance data capture reported events and may miss outbreaks that
are not detected or reported. Differences across years or categories may
reflect surveillance practices, reporting delays, or diagnostic changes
as well as underlying disease patterns. Large outbreaks may dominate
total illness counts. Therefore, I will describe patterns in reported
outbreaks without interpreting them as direct measures of individual
risk.

A future extension could incorporate population or exposure denominators
and investigate changes in reporting completeness.

## Reproducibility and final deliverables

The final project will include two analysis vignettes, documented data
sources, reproducible R code, descriptive tables, figures, and
discussions of findings and limitations. I plan to use tidyverse tools
for data preparation and visualization and base R functions for
regression.

The public GitHub repository will contain a valid R package with the
required dependencies declared in `DESCRIPTION`. I will build and check
the pkgdown website so that both analysis reports are accessible through
GitHub Pages.
