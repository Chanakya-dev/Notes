# MUI-IMDB-Movie-page

This tutorial assumes you have basic knowledge of React and JavaScript.

### **Step 1: Set Up the Project**

1. **Create a New React Application**

   ```bash
   npx create-react-app mui-tmdb-app
   cd mui-tmdb-app
   ```

2. **Install MUI (Material-UI)**

   ```bash
   npm install @mui/material @emotion/react @emotion/styled
   npm install @mui/icons-material
   ```

3. **Sign Up for TMDB API**
   - Go to [The Movie Database (TMDB) API](https://www.themoviedb.org/documentation/api) and sign up for an account.
   - Create an API key.

### **Step 2: Create a Simple Layout**

1. **AppBarComponent.js**

   Create an AppBar component to display the header.

   ```jsx
   // src/components/AppBarComponent.js
   import React from "react";
   import AppBar from "@mui/material/AppBar";
   import Toolbar from "@mui/material/Toolbar";
   import Typography from "@mui/material/Typography";

   function AppBarComponent() {
     return (
       <AppBar position="static">
         <Toolbar>
           <Typography variant="h6">TMDB Movies</Typography>
         </Toolbar>
       </AppBar>
     );
   }

   export default AppBarComponent;
   ```

2. **MovieGrid.js**

   Create a MovieGrid component to display movies in a grid.

   ```jsx
   // src/components/MovieGrid.js
   import React, { useEffect, useState } from "react";
   import Grid from "@mui/material/Grid";
   import Card from "@mui/material/Card";
   import CardContent from "@mui/material/CardContent";
   import CardMedia from "@mui/material/CardMedia";
   import Typography from "@mui/material/Typography";
   import { makeStyles } from "@mui/styles";

   const useStyles = makeStyles({
     card: {
       maxWidth: 345,
     },
     media: {
       height: 500,
     },
   });

   function MovieGrid() {
     const classes = useStyles();
     const [movies, setMovies] = useState([]);

     useEffect(() => {
       const fetchMovies = async () => {
         const response = await fetch(
           `https://api.themoviedb.org/3/movie/popular?api_key=YOUR_API_KEY`
         );
         const data = await response.json();
         setMovies(data.results);
       };

       fetchMovies();
     }, []);

     return (
       <Grid container spacing={4} style={{ padding: "16px" }}>
         {movies.map((movie) => (
           <Grid item key={movie.id} xs={12} sm={6} md={4} lg={3}>
             <Card className={classes.card}>
               <CardMedia
                 className={classes.media}
                 image={`https://image.tmdb.org/t/p/w500/${movie.poster_path}`}
                 title={movie.title}
               />
               <CardContent>
                 <Typography variant="h6" component="h2">
                   {movie.title}
                 </Typography>
                 <Typography
                   variant="body2"
                   color="textSecondary"
                   component="p"
                 >
                   {movie.overview}
                 </Typography>
               </CardContent>
             </Card>
           </Grid>
         ))}
       </Grid>
     );
   }

   export default MovieGrid;
   ```

3. **App.js**

   Update the App component to include the AppBar and MovieGrid components.

   ```jsx
   // src/App.js
   import React from "react";
   import CssBaseline from "@mui/material/CssBaseline";
   import AppBarComponent from "./components/AppBarComponent";
   import MovieGrid from "./components/MovieGrid";

   function App() {
     return (
       <>
         <CssBaseline />
         <AppBarComponent />
         <MovieGrid />
       </>
     );
   }

   export default App;
   ```

4. **index.js**

   Make sure to import the App component in your entry file.

   ```jsx
   // src/index.js
   import React from "react";
   import ReactDOM from "react-dom";
   import "./index.css";
   import App from "./App";

   ReactDOM.render(
     <React.StrictMode>
       <App />
     </React.StrictMode>,
     document.getElementById("root")
   );
   ```

5. **index.css**

   (Optional) Add some basic styles.

   ```css
   /* src/index.css */
   body {
     margin: 0;
     font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto",
       "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans",
       "Helvetica Neue", sans-serif;
     -webkit-font-smoothing: antialiased;
     -moz-osx-font-smoothing: grayscale;
   }

   code {
     font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
       monospace;
   }

   #root {
     display: flex;
     flex-direction: column;
     min-height: 100vh;
   }
   ```

### **Step 3: Run Your Application**

Start your application by running:

```bash
npm start
```

### **Summary**

In this tutorial, we created a simple React application using MUI to fetch and display movies from the TMDB API. We set up an AppBar for the header, and used a grid layout to display the movies. You can further enhance this application by adding more features like search, pagination, or additional movie details.
