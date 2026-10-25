# CS-340-Client-Server

About the Project
This project is a client-facing dashboard for Grazioso Salvare that connects to the Austin Animal Center MongoDB database. The dashboard uses the CRUD Python module developed in Project One to retrieve animal records and display them through an interactive web application. Users can filter dogs based on the rescue-training requirements provided by Grazioso Salvare. The available options are Water Rescue, Mountain or Wilderness Rescue, Disaster or Individual Tracking, and Reset. The dashboard also includes an interactive data table, a breed pie chart, and a geolocation map.
The application follows the Model-View-Controller design pattern. MongoDB acts as the model by storing the animal records. The CRUD Python module and Dash callbacks provide the controller logic that retrieves and processes the data. The dashboard components provide the view that the user interacts with.

Motivation
The purpose of this project is to help Grazioso Salvare identify dogs that may be good candidates for search-and-rescue training. Different rescue roles require different breeds, ages, and sexes, so manually searching thousands of shelter records would take time and could make it easier to overlook qualified animals.
The dashboard simplifies this process by allowing the user to select a rescue category and automatically retrieve dogs that match the required criteria. The pie chart provides a visual representation of the breeds returned by the filter, while the geolocation map shows the location associated with the selected animal.

Getting Started
This project uses the aac MongoDB database and the animals collection created from the Austin Animal Center Outcomes dataset. Authentication is handled through the aacuser account.
The main dashboard is contained in ProjectTwoDashboard.ipynb. The dashboard imports the AnimalShelter class from CRUD_Python_Module.py and uses the CRUD module to retrieve data from MongoDB.
The dashboard begins by loading the complete Austin Animal Center dataset. After the dashboard starts, the user can select one of the rescue filters to retrieve dogs that match the required criteria.
To run the project in Codio, open ProjectTwoDashboard.ipynb in Jupyter Lab and run the notebook. The Dash server will start and provide a link that opens the dashboard in a web browser.

Installation
The main tools used for this project are Python, MongoDB, PyMongo, Jupyter Lab, Codio, Dash, Plotly, and Dash Leaflet.
Python is used for the main application logic and the CRUD module. MongoDB stores the Austin Animal Center records. MongoDB works well for this project because its document-based structure can store the animal records and allows specific groups of records to be retrieved with queries.
PyMongo provides the connection between Python and MongoDB. The CRUD module uses PyMongo to access the aac database and the animals collection.
Dash provides the framework used to build the interactive web dashboard. Dash callbacks connect the filtering controls to the data table and charts so the dashboard updates when the user makes a selection.
Plotly is used to create the breed pie chart. Dash Leaflet is used to create the geolocation map and display the selected animal's location.
Jupyter Lab is used to run and test ProjectTwoDashboard.ipynb, while Codio provides the development environment for the project.
For a local setup, Python, MongoDB, Jupyter, PyMongo, Dash, Plotly, and Dash Leaflet would need to be installed and configured before running the project.

Usage
The dashboard provides four interactive rescue filtering options: Water Rescue, Mountain or Wilderness Rescue, Disaster or Individual Tracking, and Reset.
When a filter is selected, the dashboard sends the appropriate query to MongoDB through the CRUD Python module. The matching records are returned and displayed in the interactive data table.
The table supports pagination, sorting, built-in filtering, and single-row selection. The breed pie chart updates automatically to reflect the animals currently displayed in the table. The geolocation map also responds to the current table data and displays the location associated with the selected animal.
The Reset option removes the rescue filter and returns the dashboard to the complete unfiltered Austin Animal Center dataset.
Rescue Filters
The Water Rescue filter searches for Labrador Retriever Mix, Chesapeake Bay Retriever, and Newfoundland dogs. These dogs must be Intact Female and between 26 and 156 weeks old.
The Mountain or Wilderness Rescue filter searches for German Shepherd, Alaskan Malamute, Old English Sheepdog, Siberian Husky, and Rottweiler dogs. These dogs must be Intact Male and between 26 and 156 weeks old.
The Disaster or Individual Tracking filter searches for Doberman Pinscher, German Shepherd, Golden Retriever, Bloodhound, and Rottweiler dogs. These dogs must be Intact Male and between 20 and 300 weeks old.
The Reset option returns all available animal records and restores the dashboard to its original unfiltered state.
Tests
The completed dashboard was tested by running ProjectTwoDashboard.ipynb and checking the starting state and each required rescue filter.
The starting state loaded with Reset selected. The complete unfiltered dataset appeared in the data table, multiple animal types and breeds were visible, the breed pie chart displayed a large variety of breeds, and the geolocation map loaded successfully.
The Water Rescue filter was then selected. The table updated to show matching dogs that met the required breed, sex, and age criteria. The visible results included Labrador Retriever Mix dogs that were Intact Female and within the required age range. The pie chart updated to reflect the filtered data and the geolocation map remained functional.
The Mountain or Wilderness Rescue filter was tested next. The table updated to show Intact Male dogs within the required age range. The results included breeds such as Siberian Husky, Alaskan Malamute, Rottweiler, and German Shepherd. The pie chart changed to show the new breed distribution and the map continued to work.
The Disaster or Individual Tracking filter was also tested. The results included Rottweiler, Bloodhound, and German Shepherd dogs that matched the required sex and age range. The pie chart updated again and the geolocation map remained functional.
Finally, Reset was selected again. The dashboard returned to the complete unfiltered dataset, multiple animal types and breeds appeared again, and both charts continued to work.
The table was also tested for pagination, sorting, built-in filtering, and row selection. Selecting a different row caused the geolocation map marker to update.


