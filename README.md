# Weather App

A responsive weather application built with HTML, CSS, and vanilla JavaScript. The app lets users search for a city and fetches live weather data from the OpenWeatherMap API, then updates the UI with temperature, humidity, wind speed, and a weather-specific icon.

This project is a good portfolio piece for jobs and interviews because it demonstrates API integration, asynchronous JavaScript, DOM manipulation, error handling, responsive UI design, and clean separation of concerns between structure, styling, and behavior.

## Project Summary

The application solves a simple but practical problem: users can quickly check the current weather for any city from a single-page interface. It is intentionally lightweight and framework-free, which makes the implementation easy to explain in interviews and useful for showing strong fundamentals.

## Key Features

- Search weather by city name
- Fetch live weather data from OpenWeatherMap
- Show temperature in Celsius
- Show humidity and wind speed
- Change the weather icon based on current conditions
- Support both button click and Enter key search
- Show an error message for invalid city names
- Use a responsive glassmorphism-style UI

## Tech Stack

- HTML5
- CSS3
- JavaScript (ES6+)
- Fetch API
- OpenWeatherMap API

## Folder Structure

```text
03_WeatherApp/
|-- index.html
|-- style.css
|-- script.js
|-- README.md
`-- images/
    |-- clear.png
    |-- clouds.png
    |-- drizzle.png
    |-- humidity.png
    |-- mist.png
    |-- mountains.jpg
    |-- rain.png
    |-- search.png
    |-- snow.png
    `-- wind.png
```

## File-by-File Explanation

### `index.html`

This file contains the structure of the app.

- Creates the main weather card layout
- Contains the search input and search button
- Includes placeholders for temperature, city name, humidity, and wind speed
- Includes an error message section that is hidden until needed
- Loads `style.css` for styling and `script.js` for behavior

### `style.css`

This file handles the full visual presentation.

- Applies a gradient background and mountain image overlay
- Builds the glassmorphism card effect using transparency and blur
- Styles the search box, button, weather details, and error state
- Adds animation for card entry, icon floating, fade-in, and shake effects
- Includes a mobile-responsive layout for smaller screens

### `script.js`

This file contains the application logic.

- Stores the API key and API base URL
- Selects important DOM elements such as the search box and button
- Defines the `checkWeather(city)` async function
- Sends a request to the weather API using `fetch`
- Checks for a `404` response when the city is invalid
- Parses JSON data when the request succeeds
- Updates DOM elements with city name, temperature, humidity, and wind speed
- Switches weather icons based on API response values like `Clouds`, `Clear`, `Rain`, `Drizzle`, and `Mist`
- Triggers search on button click and Enter key press

## How the App Works

1. The user enters a city name in the input field.
2. The user clicks the search button or presses Enter.
3. The `handleSearch()` function validates that the input is not empty.
4. The app calls `checkWeather(city)`.
5. `checkWeather(city)` sends a request to the OpenWeatherMap API.
6. If the API returns `404`, the app shows the error message and hides the weather card.
7. If the request succeeds, the app reads the JSON response.
8. The app updates the UI with live weather values.
9. The app selects the correct icon based on the weather condition.

## API Integration

The project uses the OpenWeatherMap current weather endpoint.

Example request pattern:

```text
https://api.openweathermap.org/data/2.5/weather?units=metric&q={CITY_NAME}&appid={API_KEY}
```

Important data used from the response:

- `data.name` for city name
- `data.main.temp` for temperature
- `data.main.humidity` for humidity
- `data.wind.speed` for wind speed
- `data.weather[0].main` for selecting the correct icon

## Concepts Demonstrated

This project is especially useful for interviews because it shows:

- DOM selection and dynamic DOM updates
- Event handling with click and keyboard interactions
- Asynchronous programming with `async/await`
- REST API consumption using `fetch`
- Conditional rendering of UI states
- Basic error handling for failed requests
- Responsive design with media queries
- UI polish using transitions and keyframe animations

