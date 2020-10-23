# covid-19-geographic-analysis

<img align="right" src="img/COVID-cases-by-outbreak-groupings.png" width='500' height='auto' ></img>

## Overview
This repo compared the geographic patterns in the COVID-19 epidemic in ths US to those of the HIV epidemic

## Goals

The goals of this project are:
> - To look for meaningful patterns in the geogrpahic progression of the COVID-19 pandemic as compared to the HIV epidemic
> - To work with various EDA and data visualization tools and techniques

## Tools and techniques used in this project
- **Tools**
> - Python, Jupyter Lab, SciKitLearn, Pandas, Numpy
- **Visualization**
> - Plotly, Matplotlib
- **Techniques**
> - Supervised learning model development, spatial mapping, simple moving average

## Data and EDA

For the HIV prevalence/COVID-19 incidence comparison, data on HIV and COVID infection rates were obtained from the following sources:
- https://github.com/nytimes/covid-19-data (COVID incidence by county data) 
- https://gis.cdc.gov/grasp/nchhstpatlas/main.html (HIV incidence/prevalence) 
- EDA of the HIV incidence rates (number of new infections in a given year) revealed a lot of missing data at the county level, and low numbers for many other counties. A decision was made to use prevalence as the comparative marker of the disease. Prevalence--while not perfect--is the most accurate measure of the penetration of the disease. The downsides are that it doesn't necessarily indicate where the disease was contracted since people are mobile. 
- For COVID, incidence is the only measure that makes sense since it is not a persistent illness. 
- Fortunately, HIV is much less common than COVID, so incidence numbers are smaller--even nonexistent (or at least not reported) in many counties. 
- Spatial maps and a scatter matrix were created to compare COVID incidence rates by county to HIV prevalence by county. The spatial maps appear to show commonality of the infection distributions, but the scatter matrix demonstrates that the regional strength of signal may not translate down to the county level. I.e. while the map suggests a strong geographic trend, the trend may not be as apparent at the county level. Perhaps there's too much point variation.
- It was hypothesized that this problem could be addressed by regionalizing the data by creating KNN Regressor predictions. 
<!-- - Maps can be accessed by clicking on the links below. -->
- HIV prevalence by county (active plotly maps aren't available for markdown)
<img align="right" src="img/hiv_prev_map.png" width='400' height='auto' ></img>

<pre>










</pre>  
- COVID incidence (as of July 31, 2020) by county
<img align="left" src="img/July_31_covid_map.png" width='400' height='auto' ></img>

<!-- - [HIV Prevalence Spatial Map]('img/hiv_prev_map.png')
- [COVID Incidence Spatial Map]('img/July_31_covid_map.png') -->
<pre>













</pre>
## Results
- KNN Regressor models were created to create an epidemic predictor from the covid data and separately for the hiv data. A KNN of 10 was used to 'regionalize' the hiv data and the covid data.
- These KNN prediction mappings appear to show a much stronger regional pattern. The R^2 for these maps is .65, suggesting a moderate correlation (see graph at top of page).
- Regionalized HIV prevalence
<img align="right" src="img/hiv_epidemic_prediction.png" width='400' height='auto' ></img>
<pre>










</pre>  
- Regionalized COVID incidence
<img align="left" src="img/covid_epidemic_prediction.png" width='400' height='auto' ></img>
<pre>












</pre>
<!-- - Prediction maps can be accessed by clicking on the links below. -->
<!-- <img align="right" src="img/hiv_prev_map.png" width='500' height='auto' ></img>
<img align="right" src="img/July_31_covid_map.png" width='500' height='auto' ></img> -->


<!-- - [HIV Prediction Map]('img/hiv_epidemic_prediction.html')
- [COVID Prediction Map]('img/covid_epidemic_prediction.html')
- [Scatter Matrix]('img/prediction-scatterplot.png') -->

## Contributors
[Rob Salvino](https://github.com/salvir1)


## License
[MIT ©](https://choosealicense.com/licenses/mit/)
