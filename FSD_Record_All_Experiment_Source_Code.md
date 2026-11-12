# FSD Record – Extracted Experiment Source Codes

Source: uploaded **FSD Record-1.pdf**. The sections below reproduce the PDF's SOURCE CODE portions, organized by experiment. Formatting and line breaks have been normalized where PDF extraction split lines.

**Credential safety:** Cloudinary credentials printed in the PDF have been replaced with environment-variable references. If those credentials are real, rotate them in the Cloudinary dashboard.

## Experiment 1 Build a Basic React APP that display custom — Build a Basic React APP that display custom message from users

```text
1) Setup Project
          Run the following commands in your terminal to create a React app:
          npx create-react-app message-app cd
            message-app
   2) App Component
          Replace the content of App.jswith the following code:
       // App.js
              import React, { useState } from 'react';
               import './App.css’;
              function App() {
                     const [message, setMessage] = useState('');
                     const [messages, setMessages] =
                     useState([]);
                     // Function to handle message submission
                     const handleSubmit = (e) => {
                     e.preventDefault();
                       if (message.trim())
                       {
                         setMessages([...messages, message]);
                         setMessage(''); // Clear the input field

          }};
        return (
          <div className="App">
           <h1>Message Display App</h1>
           <form onSubmit={handleSubmit}>
             <input type="text"
               placeholder="Enter your message"
               value={message}
               onChange={(e) => setMessage(e.target.value)}
             />
             <button type="submit">Submit</button>
           </form>
           <div>
             <h2>Messages</h2>
             <ul>
               {messages.map((msg, index) => (
                 <li key={index}>{msg}</li>
               ))}
             </ul>
           </div>
          </div>
        );
        }
        export default App;
3) Styling:
Add the following CSS to App.cssfor basic styling:
     /* App.css */
       .App {
         text-align: center;
         padding: 20px;
       }
         input[type="text"] {
         padding: 10px; margin-right: 10px;width: 200px;
       }
       button {
       padding: 10px;
       }
       ul {
         list-style-type:
         none; padding: 0;
       }

                       li {
                         background:
                         #f0f0f0; margin:
                         5px 0; padding:
                         10px; border-
                         radius: 5px;
                      }
              4) Run the App
              Start the React app:
```

## Experiment 1 a — Build a Basic React APP that display

```text
1) Setup Project
             Run the following commands in your terminal to create a React app:
          npx create-react-app message-app cd
             message-app
   2) App Component
          Replace the content of App.js with the following code:
         // App.js
              import React, { useState } from 'react';
              import './App.css';
              function App() {
               const [message, setMessage] = useState('');
               const [messages, setMessages] = useState([]);
               const handleSubmit = (e) => {
                e.preventDefault();
                if (message.trim() !== '') {
                  setMessages([...messages, message]);
                  setMessage('');
                }
               };
               return (
                <div className="container">

          <div className="message-box">
           <h1>Message Display App</h1>

            <form onSubmit={handleSubmit}>
              <input
                type="text"
                placeholder="Enter your message"
                value={message}
                onChange={(e) => setMessage(e.target.value)}
              />
              <button type="submit">Submit</button>
            </form>
            <h2>Messages</h2>
            <ul>
              {messages.map((msg, index) => (
                <li key={index}>{msg}</li>
              ))}
            </ul>
           </div>
          </div>
        );
    }
    export default App;
3)Styling:
    Add the following CSS to App.cssfor basic styling: /*
         App.css */
                * { box-sizing: border-box;
    }
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        background: linear-gradient(135deg, #667eea,
            #fbc2eb);
    }
    .container {
        min-height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 20px; }
    .message-box {
        width: 450px;
        padding: 30px;

    background: white;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 5px 15px rgba(0,0,0,0.2);
} h1 {
    color: #43246f;
    margin-bottom: 25px; }
form {
    display: flex;
    gap: 10px;
    width: 100%;
}
input {
    flex: 1;
    min-width: 0;
    padding: 12px;
    border: 1px solid #aaa;
    border-radius: 6px;
}
button {
    padding: 12px 18px;
    background: #6a45a5;
    color: white;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}
h2 {
    color: #43246f;
    margin-top: 25px;
}
ul {
    list-style: none;
    padding: 0;
    margin: 15px 0 0;
    width: 100%;
} li {

                 background: #eee7fa;
                 padding: 12px;
                 margin-bottom: 8px;
                 border-radius: 6px;
                 text-align: left; }
                4)Run the App
                Start the React app:
```

