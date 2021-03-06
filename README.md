# Clone Records catalog scraper

![Clone](assets/clone.jpg)

## Introduction
This scraper collects data from [Clone Records](https://clone.nl) recordshop, writes to a database hosted on 
Heroku platform and exports a `.csv` file with results.

## Usage
### Configuration
You will need to create a postgreSQL database on [Heroku](https://dashboard.heroku.com/) or any other platform and enter the authentication credentials 
into `config.py` file. 

### Initialisation
`from scraper.clone_nl import CloneScraper`

### Scraper functions
These functions will be executed by running `main.py`. Feel free to edit the variables to suit your requirements. 
 - `drop_tables()` - Drops categories and items tables. Handle with care - this will destroy your data!
 - `create_tables()` - Creates categories and items tables and sets up foreign keys.
 - `fetch_url(genre, number_of_examples)` - Iterates through pages required to collect a specified number of examples. 
   Returns Pandas dataframe.
 - `insert_data_into_db(dataframe, genre)` - Inserts the data from dataframe into a database.
 - `export_to_csv()` - Fetches the data from the database and exports as .csv file.

## License
This project is licensed under https://tldrlegal.com/license/mit-license