
## Layout design graphical interface



Here you can assemble the skeleton of a building and populate default configuration files.
You can also view results after running a simulation.

The layout editor allows you to visually design a multi-room building system by creating rooms, defining apertures between them, and reviewing how air transport flows through your layout.

When you first open the editor, you'll see a blank canvas on the left and a toolbar at the top. The interface allows you to create rooms, connect them, and then request the backend to compute transport paths through your design.

#### Starting

```bash
python run_mbm_ui.py
```

This python script should start the UI in a browser

#### Creating Rooms

To add a new room to your layout, click the "Add Room" button in the toolbar. A new room will appear on the canvas with a default name like "Room 1". You can drag the room anywhere on the canvas to position it, and resize it by dragging the corner. Double clicking on the name allows the name to be changed

Each room has editable properties displayed in the JSON editor panel on the right side of the screen. Click on a room to select it and see its JSON data. You can modify the room's properties directly in the JSON editor, such as changing its name or adding custom properties. 

#### Creating Apertures

Apertures represent openings between rooms or between a room and the outside. To create an aperture, click the "Link Mode" button in the toolbar to enter linking mode. The interface will show a banner indicating that you're ready to create connections.

In link mode, you can create connections in two ways:

1. **Between two rooms**: Select two rooms by clicking on them. An aperture will automatically be created between the selected rooms.

2. **Between a room and the outside**: Select a single room and then click on one of the four directional buttons (Front, Back, Left, Right) to create an opening on that side of the room.

Each aperture can be edited to set its area. Click on an aperture to select it and modify its properties in the JSON editor.

#### Viewing Transport Paths

Once you've created your room layout with apertures, you can request the backend to calculate transport paths through your system. Click the "Transport Paths" button to analyse how air flows through the connections you've defined.


#### Saving and Loading Your Layouts

Your work can be saved for later use. Click the "Save Layout" button to export your design. The system will save individual JSON files for each room as well as a master layout file containing the overall structure and aperture connections.
The saved json files can act as the start of your configuration for running.

To restore a previous design, click the "Load Layout" button and select your saved layout file. The editor will reconstruct your entire room configuration, apertures, and positioning, allowing you to continue editing where you left off.

#### Viewing Simulation Results

After running simulations in the backend, you can visualize the results directly in the layout editor. Click the "View Results" button to load a results file (pickle file) from a completed simulation.

Once loaded, you can select which chemical species to display and choose a specific time point from your simulation. The rooms in your layout will be coloured according to the concentration levels of the selected species at that time, providing an instant visual representation of how pollutants or other chemicals distribute through your building over time. You can switch between different species and time points to explore various aspects of your simulation results.

