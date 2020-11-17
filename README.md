# GeoSpatial Data Project

In this project, we will have to find the best location for our gaming company. This will be the one that fills most of the preferences of our employees.

We will do this first by sending queries both in MongoDB and Foursquare with our requirements, so these queries will return us (hopefully) coordinates with locations nearby.

- MongoDB:

First things first, we unwind the companies by offices, so each document(company) has only one office location. After that, we will have to create a 2dsphere index so the queries can return the office's coordinates of each document.

We then have created functions for each requirement that will return a tuple of coordinates (i.e. startups raised over 1M within 2km).

- Foursquare:

We do a similar process with the Foursquare API. We have defined functions for each of the requirements of our employees, and we have searched through the API looking for primary schools/nurseries, nightlife spots, starbucks, airports, basketball stadiums, etc.

Our aim is to find an existing office from the database that could fill most of these preferences, but the dataset contains more than 10.000 documents. We will need to filter them so the search for the most suitable office (the one that contains most of our requirements) is done by a lot less companies (otherwise we will run out of API tokens). We have seen through MongoDB that filtering the offices by the city "San Diego", there are 114 offices which is a reasonable number, as we need to make 7 calls per office so won´t reach the limit of 950 tokens per day (we would use 798 tokens).

By the time we are doing the calls to the API, we are also scoring the requirements depending on the amount of points each call returns, so we can set up a ranking and find the best location as it will get the highest score.

- Drawing the requirements in a map:

Once we have the coordinates of the chosen office, we will draw it in a map showing the surrounded spots for vegan restaurants, airports, starbucks... showing all the requirements our employees asked for.



- *Comentarios finales: 

Me pasa en la mayoria de los proyectos, me cuesta mucho empezar, plantearme lo que me piden, organizarlo/separarlo en pequeñas tareas y empezar a ser eficiente, con lo que al final nunca tengo suficiente tiempo para entregarlo mejor, sacar mejores graficas, desarrollar más el readme, etc. Siempre me falta tiempo en estos proyectos.