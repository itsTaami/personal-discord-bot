# Weather Skill

## Description
Look up current weather conditions and forecast for any city.

## Trigger Conditions
Use this skill when the user asks about:
- Current weather in a city or location
- Temperature somewhere
- Weather forecast
- "What's the weather in [city]?"
- "Is it raining in [city]?"
- "How hot/cold is it in [city]?"

## Instructions
1. Extract the city name from the user's message
2. Use the WebSearch tool to search: "current weather in [city]"
3. From the results extract: temperature, conditions, humidity, wind speed
4. Format the response clearly with a relevant weather emoji
5. Include the city name in the response

### Response format:
```
☀️ Weather in [City]

Temperature: [X]°C ([X]°F)
Conditions: [e.g. Partly Cloudy]
Humidity: [X]%
Wind: [X] mph [direction]
```

## Edge Cases
- If the city is ambiguous (e.g. "Springfield"), pick the most likely one and mention which you chose
- If weather data cannot be found, say so and suggest the user check a weather site directly
- If no city is given, ask: "Which city would you like the weather for?"
