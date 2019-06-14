# Live Project using ASP.NET MVC https://www.erectorsinc.com
ASP.NET MVC C# Project W/ code first Entity Framework Database. The UI is bootstrap 3. We used Azure DevOps to select stories.
This software will be used to manage a collection of construction jobs. Admins will be able to create and distribute a weekly schedule assigning users to certain jobs. Users will be able to keep track of which job they are assigned to for the week. There will also be the ability for admins to post company news and announcements, and chat functionality for the users to socialize.


## Stories I worked on include:

## Google Maps & Geocode API

### My task was to create a marker on the jobs address
This story was to place a marker on the map of the job address. I had to make it dynamic so the marker would change as the job sites address changed. I researched Google Map API and then found out I also needed to use a Geocode API. The Geocode API would take a jobs address then return map coordinates in JSON format. I used those coordinates to

### Changed date input from a textbox to a datetime
This story was to fix an issue the main create view for the Company News uses a date picker for the expiration date, but the pop-up linked on the dashboard and the edit view do not have a date picker. I had to make the expiration date field for these views a date picker.
