### **Part 1: Setup and Basic Project Structure**

### **Step 1: Install Node.js and npm**

- Download and install Node.js from [nodejs.org](https://nodejs.org/).
- Verify installation by running the following commands in your terminal:

  ```bash
  node -v
  npm -v
  ```

### **Step 2: Create a New React Application**

- Create a new React application using Create React App:

  ```bash
  npx create-react-app mui-tutorial
  cd mui-tutorial
  npm start
  ```

### **Step 3: Install Material-UI and Additional Dependencies**

- Install Material-UI and additional dependencies:

  ```bash
  npm install @mui/material @emotion/react @emotion/styled
  npm install @mui/icons-material
  npm install @mui/styles
  ```

### **Part 2: Theme Customization**

### **Step 1: Create a Theme File**

- Create a new file called `theme.js` in the `src` directory:

  ```jsx
  // src/theme.js
  import { createTheme } from "@mui/material/styles";

  const theme = createTheme({
    palette: {
      primary: {
        main: "#556cd6",
      },
      secondary: {
        main: "#19857b",
      },
    },
  });

  export default theme;
  ```

### **Step 2: Apply the Theme to Your Application**

- Modify the `index.js` file to apply the theme:

  ```jsx
  // src/index.js
  import React from "react";
  import ReactDOM from "react-dom";
  import { ThemeProvider } from "@mui/material/styles";
  import CssBaseline from "@mui/material/CssBaseline";
  import App from "./components/App";
  import theme from "./theme";

  ReactDOM.render(
    <ThemeProvider theme={theme}>
      <CssBaseline />
      <App />
    </ThemeProvider>,
    document.getElementById("root")
  );
  ```

### **Part 3: AppBar and Toolbar**

### **Step 1: Create the AppBarComponent**

- Create a new file called `AppBarComponent.js` in the `components` directory:

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
          <Typography variant="h6">MUI Tutorial</Typography>
        </Toolbar>
      </AppBar>
    );
  }

  export default AppBarComponent;
  ```

### **Step 2: Update App.js**

- Import and use `AppBarComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";

  function App() {
    const handleMenuClick = () => {
      console.log("Menu clicked");
    };

    return (
      <div>
        <AppBarComponent onMenuClick={handleMenuClick} />
      </div>
    );
  }

  export default App;
  ```

### **Part 4: Drawer (Sidebar)**

### **Step 1: Create the DrawerComponent**

- Create a new file called `DrawerComponent.js` in the `components` directory:

  ```jsx
  // src/components/DrawerComponent.js
  import React, { useState } from "react";
  import Drawer from "@mui/material/Drawer";
  import List from "@mui/material/List";
  import ListItem from "@mui/material/ListItem";
  import ListItemIcon from "@mui/material/ListItemIcon";
  import ListItemText from "@mui/material/ListItemText";
  import IconButton from "@mui/material/IconButton";
  import MenuIcon from "@mui/icons-material/Menu";
  import FavoriteIcon from "@mui/icons-material/Favorite";

  function DrawerComponent() {
    const [drawerOpen, setDrawerOpen] = useState(false);

    const toggleDrawer = (open) => (event) => {
      if (
        event.type === "keydown" &&
        (event.key === "Tab" || event.key === "Shift")
      ) {
        return;
      }
      setDrawerOpen(open);
    };

    return (
      <>
        <Drawer anchor="left" open={drawerOpen} onClose={toggleDrawer(false)}>
          <List>
            {["Inbox", "Starred", "Send email", "Drafts"].map((text, index) => (
              <ListItem button key={text}>
                <ListItemIcon>
                  <FavoriteIcon />
                </ListItemIcon>
                <ListItemText primary={text} />
              </ListItem>
            ))}
          </List>
        </Drawer>
        <IconButton
          edge="start"
          color="inherit"
          aria-label="menu"
          onClick={toggleDrawer(true)}
        >
          <MenuIcon />
        </IconButton>
      </>
    );
  }

  export default DrawerComponent;
  ```

### **Step 2: Update App.js**

- Import and use `DrawerComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 5: Buttons**

### **Step 1: Create the ButtonComponent**