Screenshots
The screenshot below shows the dashboard in its original unfiltered state. The Grazioso Salvare logo, my name, filtering options, interactive data table, breed pie chart, and geolocation map are displayed.
 
Water Rescue
The screenshot below shows the dashboard with Water Rescue selected. The table displays matching rescue candidates and the pie chart and map update based on the filtered data.
 
Mountain or Wilderness Rescue
The screenshot below shows the dashboard with Mountain or Wilderness Rescue selected. The table displays the matching dogs and both charts update based on the filtered data.
 
Disaster or Individual Tracking
The screenshot below shows the dashboard with Disaster or Individual Tracking selected. The table, pie chart, and geolocation map update to display the matching animals.
 
Reset
The screenshot below shows the dashboard after Reset was selected again. The complete unfiltered dataset is restored and the charts continue to function.
 
Challenges
One challenge I encountered was making sure the geolocation map continued to work correctly after changing rescue filters. Filtering the table can reduce the number of rows, which means a previously selected row may no longer exist in the new results.
I corrected this by checking whether the selected row was still valid after the table changed. If the selected row was outside the filtered data, the map returned to the first available row instead of causing an error.
Another challenge was making sure the dashboard callbacks handled empty values during the initial load. Checks were added so the chart and map would not fail if data or selections were temporarily unavailable.
Testing each rescue filter also helped confirm that the MongoDB queries, interactive data table, pie chart, and geolocation map continued to work together correctly.

Steps Taken to Complete the Project
The project began by reusing the CRUD Python module created in Project One and connecting the Project Two dashboard to the aac MongoDB database.
The dashboard was then set up to retrieve the complete Austin Animal Center dataset and display it in an interactive table. Pagination, sorting, filtering, and single-row selection were included to make the data easier to use.
The rescue requirements from the Dashboard Specifications Document were then used to create MongoDB queries for Water Rescue, Mountain or Wilderness Rescue, and Disaster or Individual Tracking. Reset was configured to return the full unfiltered dataset.
Interactive radio buttons were added so the user could choose between the different rescue categories. Dash callbacks were used to connect those controls to the data table.
A Plotly pie chart was added to show the breed distribution for the currently displayed animals. A Dash Leaflet geolocation map was also connected to the selected table row so the location of the selected animal could be displayed.
The Grazioso Salvare logo and my name were added to the dashboard. The finished application was then tested using the starting state, all three rescue filters, Reset, row selection, the pie chart, and the geolocation map.

Roadmap/Features
The Grazioso Salvare dashboard is now connected to MongoDB through the CRUD Python module. The completed application includes rescue-type filtering, an interactive data table, pagination, sorting, built-in table filtering, single-row selection, a breed pie chart, a geolocation map, Grazioso Salvare branding, and a unique identifier containing my name.
The data table and both charts dynamically respond to the selected rescue filter.
Future improvements could include additional search options, more chart types, more detailed map information, and additional visual improvements to the dashboard.

Contact
Lawrence Langelier


