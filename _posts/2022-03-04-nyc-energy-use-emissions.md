---
layout: post
title:  Reducing Carbon Emissions of NYC's Large Buildings
---
## Abstract

The goal of this project was to perform an initial analysis of energy use in NYC in order to reduce carbon emissions (or greenhouse gas emissions) and potentially help the city reach its goal of net-zero greenhouse gas emissions by 2050.

## Design

The hypothetical client for this project would be the city of New York, [which has pledged to achieve "carbon-neutrality" by 2050](http://onenyc.cityofnewyork.us/initiatives/achieve-carbon-neutrality-and-100-percent-clean-electricity/). In order to achieve this, the city would need to reduce their greenhouse gas emissions as much as possible. By looking at current sources of emissions (primarily energy usage by large buildings), I hope to gather insights that could help the city figure out where and how to start tackling the problem of reducing their carbon emissions.

## Data

The main datasets for this project are the [2019](https://data.cityofnewyork.us/Environment/Energy-and-Water-Data-Disclosure-for-Local-Law-84-/wcm8-aq5w) and [2020](https://data.cityofnewyork.us/Environment/Energy-and-Water-Data-Disclosure-for-Local-Law-84-/usc3-8zwd) Energy and Water Data Disclosures for Local Law 84 (via NYC Open Data). These datasets include data (mostly self-reported) from privately owned buildings over 25,000 square feet and city owned buildings over 10,000 square feet.

I chose to focus on large buildings also in part because **[66-](http://onenyc.cityofnewyork.us/initiatives/achieve-carbon-neutrality-and-100-percent-clean-electricity/)[70](https://nyc-ghg-inventory.cusp.nyu.edu/)%** of NYC’s carbon emissions come from buildings (as opposed to transportation or waste).

## Algorithms

An initial analysis of the datasets led to the following insights and recommendations:

1. **Most of NYC's energy usage comes from natural gas.** For the city to reduce its carbon emissions, it must decrease its reliance on gas and oil and increase use of electricity generated onsite from renewable sources, which currently comprise only a small fraction of the city's total energy usage.
![Screen Shot 2022-03-07 at 10 24 17 PM](https://user-images.githubusercontent.com/81931093/157160346-f22bb061-708f-4c58-8bf7-db9056cb1abb.png)

2. **Residential properties have the highest total energy usage of any property type.** The city might focus on reducing energy usage at residential properties, perhaps by upgrading old buildings.
![Screen Shot 2022-03-07 at 10 26 28 PM](https://user-images.githubusercontent.com/81931093/157160438-5f0ad578-5228-4bf6-b57d-09e5b8b3078a.png)

3. **Much energy is lost from source to site.** The large difference between the total Site [Energy Use Intensity](https://www.energystar.gov/buildings/benchmark/understand_metrics/what_eui) and Source Energy Use Intensity points to energy being lost in the transfer from its source ([likely upstate NY](http://onenyc.cityofnewyork.us/initiatives/achieve-carbon-neutrality-and-100-percent-clean-electricity/)) to its site in NYC. Increased efficiency in energy transportation and/or the creation of more local sources of energy would help reduce the energy loss.
![Screen Shot 2022-03-07 at 10 28 36 PM](https://user-images.githubusercontent.com/81931093/157160632-28afdbc1-ea94-487e-9a10-98048bb78a98.png)

4. **"Clean" energy still generates carbon emissions.** There was a substantial decrease in emissions and energy usage from 2019 to 2020, possibly due to reduced energy usage as a result of COVID-19. In order to significantly reduce its greenhouse gas emissions, the city must cut down its overall energy consumption.

Although no machine learning algorithms were employed in this project, future work could include time series modeling to analyze changes in emissions over time or linear regression to see which features of a building might correlate with higher emissions. Future work could reveal more specific insights, which could be used for more specific policy recommendations.

## Tools

- Google Sheets for exploration and data cleaning, some visualizations
- Python/Pandas to fill in some missing Latitude/Longitude values using Google Maps API
- Tableau for visualization

## Communication

A .pdf of the Google Slides presentation can be found [here on GitHub](https://github.com/amitian/NYC-Energy-Use-Emissions).

The Tableau workbook can be found [here](https://public.tableau.com/views/NYCCarbonEmissionsofLargeBuildings/2019Map?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link).