- Create a new file called `ButtonComponent.js` in the `components` directory:

  ```jsx
  // src/components/ButtonComponent.js
  import React from "react";
  import Button from "@mui/material/Button";
  import HomeIcon from "@mui/icons-material/Home";

  function ButtonComponent() {
    return (
      <div style={{ padding: 16 }}>
        <Button variant="contained" color="primary" startIcon={<HomeIcon />}>
          Home
        </Button>
        <Button variant="outlined" color="secondary" style={{ marginLeft: 8 }}>
          Secondary Button
        </Button>
        <Button variant="text" style={{ marginLeft: 8 }}>
          Default Button
        </Button>
      </div>
    );
  }

  export default ButtonComponent;
  ```

### **Step 2: Update App.js**

- Import and use `ButtonComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 6: Icons**

### **Step 1: Create the IconComponent**

- Create a new file called `IconComponent.js` in the `components` directory:

  ```jsx
  // src/components/IconComponent.js
  import React from "react";
  import HomeIcon from "@mui/icons-material/Home";
  import IconButton from "@mui/material/IconButton";

  function IconComponent() {
    return (
      <IconButton color="primary">
        <HomeIcon />
      </IconButton>
    );
  }

  export default IconComponent;
  ```

### **Step 2: Update App.js**

- Import and use `IconComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 7: Avatar**

### **Step 1: Create the AvatarComponent**

- Create a new file called `AvatarComponent.js` in the `components` directory:

  ```jsx
  // src/components/AvatarComponent.js
  import React from "react";
  import Avatar from "@mui/material/Avatar";
  import AccountCircleIcon from "@mui/icons-material/AccountCircle";

  function AvatarComponent() {
    return (
      <Avatar>
        <AccountCircleIcon />
      </Avatar>
    );
  }

  export default AvatarComponent;
  ```

### **Step 2: Update App.js**

- Import and use `AvatarComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from 'react';
  import AppBarComponent from './AppBarComponent';
  import DrawerComponent from './DrawerComponent';
  import ButtonComponent from './ButtonComponent';
  import IconComponent from './IconComponent';
  import AvatarComponent from './AvatarComponent';

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />

  ```

 <DrawerComponent />
          <ButtonComponent />
          <IconComponent />
          <AvatarComponent />
        </div>
      );
    }

    export default App;
    ```

### **Part 8: Typography**

### **Step 1: Create the TypographyComponent**

- Create a new file called `TypographyComponent.js` in the `components` directory:

  ```jsx
  // src/components/TypographyComponent.js
  import React from "react";
  import Typography from "@mui/material/Typography";

  function TypographyComponent() {
    return (
      <div style={{ padding: 16 }}>
        <Typography variant="h1" component="h2">
          h1. Heading
        </Typography>
        <Typography variant="body1">Body text</Typography>
      </div>
    );
  }

  export default TypographyComponent;
  ```

### **Step 2: Update App.js**

- Import and use `TypographyComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 9: Grid System**

### **Step 1: Create the GridComponent**

- Create a new file called `GridComponent.js` in the `components` directory:

  ```jsx
  // src/components/GridComponent.js
  import React from "react";
  import Grid from "@mui/material/Grid";
  import Box from "@mui/material/Box";
  import Typography from "@mui/material/Typography";

  function GridComponent() {
    return (
      <Grid container spacing={2} style={{ padding: 16 }}>
        <Grid item xs={12} sm={6}>
          <Box bgcolor="background.paper" p={2}>
            <Typography variant="h6">Grid Item 1</Typography>
          </Box>
        </Grid>
        <Grid item xs={12} sm={6}>
          <Box bgcolor="background.paper" p={2}>
            <Typography variant="h6">Grid Item 2</Typography>
          </Box>
        </Grid>
      </Grid>
    );
  }

  export default GridComponent;
  ```

### **Step 2: Update App.js**

