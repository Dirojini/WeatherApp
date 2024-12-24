
# Weather App
this is an weather app used skills were html,css,js and also Api 
##Demo screenshort
![weatherapp image]()
A dynamic and responsive Weather App created using HTML, CSS, and JavaScript. This app provides real-time weather information based on user input and location data.

## Features

- **Real-time Weather Data**: Fetches current weather information from an external API.
- **City Search**: Allows users to search for weather conditions in different cities.
- **Responsive Design**: Adapts to various screen sizes for seamless user experience.
- **Dynamic Background**: Background changes based on weather conditions.
- **Error Handling**: Displays alerts for invalid city names or API errors.

## Technologies Used

- **HTML** – For structuring the app.
- **CSS** – For styling and layout.
- **JavaScript** – For fetching data and implementing interactive features.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/Dirojini/weatherapp.git
   ```
2. Navigate to the project directory:
   ```bash
   cd weatherapp
   ```
3. Open the `index.html` file in your web browser.

## File Structure

```
weather-app/
│
├── index.html       # Main HTML file
├── style.css        # CSS for styling
└── script.js        # JavaScript for weather API integration
```

## Sample JavaScript (script.js)

```javascript
const apiKey = 'your_api_key';
const weatherForm = document.querySelector('#weatherForm');
const weatherDisplay = document.querySelector('#weatherDisplay');

weatherForm.addEventListener('submit', (e) => {
    e.preventDefault();
    const city = document.querySelector('#city').value;
    fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)
        .then(response => response.json())
        .then(data => {
            weatherDisplay.innerHTML = `
                <h2>${data.name}</h2>
                <p>${data.weather[0].description}</p>
                <p>Temperature: ${data.main.temp}°C</p>
            `;
        })
        .catch(() => {
            weatherDisplay.innerHTML = '<p>City not found. Please try again.</p>';
        });
});
```


## Future Enhancements

- **Hourly Forecasts**
- **Weather Map Integration**
- **User Location Auto-detection**
- **Theme Customization**

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License.


