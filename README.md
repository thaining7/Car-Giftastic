# Car Giftastic

#### Search for animated gifs of your favorite cars!
https://thaining7.github.io/Car-Giftastic/

# Description

#### This application uses JavaScript, jQuery and the Giphy API to find find and display animated Gifs

# Screenshot

![App Screenshot](/assets/images/Giftastic.png)

# Tech Used

* JavaScript
* jQuery
* Giphy API
* HTML
* CSS
* Bootstrap CSS Framework

# Features

#### Uses the Giphy API to display images with a rating of "G"

# Code Example

#### Ajax call and JS used to query the API

```
$.ajax({
                    url: queryURL,
                    method: "GET"
                })

                    .then(function (response) {

                        var results = response.data;

                        for (var i = 0; i < results.length; i++) {

                            if (results[i].rating !== "r" && results[i].rating !== "pg-13") {

                                var gifDiv = $("<div class='col-md-12'>");

                                var rating = results[i].rating;

                                var p = $("<p>").text("Rating: " + rating);

                                var carImage = $('<img class= "gif" src= "' + results[i].images.fixed_height_still.url + '" data-still="' + results[i].images.fixed_height_still.url + '" data-animate="' + results[i].images.fixed_height.url + '" data-state="still">');

                                gifDiv.append(p);
                                gifDiv.append(carImage);

                                $("#gifs-appear-here").prepend(gifDiv);
                            }
                        }
```

# API Reference

https://developers.giphy.com/

# How To Use

* Simply type your desired car in the search box and click the "add a car" button
* Then, your car will appear on a button at the top of the page
* Click your cars button to load gifs from the Giphy API
* Click on the images to start and stop the Gifs animation