- Import and use `GridComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";
  import GridComponent from "./GridComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
        <GridComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 10: Box Component**

### **Step 1: Update GridComponent to use Box Component**

- Modify the `GridComponent.js` file to include `Box` components:

  ```jsx
  // src/components/GridComponent.js
  import React from "react";
  import Grid from "@mui/material/Grid";
  import Box from "@mui/material/Box";
  import Typography from "@mui/material/Typography";

  function GridComponent() {
    return (
      <Grid container spacing={2} style={{ padding: 16 }}>
        <Grid item xs={12} sm={6}>
          <Box bgcolor="grey.300" p={2}>
            <Typography variant="h6">Grid Item 1</Typography>
          </Box>
        </Grid>
        <Grid item xs={12} sm={6}>
          <Box bgcolor="grey.300" p={2}>
            <Typography variant="h6">Grid Item 2</Typography>
          </Box>
        </Grid>
      </Grid>
    );
  }

  export default GridComponent;
  ```

### **Part 11: CircularProgress**

### **Step 1: Create the CircularProgressComponent**

- Create a new file called `CircularProgressComponent.js` in the `components` directory:

  ```jsx
  // src/components/CircularProgressComponent.js
  import React from "react";
  import CircularProgress from "@mui/material/CircularProgress";

  function CircularProgressComponent() {
    return (
      <div style={{ marginTop: 16 }}>
        <CircularProgress />
      </div>
    );
  }

  export default CircularProgressComponent;
  ```

### **Step 2: Update App.js**

- Import and use `CircularProgressComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";
  import GridComponent from "./GridComponent";
  import CircularProgressComponent from "./CircularProgressComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
        <GridComponent />
        <CircularProgressComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 12: Modal**

### **Step 1: Create the ModalComponent**

- Create a new file called `ModalComponent.js` in the `components` directory:

  ```jsx
  // src/components/ModalComponent.js
  import React, { useState } from "react";
  import Modal from "@mui/material/Modal";
  import Box from "@mui/material/Box";
  import Typography from "@mui/material/Typography";
  import Button from "@mui/material/Button";

  function ModalComponent() {
    const [modalOpen, setModalOpen] = useState(false);

    const toggleModal = () => {
      setModalOpen(!modalOpen);
    };

    return (
      <>
        <Button
          variant="contained"
          color="secondary"
          onClick={toggleModal}
          style={{ marginTop: 16 }}
        >
          Open Modal
        </Button>
        <Modal
          open={modalOpen}
          onClose={toggleModal}
          aria-labelledby="simple-modal-title"
          aria-describedby="simple-modal-description"
        >
          <Box p={4} bgcolor="background.paper" m="auto">
            <Typography variant="h6" id="simple-modal-title">
              Text in a modal
            </Typography>
            <Typography variant="subtitle1" id="simple-modal-description">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit.
            </Typography>
          </Box>
        </Modal>
      </>
    );
  }

  export default ModalComponent;
  ```

### **Step 2: Update App.js**

- Import and use `ModalComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";
  import GridComponent from "./GridComponent";
  import CircularProgressComponent from "./CircularProgressComponent";
  import ModalComponent from "./ModalComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
        <GridComponent />
        <CircularProgressComponent />
        <ModalComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 13: ButtonGroup**

### **Step 1: Create the ButtonGroupComponent**

- Create a new file called `ButtonGroupComponent.js` in the `components` directory:

  ```jsx
  // src/components/ButtonGroupComponent.js
  import React from "react";
  import ButtonGroup from "@mui/material/ButtonGroup";
  import Button from "@mui/material/Button";

  function ButtonGroupComponent() {
    return (
      <ButtonGroup
        variant="contained"
        color="primary"
        aria-label="contained primary button group"
        style={{ marginTop: 16 }}
      >
        <Button>One</Button>
        <Button>Two</Button>
        <Button>Three</Button>
      </ButtonGroup>
    );
  }

  export default ButtonGroupComponent;
  ```

### **Step 2: Update App.js**

- Import and use `ButtonGroupComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from 'react';
  import AppBarComponent from './AppBarComponent';
  import DrawerComponent from './DrawerComponent';
  import ButtonComponent from './ButtonComponent';
  import IconComponent from './IconComponent';
  import AvatarComponent from './AvatarComponent';
  import TypographyComponent from './TypographyComponent';
  import GridComponent from './GridComponent
  ```

';
import CircularProgressComponent from './CircularProgressComponent';
import ModalComponent from './ModalComponent';
import ButtonGroupComponent from './ButtonGroupComponent';

    function App() {
      return (
        <div>
          <AppBarComponent onMenuClick={() => {}} />
          <DrawerComponent />
          <ButtonComponent />
          <IconComponent />
          <AvatarComponent />
          <TypographyComponent />
          <GridComponent />
          <CircularProgressComponent />
          <ModalComponent />
          <ButtonGroupComponent />
        </div>
      );
    }

    export default App;
    ```

