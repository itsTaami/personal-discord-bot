# Weather Skill

## Description
Look up current weather conditions and forecast for any city. Supports both metric and imperial units based on user preference.

## Trigger Conditions
Use this skill when the user asks about:
- Current weather in a city or location
- Temperature somewhere
- Weather forecast
- "What's the weather in [city]?"
- "Is it raining in [city]?"
- "How hot/cold is it in [city]?"
- "Weather forecast for [city]"
- "Will it rain in [city] today?"

## Instructions
1. Extract the city name from the user's message
2. Check if the user specified units (Celsius/Fahrenheit). Default to Celsius.
3. Use the WebSearch tool to search: "current weather in [city] today"
4. From the results extract: temperature, conditions, humidity, wind speed, and if available — a short forecast
5. Convert units if the user requested Fahrenheit (°F = °C × 9/5 + 32)
6. Format the response clearly with a relevant weather emoji based on conditions:
   - ☀️ Sunny / Clear
   - 🌤️ Partly Cloudy
   - ☁️ Cloudy / Overcast
   - 🌧️ Rainy
   - ⛈️ Thunderstorm
   - ❄️ Snow
   - 🌫️ Foggy / Misty

### Response format:
```
[emoji] Weather in [City]

Temperature: [X]°C ([X]°F)
Conditions: [e.g. Partly Cloudy]
Humidity: [X]%
Wind: [X] mph [direction]

Forecast: [one-line summary if available]
```

## Edge Cases
- If the city is ambiguous (e.g. "Springfield"), pick the most likely one and mention which you chose
- If weather data cannot be found, say so and suggest the user check weather.com directly
- If no city is given, ask: "Which city would you like the weather for?"
- If the user asks for Fahrenheit, convert and display both units
- If wind direction is unavailable, omit it rather than guessing
- If the user asks about "today" or "now", emphasize current conditions over forecast
