# Global Power Plant Data ETL - \#DPFromScratch01

This project is an attempt to learn to build _#DataPipelinesFromScratch_ using the following data engineering tools (in general).

1. Docker and Docker Compose
2. Jupyter Server and PyMongo
3. MongoDB

The use case is very basic and could be easily performed using a different approach; but since the objective is to get hands-on learning on different data engineering tools, the following approach is used.

## Goal

The goal is to extract [_Global Power Plant Data_](https://datasets.wri.org/dataset/globalpowerplantdatabase) data from a CSV file, do simple transformations to data fields and load them into a MongoDB server.

The CSV file at `data/global_power_plant_database.csv` which is the datasoure has the following structure:

![CSV File](images/csv-image.png)

The format we are going to transform the data to and load them to MongoDB:

```
{
        'country_id': '',
        'country_name': '',
        'plant_name': '',
        'gppd_id': '',
        'capacity_mw': 0.0,
        'latitude': 0.0,
        'longitude': 0.0,
        'fuel_source': {
            'primary': '',
            'secondary': '',
            'tertiary': '',
            'quaternary': ''
        },
        'commissioning_year': '',
        'owner': '',
        'data_source': '',
        'data_source_url': '',
        'actual_generation': {
            'generation_gwh_2013': 0.0,
            'generation_gwh_2014': 0.0,
            'generation_gwh_2015': 0.0,
            'generation_gwh_2016': 0.0,
            'generation_gwh_2017': 0.0,
            'generation_gwh_2018': 0.0,
            'generation_gwh_2019': 0.0
        },
        'estimated_generation': {
            'estimated_generation_gwh_2013': 0.0,
            'estimated_generation_gwh_2014': 0.0,
            'estimated_generation_gwh_2015': 0.0,
            'estimated_generation_gwh_2016': 0.0,
            'estimated_generation_gwh_2017': 0.0
        }
    }
```

## Method and Architecture

First the following docker network needs to be created with two containers:

1. Container 1 - carrying our Jupyter server and our data file
2. Container 2 - carrying our MongoDB server

![Architecture](images/DP4mS_architecture.png)

## How to Run