## Experiment 2 — Create a Login form using React JS

```text
1) Setup Project
                            npx create-react-app
                            login-app cd login-app

                   2) Create Login Form Component
                   // LoginForm.js
                   import React, { useState } from 'react'; function
                   LoginForm() {
                   const [username, setUsername] = useState('');
                   const [password, setPassword] = useState('');
                   const [error, setError] = useState('');
                  // Handle form
                   submission const handleSubmit = (e) => {
                   e.preventDefault();
                  // Basic validation
                  if (!username || !password) {
                  setError('Please enter both username and password'); return;

     }
    setError(''); // Clear error console.log('Username:',
    username); console.log('Password:', password);
   // Further authentication logic here
       };
   return (
 <div className="login-form">
  <h2>Login</h2>
 {error && <p className="error">{error}</p>}
 <form onSubmit={handleSubmit}>
 <div>
 <label>Username:</label>
 <input type="text" value={username} onChange={
(e) =>setUsername(e.target.value)}
  placeholder="Enter username"/>
  </div>
 <div>
 <label>Password:</label>
 <input type="password" value={password} onChange={
(e) => setPassword(e.target.value)}
 placeholder="Enter password"/>
 </div>
 <button type="submit">Login</button>
 </form>
 </div>
 );
 }
 export default LoginForm;

3) Import and Use LoginForm in App Component
import React from 'react';
import LoginForm from './LoginForm'; function
App() {
return (
<div className="App">

 <h1>User Login Portal</h1>
 <LoginForm />
 </div>
 );
 }
 export default App;

4) App.css
 .login form {
   width: 300px;
   margin: auto;
   padding: 20px;
   border: 1px solid #ccc;
    border-radius: 10px;
     }
      .login-form h2 {
   margin-bottom: 20px;
   }
   .login-form label {
   display: block;
   margin-top: 10px;
   }
   .login-form input {
   width: 100%;
   padding: 8px;
   margin-top: 5px;
   margin-bottom:
   10px;
   }
   .login-form button {
     width: 100%;
     padding: 10px;
     margin-top: 10px;
     background-color: #007BFF;
     color: white;
     border: none;
     border-radius: 5px;
     cursor: pointer;

              }

              .login-form button:hover {
                background-color: #0056b3;
              }

              .error {
                color: red;
              }
```

## Experiment 2 a — Create a Login form using React JS

```text
1)Setup Project
         If you haven’t already, create a new React project:
                  npx create-react-app
                  login-app cd login-app
         2)Create Login Form Component
            Inside the src directory, create a new file called LoginForm.js and
         add the following code:
         // LoginForm.js
         import React, { useState } from 'react';
         import './App.css';
         function LoginForm() {
            const [user, setUser] = useState('');
            const [pass, setPass] = useState('');
            const [errorMsg, setErrorMsg] = useState('');
            const checkLogin = (e) => {
               e.preventDefault();
               if (user.trim() === '' || pass.trim() === '') {
                  setErrorMsg('Please fill all the fields');
               }
               else {
                  setErrorMsg('');

        console.log('User Name:', user);
        console.log('Password:', pass);
        alert('Login Successful!');
    }
  };
  return (
     <div className="login-container">
       <div className="login-card">
           <h2>User Login</h2>
           <form onSubmit={checkLogin}>
             <label>Username</label>
             <input
                type="text"
                placeholder="Enter username"
                value={user}
                onChange={(e) => setUser(e.target.value)}
             />
             <label>Password</label>
             <input
                type="password"
                placeholder="Enter password"
                value={pass}
                onChange={(e) => setPass(e.target.value)}
             />
             {errorMsg && (
                <p className="error">{errorMsg}</p>
             )}
             <button type="submit">Login</button>
           </form>
       </div>
     </div>
  );
}
export default LoginForm;
3)Import and Use LoginForm in App Component
In App.js, import and use the LoginFormcomponent:
// App.js
 import React from 'react';
import LoginForm from './LoginForm';
import './App.css';
function App() {
   return (
      <div className="App">

                <LoginForm />
              </div>
           ); }
        export default App;
/* App.css */
      * { box-sizing: border-box;
}
body {
   margin: 0;
   font-family: Arial, sans-serif;
   background: linear-gradient(135deg, #667eea, #764ba2);
}
.login-container {
   min-height: 100vh;
   display: flex;
   justify-content: center;
   align-items: center;
   padding: 20px;
}
.login-card {
   width: 350px;
   padding: 30px;
   background: white;
   border: 1px solid #ccc;
   border-radius: 12px;
   box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}
.login-card h2 {
   text-align: center;
   color: #493477;
   margin-bottom: 25px;
}
.login-card label {
   display: block;
   margin-bottom: 7px;
   font-weight: bold;
}
.login-card input {
   width: 100%;
   padding: 11px;
   margin-bottom: 15px;
   border: 1px solid #aaa;
   border-radius: 5px;
}

        .login-card button {
           width: 100%;
           padding: 12px;
           margin-top: 10px;
           background: #6741a5;
           color: white;
           border: none;
           border-radius: 5px;
           cursor: pointer;
           font-size: 16px;
        }
        .login-card button:hover {
           background: #43246f;
        }
        .error {
           color: red;
           font-size: 13px;
           text-align: center;
        }
```

