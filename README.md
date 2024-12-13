# Cell Tower Dataset Analysis

## Project Overview

This project involves the analysis of a large-scale cell tower dataset that contains over 46 million records of geographic coordinates and network information for cell tower locations across the globe. The dataset provides valuable insights into the distribution and coverage of cell towers by mobile network operators. The project includes data cleaning, data enrichment, and spatial analysis using various Python libraries.

You can View the `Folium Map` by opening the notebook in my kaggle code [Here](https://www.kaggle.com/code/zakariaeyoussefi/cell-tower-analysis)


I couldn't upload the csv files since the github limit file upload on 25MB, but you can find the dataset on my kaggle in [This Link](https://www.kaggle.com/datasets/zakariaeyoussefi/cell-towers-worldwide-location-data-by-continent)
## Libraries Used

- `polars`: Fast DataFrame library for data manipulation and analysis.
- `dask`: Parallel computing library for handling large datasets efficiently.
- `pandas`: Data manipulation and analysis library.
- `Folium`: Python library for creating interactive maps.
- `numpy`: Numerical operations and array handling.
- `matplotlib`: Visualization library for creating static plots.
- `seaborn`: Statistical data visualization library.
- `data cleaning`: General data cleaning techniques applied to the dataset.

## What I Learned

During this project, I gained hands-on experience with the following:

- **Data Cleaning and Enrichment**: I learned how to clean and preprocess large datasets by handling missing values, converting data formats, and enriching the data with external sources (e.g., mapping MCC and MNC codes to countries).
- **Handling Large Datasets**: Using `Dask` and `Polars`, I improved my ability to efficiently process and analyze large datasets that would otherwise be too memory-intensive for standard tools like `Pandas`.
- **Geospatial Analysis**: I explored geographic data visualization using `Folium` to create interactive maps of cell tower locations and understand the global distribution of cell networks.
- **Temporal Data Analysis**: I analyzed trends in the creation and updating of cell towers over time, learning how to work with UNIX timestamps and draw insights from temporal patterns.
- **Signal Strength Analysis**: I explored signal strength data and gained insights into how data collection methods can affect the interpretation of information in telecommunications datasets.
- **Key Performance Indicators (KPIs)**: I utilized KPIs such as network coverage range, the number of active cell towers per country/continent, and signal strength averages to assess network performance across regions. This helped in understanding patterns in network expansion and coverage quality.


## Dataset Description

The dataset contains over 46 million records, organized by continent, and includes the following columns:

- **Radio**: The generation of broadband cellular network technology (e.g., LTE, GSM).
- **MCC**: Mobile Country Code, a unique identifier for each country in the mobile network.
- **MNC**: Mobile Network Code, identifying the mobile network within a country.
- **LAC**: Location Area Code, Tracking Area Code, or Network Identifier.
- **CID**: Unique identifier for each Base Transceiver Station (BTS) or sector.
- **Longitude**: Geographic coordinate specifying the east-west position.
- **Latitude**: Geographic coordinate specifying the north-south position.
- **Range**: Approximate area within which the cell coverage extends (in meters).
- **Samples**: Number of measures processed to derive the data point.
- **Changeable**: Indicates if the cell location was determined through sample processing (1) or directly obtained from the telecom firm (0).
- **Created**: Timestamp indicating when the cell was first added to the database (UNIX format).
- **Updated**: Timestamp indicating when the cell was last seen or updated in the database (UNIX format).
- **AverageSignal**: Represents the averaged signal strength of the cell location.
- **Country**: The country of the cell tower (added after processing MCC and MNC).
- **Network**: The company that owns the cell tower.
- **Continent**: The continent of the cell tower.

### Data Cleaning and Enrichment

The original dataset did not contain the country information, only the MCC and MNC codes. To address this, I used an external website to extract and map MCC and MNC to their corresponding countries. After enriching the dataset with this country information, I filtered the data by continent and saved separate files for each continent.

### Analysis and Visualization

- **Geospatial Analysis**: The geographic distribution of cell towers was analyzed, and a map of cell towers in Morocco was generated using Folium.
- **Temporal Analysis**: Trends in the creation and update timestamps of cell towers were explored.
- **Signal Strength Analysis**: The average signal strength across different regions and networks was analyzed, although most of the "AverageSignal" values were zeros due to the data processing methodology.

