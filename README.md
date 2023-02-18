## A web-scraping project

This repo contains a simple [Scrapy](https://scrapy.org/) project for scraping exhibit- and gallery-level data from 
[exploratorium.edu](https://www.exploratorium.edu), the official webpage of the Exploratorium. 
This project is Part 1 of [Explorer AI](https://github.com/kristenvonbecker/Explorer_AI).

The spiders `exhibits.py` and `galleries.py` defined in `exploratorium/spiders/`, scrape the following data from 
the landing pages for the museum's [exhibits](https://www.exploratorium.edu/exhibits/all) and 
[galleries](https://www.exploratorium.edu/visit/galleries), respectively.

  - Each item in the exhibit-level data (i.e. each exhibit) has the following fields:
    - `id` is the id of the exhibit (taken from the URL slug)
    - `title` is the title of the exhibit
    - `tagline` is a (catchy) short description
    - `description` gives a brief description of the exhibit
    - `location` gives the (current) location of the exhibit (e.g. gallery) inside the museum, or says that it is not 
currently on view
    - `byline` is the information contained in the line beginning "Exhibit developer(s):"
    - `whats_going_on` is one of the more common headings in the exhibit's "about" section
    - `going_further` is the other common heading
    - `details` stores the text contents of the "about section" whenever it does not contain the previous two features
    - `phenomena` gives a list of phenomena which are illustrated by the exhibit
    - `keywords` gives a list of keywords for the exhibit
    - `collections` gives a list of collections (groupings of exhibits, based on some theme) that the exhibit belongs to
    - `aliases` gives other names that the exhibit might go by
    - `collection_id` gives a list of ids for collections to which the exhibit belongs
    - `related_exhibit_id` gives a list of ids for related exhibits 


  - Each item in the gallery-level data (i.e. each gallery) has the following fields:
    - `id` is the id of the gallery (taken from the URL slug)
    - `title` is the title of the exhibit
    - `tagline` is a catchy short description
    - `description` gives a brief description of the exhibit
    - `curator_url` gives a link to the curators' statement
    - `curator_statement` gives the curators' names and their statement about the gallery
    
The `json` files containing this data are located in `data/`.
