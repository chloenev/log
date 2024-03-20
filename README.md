# Technical Activity Log 

Created alongside my [Activity Timesheet](https://docs.google.com/spreadsheets/d/1l5CtPyyME90kUm4xr6jZesHhcpF23J1mbdviPXfV1iE/edit?usp=sharing). 

## March 20
### Exploring ArcGIS Web Apps - Dashboards

Andie has looked into Experience Builder to use with our online data, but she didn't find much luck... I am going to explore Dashboards with our data and see what I find. 

Previously found [an example](https://www.arcgis.com/apps/dashboards/c1620b1dfaec4c5fa6897df5f74e1a90) from the City of Kenosha that used a dashboard to display development properties & within a pop-up window had a link to floor plan. I thought that could be useful to our project scope.

![image](https://github.com/chloenev/log/assets/146447252/0a642504-0d10-4db0-a121-b8e04fef5e76)
![image](https://github.com/chloenev/log/assets/146447252/ec45f2d6-3054-42d2-aed3-9452775fa0d3)


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