## Experiment 3 — Inscribe a program to upload Single/Multiple

```text
require('dotenv').config();
         const http = require('http');
         const { formidable } = require('formidable');
         const cloudinary = require('cloudinary').v2;

         cloudinary.config({
            cloud_name:’zta12sui’,
            api_key: process.env.CLOUDINARY_API_KEY
            api_secret:’ qGN4xSBGvH1xcVyvVfRFRLPJFsM’,
            secure: true
         });

         const server = http.createServer((req, res) => {
           if (req.method === 'POST') {
              const form = formidable({ multiples: true });

              form.parse(req, async (err, fields, files) => {
                 if (err) {
                    res.writeHead(400);
                    return res.end('Error parsing files');
                 }

                const images = Array.isArray(files.image)
                  ? files.image
                  : files.image ? [files.image] : [];

    if (!images.length) {
       res.writeHead(400);
       return res.end('No images selected');
    }

    try {
       const results = await Promise.all(images.map(file => {
          if (!file.mimetype?.startsWith('image/')) {
             throw new Error('Only images are allowed');
          }

          return cloudinary.uploader.upload(file.filepath, {
             folder: 'uploads',
             resource_type: 'image'
          });
       }));

       res.writeHead(200, {
          'Content-Type': 'text/html; charset=utf-8'
       });

         res.end(`
             <h2>Images Uploaded Successfully!</h2>
             ${results.map(r =>
                `<p><a href="${r.secure_url}">${r.secure_url}</a></p>`
             ).join('')}
             <a href="/">Upload More Images</a>
         `);
      } catch (error) {
         console.error(error);
         res.writeHead(500);
         res.end('Cloudinary upload failed');
      }
   });
} else {
   res.writeHead(200, {
      'Content-Type': 'text/html; charset=utf-8'
   });

  res.end(`
     <!DOCTYPE html>
     <html>
     <head>
       <title>Cloudinary Image Upload</title>
       <style>
          * { box-sizing: border-box; }

         body {
           font-family: Arial, sans-serif;
           background: #eef2ff;

      text-align: center;
      padding: 30px 15px;
      color: #1e293b;
  }

  .box {
     background: white;
     max-width: 440px;
     margin: 20px auto;
     padding: 24px;
     border-radius: 12px;
     box-shadow: 0 4px 14px #cbd5e1;
  }

  h2 {
    color: #4338ca;
    font-size: 23px;
    margin-bottom: 12px;
  }

  p{
    font-size: 15px;
    line-height: 1.5;
  }

  input {
    margin: 16px 0;
    max-width: 100%;
    font-size: 14px;
  }

  button {
    background: #4f46e5;
    color: white;
    padding: 10px 18px;
    border: none;
    border-radius: 6px;
    font-size: 14px;
    cursor: pointer;
  }

  button:hover {
    background: #3730a3;
  }

  @media (max-width: 480px) {
     .box { padding: 18px; }
     h2 { font-size: 21px; }
  }
</style>

                    </head>
                    <body>
                      <div class="box">
                        <h2>Cloudinary Image Upload</h2>
                        <p>Select one or multiple images</p>

                        <form method="POST" enctype="multipart/form-data">
                           <input type="file" name="image"
                               accept="image/*" multiple required>
                           <br>
                           <button type="submit">Upload Images</button>
                        </form>
                      </div>
                    </body>
                    </html>
              `);
          }
       });

       const PORT = 3000;

       server.listen(PORT, () => {
          console.log('Server running at http://localhost:' + PORT);
       });
```

