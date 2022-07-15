Part 1: SWAPI
Instructions
For each of the following use the SWAPI docs, to figure out the complete URL(s) (including params or queries) that you need to go to in order to reach the following data:

1. the height of Darth Vader

https://swapi.dev/api/people/?search=Darth%20Vader

To look up Darth Vader, use the "?search=Darth%20Vader". "the "%20" stands for space.  

"height": "202",

2. the population of the planet Alderaan

"population": "2000000000"

3. the name of the manufacturer of the Millennium Falcon

"Corellian Engineering Corporation"

4. the name of the species that C-3PO belongs to (multiple URLs)

"https://swapi.dev/api/species/2/"



5. the title of each film that Obi-Wan Kenobi is in (multiple URLs)

"https://swapi.dev/api/films/1/",
                "https://swapi.dev/api/films/2/",
                "https://swapi.dev/api/films/3/",
                "https://swapi.dev/api/films/4/",
                "https://swapi.dev/api/films/5/",
                "https://swapi.dev/api/films/6/"

6. use the search query (the how to on the search query is at the bottom of the Getting Started section of the  documentation) to get the information about the Millennium Falcon, it’s a starship



Part 2: Social Mountain
Summary
In this section, you’ll be looking through the documentation for the Social Mountain API and answering questions. You’ll also be making requests and recording the URLs and some information about the responses. Run the requests in Postman. Note: this API is live and viewable by your classmates and staff. Keep things appropriate for class.

You can view the documentation for the Social Mountain API here

The base URL of your requests is: https://practiceapi.devmountain.com/api (make sure to have the “s” in “https”)

1. Check if the POST request accept params, queries, and/or a body. Which one(s) and what information is it expecting to be sent?

Post request is expecting Body. 

2. What data type does the GET request return?

Array

3. What would the URL look like for deleting the post with the id 555? (This post does not exist anymore, but the syntax is the same for existing posts, )

 https://practiceapi.devmountain.com/api/posts?id=555
the question mark indicates that there's a query. 

4. List the possible response codes from the GET request at ‘/posts/filter’

Return vs Response?

200
409


5. Create a post whose text is your name, record the URL and body here:

{
    "id": 130,
    "text": "Abdirahman",
    "date": "13 Jul 2022"
  }

URL: https://practiceapi.devmountain.com/api/posts

6. What would the URL and body object be to update the post you just made to contain your faovrite color instead of your name?

The body will be "blue"
and the URL will be https://practiceapi.devmountain.com/api/posts?id=130


7. What is the URL to get posts that contain the text “blue”?

https://practiceapi.devmountain.com/api/posts/filter?text=blue


8. Make a request to GET all the posts. What are the content type and charset of the response? (Hint: look on the Headers)

application/json; charset=utf-8


9. What would cause a PUT request to return a 409 status?

Go to devmountain api documentation website at 
https://practiceapi.devmountain.com/api/posts

Click on PUT and scroll down to Code Description

"Request was missing req.query.id or req.body.text"

10. What happens if you try to send a query in the GET request URL? Why do you get that response?
Inside GET, I sent this query: 

https://swapi.dev/api/?search=?

{
    "people": "https://swapi.dev/api/people/",
    "planets": "https://swapi.dev/api/planets/",
    "films": "https://swapi.dev/api/films/",
    "species": "https://swapi.dev/api/species/",
    "vehicles": "https://swapi.dev/api/vehicles/",
    "starships": "https://swapi.dev/api/starships/"
}

Part 3: 

Setup
Create a folder called “swapi” and three files inside - index.html, styles.css, and main.js

Open the folder up in VS Code

Run npm init -y which will create a package.json file

Install axios using npm

index.html
Create a basic HTML layout (doctype, html, head, body)

Connect the CSS file (using a link) and the JS file (script tag)

Add another script tag, above the main.js script, to import axios (since axios is in our node modules folder, the src of the script can just use the file path to get to axios, which is “./node_modules/axios/dist/axios.min.js”)

In the body tag create a button that says “get residents” on it

main.js
Select the button using querySelector and save it to a variable

Write a function that just console logs a string like ‘button clicked’

Use addEventListener to attach the function you just wrote to a click event on the button

Open index.html in the browser (right click and copy path)

Click the button and check the console, if it’s working, move on to the next section

making a request
As you complete this section, be sure to test along the way using Postman and console.logs

Now you’ll modify the function to make an axios call to SWAPI

Make an axios request that gets the information about the planet Alderaan (use the search query to request it, the how to on the search query is at the bottom of the Getting Started section of the documentation)

Inside the callback passed to the .then, loop over the residents array returned on the results. It’s full of URLs.

In the loop, make another get request for each URL in the array.

You’ll have another .then that has its own callback, inside which you should create an h2 element whose content is the name of the resident that you just requested. Append the h2 to your HTML document.

styles.css
add any styles you’d like to your page