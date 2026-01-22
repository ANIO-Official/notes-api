# Notes API🔒 | Backend Authorization & Authentication

A lab study focused on updating the Authorization and Authentication of a pre-existing “Notes” API.

## Module 14: Lab 2

## Overview
The core focus of this lab is to implement authorization logic to ensure that users can only access and manage the notes they personally own.

### GitHub Link
https://github.com/ANIO-Official/notes-api

## How to Use
1.  Clone the repository or Download the ZIP file and extract the files.
2.  Open the file in Visual Studio Code.
3.  Open the Terminal using Ctrl + ~
4.  `cd` into the directory 'notes-api' in the terminal. Like so: 
    `cd notes-api`

    **Ensure NPM is is installed for the project to run:** 

      inside the terminal window run `npm i` to install npm
5.  Create a `.env` file in the root directory/folder ( notes-api ). Add the following to the file:
    - Your personal connection string from [MongoDB]( https://www.mongodb.com) in the following format `MONGO_URI=your_connection_string_goes_here/innovative-inc`. 
    - A Secret Key in the following format `JWT_SECRET=yourSecretKeyGoesRightHere`
    - (Optional) A port number within the 3000s: `PORT=3000`
6.  (Once NPM is indeed installed in the project file directory, you'll see a node modules folder) Run the project using `node server.js` in the terminal. You can also use npm run dev (Nodemon is installed)

7.  You should see a message appear. Follow the link such as: "http://localhost:3000/" or "http://localhost:3001/"

From here, you can test creating a new user or logging in as an existing user using software/Visual Studio extension such as Thunderclient or Postman or a simlar software/Visual Studio extension.

To create using JSON body, following this format:

```JSON

{
    "username": "coolest1stUser",
    "email": "bestCoolemail@gmail.com",
    "password": "b3tterP4ssword"
}

```

To login using JSON body, following this format:


```JSON

{
    "email": "bestCoolemail@gmail.com",
    "password": "b3tterP4ssword"
}

```

Using JSON body, Create Notes use this format:

```JSON

{
    "title": "Note to Self",
    "content": "Don't feed the pigeons banana bread.",
    "createdAt": 2020-05-07
}

```

For all Updates, Deletions, and Reads of Notes using JSON body, you need to be the authorized User. You can test both unauthorized and authorized using the token generated upon login in the response JSON.

Follow this format:

```JSON

"token": "esfodijweijfi439584jjndmlm]e[r][p320403mkdfm]_3483msdlfiowe"

```

*For bodies of type Form-encode, simply make a token, notes details (title, content, createdAt), username, email, and password with their associated values you determine for testing. You can also place the token into the Auth > Bearer token input area.*

**Upon testing: You will see corresponding text or JSON messages upon successfully/unsuccessfully creating users, logging in users, creating notes, reading notes, reading specific user notes, updating user's notes, and deleting user notes.**

### End points
``` JS
/api/users/register //Post/Create User
/api/users/login //Post/Login Existing User

/api/notes // Get/Read All Notes or Post/Create Note
/api/notes/:id  // Get/Read Specific Note, Put/Update, Delete Notes
```

## My process

 1. Initialized repo and npm. Installed all necessary & personally preferenced dev packages (`dotEnv`, `express`, `bcrypt`, `jsonwebtoken`, `mongoose`,a nd `nodemon`). Added server.js, .gitignore, and .env files.
 2. Added .env and node_modules to .gitignore
 3. Refactored provided code & perform Debugging and thorough testing using Thunderclient and `console.log`. Added mongoose connection uri and called connection function.
 4. Added new field `owner` to Notes model.
 5. `Added Authentication to notes access routes for full CRUD (Create, Read, Update, Delete) routes. 
 8. Testing and debugging using Thunderclient, MongoDB, and console.log.

### Built with

- Node.js
- Express
- MongoDB / Mongoose
- Javascript
- dotenv
- Nodemon
- JWT (JSON Web Token)
- Bcrypt

### Useful resources

**PerScholas** | Authentication and Authorization | Lessons 1-3
**PerScholas Cohort** | Eduart - Helped with debugging an issue with value checking due to req.body undefined error.

## Author

- LinkedIn - [Amanda Ogletree](https://www.linkedin.com/in/amanda-ogletree-a61b60168)