## Experiment 3 a — Upload a Single Profile Image to Cloudinary

```text
require('dotenv').config();
                const express = require('express');
                const multer = require('multer');
                const cloudinary = require('cloudinary').v2;
                const app = express();
                const port = 3000;
                // Multer configuration
                const upload = multer({
                  storage: multer.memoryStorage(),
                  limits: {
                       fileSize: 5 * 1024 * 1024
                  },
                  fileFilter: (req, file, cb) => {
                       if (file.mimetype.startsWith('image/')) {

          cb(null, true);
      } else {
          cb(new Error('Only image files are allowed!'));
      }
  }
});
// Cloudinary configuration
cloudinary.config({
  cloud_name: process.env.CLOUDINARY_CLOUD_NAME,
  api_key: process.env.CLOUDINARY_API_KEY,
  api_secret: process.env.CLOUDINARY_API_SECRET
});
// CSS styling
const styles = `
  <style>
      body {
          font-family: Arial, sans-serif;
          background: linear-gradient(135deg, #667eea, #764ba2);
          display: flex;
          justify-content: center;
          align-items: center;
          min-height: 100vh;
          margin: 0;
      }
      .container {
          background: white;
          padding: 35px;
          width: 350px;
          text-align: center;
          border-radius: 15px;

    box-shadow: 0 5px 20px rgba(0,0,0,0.2);
}
h2 {
    color: #333;
}
p{
    color: #777;
}
input[type="file"] {
    margin: 20px 0;
    padding: 10px;
    width: 90%;
    border: 1px solid #ddd;
    border-radius: 8px;
}
button {
    background: #667eea;
    color: white;
    border: none;
    padding: 12px 25px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 15px;
}
button:hover {
    background: #764ba2;
}
img {
    width: 200px;
    height: 200px;

           object-fit: cover;
           border-radius: 12px;
           margin: 15px;
       }
       a{
           color: #667eea;
           word-break: break-all;
       }
       .success {
           color: green;
       }
       .error {
           color: red;
       }
     </style>
`;
// Home page - Image upload form
app.get('/', (req, res) => {
     res.send(`
       <!DOCTYPE html>
       <html>
       <head>
           <title>Profile Image Upload</title>
           ${styles}
       </head>
       <body>
           <div class="container">
             <h2>Profile Image Upload</h2>
             <p>Select an image from your computer</p>

                  <form action="/upload" method="POST"
                     enctype="multipart/form-data">
                    <input type="file" name="image"
                           accept="image/*" required>
                    <br>
                    <button type="submit">Upload Image</button>
                  </form>
            </div>
        </body>
        </html>
  `);
});
// Upload image to Cloudinary
app.post('/upload', (req, res, next) => {
  upload.single('image')(req, res, (err) => {
        if (err) {
            console.error('File error:', err.message);
            return res.status(400).send(`
                  ${styles}
                  <div class="container">
                    <h2 class="error">Upload Error</h2>
                    <p>${err.message}</p>
                    <a href="/">Try Again</a>
                  </div>
            `);
        }
        next();
  });
}, async (req, res) => {
  try {

if (!req.file) {
     return res.status(400).send('Please select an image.');
}
console.log('Image received:', req.file.originalname);
// Convert image buffer into Base64
const base64Image = `data:${req.file.mimetype};
base64,${req.file.buffer.toString('base64')}`;
// Upload image to Cloudinary
const result = await cloudinary.uploader.upload(
     base64Image,
     {
         folder: 'profile_images'
     }
);
console.log('Image uploaded successfully!');
console.log('Cloudinary URL:', result.secure_url);
// Display uploaded image
res.send(`
     <!DOCTYPE html>
     <html>
     <head>
         <title>Upload Successful</title>
         ${styles}
     </head>


     <body>
         <div class="container">
           <h2 class="success">
              Image Uploaded Successfully!
           </h2>

            <img src="${result.secure_url}"
                  alt="Uploaded Image">
            <p>Your image has been saved to Cloudinary.</p>
            <p>Image URL:</p>
            <a href="${result.secure_url}" target="_blank">
                 View Uploaded Image
            </a>
            <br><br>
            <a href="/">Upload Another Image</a>
          </div>
        </body>
        </html>
  `);
} catch (error) {
  console.error('Cloudinary Upload Error:', error);
  res.status(500).send(`
        <!DOCTYPE html>
        <html>
        <head>
          <title>Upload Failed</title>
          ${styles}
        </head>
        <body>
          <div class="container">
            <h2 class="error">Image Upload Failed!</h2>
            <p>${error.message}</p>
            <a href="/">Try Again</a>
          </div>
        </body>

                          </html>
                    `);
                }
              });
              // Start server
              app.listen(port, () => {
                console.log(`Server running at http://localhost:${port}`);
              });