## Interview Explanation

### Short Interview Pitch

"I built a weather app using HTML, CSS, and vanilla JavaScript. Users can search for a city, and the app calls the OpenWeatherMap API to fetch live weather data. I used async/await for asynchronous requests, updated the DOM dynamically with temperature, humidity, and wind speed, and added error handling for invalid city names. I also focused on responsive design and a polished UI with glassmorphism styling and animations."

### What This Project Says About You

- You understand JavaScript fundamentals without depending on frameworks
- You can integrate third-party APIs into a frontend application
- You know how to connect UI interactions with business logic
- You care about user experience, feedback states, and responsiveness
- You can organize a small frontend project cleanly

### Good Interview Talking Points

- Why you chose vanilla JavaScript: to show strong fundamentals
- How `async/await` improves readability over chained promises
- How you handled invalid city input and 404 API responses
- How the UI is updated without reloading the page
- How CSS animations improve perceived quality and engagement
- How the app could be extended into a larger product

## Strengths of the Current Implementation

- Clean separation between HTML, CSS, and JavaScript
- Simple and easy-to-understand control flow
- Real-world API usage
- Good beginner-to-intermediate frontend portfolio project
- Responsive and visually appealing UI
- Includes basic error state handling

## Current Limitations

These are useful to mention honestly in interviews.

- The API key is hardcoded in `script.js`, which is acceptable for a learning/demo project but not ideal for production
- Error handling is limited mainly to the `404` case
- The app shows only current weather, not forecast data
- There is no loading state while the request is in progress
- Some weather conditions are not mapped to custom icons
- Input sanitization and accessibility can be improved further

## Suggested Improvements

If asked what you would build next, these are strong answers:

- Move the API key to a backend or environment-based setup
- Add a loading spinner during API calls
- Support geolocation-based weather lookup
- Add 5-day or hourly forecast support
- Improve accessibility with labels and ARIA-friendly feedback
- Add more weather icons for conditions like snow, thunderstorm, or haze
- Cache recent searches in local storage
- Add unit conversion between Celsius and Fahrenheit

## Resume Bullet Ideas

You can use or adapt these in your resume:

- Built a responsive weather application using HTML, CSS, and JavaScript with live data from the OpenWeatherMap API
- Implemented asynchronous API calls with `fetch` and `async/await` to display real-time city weather information
- Developed interactive UI behavior including dynamic DOM updates, weather-state icon switching, and invalid-search error handling
- Designed a mobile-friendly glassmorphism interface with CSS animations and responsive layouts

## Questions You May Be Asked in an Interview

### Why did you choose this project?

This project is small enough to complete independently, but rich enough to demonstrate real frontend skills such as API integration, event handling, DOM updates, and responsive styling.

### Why use vanilla JavaScript instead of React or another framework?

Vanilla JavaScript highlights core fundamentals. It proves you understand browser APIs, DOM manipulation, and asynchronous logic directly before abstracting those concepts with frameworks.

### What was the main challenge?

A practical challenge is connecting API response data to UI states in a clean way, especially handling invalid searches and mapping weather conditions to icons.

### How would you improve it for production?

I would secure the API key, handle more error cases, add a loading state, improve accessibility, and possibly move to a component-based architecture if the app grew larger.

## How to Run the Project

1. Clone or download the project folder.
2. Make sure all files stay in the same structure, including the `images` folder.
3. Open `index.html` in a browser.
4. Enter a city name and search.

## Notes for Reviewers and Recruiters

This project is best evaluated as a frontend fundamentals project. It demonstrates practical JavaScript usage, clean UI implementation, and the ability to integrate an external API into a working user-facing application without relying on frameworks.

## Final Takeaway

If you present this project in a job interview, focus on three things:

1. You built a complete, working product from scratch.
2. You integrated real-time external data into the UI.
3. You combined functionality, design, and usability in a simple but polished application.
