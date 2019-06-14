# Live Project using ASP.NET MVC https://www.erectorsinc.com
ASP.NET MVC C# Project W/ code first Entity Framework Database. The UI is bootstrap 3. We used Azure DevOps to select stories.
This software will be used to manage a collection of construction jobs. Admins will be able to create and distribute a weekly schedule assigning users to certain jobs. Users will be able to keep track of which job they are assigned to for the week. There will also be the ability for admins to post company news and announcements, and chat functionality for the users to socialize.


## Google Maps & Geocode API

### My task was to create a dynamic marker on a map with the current job sites address
This story was to place a marker on the map of the job sites address. I had to make it dynamic so the marker would change as the job sites address changed. I researched Google Map API and then found out I also needed to use a Geocode API. The Geocode API would take a jobs address then return map coordinates in JSON format. I used those coordinates to

<script>


    // The below code generates the JSON 
    // var locator = String.Format("https://maps.googleapis.com/maps/api/geocode/json?address={0}&key=AIzaSyCz3vFGdOrnD0oveurROUfzVSBQ6sLXoP4", shortAddress);

    function initMap() {
        var map = new google.maps.Map(document.getElementById('map'), {
            zoom: 8,
            center: {  }
        });
        var geocoder = new google.maps.Geocoder();
        geocodeAddress(geocoder, map);
    }



    function geocodeAddress(geocoder, resultsMap) {
        var address = '@Model.StreetAddress';
        geocoder.geocode({ 'address': address }, function (results, status) {
            if (status === 'OK') {
                resultsMap.setCenter(results[0].geometry.location);
                var marker = new google.maps.Marker({
                    map: resultsMap,
                    position: results[0].geometry.location
                });
            } else {
                alert('Geocode was not successful for the following reason: ' + status);
            }
        });
    }
    

</script>


<img src="https://github.com/CodingMikey/LiveProject/blob/master/Screenshot%20(34).png" title="" alt="">


### Changed date input from a textbox to a datetime
This story was to fix an issue the main create view for the Company News uses a date picker for the expiration date, but the pop-up linked on the dashboard and the edit view do not have a date picker. I had to make the expiration date field for these views a date picker.
