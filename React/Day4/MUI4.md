### **1. Update AppBarComponent**

First, update the `AppBarComponent` to include a button to open the sidebar.

```jsx
// src/components/AppBarComponent.js
import React from "react";
import AppBar from "@mui/material/AppBar";
import Toolbar from "@mui/material/Toolbar";
import Typography from "@mui/material/Typography";
import IconButton from "@mui/material/IconButton";
import MenuIcon from "@mui/icons-material/Menu";

function AppBarComponent({ onMenuClick }) {
  return (
    <AppBar position="static">
      <Toolbar>
        <IconButton
          edge="start"
          color="inherit"
          aria-label="menu"
          onClick={onMenuClick}
        >
          <MenuIcon />
        </IconButton>
        <Typography variant="h6" style={{ flexGrow: 1 }}>
          TMDB Movies
        </Typography>
      </Toolbar>
    </AppBar>
  );
}

export default AppBarComponent;
```

### **2. Create DrawerComponent**

Next, create a `DrawerComponent` for the sidebar navigation.

```jsx
// src/components/DrawerComponent.js
import React from "react";
import Drawer from "@mui/material/Drawer";
import List from "@mui/material/List";
import ListItem from "@mui/material/ListItem";
import ListItemIcon from "@mui/material/ListItemIcon";
import ListItemText from "@mui/material/ListItemText";
import HomeIcon from "@mui/icons-material/Home";
import MovieIcon from "@mui/icons-material/Movie";
import InfoIcon from "@mui/icons-material/Info";

function DrawerComponent({ open, onClose }) {
  return (
    <Drawer anchor="left" open={open} onClose={onClose}>
      <List>
        <ListItem button>
          <ListItemIcon>
            <HomeIcon />
          </ListItemIcon>
          <ListItemText primary="Home" />
        </ListItem>
        <ListItem button>
          <ListItemIcon>
            <MovieIcon />
          </ListItemIcon>
          <ListItemText primary="Movies" />
        </ListItem>
        <ListItem button>
          <ListItemIcon>
            <InfoIcon />
          </ListItemIcon>
          <ListItemText primary="About" />
        </ListItem>
      </List>
    </Drawer>
  );
}

export default DrawerComponent;
```

### **3. Update MainContent and Footer**

Update the `MainContent` and `Footer` components as needed.

**MainContent.js**

```jsx
// src/components/MainContent.js
import React from "react";
import MovieGrid from "./MovieGrid";

function MainContent() {
  return (
    <div style={{ flex: 1, padding: "16px" }}>
      <MovieGrid />
    </div>
  );
}

export default MainContent;
```

**Footer.js**

```jsx
// src/components/Footer.js
import React from "react";
import Button from "@mui/material/Button";
import HomeIcon from "@mui/icons-material/Home";

function Footer() {
  return (
    <div style={{ padding: "16px", display: "flex", justifyContent: "center" }}>
      <Button variant="contained" color="primary" startIcon={<HomeIcon />}>
        Home
      </Button>
    </div>
  );
}

export default Footer;
```

### **4. Update App.js to Include Drawer State Management**

Update the `App.js` file to manage the state of the drawer and pass the necessary props to `AppBarComponent` and `DrawerComponent`.

```jsx
// src/App.js
import React, { useState } from "react";
import { CssBaseline } from "@mui/material";
import AppBarComponent from "./components/AppBarComponent";
import DrawerComponent from "./components/DrawerComponent";
import MainContent from "./components/MainContent";
import Footer from "./components/Footer";

function App() {
  const [drawerOpen, setDrawerOpen] = useState(false);

  const handleDrawerToggle = () => {
    setDrawerOpen(!drawerOpen);
  };

  return (
    <div
      style={{ display: "flex", flexDirection: "column", minHeight: "100vh" }}
    >
      <CssBaseline />
      <AppBarComponent onMenuClick={handleDrawerToggle} />
      <DrawerComponent open={drawerOpen} onClose={handleDrawerToggle} />
      <MainContent />
      <Footer />
    </div>
  );
}

export default App;
```

### **5. Ensure All Components are Properly Styled**

Add any necessary CSS styles to ensure the layout looks good.

**index.css**

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

### **6. Run Your Application**

Start your application by running:

```bash
npm start
```

### **Summary**

In this extended tutorial, we added a header (AppBar) and a sidebar (Drawer) to the React application. The AppBar includes a menu button that toggles the Drawer. The Drawer contains navigation links. We also used the MovieGrid component to display movies fetched from the TMDB API in a grid layout, and the Footer component to place the Home button at the bottom of the page.

This setup provides a basic structure for a more interactive and navigable application. You can further enhance the application by adding routing for different pages, handling navigation actions, and styling the components to match your design requirements.
