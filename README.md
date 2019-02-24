# mission_to_mars

In this assignment,  will build a web application that scrapes various websites for data 
related to the Mission to Mars and displays the information in a single HTML page.
The following outlines were used:
## Step 1 - Scraping: 

    1/  Inital scrape using Jupyter Notebook, Beautiful Soup,Pandas, and Requests/Splinter.
    
    2/  With Jupyter notebook file called `mission_to_mars.ipynb` 
        and use this to complete all of your scraping and analysis tasks.
        Here ,,
     *  Scrape the [NASA Mars News Site](https://mars.nasa.gov/news/) and 
        collected the latest News Title and Paragraph Text.
          
    3/  Visited the url for JPL Featured Space Image [here](https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars).
     *  Used splinter to navigate the site and find the image url for the current Featured Mars Image and 
        assigned the url string to a variable called `featured_image_url.
         
         
     4/ Mars Weather
      * Visited the Mars Weather twitter account [here](https://twitter.com/marswxreport?lang=en) and 
        scraped the latest Mars weather tweet from the page. 
        Saved the tweet text for the weather report as a variable called `mars_weather`.
        
     5/  Mars Facts
       * Visited the Mars Facts webpage [here](http://space-facts.com/mars/) and use Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc.
       * Used Pandas to convert the data to a HTML table string.
       
       
     6/  Mars Hemisphere
       * Visited the USGS Astrogeology site [here](https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) 
         to obtain high resolution images for each of Mar's hemispheres.
         
         
       * Save both the image url string for the full resolution hemisphere image, and 
         the Hemisphere title containing the hemisphere name.
         Used a Python dictionary to store the data using the keys `img_url` and `title`.

       * Append the dictionary with the image url string and the hemisphere title to a list.
         This list will contain one dictionary for each hemisphere.
         
         

## Step 2 - MongoDB and Flask Application:

      1/ Used MongoDB with Flask templating to create a new HTML page that displays all of the information 
        that was scraped from the URLs above.
        
       * Converted your Jupyter notebook into a Python script called `scrape_mars.py` with a function called `scrape` 
         that  executed all  scraping code from above and return one Python dictionary containing all of the scraped data.

       * created a route called `/scrape` that will import your `scrape_mars.py` script and called  `scrape` function.

       * Stored the return value in Mongo as a Python dictionary.

       * Created a root route `/` that will query your Mongo database and 
         passed the mars data into an HTML template to display the data.

       * Create a template HTML file called `index.html` that will take the mars data dictionary and 
         displayed all of the data in the appropriate HTML elements. 
         