### **Part 14: Rating**

### **Step 1: Create the RatingComponent**

- Create a new file called `RatingComponent.js` in the `components` directory:

  ```jsx
  // src/components/RatingComponent.js
  import React, { useState } from "react";
  import Rating from "@mui/material/Rating";
  import Box from "@mui/material/Box";

  function RatingComponent() {
    const [rating, setRating] = useState(2);

    return (
      <Box my={2}>
        <Rating
          name="simple-controlled"
          value={rating}
          onChange={(event, newValue) => {
            setRating(newValue);
          }}
        />
      </Box>
    );
  }

  export default RatingComponent;
  ```

### **Step 2: Update App.js**

- Import and use `RatingComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";
  import GridComponent from "./GridComponent";
  import CircularProgressComponent from "./CircularProgressComponent";
  import ModalComponent from "./ModalComponent";
  import ButtonGroupComponent from "./ButtonGroupComponent";
  import RatingComponent from "./RatingComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
        <GridComponent />
        <CircularProgressComponent />
        <ModalComponent />
        <ButtonGroupComponent />
        <RatingComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 15: TextField**

### **Step 1: Create the TextFieldComponent**

- Create a new file called `TextFieldComponent.js` in the `components` directory:

  ```jsx
  // src/components/TextFieldComponent.js
  import React, { useState } from "react";
  import TextField from "@mui/material/TextField";
  import InputAdornment from "@mui/material/InputAdornment";
  import FavoriteIcon from "@mui/icons-material/Favorite";
  import Box from "@mui/material/Box";

  function TextFieldComponent() {
    const [inputValue, setInputValue] = useState("");

    return (
      <Box my={2}>
        <TextField
          label="Input Field"
          value={inputValue}
          onChange={(e) => setInputValue(e.target.value)}
          InputProps={{
            startAdornment: (
              <InputAdornment position="start">
                <FavoriteIcon />
              </InputAdornment>
            ),
          }}
        />
      </Box>
    );
  }

  export default TextFieldComponent;
  ```

### **Step 2: Update App.js**

- Import and use `TextFieldComponent` in `App.js`:

  ```jsx
  // src/components/App.js
  import React from "react";
  import AppBarComponent from "./AppBarComponent";
  import DrawerComponent from "./DrawerComponent";
  import ButtonComponent from "./ButtonComponent";
  import IconComponent from "./IconComponent";
  import AvatarComponent from "./AvatarComponent";
  import TypographyComponent from "./TypographyComponent";
  import GridComponent from "./GridComponent";
  import CircularProgressComponent from "./CircularProgressComponent";
  import ModalComponent from "./ModalComponent";
  import ButtonGroupComponent from "./ButtonGroupComponent";
  import RatingComponent from "./RatingComponent";
  import TextFieldComponent from "./TextFieldComponent";

  function App() {
    return (
      <div>
        <AppBarComponent onMenuClick={() => {}} />
        <DrawerComponent />
        <ButtonComponent />
        <IconComponent />
        <AvatarComponent />
        <TypographyComponent />
        <GridComponent />
        <CircularProgressComponent />
        <ModalComponent />
        <ButtonGroupComponent />
        <RatingComponent />
        <TextFieldComponent />
      </div>
    );
  }

  export default App;
  ```

### **Part 16: Toggle Color Mode**

### **Step 1: Create the ToggleColorModeProvider**

- Create a new file called `ToggleColorModeProvider.js` in the `components` directory:

  ```jsx
  // src/components/ToggleColorModeProvider.js
  import React, { createContext, useMemo, useState } from "react";
  import { ThemeProvider, createTheme } from "@mui/material/styles";
  import CssBaseline from "@mui/material/CssBaseline";

  export const ColorModeContext = createContext({ toggleColorMode: () => {} });

  function ToggleColorModeProvider({ children }) {
    const [mode, setMode] = useState("light");
    const colorMode = useMemo(
      () => ({
        toggleColorMode: () => {
          setMode((prevMode) => (prevMode === "light" ? "dark" : "light"));
        },
      }),
      []
    );

    const theme = useMemo(
      () =>
        createTheme({
          palette: {
            mode,
          },
        }),
      [mode]
    );

    return (
      <ColorModeContext.Provider value={colorMode}>
        <ThemeProvider theme={theme}>
          <CssBaseline />
          {children}
        </ThemeProvider>
      </ColorModeContext.Provider>
    );
  }

  export default ToggleColorModeProvider;
  ```

### **Update AppBarComponent to Include Toggle Button**

### **1. AppBarComponent.js**

Update `AppBarComponent.js` to include the toggle button:

```jsx
// src/components/AppBarComponent.js
import React from "react";
import AppBar from "@mui/material/AppBar";
import Toolbar from "@mui/material/Toolbar";
import Typography from "@mui/material/Typography";
import IconButton from "@mui/material/IconButton";
import MenuIcon from "@mui/icons-material/Menu";
import Brightness4Icon from "@mui/icons-material/Brightness4";
import Brightness7Icon from "@mui/icons-material/Brightness7";
import { useTheme } from "@mui/material/styles";
import { ColorModeContext } from "./ToggleColorModeProvider";