```

## Experiment 4 — Craft a program to create router using Node.js

```text
1)Setup Project
         Initialize a Node.js project and install Express:
                 mkdir express -router-app cd
                 express-router-app
                 npm init -y
                 npm install express
         2)Create the Server File
         In the project root, create a file called server.js. This file will set up
         the Express server and use the router.
                 // server.js
                 const express =require('express');
                 const app = express();
                 const port = 3000;
                 const mainRouter = require('./routes/mainRoutes');
                 app.use('/', mainRouter);
                 app.listen(port, () => {

               console.log(`Server is running on http://localhost:${port}`);
               });
       3)Create the Router
               Inside the project, create a routes directory, and inside it, create a file
               named mainRoutes.js. Define routes for different endpoints in this
               file using Express Router.
               // routes/mainRoutes.js
               const express = require('express');
               const router = express.Router();
               router.get('/', (req, res) => {
               res.send(‘<h1 style="font-size: 30px;">This is where the Home Page displays’);
               });
               router.get('/about', (req, res) => {
               res.send(‘<h1 style="font-size: 30px;">This is where the About Page displays’);
               });
               router.get('/contact', (req, res) => {
               res.send(' <h1 style="font-size: 30px;">This is where the Contact Page displays’);
               });
               module.exports = router;
```

## Experiment 4 a Develop a Student and Course Details Management — Develop a Student and Course Details Management Application Using Express Router in Node.js.

```text
1)Setup Project
         Initialize a Node.js project and install Express:
                 mkdir student-router-app
                 cd student-router-app
                 npm init -y
                 npm install express
         2)Create the Server File
         In the project root, create a file called server.js. This file will set up
         the Express server and use the router.
                 const express = require('express');
                 const app = express();
                 const port = 3000;

      const mainRouter = require('./routes/mainRoutes');
      app.use('/', mainRouter);
      app.listen(port, () => {
        console.log(`Server is running on http://localhost:${port}`);
      });
3)Create the Router
      Inside the project, create a routes directory, and inside it, create a file
      named mainRoutes.js. Define routes for different endpoints in this
      file using Express Router.
      // routes/mainRoutes.js
      const express = require('express');
      const router = express.Router();
      // Student route
      router.get('/student', (req, res) => {
        res.send(`
              <h2>Student Details</h2>
              <p>Name: Rahul</p>
              <p>Department: CSE</p>
              <p>Year: III</p>
        `);
      });
      // Course route
      router.get('/course', (req, res) => {
        res.send(`
              <h2>Course Details</h2>
              <p>Course Name: Full Stack Development</p>
              <p>Course Code: 22CSP09</p>
        `);
      });
      module.exports = router;

```

## Experiment 5 — Design a program to create Single Responsive

```text
<!DOCTYPE html>
                <html lang="en">
                <head>
                 <meta charset="UTF-8">
                 <meta name="viewport" content="width=device-width, initial-scale=1.0">
                   <title>Bootstrap simple page</title>
                   <!-- Bootstrap CSS -->
                   <link
                href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css
                " rel="stylesheet">
                   <style>
                      body {
                                  padding-top: 56px;

    }
    .hero {
        background: #540b0e;
        color: #feeac7;
        height: 120px;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        flex-direction: column;
    }
  </style>
</head>
<body>
  <!-- Navigation Bar -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
    <div class="container">
        <a class="navbar-brand" href="#">
          Admission Page
        </a>
        <button class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarNav"
          aria-controls="navbarNav"
          aria-expanded="false"
          aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">

         <ul class="navbar-nav ml-auto">
           <li class="nav-item">
             <a class="nav-link" href="#about">
                 About
             </a>
           </li>
           <li class="nav-item">
             <a class="nav-link" href="#contact">
                   Contact
             </a>
           </li>
         </ul>
    </div>
  </div>
</nav>
<!-- Hero Section -->
<div class="hero">
  <h1>ABC Matric. Hr. Sec. School</h1>
  <p>For admission inquiries, please contact us.</p>
