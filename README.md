﻿# Redfin Scraper

## Description
A scalable Python library that leverages the unofficial Stringray API to quickly scrape real estate data hosted by Redfin.

## One-Time Setup
### Zip Code Database
> A database of zip codes is required to search for City, State values  

> It is strongly recommended to download this [free](https://www.unitedstateszipcodes.org/zip-code-database/#) version in .csv format
### The Config
> Parameters for the RedfinScraper class can be controlled using an optional `config.json` file  

> [Sample Config](https://github.com/ryansherby/RedfinScraper/blob/main/config.json)



## Getting Started
### Installation
`pip install redfin-scraper`

### Import Module
`from redfin_scraper import RedfinScraper`  

### Initialize Module
`scraper = RedfinScraper()`

## Using The Scraper
### Required Setup
`scraper.setup(zip_database_path:str,multiprocessing:bool=False)`

> **zip_database_path**: Binary path to the zip_code_database.csv  

> **multiprocessing**: Allow for multiprocessing

### Activating The Scraper
`scraper.scrape(city_states:list[str]=None,zip_codes:list[str],lat_tuner:float,lon_tuner:float)`
>**city_states**: List of strings representing US cities formatted as "City, State"  

>**zip_codes**: List of strings representing US zip codes  

>**lat_tuner**: Represents # of standard deviations beyond the local latitude average that a zip code may exist within   

>**lon_tuner**: Represents # of standard deviations beyond the local longitude average that a zip code may exist within  

### Accessing Prior Scrapes
`scraper.get_data(id:str)`
>**id**: IDs are indexed at 1 and increase in the format "D00#"

## Appendix
### Warnings
> Multiprocessing can result in the consumption of all available CPU resources for an extended period of time  

> Unethical use of this library can result in Redfin taking disciplinary action against your IP address  

### Recommendations
> Requests for large amounts of data (# of zip codes > 2,000) should be split into separate requests  

> The `package.log` file can be used to investigate unexpected results
