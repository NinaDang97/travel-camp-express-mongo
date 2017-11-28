# TravelCamp
Welcome to TravelCamp!<br /> A Travel Blog where everyone can create their own travel posts and view other users' experiences, as well as give reviews or contact with the posts' owners. As long as you sign up and log in, the whole blog is yours!
Built in [cloud9](https://c9.io) - a powerful online code editor with a full Ubuntu workspace in the cloud.

### Setup MongoDB
If built with [cloud 9](https://community.c9.io/t/setting-up-mongodb/1717) 

### NPM Install
```
npm install --save 
```
- express (Server-side Javascript)
- ejs (Embedded Javascript)
- body-parser (middleware: convert form data under `req.body` property as an object)
- mongoose (mongoDB for Express version)
- method-override (used for method PUT and DELETE in RESTful ROUTE that form type in cliend-side doesn't support
- connect-flash (middleware: store message displayed for user once and cleared after page being refreshed)
- passport
- passport-local
- passport-local-mongoose
- express-session

## Simple guideline from scratch

 1. The differences between Authentication and Authorization:
 - Authentication: get people signup/login. In other words, people need to tell app/website who they are.
 - Authorization: Once figure out who user is, grant permission on specific things they are allowed to do.
 
 2. How To Do?
 - Hint: 
   + Verify the id of current user with id of author who creates the post
   + However, id of current user - a string (req.user._id) is different than id of author (foundBlog.author.id) - a mongoose object
   + Instead of using: if(req.user._id === foundBlog.author.id). We use:
   ```
   if(foundBlog.author.id.equals(req.user._id)){
                  ...
          }
   ```
## Guideline from scratch: 
### Layout and Basic Styling
* Create header and footer partials
* Add Bootstrap

### Create New Campgrounds
* Setup new campground POST route
* Add in `body-parser`
* Setup route to show form
* Add basic unstyled form
 
### Style the campground page
* Add batter header/title
* Make campgrounds display in a grid 

### Style the Navbar and Form
* Add navbar to all templates
* Style the new campground form

### Add Mongoose
* Install and configure mongoose
* Setup campground model
* Use campground model inside of our routes

### Show Page
* Reciew the RESTful routes we've seen so far
* Add description to our campground model
* Show db.collection.drop()
* Add a show route/template

### Refactor Mongoose Code
* Create a models directory
* Use module.exports
* Require everything correctly

### Add Seeds File
* Add a seeds.js file
* Run the seeds file every time the server starts

### Add the Comment model
* Make our errors go away!
* Display comments on campground show page

### Comment New/Create
* Discuss nested routes
* Add the comment new and create routes
* Add the new comment form

### Style Show Page
* Add sidebar to show page
* Display comments nicely


----- AUTHENTICATION ---------
### Installment:
* passport
* passport-local
* passport-local-mongoose
* express-session

### Auth Pt. 1 - Add User Model
* Install all packages
* Define User model

### Auth Pt. 2 - Register 
* Configure Passport
* Add register routes
* Add register template

### Auth Pt. 3 - Login
* Add login routes
* Add login template

### Auth Pt. 4 - Logout/Navbar
* Add logout route
* Prevent user from adding a comment if not signed in 
 + from create new campground (both app.get() and app.post() ROUTES)
    * => because we just hide the form from user
    * => user can use Postman and submit form from POST ROUTE
* Add links to navbar

### Auth Pt. 5 - Show/Hide Links
* Show/hide auth links correctly

### Refactor the routes
* Use Express router to reorganize all routes
    * Categorize 3 different groups of routes
    1. Authentication routes
    2. Comment routes
    3. Campground routes

### Users + Comments
* Associate users and comments
    * commentSchema = mongoose.Schema({
        text: String,
        author: {
            id: {
                type: mongoose.Schema.Types.ObjectId,
                ref: "User"
            }
            username: String
        }
    }) 
* Save author's name to a comment automatically

### Users + Campgrounds
* Prevent an unauthenticated user from creating a campground
* Save username + id to newly created campground

### Editing campgrounds
* Add Method-Override
* Add Edit Route for Campgrounds
* Add Link to Edit Page
* Add Update Route

### Delete Campgrounds
* Add Destroy Route
* Add Delete button

### Authorization
* User can only edit his/her campground
* User can only delete his/her campground
* Hide/Show edit and delete buttons

### Middleware Refactor

### Flash Message Adding
* Install and configure connect-flash
#### Inspired by Web Developer Bootcamp - Colt Steele
