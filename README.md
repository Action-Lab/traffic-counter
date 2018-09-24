# traffic-counter
One-page Firebase mobile app to count cars, driver behaviors, pedestrians, and cyclists.

### Usage
1. Open the app on your phone: https://action-lab.github.io/traffic-counter/ and log in with your Google account. You will need to enable location services in your browser.
2. After successfull login, fill in the form which describes the weather at your intersection, choose what you're counting (Cars, Behaviors, Peds/Bikes), and press Start.
3. You will see a screen with relevant to what you're counting buttons. Each button push creates a database entry (object) and sends it to the Firebase. The console row at the bottom shows an icon if the entry was successfully received by the server.
4. The timer is on top for your convenience. There is NO time limit (that is, the app won't terminate unless inactive for too long).

### Management
1. You can manage the Firebase database through the **Console** at https://console.firebase.google.com/u/0/.
2. Under **Develop**, select **Database** in the menu on the left. In the main window, you will see a list of JSON objects — database entries, each representing a button click. Each object is as follows:

```javascript
{
  code: 12, /* Code of recorded action = what button was pressed. See below for link to crosswalk. */
  count: 1, /* How many items were observed, usually 1 but some buttons are 2 or 5 */
  date: "Jun 13, 2018", /* Date in easy to read format */
  day: "Wed", /* Day of week */
  email: "someone@gmail.com", /* Gmail of a person who submitted the entry */
  intersection: "Intersection A", /* Intersection from dropdown menu */
  location: "41.76,-72.69", /* If location services enabled, latitude and longitude */
  name: "Counting Person", /* Name of person from their Gmail profile */
  rain: "No rain", /* Rain value */
  session_id: "hpgb5ae", /* Every counting session (from Start to Finish buttons) has a unique ID for convenience / easy filtering */
  sky: "Clear", /* Sky value */
  temp: 70, /* Temperature */
  time: "21:39:05", /* Time in 24 format, hh:mm:ss */
  timestamp: "Sun Sep 23 2018 21:39:05 GMT-0400 (EDT)", /* Timestamp */
  wind: "No wind" /* Wind value */
}
```

See [this spreadsheet](https://docs.google.com/spreadsheets/d/1eAw-aQ75h4LgyA_-uXophLY03_pgO_9GgfEsUv43yCk/edit?usp=sharing) for a code-action crosswalk.

3. To export the entire database, click the three dots button in the upper right corner and choose `Export JSON`.
4. JSON needs to be converted to CSV for easy Excel manipulations. Use one of the online converters (e.g. https://json-csv.com/) to convert from JSON to CSV. Now you can perform your data analysis!