function AppBarComponent({ onMenuClick }) {
  const theme = useTheme();
  const colorMode = React.useContext(ColorModeContext);

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
          MUI Tutorial
        </Typography>
        <IconButton color="inherit" onClick={colorMode.toggleColorMode}>
          {theme.palette.mode === "dark" ? (
            <Brightness7Icon />
          ) : (
            <Brightness4Icon />
          )}
        </IconButton>
      </Toolbar>
    </AppBar>
  );
}

export default AppBarComponent;
```

### **Update App.js to Remove the Toggle Button**

Since the toggle button is now included in the `AppBarComponent`, you can remove it from `App.js`:

### **2. App.js**

Update `App.js` to remove the toggle button:

```jsx
// src/components/App.js
import React from "react";
import { CssBaseline } from "@mui/material";
import AppBarComponent from "./AppBarComponent";
import DrawerComponent from "./DrawerComponent";
import ButtonComponent from "./ButtonComponent";
import IconComponent from "./IconComponent";
import AvatarComponent from "./AvatarComponent";
import TypographyComponent from "./TypographyComponent";
import GridComponent from "./GridComponent";
import CircularProgressComponent from "./CircularProgressComponent";
import ModalComponent from "./ModalComponent";
import ButtonGroupComponent from "./ButtonGroupComponent";
import RatingComponent from "./RatingComponent";
import TextFieldComponent from "./TextFieldComponent";

function App() {
  return (
    <>
      <CssBaseline />
      <AppBarComponent onMenuClick={() => {}} />
      <DrawerComponent />
      <ButtonComponent />
      <IconComponent />
      <AvatarComponent />
      <TypographyComponent />
      <GridComponent />
      <CircularProgressComponent />
      <ModalComponent />
      <ButtonGroupComponent />
      <RatingComponent />
      <TextFieldComponent />
    </>
  );
}

export default App;
```

### **Ensure the Theme is Applied Correctly**

Ensure your `index.js` applies the theme correctly:

### **3. index.js**

```jsx
// src/index.js
import React from "react";
import ReactDOM from "react-dom/client";
import ToggleColorModeProvider from "./components/ToggleColorModeProvider";
import App from "./components/App";
import "./index.css";

const rootElement = document.getElementById("root");
const root = ReactDOM.createRoot(rootElement);

root.render(
  <ToggleColorModeProvider>
    <App />
  </ToggleColorModeProvider>
);
```

With these changes, your application should now have a working dark mode toggle button integrated into the AppBar. The `ToggleColorModeProvider` manages the theme state and provides a context for toggling the color mode

. The `AppBarComponent` includes a button that allows users to switch between light and dark modes.
