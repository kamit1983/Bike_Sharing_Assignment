# Project Name
> A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profit.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to:

Which variables are significant in predicting the demand for shared bike
How well those variables describe the bike demands
Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors.


## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
### Business Goal
- Model the demand for shared bikes with the available independent variables
- Help Business understand how the demand varies with Features
- Business can manipulate stratagy to meet custimer demands

### Dataset
- Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors. 
=========================================
Dataset characteristics
=========================================	
day.csv have the following fields:
	
	- instant: record index
	- dteday : date
	- season : season (1:spring, 2:summer, 3:fall, 4:winter)
	- yr : year (0: 2018, 1:2019)
	- mnth : month ( 1 to 12)
	- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
	- weekday : day of the week
	- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
	+ weathersit : 
		- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
		- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
		- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
		- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
	- temp : temperature in Celsius
	- atemp: feeling temperature in Celsius
	- hum: humidity
	- windspeed: wind speed
	- casual: count of casual users
	- registered: count of registered users
	- cnt: count of total rental bikes including both casual and registered
	
=========================================
License
=========================================
Use of this dataset in publications must be cited to the following publication:

[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
	year={2013},
	issn={2192-6352},
	journal={Progress in Artificial Intelligence},
	doi={10.1007/s13748-013-0040-3},
	title={Event labeling combining ensemble detectors and background knowledge},
	url={http://dx.doi.org/10.1007/s13748-013-0040-3},
	publisher={Springer Berlin Heidelberg},
	keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
	author={Fanaee-T, Hadi and Gama, Joao},
	pages={1-15}
}

=========================================
Contact
=========================================
	
For further information about this dataset please contact Hadi Fanaee-T (hadi.fanaee@fe.up.pt)

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Conclusions
### Model Summary Overview
### R-squared: 0.824
- This indicates that 82.4% of the variance in bike demand is explained by the variables in your model.
Adjusted R-squared: 0.820
This is a slight reduction from the R-squared value, accounting for the number of predictors. It still suggests a good fit, with 82% of the variance explained.
### F-statistic: 233.3 (p-value: 5.71e-181)
- This very high F-statistic and an extremely low p-value imply that your overall model is statistically significant.
### Durbin-Watson statistic: 2.044
- This value close to 2 indicates that there is likely no autocorrelation in the residuals, suggesting that the model's errors are independent.

### Key Insights from the Significant Variables
- Year (yr):
    - A positive coefficient (0.2326) indicates that bike demand has significantly increased in the second year.
- Temperature (temp):
    - The strong positive coefficient (0.5029) suggests that warmer temperatures drive higher bike usage.
- Weather Conditions:
    - Light Snow or Rain has a significant negative effect on bike demand, with a large negative coefficient (-0.2989).
    - Mist or Cloudy weather also has a negative impact (-0.0785).
- Seasonal Effects:
    - Spring shows a decrease in demand (-0.0766), while winter has an increase (0.0829).
    - July has a slight negative impact, while September shows a positive effect on demand.
- Holidays:
    - The coefficient for holiday is negative (-0.1003), indicating that demand drops on holidays.Key Insights from the Significant Variables


### Interpreting the Coefficients

| **Variable**        | **Coefficient** | **Std Err** | **t-value** | **p-value** | **95% Confidence Interval** | **Interpretation** |
|---------------------|-----------------|--------------|-------------|-------------|----------------------------|---------------------|
| **const**           | 0.1501         | 0.029        | 5.124       | 0.000       | [0.093, 0.208]             | The intercept. |
| **yr**              | 0.2326         | 0.009        | 27.333      | 0.000       | [0.216, 0.249]             | **Highly significant**. Positive impact on bike demand. |
| **holiday**         | -0.1003        | 0.027        | -3.721      | 0.000       | [-0.153, -0.047]           | **Significant**. Holidays reduce bike demand. |
| **temp**            | 0.5029         | 0.034        | 14.670      | 0.000       | [0.436, 0.570]             | **Highly significant**. Warmer temperatures increase bike demand. |
| **Jul**             | -0.0523        | 0.019        | -2.715      | 0.007       | [-0.090, -0.014]           | **Significant**. Bike demand decreases in July. |
| **Sep**             | 0.0812         | 0.018        | 4.623       | 0.000       | [0.047, 0.116]             | **Significant**. Bike demand increases in September. |
| **spring**          | -0.0766        | 0.022        | -3.514      | 0.000       | [-0.119, -0.034]           | **Significant**. Lower bike demand in spring. |
| **summer**          | 0.0367         | 0.016        | 2.342       | 0.020       | [0.006, 0.067]             | **Significant**. Slight increase in summer demand. |
| **winter**          | 0.0829         | 0.018        | 4.642       | 0.000       | [0.048, 0.118]             | **Significant**. Higher bike demand in winter. |
| **Light_Snow_Rain** | -0.2989        | 0.025        | -11.756     | 0.000       | [-0.349, -0.249]           | **Highly significant**. Bad weather (snow/rain) decreases bike demand. |
| **Mist_Cloudy**     | -0.0785        | 0.009        | -8.669      | 0.000       | [-0.096, -0.061]           | **Highly significant**. Mist/cloudy weather reduces demand. |

<!-- You don't have to answer all the questions - just the ones relevant to your project. -->


## Technologies Used

- **Python**: The primary programming language used for data analysis and model development.
- **Pandas (version 1.3.3)**: For data manipulation and preparation, including handling missing values, feature engineering, and transforming the dataset.
- **NumPy (version 1.21.2)**: For numerical computations, used primarily for array operations and statistical calculations.
- **Matplotlib (version 3.4.3)**: For data visualization, used to create plots such as histograms, boxplots, and bar charts.
- **Seaborn (version 0.11.2)**: High-level visualization library based on Matplotlib, used for statistical graphics like heatmaps and count plots.
- **Jupyter Notebook**: For writing and organizing the code, visualizations, and documentation interactively.

These technologies helped efficiently process, visualize, and analyze the data, providing key insights into loan default patterns.

<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements

- This project was inspired byA **US bike-sharing provider BoomBikes** has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic.
- Special thanks to the **UpGrad Data Science Program** for providing the framework and guidance for this project.
- References: 

## Contact
Created by [@kamit1983] - feel free to contact me!
