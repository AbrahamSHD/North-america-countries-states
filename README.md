# North America Countries and States JSON

This repository contains a JSON file with detailed information about the countries in North America, including their states, provinces, and territories. This dataset is useful for projects requiring geographic data, such as web applications, APIs, or educational purposes.

## Features

- **Countries Included:**
  - United States
  - Canada
  - Mexico
  - Greenland
  - Bermuda
  - Saint Pierre and Miquelon
- **Data Details:**
  - States for the United States and Mexico.
  - Provinces and territories for Canada.
  - Territories for smaller regions like Bermuda and Greenland.

## File Structure

- **`north-america.json`:**  
  The main JSON file containing the data in the following structure:
  ```json
  {
    "NorthAmerica": [
      {
        "country": "Country Name",
        "states": ["State1", "State2", ...]
      },
      ...
    ]
  }

## Usage

- **Below are examples of how to use this JSON file in JavaScript, Python, and C#.**

  ### JavaScript
  ```javascript
  // Import the JSON file
  const northAmericaData = require('./north-america.json');

  // Access countries and their states/provinces/territories
  northAmericaData.NorthAmerica.forEach(country => {
    console.log(`Country: ${country.country}`);
    console.log(`Regions: ${country.states || country.provinces || country.territories}`);
  });

  ```

  ### Python
  ```python
  import json

  # Load the JSON file
  with open('north-america.json') as file:
      data = json.load(file)

  # Print countries and their regions
  for country in data['NorthAmerica']:
      print(f"Country: {country['country']}")
      print(f"Regions: {country.get('states') or country.get('provinces') or country.get('territories')}")
  ```

  ### C#
  ```c#
  using System;
  using System.IO;
  using Newtonsoft.Json.Linq;

  class Program
  {
      static void Main()
      {
          // Load the JSON file
          string json = File.ReadAllText("north-america.json");
          var data = JObject.Parse(json);

          // Iterate through countries and print regions
          foreach (var country in data["NorthAmerica"])
          {
              Console.WriteLine($"Country: {country["country"]}");
              var regions = country["states"] ?? country["provinces"] ?? country["territories"];
              Console.WriteLine($"Regions: {string.Join(", ", regions)}");
          }
      }
  }

  ```
