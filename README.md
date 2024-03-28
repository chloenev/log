# Technical Activity Log 

Created alongside my [Activity Timesheet](https://docs.google.com/spreadsheets/d/1l5CtPyyME90kUm4xr6jZesHhcpF23J1mbdviPXfV1iE/edit?usp=sharing). 

## March 28
### Where was I... 
Been a while, but we #back! At the last meeting Shawn suggested we look into small area data, rather than limiting ourselves to the previous floor plan data which was a nuisance because really the best solution is ArcGIS Indoors in the online space 🙃

#### Newmarket Park Data 
Using this park data we are exploring tools within Experience Builder for small areas. In particular I want to try out dDicrections because I wanted to used it with the indoor data for routing, but it wasn't possible because the data was not floor aware (something you set up in Indoors)!

Just getting started, I added a new page to my EB file, added the park data to a map and clicked to add the Directions widget:

![image](https://github.com/chloenev/log/assets/146447252/afa42dcd-b78f-419b-9c76-68388bab8059)

On the right sidebar you need to select your map source (you can pick any from your EB file), the route settings (by default there is the ArcGIS route services URL), and then locator source (again the default ArcGIS default 'World Geocoding Service' was chosen). 

THIS IS SUPER EASY AND VERY COOL! Just trying out using the map to click on various parks & get walking or driving times, and distances! Can add multiple stops too. 

https://github.com/chloenev/log/assets/146447252/85d6c452-1e08-49c4-a9a3-2a7a9a46c445





## March 21
### Experience Builder
Got annoyed with Dashboards, so I'm going to explore what Experience Builder (EB) can do. 

Starting off by following this [video from GeoMarvel on YouTube.](https://www.youtube.com/watch?v=0HOkC20Zj3Y)

I set up a map with the floor plan data & am adjusting to the interface (which seems really cool at first glance! More fun than Dashboard lol). 
![image](https://github.com/chloenev/log/assets/146447252/79176fd3-ac21-4d41-9a12-4916ea6803be)

It's very easy to add data in, all you do is click and drag Map from the left sidebar (where all the other widgets are) and drag it to the middle frame. There are lots of templates to choose from, but to start I just did a blank page. Then, with the map selected, on the right hand side you can 'Select map' and then ➕Add new data. 

![image](https://github.com/chloenev/log/assets/146447252/51df778b-7263-44a5-97ed-fcc8bf9cd6ec)

I was confused at first how to interact with the data, but you need to press the LIVE VIEW button! You can also see how the app would look on different displays like a desktop, a tablet, or a phone! 

![image](https://github.com/chloenev/log/assets/146447252/d282514e-e539-42e0-a02f-08725f2ffe84)

#### Analysis Widget 
You can add an analysis widget inside EB! It uses credits (0.1 credits per input feature).

I wanted to see if I could overlay multiple floor levels, so that I could have 1 layer that I could easily query through based on the attribute "Floor". 

![image](https://github.com/chloenev/log/assets/146447252/031371bc-1bcd-49ef-bdbd-c64d24b10c8c)
![image](https://github.com/chloenev/log/assets/146447252/f63e5ce1-39ef-42d3-adef-308a071b7663)

Clicked around on a few more widgets and kept running into the problem:
![image](https://github.com/chloenev/log/assets/146447252/2f5c1aab-e733-42aa-b681-5fb5ce7c66f9)
I think we need ArcGIS Indoors extension for this which we don't have the licensing for... 🤔

I definitely want to keep playing around with EB, it's much more fun than Dashboard! Visually I think it makes for a better product in our use case since we aren't really looking at a lot of stastical data to display, and it seems (so far) that it could be easier to handle multiple layers. 

Will talk with my group soon and update Shawn on our findings! 


### Exploring Dashboards cont. 

This [YouTube video](https://www.youtube.com/watch?v=pGBpdZOBwko) led me to look at the [documentation on Selectors](https://doc.arcgis.com/en/dashboards/latest/create-and-share/selectors.htm). 

Trying out different selectors to filter rooms displayed by department on each floor. This is a category selector which I think could be useful if there were attributes such as rooms by department, rooms designated to specific cleaners/cleaning shifts, rooms that contain XYZ. 
![image](https://github.com/chloenev/log/assets/146447252/abb104e6-4b5e-42d8-9d0f-bdef3b06e139)
* Have to toggle the other layers off or it gets too confusing

I'm trying to add multiple filters so that the user can choose both the floor level (basement, 1-5) plus another selector (category, number, or date), but I can't seem to figure out how yet... 😠 That way they don't have to manually toggle the layers on/off

I'm also trying to see if I can set up easy filtering on a chart element. For example, a bar chart (called serial chart) of the level of employee (entry, junior, senior, etc.) per floor. But, I just want 1 chart on the dashboard that changes based on the selected/searched for layer... Not sure if possible - going to keep looking at documentation and YouTube videos.

Unfortunately, I do not see any way we could do a navigational aspect using Dashboards, so ultamitely this may not be the best web solution anyway... 🙃



## March 20
### Exploring ArcGIS Web Apps - Dashboards

I am going to explore Dashboards with our data and see what I find. 

Creating a dashboard help - https://www.esri.com/arcgis-blog/products/ops-dashboard/mapping/create-first-arcgis-dashboards/ 

Previously found [an example](https://www.arcgis.com/apps/dashboards/c1620b1dfaec4c5fa6897df5f74e1a90) from the City of Kenosha that used a dashboard to display development properties & within a pop-up window had a link to floor plan. I thought that could be useful to our project scope.

![Screenshot 2024-03-20 111207](https://github.com/chloenev/log/assets/146447252/7b7df0af-bb73-47d4-9c1f-53f906bebe54)

Likely not the best way to do so yet, but you can toggle layers on/off which helps view different floors! Here I was able to just view Floor 1 & Floor 1 detail using the Layers dropdown:

![image](https://github.com/chloenev/log/assets/146447252/2263c6d3-946c-41c1-ae65-0ee9b2a5e4f6)
The pop-up window shows the floor, room group, name, and more. 

I want to create an indicator based on what layers are visible (for example when I want to look at just floor 1). 
Look at: 
* https://community.esri.com/t5/arcgis-dashboards-questions/dashboard-indicators-with-multiple-layers/td-p/13913
* https://community.esri.com/t5/arcgis-dashboards-questions/dashboard-indicator/td-p/1253478
* Arcade expressions for data expressions - https://github.com/Esri/arcade-expressions/tree/master/dashboard_data

Next steps:
* Figure out data filtering


## Weeks 7 & 8 Checklist
### Starting my own ArcGIS Server on the Google Cloud Platform (GCP)

Closely followed the video: [Creating your own VM from the image](https://www.youtube.com/watch?v=dyFeyBX9jIY)

But had to troubleshoot some issues... 

![Screenshot 2024-03-09 192002](https://github.com/chloenev/log/assets/146447252/e21dd656-43bb-47dc-ab79-86a9773345de)

* Got this message, so I traced my steps and realized that I inputted my **private** IP address into the firewall rule (5:40 min mark in the above video) 
* Found my public IP address by Googling "what is my IP address
* IP address was not in specified CIDR notation (**ask/look up how I would do this because I couldn't get it to work**)
* Changed IP address range to completely unrestricted range of 0.0.0.0/0 - not recommended, but used it in order to move on 

![Screenshot 2024-03-09 200141](https://github.com/chloenev/log/assets/146447252/5f0d2015-86cb-44d0-8c30-ea486fb13a29)

* Entered incorrect credentials and received this message

Eventually I was able to connect and access the data layers! 😄
![Screenshot 2024-03-09 201229](https://github.com/chloenev/log/assets/146447252/bae99354-6a45-4f78-b39e-ea788362f036)

* 
