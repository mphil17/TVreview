# What 2 Watch

![Website view](/static/media/responsive.png)

## Introduction
What 2 Watch is a website that tells you what next series you should watch on Netflix, Amazon
Prime etc. It is unique in having only tv series so attracts the ‘binge watchers’ as oppose to the ‘film
buffs’ to the website. Website can be viewed [here.](http://tvreview.herokuapp.com/)

## UX

### Project Goals
What to watch came about as a result of lockdown. With people stuck in their homes,
conversations turned to what to watch and series such as ‘Tiger King’ were very popular. When
looking for a new series to watch, there are sources such as IMDB and Rotten Tomatoes.
However, these also include films and the information contained in them is very detailed. I wanted
to create a site that would give basic information on only tv series about whether it was worth
watching or not. Rotten Tomatoes have a user rating and their own rating. I wanted just a rating
and review from people who have watched it.

### Developer Goals
As a developer:
- I want to make a website that has useful information about tv shows
- I want to demonstrate my skills in using a database and CRUD functionality

### User Stories
As a user:
- I want to search for a tv show
- I want to see the reviews of the tv show
- I want to write my own review of a tv show
- I want to rate how good a tv show is
- I want to see the average rating for a tv show
- I want to sign in
- I want to book mark a show by making it a favourite
- I want to see my history of reviews and favourites
- To be given suggested shows based on my likes

### Data 
![Database Structure](/static/media/db.png)
### Design
#### Fonts
The text is a little archaic in style to signify going back to basics- a recommendation from
a friend as oppose to modern data laden websites. The main text is Xanh Mono. The review text is Caveat. This looks more like handwriting
as if the user has hand written it.
#### Colours
A lot of the popular tv series have mystery and twists involved. The design is dark to signify
mystery. The alert font was initially red but changed to green as the alert does not always mean something bad. Some colour added to the buttons, e.g. the login button to make them stand out more.
#### Icons
I used icons from materialize. These icons are recognisable by the user and they can work out what the function is.
#### Styling
I used Materilize to help to organise my layout. What 2 Watch is the title of the website and is shortened to W2W for the logo. 
The buttons have slightly rounded edges to look more appealing. Colours change on the buttons as the user hovers over. Also, the cards pop out as the user hovers over them.

### Wireframes
I created the wireframes on [Balsamiq](https://balsamiq.com/). There were changes to the shortened title (from WtW to W2W). Also, I removed the add tv show and 
decided to import from an API: 

- [Home page on computer](/static/wireframes/home-web.jpg)
- [Profile page on computer](/static/wireframes/profile-web.jpg)
- [TV show page on computer](/static/wireframes/tv-show-web.jpg)
- [Home page on mobile](/static/wireframes/home-mobile.jpg)
- [Profile page on mobile](/static/wireframes/profile-mobile.jpg)
- [TV show page on mobile](/static/wireframes/tv-show-mobile.jpg)
## Features

### Existing Features
- Navbar with links to home page, sign up and login. Changes when logged in so that log out and profile are available  
_As a user I want to search for a tv show:_
- Search bar for searching tv shows titles from IMDB API  
_As a user I want to sign in:_  
- Ability to sign up and login with user authentication and password validation
- Password stored securely using Werkzeug
- Message flashes to ensure the user knows what is happening  
_As a user I want to write my own review of a tv show:_  
_As a user I want to rate how good a tv show is:_  
- User, when logged in, can rate and review a tv show  
_As a user I want to book mark a show by making it a favourite:_  
- User, when logged in, can favourite a tv show  
_As a user I want to see my history of reviews and favourites:_  
- User profile with their favourite tv shows and their reviews
- ability for user to edit and delete their reviews
- protection against a user rating or reviewing multiple times
- User can navigate back to previously viewed tv show  
_As a user I want to see the reviews of the tv show:_  
_As a user I want to see the average rating for a tv show:_  
- User can see the reviews and average star rating for each show
- User can see information pulled from IMDB API about the tv show  
_As a user To be given suggested shows based on my likes:_  
- Suggested tv shows similar to the one they are looking at 

### Future Features
These features could be added to the website with more time and with more expertise:
- As the user types in the search bar, a list of suggested titles comes up. This means that the user can click on one of the suggestions which shortens the time for the user to get to the tv show.
- Users would want to be able to search for genres, actors etc. This means if they do not know the title of the movie but do know one of the actors, it will find the appropriate tv shows. 
Also, users may want to search for a particular genre or tv shows from a particular country rather than a specific show. 
- On the tv show page, the user may want to see a trailer for the tv show to get a feel for what it is like.
- If a user likes a tv show and wants to watch it, the website can give a link to Netflix or Amazon Prime etc. so that the user can go straight to watching it rather than having to search for it again
on a streaming platform. As well as this, as the websites owner, money can be made in this way. Netflix or Amazon Prime would pay for the link to their websites.
- On the home page, underneath the search bar, the User can view the top rated tv shows. This is another way of suggesting to the user what tv show they may want to watch.
- Users will be able to toggle favourites and delete favourites from their profile page. They may make a mistake and want to rectify or want to trim down their favourites.


## Technologies Used
- This project uses HTML5, CSS3, Javascript, Python, Flask and Jinja.
- This project uses [Mongo DB](https://www.mongodb.com) as its database 
- This project uses [Materialize](https://materializecss.com) to support with structuring the website responsively
- This project uses [Google Fonts](https://fonts.google.com) for more interesting fonts
- This project uses [Github](https://github.com)
## Testing
### Debugging
The debugger in flask was used throughout the development stage. This gave me information as to where there was a bug. Manuel debugging was done by printing to the
console. This was particularly helpful when pulling information from the database to check that I had the correct information. Chrome Developer Tools allowed me to view any 
layout issues. This was particularly helpful when laying out the tvshow.html. There are a lot of 'div's and it got confusing as to where the closing 'div's should be. 
### Fixed Issues
- Information required for users to view dependent on whether they had written reviews or not etc. was too complex for Jinja. I used a global variable for whether any user was 
logged in and then was able to have conditional statements in app.py.
- The search term used was being lost as the page redirected meaning no results were being shown. I created a new function which could grab the search term and then pass it into
the next function.
- User was able to use same email address to sign up so needed to find if that email was already in the database before allowing progress.
- Tried to use Javascript to display the correct amount of stars as per the rating. Was difficult to link this to Flask, though, so instead used a loop in Jinja.
- It would have been frustrating for the user to login on the tvshow.html and then have to press the back button to get back. In order to get back to the tv show they last looked at,
I created a session variable for the tv show id.
- Having moved elements around on tvshow.html, there appeared a white space between the sections. Using overflow: none fixed it.
- Stars responsiveness was not correct. Stars kept going out of line on ipad screen size. Used media queries to fix the small size window where this happened.
### Manuel Testing
Site tested on Chrome, Safari and Microsoft Edge browsers. Media queries work on different size devices. Card-image and stars grow as device gets bigger
and words on buttons on profile appear on larger devices.
#### Flow of website
![Website Flow](/static/media/flow.jpeg)
#### Nav Links
- Home nav links go to the correct places.
- Nav links  on each page
- Login and Sign up nav links working and buttons between the two.

#### Login and Sign up
- Password validator/ pattern works.
- Input fields for username only allows text and numbers, email has to have @.
- The check to see if username/ email exists works.
- Sign Up, logout, login works.
![Clip of logging in with incorrect username](/static/media/login1.gif)   
![Clip of logging in successfully](/static/media/login2.gif)   
![Clip of password validator](/static/media/pass.gif)    
![Clip of of signing up with username that already exists](/static/media/sign-up.gif)  

#### Search
- Input field initially allowed other characters, now changed.
- Needed to add allow for spaces.
- If nothing typed it prompts you to type something.
- If nothing found, it says 'sorry, there are no results'.
![Clip of search bar only allowing letters and numbers](/static/media/search.gif)

#### Profile
- Link to profile from logged in page works.
- Buttons that link to previous tv show and new search work.
- Favourite tv shows and reviews shown.
- Links to favourite tv shows work.
- Edit review works.
- Fixed issue where cancel button still sent form. Changed button to type button as it was defaulting as submit.
- Delete button works.
- After searching for another tv show, link to previous tv show sends you to correct show.

#### Tv Show
- Favourites heart button works. Clicking it again brings up flash message that it is already a favourite.
- Login button works.
- Changes to layout and what the user can see when logged in- needed to alter favourites heart icon only appear when user logged in.
- Reviews are shown. If no reviews, it just has the title.
- Show all reviews link button works and link back.
- Link to profile works when logged in.
- Star rating works when user rates the show. Stars are shown correctly as well as correct number of ratings.
- Adding a review works.
- Links to simliar tv shows work.

#### Responsiveness
- Nav sidebar slides out as it should. Links work. Logo in centre at top.
- Home page- all elements responsive
- Search page- all elements responsive
- Sign up and login- form fills screen 
- Tv show page- elements stacked underneath each other. User scrolls to see them.
- All reviews- Needed to make card wider on smaller devices. Elements responsive.
- Profile- took the words out from the buttons to make it look cleaner. Made card wider on smaller devices. Elements responsive.

### Validators
- [PEP8 Online Check](http://pep8online.com/) used. Adjusted some under indented continuation lines and removed whitespace.
- [HTML Validator](https://validator.w3.org/) used. Moved 'hr' and 'br' outside of 'a' tag on search.html. Added alt on tvshow.html.
- [CSS Validator](https://jigsaw.w3.org/css-validator/) used. No errors reported.
- [Javascript Validator](https://jshint.com/) used. No major issues.

### Website speed
- Home page speed
![Home page speed](/static/media/ping_index.png)
![Home page performance](/static/media/lighthouse.png)
- TV show speed
![TV show page speed](/static/media/ping_tvshow.png) 
![TV show page Performance](/static/media/lighthouse_tv.png)  
Speed slow in tvshow.html due to lots of images for similar tv shows at the bottom. Added lazy loading for those so that main content is shown quicker.

### Know issues
- On free plan, only 100 API calls allowed.

## Deployment
### Deploy on Heroku
- You will need to use [PIP](https://pypi.org/project/pip/) and ensure it is up to date, Git for version control and [Mongo DB](https://www.mongodb.com/) 
with a database set up as described earlier.
#### Create a requirements.txt
- You need a requirements.txt so that your app knows what libraries to use. In order to do that, in your terminal type:
```
pip3 freeze --local > requirements.txt
```
#### Add a Procfile
- To add a Procfile, type into your teminal:
```
echo web: python app.py > Procfile
```
Make sure that there is not a blank line added at the bottom
#### Create a Heroku app
- Log into Heroku or create an account.
- Create a new app and give it a unique name
- Select a region to deploy from
- Connect your github to Heroku by adding in your github repository name
- In settings, add config variables as below:  

| KEY          | VALUE                   |  
|--------------|-------------------------|   
| IP           | 0.0.0.0                 |
| PORT         | 5000                    |
| MONGO_URI    | (Your own Mongo URI)    |
| SECRET_KEY   | (Your own secret key)   |
| MONGO_DBNAME | (Your own DB name)      |
- Enable Automatic Deployment from your Github
- Deploy the correct branch

### Deploy Locally
#### Clone repository
1. In your terminal, type:
```
git clone https://github.com/mphil17/TVreview.git
```
2. Add the requirements for the project:
```
pip3 install -r requirements.txt
```
3. Create an account and new project with MongoDB. Add in the database as above. (note: rating is an integer with all other fields being strings). Get the Mongo URI.
4. Sign up to [IMDb API](https://imdb-api.com/) for the API data and get the API key.
5. Create an env.py file for all of your environment variables:
```
import os

os.environ.setdefault("IP", "0.0.0.0")
os.environ.setdefault("PORT", "5000")
os.environ.setdefault("SECRET_KEY", "YOUR_SECRET_KEY")
os.environ.setdefault("MONGO_URI", "YOUR_MONGO_URI")
os.environ.setdefault("MONGO_DBNAME", "YOUR_MONGO_DBNAME")
os.environ.setdefault("APIKEY", "YOUR_API_KEY")
```
(make sure that env.py is added to .gitignore if you are pushing to a public repository)  
6. Run the app:
```
python3 app.py
```
## Credits
### Content
[IMDb API](https://imdb-api.com/) for the data on tv shows.
### Code
[Bearer](https://blog.bearer.sh/making-api-requests-with-python/) blog for helping with API requests with Python.
[W3Schools](https://www.w3schools.com/) for help whenever I forgot some simple code.
### Acknowledgements
- Thank you to Felipe Souza Alarcon for his great support as always.
- Thank you to Stephen Moody from Code Institute for helping me with linking documents together in a database.
- Thank you to Clare Robinson for trying out the website to check for bugs.