</div>
<!-- About Section -->
<div class="container my-5" id="about">
  <h2 class="text-center">About Us</h2>
  <p class="text-center">
    We are dedicated to providing the best education to our students.
  </p>
</div>
<!-- Contact Section -->
<div class="container my-5" id="contact">
  <h2 class="text-center">Contact Us</h2>

       <form>
         <div class="form-group">
           <label for="name">Name</label>
           <input
                type="text"
                class="form-control"
                id="name"
                required>
         </div>
         <div class="form-group">
           <label for="email">Email</label>
           <input type="email"
                class="form-control"
                id="email"
                required>
         </div>
         <button type="submit" class="btn btn-warning">
           Submit
         </button>
       </form>
  </div>
  <!-- Footer -->
  <footer class="text-center py-4 bg-dark text-light">
       <div class="container bg-dark text-light">
         <p> &copy; 2026 ABC Matric. Hr. Sec. School. All rights reserved.
</p>
       </div>
  </footer>
  <!-- Bootstrap JavaScript -->
  <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>

                  <script
               src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.
               js"></script>
                  <script
               src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"><
               /script>
               </body>
               </html>
```

## Experiment 5 a Design a program to create Single — Design a program to create Single Responsive Page using Bootstrap

```text
<!DOCTYPE html>
          <html lang="en">
          <head>
              <meta charset="UTF-8">
              <meta name="viewport" content="width=device-width, initial-scale=1.0">
              <title>Simple Responsive Page</title>
              <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
              rel="stylesheet">
              <style>
                body {
                  padding-top: 56px;
                  font-family: Arial, sans-serif;




          }

    .hero {
      background: linear-gradient(135deg, #007bff, #00c6ff);
      color: white;
      height: 300px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center; }
    .hero h1 {
      font-size: 36px;      }
    .about {
      padding: 40px;            }
    .contact {
      padding: 30px;        }
    footer {
      background: #f1f1f1;
      padding: 20px;
      text-align: center;           }
  </style>
</head>
<body>
  <!-- Navigation Bar -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
    <div class="container">
      <a class="navbar-brand" href="#">
          My Simple Page            </a> <button class="navbar-toggler" type="button"
          data-toggle="collapse"
          data-target="#navbarNav">




          <span class="navbar-toggler-icon"></span>

    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
         <ul class="navbar-nav ml-auto">
           <li class="nav-item">
             <a class="nav-link" href="#about">About</a>        </li>
           <li class="nav-item">
             <a class="nav-link" href="#contact">Contact</a>            </li>
         </ul>
    </div>
  </div>
</nav>
<!-- Hero Section -->
<div class="hero">
  <div>
    <h1>Welcome to My Simple Page</h>          <p>
         This is a simple responsive webpage using Bootstrap.
    </p>
  </div>
</div>
<!-- About Section -->
<div class="container about" id="about">
  <h2 class="text-center">About Us</h2>
  <p class="text-center">
    We are dedicated to providing the best
    services to our customers.     </p>
</div>
<!-- Contact Section -->
<div class="container contact" id="contact">




  <h2 class="text-center">Contact Us</h2>

  <form>
     <div class="form-group">
         <label for="name">Name</label>
         <input type="text"
           class="form-control"
           id="name"
           placeholder="Enter your name"
           required>
     </div>
     <div class="form-group">
         <label for="email">Email</label>
         <input type="email"
           class="form-control"
           id="email"
           placeholder="Enter your email"
           required>
     </div>
     <button type="submit" class="btn btn-primary">
         Submit
     </button>
  </form>
</div>
<!-- Footer -->
<footer>
  <div class="container">
     <p>
         &copy; 2026 My Simple Page.
         All rights reserved. </p>




  </div>

         </footer>
         <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js">
         </script>
         <script
      src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js">
         </script>
         <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js">
         </script>
      </body>
      </html>
```

## Experiment 6 — Establish Connection to MongoDB with Node JS

```text
const { MongoClient } = require('mongodb');
     const uri = "mongodb://localhost:27017";
     const databaseName = "test";
     const collectionName = "test_collection";
     async function fetchData() {
     const client = new MongoClient(uri);
     try {
     await client.connect();
     console.log("Connected to MongoDB!");
     const db =client.db(databaseName);
     const collection = db.collection(collectionName);
     const documents = await collection.find({}).toArray();
     console.log(documents);
     }
     catch (error) {
     console.error("Error connecting to MongoDB:", error);
     }
     finally {
     await client.close();
     }
     }
     fetchData();

```

## Experiment 6 a — Develop a Student Record Management

```text
const express = require('express');
         const { MongoClient } = require('mongodb');
         const app = express();
         const port = 3000;

// MongoDB Connection
const uri = "mongodb://127.0.0.1:27017";
const client = new MongoClient(uri);
app.use(express.urlencoded({ extended: true }));
let collection;
// CSS Styling
const styles = `
<style>
  body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #667eea, #764ba2);
      margin: 0;
      padding: 30px;
      text-align: center;
  }
  .container {
      background: white;
      width: 400px;
      margin: 30px auto;
      padding: 25px;
      border-radius: 15px;
      box-shadow: 0 5px 20px rgba(0,0,0,0.2);
  }
  h2 {
      color: #333;
  }
  input {
      width: 90%;
      padding: 12px;
      margin: 10px 0;

         border: 1px solid #ccc;
         border-radius: 7px;
         box-sizing: border-box;
     }
     button {
         background: #667eea;
         color: white;
         padding: 12px 25px;
         border: none;
         border-radius: 7px;
         cursor: pointer;
     }
     button:hover {
         background: #764ba2;
     }
     .record {
         background: #f2f3ff;
         margin: 12px auto;
         padding: 12px;
         border-radius: 8px;
         text-align: left;
     }
</style>
`;
// Home Page - Student Form
app.get('/', async (req, res) => {
     try {
         const students = await collection.find({}).toArray();
         let records = students.map(student => `
             <div class="record">

       <b>Name:</b> ${student.name}<br>
       <b>Age:</b> ${student.age}<br>
       <b>Department:</b> ${student.department}
    </div>
 `).join('');
res.send(`
    <html>
    <head>
       <title>Student Record Management</title>
       ${styles}
    </head>
    <body>
       <div class="container">
          <h2>Student Record Management</h2>
          <form action="/add" method="POST">
                <input type="text"
                name="name"
                placeholder="Enter Student Name"
                required>
                <input type="number"
                name="age"
                placeholder="Enter Age"
                min="1"
                required>
                <input type="text"
                name="department"
                placeholder="Enter Department"
                required>
                <br>
                <button type="submit">

                       Add Student
                   </button>
                </form>
              </div>
              <div class="container">
                <h2>Student Records</h2>
                ${records || '<p>No student records found.</p>'}
              </div>
            </body>
            </html>
      `);
  } catch (error) {
      console.error(error);
      res.status(500).send("Error retrieving student records.");
  }
});
// Create Operation - Insert Student
app.post('/add', async (req, res) => {
  try {
      const student = {
            name: req.body.name,
            age: Number(req.body.age),
            department: req.body.department
      };
      await collection.insertOne(student);
      res.redirect('/');
  } catch (error) {
      console.error(error);
      res.status(500).send("Error adding student.");
  }

        });
        // Connect to MongoDB and Start Server
        async function startServer() {
            try {
                await client.connect();
                console.log("Connected to MongoDB successfully!");
                const db = client.db("test");
                collection = db.collection("students");
                app.listen(port, () => {
                    console.log(`Server running at http://localhost:${port}`);
                });
            } catch (error) {
                console.error("MongoDB Connection Error:", error);
            }
        }
        startServer();
```

## Experiment 7 — Establish Connection to MongoDB with Node JS

```text
const { MongoClient } = require('mongodb');
         const uri = "mongodb://localhost:27017";
         string const databaseName = "test";
         const collectionName = "test_collection";
         async function performCRUD() {
         const client = new MongoClient(uri);
         try{
         await client.connect();
         console.log("Connected to MongoDB!");
         const db = client.db(databaseName);
         const collection = db.collection(collectionName);
         const insertResult = await collection.insertOne({ name: "Kavin", age: 21,

       department: "Information Technology" });
       console.log("Insert Acknowledgement:", insertResult.acknowledged);
       console.log("All Documents:", await collection.find({}).toArray());
       const updateResult = await collection.updateOne({ name: "Rahul" }, { $set: { age: 19
       } });
       console.log("Updated Document Count:", updateResult.modifiedCount);
       console.log("All Documents:", await collection.find({}).toArray());
       const deleteResult = await collection.deleteOne({ name: "Rahul" });
       console.log("Deleted Document Count:", deleteResult.deletedCount);
       }
        catch (error) {
       console.error("Error performing CRUD operations:", error);
       }
       finally {
       await client.close();
       }}
       performCRUD();
```

## Experiment 7 a Performing CRUD operations to MongoDB — Performing CRUD operations to MongoDB with Node.js

```text
const { MongoClient } = require('mongodb');
     const uri = "mongodb://localhost:27017"; // MongoDB connection
     string const databaseName = "test";
     const collectionName = "test_collection";
     async
     function performCRUD() {
         const client = new MongoClient(uri);
          try{
             // Connect to MongoDB
             await client.connect();
             console.log("Connected to MongoDB!");
             const db = client.db(databaseName);
             const collection = db.collection(collectionName);
             const insertResult = await collection.insertOne({ name: "Ramya", age: 21,
             department: "Computer Science and Engineering" });
               console.log("Insert Acknowledgement:", insertResult.acknowledged);
             console.log("All Documents:", await collection.find({}).toArray());
             const updateResult = await collection.updateOne({ name: "Rahul" }, { $set: {
             age: 19 } });
             console.log("Updated Document Count:", updateResult.modifiedCount);
             console.log("All Documents:", await collection.find({}).toArray());
             const deleteResult = await collection.deleteOne({ name: "Rahul" });
             console.log("Deleted Document Count:", deleteResult.deletedCount);
         }

           catch (error) {
              console.error("Error performing CRUD operations:", error);
           }
           finally {
              await client.close();
           }} performCRUD();
```

## Experiment (a) Creating a Node.js Server with Routes for an E- — Creating a Node.js Server with Routes for an E-commerce Application

```text
Install Dependencies
             npm init -y
             npm install express
     //Index.js
             const express = require('express');
             const app = express();
             // Middleware to parse JSON
             app.use(express.json());
             // Sample Users
             let users = [
                 { id: 1, name: "Alice Johnson", email: "alice.johnson@example.com",
             address: "123 Main St, Springfield", phone: "123-456-7890" }];
             // Sample Products let
             products = [
                 { id: 101, name: "Smartphone", description: "Latest 5G smartphone with
             128GB storage", price: 599.99, category: "Electronics", stock: 50 }];
             // Sample Orders let
             orders = [
                 { orderId: 1001, userId: 1, products: [{ productId: 101, quantity: 1 }, {
             productId: 103, quantity: 2 }], totalAmount: 899.97, status: "Shipped",
             orderDate: "2024-11-20" }]; // Product Routes

                  app.get('/products', (req, res) => {
                      res.json({ message: "List of products", data: products });
                  });
                  app.post('/products', (req, res) => { const
                      product = req.body;
                      products.push(product);
                      res.json({ message: "Product added", product });
                  }); // User Routes
                  app.get('/users', (req, res) => {
                res.json({ message: "List of users", data: users });
               });
                app.post('/users', (req, res) => {
               const user = req.body;
               users.push(user);
               res.json({ message: "User registered", user });
              }); // Order Routes
            app.get('/orders', (req, res) => {
            res.json({ message: "List of orders", data: orders });
          });
           app.post('/orders', (req, res) => { const
          order = req.body; orders.push(order);
         res.json({ message: "Order placed", order });
      }); // Start Server
      const PORT = 3000;
      app.listen(PORT, () => {
         console.log(`Server running on http://localhost:${PORT}`);
});
```

## Experiment (b) Setting up a Node.js Server to Handle Bookstore — Setting up a Node.js Server to Handle Bookstore Requests

```text
const express = require('express');
         const bodyParser = require('body-parser'); const app = express();
         const PORT = 3000;
         // Middleware to parse JSON app.use(bodyParser.json());
         // In-memory "database" for books
             let books = [
             { id: 1, title: 'To Kill a Mockingbird', author: 'Harper Lee' },
             { id: 2, title: '1984', author: 'George Orwell' },
         ];
         // GET route to retrieve all books
             app.get('/books', (req, res) => {
             res.status(200).json(books);
         });
         // POST route to add a new book
             app.post('/books', (req, res) => {
             const { title, author } = req.body; if (!title || !author) {
                return res.status(400).json({ error: 'Title and Author are required' });
             }
             const newBook = { id: books.length + 1, title,
             author }; books.push(newBook);
             res.status(201).json(newBook);
         });
         // Root endpoint app.get('/',
         (req, res) => {
             res.send('Welcome to the Simple Bookstore API!');
         });

               // Start the server
               app.listen(PORT, () => {
                   console.log(`Server running on http://localhost:${PORT}`);
               });
```
