# HW7 - {Train Scheduler}
Train schedule application that incorporates Firebase to host arrival and departure data.


## Overview
Enter basic train information including name, destination, first train time and frequency in minutes.
The app will then retrieve and manipulate this information with Moment.js, and display the information for the next train time relative to the current time.

## Technologies Used
- HTML
- CSS Bootstrap
- JavaScript to make the page dynamic
- jQuery for Dom Manipulation
- FIREBASE for data storage/data persistence

### FIREBASE Snapshot (Example)
In order to read the train data from the Firebase database, childSnapshot was used to extract the contents of the snapshot as a JavaScript object by calling the val() method.

```
dataRef.ref().on("child_added", function(childSnapshot) {

      $("#trainSchedule").append("<tr><td span id='name'> " + childSnapshot.val().name + "</td>" +
        " </span><td span id='destination'> " + childSnapshot.val().destination + "</td>" +
        " </span><td span id='frequency'> " + childSnapshot.val().frequency + "</td>" +
        " </span><td span id='next'> " + childSnapshot.val().nextTrainArrival + "</td>" +
        " </span><td span id='minAway'> " + childSnapshot.val().minutesAway + "</td>" + " </span></div>");

      // Handle the errors
    }, function(errorObject) {
      console.log("Errors handled: " + errorObject.code);
    });

```