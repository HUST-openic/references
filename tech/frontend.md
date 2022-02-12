[TOC]

# Web-based frontend design

Current plan:  Vue.js3 + Vite + Tailwind + Xterm.js (for terminals).

## Overall design

### Compositions - the first layer.

*Composition* are the neccessary parts of the app, it should always **exist** and root in the first layer of the app, and can be:

- **Switched** to be hidden or display - P0.

- Covered by popups. - P0

- **Organizable**. - P2

- **Responsive** while other *compositions* change it's status. -P2

#### Terminals & Console

### Options

Those are buttons/blocks containing adjustable params & optional actions, held in compositions. We can say that *composition* is a collection of certain class of *options* that must be selected/toggled/changed.

### Popups - the second layer and above.

*Popups* can be put on *components* and other *popups*, visually covering them. 

They work as:

- Detail cards for component options. For example, click component option and call out a popup to change it's settings or parameters, etc.
  
  - They can be:
    
    - Closed.
    
    - Hidden or displaying.
    
    - Minimized.
    
    - Chained to open other popups.
    
    - Collected in a brower bar, like tabs in browsers.

- Option Menu that give your more action choices towards an option, which can be chained. Think about the right click menu on Windows.
