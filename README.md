# aviation-edge-api

## Static Data:
Static data refers to any data that, by nature, is not frequently changing. However, due to the size of our database, there are constantly updates happening, making this a valuable API when you have to maintain a big database yourself. So even though the nature of the data is static, make sure to check for updates frequently using your API key. The moment a change is detected we will pursue and update our database.


## Airlines

### Request 
GET https://aviation-edge.com/api/public/airlineDatabase?key=YOUR-API-KEY
### Responce
```
[ 
    { 
        "airlineId": "1", 
        "nameAirline": "American Airlines", 
        "codeIataAirline": "AA", 
        "iataPrefixAccounting": "1", 
        "codeIcaoAirline": "AAL", 
        "callsign": "AMERICAN", 
        "type": "scheduled", 
        "statusAirline": "active", 
        "sizeAirline": "963", 
        "ageFleet": "10.9", 
        "founding": "1934", 
        "codeHub": "DFW", 
        "nameCountry": "United States", 
        "codeIso2Country": "US" 
    }
]
```

## Airplanes

### Request 
GET https://aviation-edge.com/api/public/airplaneDatabase?key=YOUR-API-KEY
### Responce
```
[ 
    { 
      "airplaneId": "55", 
      "numberRegistration": "HB-JVE", 
      "productionLine": "Fokker 28/70/100", 
      "airplaneIataType": "F28 MK0100", 
      "planeModel": "F-100", 
      "modelCode": "F100", 
      "hexIcaoAirplane": "4B19EA", 
      "codeIataPlaneShort": "100", 
      "codeIataPlaneLong": "F100", 
      "constructionNumber": "11459", 
      "numberTestRgistration": "PH-EZD", 
      "rolloutDate": "0000-00-00", 
      "firstFlight": "1993-05-31T22:00:00.000Z", 
      "deliveryDate": "1993-06-29T22:00:00.000Z", 
      "registrationDate": "2004-05-11T22:00:00.000Z", 
      "lineNumber": "", 
      "planeSeries": "", 
      "codeIataAirline": "2L", 
      "codeIcaoAirline": "", 
      "planeOwner": "", 
      "enginesCount": "2", 
      "enginesType": "JET", 
      "planeAge": "24", 
      "planeStatus": "active", 
      "planeClass": 
      [ 
          { 
              "name": "Economy", 
              "seats": "100", 
              "pitch": "31", 
              "bedLength": "", 
              "bedType": "Standard", 
              "width": "17" 
          }, 
          { 
              "name": "Business", 
              "seats": "40", 
              "pitch": "33", 
              "bedLength": "", 
              "bedType": "Recliner", 
              "width": "17" 
           } 
       ] 
    } 
 ]
```

## Airport

### Request 
GET https://aviation-edge.com/api/public/airportDatabase?key=YOUR-API-KEY
### Responce
```
[
    {
        "airportId": "7",
        "nameAirport": "Aachen/Merzbruck",
        "codeIataAirport": "AAH",
        "codeIcaoAirport": "EDKA",
        "nameTranslations": "Aachen/Merzbruck,Aachen Merzbruck HavalimanÄ±,äºšç›æœºåœº",
        "latitudeAirport": "50.75",
        "longitudeAirport": "6.133333",
        "geonameId": "3247449",
        "timezone": "Europe/Berlin",
        "GMT": "1",
        "phone": "",
        "nameCountry": "Germany",
        "codeIso2Country": "DE",
        "codeIataCity": "AAH"
    }
]
```

## Airline Benchmark

### Request 
GET https://aviation-edge.com/api/public/benchmarkAirlines?key=YOUR-API-KEY
### Responce
```
[
    {
        "benchmarkAirlinesId": "1",
        "nameAirline": "American Airlines",
        "codeIataAirline": "AA",
        "codeIcaoAirline": "AAL",
        "nameCountry": "United States",
        "codeIso2Country": "US",
        "statusAirline": "active",
        "type": "scheduled",
        "founding": "1934",
        "ageFleet": "10.9",
        "sizeAirline": "963",
        "website": "aa.com",
        "twitter": "twitter.com/AmericanAir",
        "facebook": "facebook.com/AmericanAirlines"
    }
]
```

## Airport Benchmark

### Request 
GET https://aviation-edge.com/api/public/benchmarkAirports?key=YOUR-API-KEY
### Responce
```
[
    {
        "benchmarkAirportsId": "1",
        "nameAirport": "Anaa",
        "codeIataAirport": "AAA",
        "nameCountry": "French Polynesia",
        "codeIso2Country": "PF",
        "popularity": "0",
        "website": ""
    }
]
```

## City Benchmark

### Request 
GET https://aviation-edge.com/api/public/benchmarkCities?key=YOUR-API-KEY
### Responce
```
[
    {
        "benchmarkCitiesId": "1",
        "nameCity": "Anaa",
        "codeIataCity": "AAA",
        "nameCountry": "French Polynesia",
        "codeIso2Country": "PF",
        "popularity": "0"
    }
]
```

## City

### Request 
GET https://aviation-edge.com/api/public/cityDatabase?key=YOUR-API-KEY
### Responce
```
[
    {
        "cityId": "1",
        "nameCity": "Anaa",
        "codeIataCity": "AAA",
        "codeIso2Country": "PF",
        "nameTranslations": "Anaa,Anaa,????,?????,??",
        "latitudeCity": "-17.05",
        "longitudeCity": "-145.41667",
        "timezone": "Pacific/Tahiti",
        "GMT": "-10",
        "geonameId": "0"
    }
]
```

## Country

### Request 
GET https://aviation-edge.com/api/public/countryDatabase?key=YOUR-API-KEY
### Responce
```
[
    {
        "countryId": "1",
        "nameCountry": "Andorra",
        "codeIso2Country": "AD",
        "codeIso3Country": "AND",
        "numericIso": "20",
        "nameTranslations": "ÐÐ½Ð´Ð¾Ñ€Ñ€Ð°,An Ä‘Ã´ ra,Andorra,à¸­à¸±à¸™à¸”à¸­à¸£à¹Œà¸£à¸²,å®‰é“çˆ¾,Andorra,Andorra,ÐÐ½Ð´Ð¾Ñ€Ñ€Ð°,Î‘Î½Î´ÏŒÏÎ±,ì•ˆë„ë¼,å®‰é“ å°”,å®‰é“çˆ¾,ã‚¢ãƒ³ãƒ‰ãƒ©,Andorra,Andorra,Andorra,Andorre,Andorra,Andorra,Andora,Andorra,Andora,Andora,Andora,Ø£Ù†Ø¯ÙˆØ±,Andorra,å®‰é“å°”,ÐÐ½Ð´Ð¾Ñ€Ñ€Ð°,Andorre,Andorra,Andorra,à¸›à¸£à¸°à¹€à¸—à¸¨à¸­à¸±à¸™à¸”à¸­à¸£à¹Œà¸£à¸²",
        "population": "84000",
        "capital": "Andorra la Vella",
        "continent": "EU",
        "nameCurrency": "Euro",
        "codeCurrency": "EUR",
        "codeFips": "AN",
        "phonePrefix": "376"
    }
]
```

## Taxes

### Request 
GET https://aviation-edge.com/api/public/taxDatabase?key=YOUR-API-KEY
### Responce
```
[
    {
        "taxId": "1",
        "nameTax": "Government Tax",
        "codeIataTax": "AB"
    }
]
```


## Dynamic Data:
Dynamic data refers to any data that requires constant or frequent tracking. The nature of the data is dynamic. You can think about information such as flight tracking, delays, airport timetables, etc.

## Real-Time Flight Tracking

### Request 
GET https://aviation-edge.com/api/public/flights?key=YOUR-API-KEY
### Responce
```
[
    {
        "geography": {
            "latitude": 37.4096,
            "longitude": -66.8228,
            "altitude": 12192,
            "direction": 304
        },
        "speed": {
            "horizontal": 788.952,
            "vertical": 0
        },
        "departure": {
            "iataCode": "JNB",
            "icaoCode": "FAJS"
        },
        "arrival": {
            "iataCode": "JFK",
            "icaoCode": "KJFK"
        },
        "aircraft": {
            "regNumber": "ZSSNG",
            "icaoCode": "A346",
            "icao24": "00B0F1",
            "iataCode": "A346"
        },
        "airline": {
            "iataCode": "SA",
            "icaoCode": "SAA"
        },
        "flight": {
            "iataNumber": "SA203",
            "icaoNumber": "SAA203",
            "number": "203"
        },
        "system": {
            "updated": 1510914767,
            "squawk": "0000"
        },
        "status": "en-route" 
    } 
]
```

## Nearby Service

### Request 
GET https://aviation-edge.com/api/public/nearby?key=YOUR-API-KEY&lat=-6.1744&lng=122.111
### Responce
```
[
    {
        "code": "BUW",
        "icao": "WAWB",
        "name": "Baubau",
        "cityCode": "BUW",
        "cityName": "Baubau",
        "countryCode": "ID",
        "countryName": "Indonesia",
        "lat": -5.466667,
        "lng": 122.63333,
        "timezone": "Asia/Makassar",
        "type": "airport",
        "isRailRoad": 0,
        "isBusStation": 0,
        "distance": 97625
    }
]
```

## Routes

### Request 
GET https://aviation-edge.com/api/public/routes?key=YOUR-API-KEY
### Responce
```
[
    {
        "departureIata": "CDG",
        "departureIcao": "LFPG",
        "departureTerminal": "1",
        "departureTime": "10:40:00",
        "arrivalIata": "WAW",
        "arrivalIcao": "EPWA",
        "arrivalTerminal": null,
        "arrivalTime": "12:55:00",
        "airlineIata": "0B",
        "airlineIcao": "BMS",
        "flightNumber": "332",
        "codeshares": [
            {
                "airlineCode": "LO",
                "flightNumber": "332"
            }
        ],
        "regNumber": null
    }
]
```

## Airport Timetable

### Request 
GET https://aviation-edge.com/api/public/timetable?key=YOUR-API-KEY
### Responce
```
[
    {
        "type": "departure",
        "status": "scheduled",
        "departure": {
            "iataCode": "LGA",
            "icaoCode": "KLGA",
            "terminal": "B",
            "gate": "C11",
            "scheduledTime": "2017-11-17T05:45:00.000",
            "estimatedTime": "2017-11-17T05:45:00.000",
            "estimatedRunway": "2017-11-17T05:58:00.000"
        },
        "arrival": {
            "iataCode": "IAH",
            "icaoCode": "KIAH",
            "terminal": "C",
            "gate": "8",
            "baggage": "C6",
            "scheduledTime": "2017-11-17T08:50:00.000",
            "estimatedTime": "2017-11-17T08:50:00.000",
            "estimatedRunway": "2017-11-17T08:43:00.000"
        },
        "airline": {
            "name": "Air New Zealand",
            "iataCode": "NZ",
            "icaoCode": "ANZ"
        },
        "flight": {
            "number": "6686",
            "iataNumber": "NZ6686",
            "icaoNumber": "ANZ6686"
        },
        "codeshared": {
            "airline": {
                "name": "United Airlines",
                "iataCode": "UA",
                "icaoCode": "UAL"
            },
            "flight": {
                "number": "657",
                "iataNumber": "UA657",
                "icaoNumber": "UAL657"
            }
        }
    }
]
```

## Autocomplete

### Request 
GET https://aviation-edge.com/api/public/autocomplete?key=YOUR-API-KEY
### Responce
```
{
    "countries": [
        {
            "code": "IN",
            "name": "India",
            "countryCode": "IN",
            "countryName": "India",
            "type": "country"
        },
        {
            "code": "IO",
            "name": "British Indian Ocean Territory",
            "countryCode": "IO",
            "countryName": "British Indian Ocean Territory",
            "type": "country"
        }
    ],
    "cities": [
        {
            "code": "IND",
            "name": "Indianapolis",
            "cityCode": "IND",
            "cityName": "Indianapolis",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 39.714516,
            "lng": -86.29805,
            "timezone": "America/Indiana/Indianapolis",
            "type": "city"
        },
        {
            "code": "XSI",
            "name": "South Indian Lake",
            "cityCode": "XSI",
            "cityName": "South Indian Lake",
            "countryCode": "CA",
            "countryName": "Canada",
            "lat": 56.8,
            "lng": -98.916664,
            "timezone": "America/Winnipeg",
            "type": "city"
        },
        {
            "code": "IDI",
            "name": "Indiana",
            "cityCode": "IDI",
            "cityName": "Indiana",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.61667,
            "lng": -79.15,
            "timezone": "America/New_York",
            "type": "city"
        },
        {
            "code": "MUI",
            "name": "Fort Indiantown",
            "cityCode": "MUI",
            "cityName": "Fort Indiantown",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.447582,
            "lng": -76.59661,
            "timezone": "America/New_York",
            "type": "city"
        },
        {
            "code": "INS",
            "name": "Indian Springs",
            "cityCode": "INS",
            "cityName": "Indian Springs",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 36.583332,
            "lng": -115.666664,
            "timezone": "America/Los_Angeles",
            "type": "city"
        }
    ],
    "airports": [
        {
            "code": "IND",
            "name": "Indianapolis International",
            "cityCode": "IND",
            "cityName": "Indianapolis",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 39.714516,
            "lng": -86.29805,
            "timezone": "America/Indiana/Indianapolis",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "XSI",
            "name": "South Indian Lake",
            "cityCode": "XSI",
            "cityName": "South Indian Lake",
            "countryCode": "CA",
            "countryName": "Canada",
            "lat": 56.8,
            "lng": -98.916664,
            "timezone": "America/Winnipeg",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "UTO",
            "name": "Indian Mountain AFS",
            "cityCode": "UTO",
            "cityName": "Utopia Creek",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 65.99333,
            "lng": -153.70166,
            "timezone": "America/Anchorage",
            "type": "military_airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "IDI",
            "name": "ndiana County Airport (Jimmy Stewart Field)",
            "cityCode": "IDI",
            "cityName": "Indiana",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.61667,
            "lng": -79.15,
            "timezone": "America/New_York",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        }
    ],
    "citiesByCountries": [
        {
            "code": "DEL",
            "name": "New Delhi",
            "cityCode": "DEL",
            "cityName": "New Delhi",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 28.556555,
            "lng": 77.10079,
            "timezone": "Asia/Kolkata",
            "type": "city"
        },
        {
            "code": "BOM",
            "name": "Mumbai",
            "cityCode": "BOM",
            "cityName": "Mumbai",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 19.095509,
            "lng": 72.87497,
            "timezone": "Asia/Kolkata",
            "type": "city"
        },
        {
            "code": "GOI",
            "name": "Goa",
            "cityCode": "GOI",
            "cityName": "Goa",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 15.384534,
            "lng": 73.83983,
            "timezone": "Asia/Kolkata",
            "type": "city"
        },
        {
            "code": "IXL",
            "name": "Leh",
            "cityCode": "IXL",
            "cityName": "Leh",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 34.14035,
            "lng": 77.54746,
            "timezone": "Asia/Kolkata",
            "type": "city"
        },
        {
            "code": "BLR",
            "name": "Bangalore",
            "cityCode": "BLR",
            "cityName": "Bangalore",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 13.198889,
            "lng": 77.70556,
            "timezone": "Asia/Kolkata",
            "type": "city"
        }
    ],
    "citiesByAirports": [
        {
            "code": "IND",
            "name": "Indianapolis",
            "cityCode": "IND",
            "cityName": "Indianapolis",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 39.714516,
            "lng": -86.29805,
            "timezone": "America/Indiana/Indianapolis",
            "type": "city"
        },
        {
            "code": "IDI",
            "name": "Indiana",
            "cityCode": "IDI",
            "cityName": "Indiana",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.61667,
            "lng": -79.15,
            "timezone": "America/New_York",
            "type": "city"
        },
        {
            "code": "UTO",
            "name": "Utopia Creek",
            "cityCode": "UTO",
            "cityName": "Utopia Creek",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 65.99333,
            "lng": -153.70166,
            "timezone": "America/Anchorage",
            "type": "city"
        },
        {
            "code": "XSI",
            "name": "South Indian Lake",
            "cityCode": "XSI",
            "cityName": "South Indian Lake",
            "countryCode": "CA",
            "countryName": "Canada",
            "lat": 56.8,
            "lng": -98.916664,
            "timezone": "America/Winnipeg",
            "type": "city"
        }
    ],
    "airportsByCities": [
        {
            "code": "IND",
            "name": "Indianapolis International",
            "cityCode": "IND",
            "cityName": "Indianapolis",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 39.714516,
            "lng": -86.29805,
            "timezone": "America/Indiana/Indianapolis",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "IDI",
            "name": "ndiana County Airport (Jimmy Stewart Field)",
            "cityCode": "IDI",
            "cityName": "Indiana",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.61667,
            "lng": -79.15,
            "timezone": "America/New_York",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "INS",
            "name": "Af Aux",
            "cityCode": "INS",
            "cityName": "Indian Springs",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 36.583332,
            "lng": -115.666664,
            "timezone": "America/Los_Angeles",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "MUI",
            "name": "Muir AAF",
            "cityCode": "MUI",
            "cityName": "Fort Indiantown",
            "countryCode": "US",
            "countryName": "United States",
            "lat": 40.447582,
            "lng": -76.59661,
            "timezone": "America/New_York",
            "type": "unknown",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "XSI",
            "name": "South Indian Lake",
            "cityCode": "XSI",
            "cityName": "South Indian Lake",
            "countryCode": "CA",
            "countryName": "Canada",
            "lat": 56.8,
            "lng": -98.916664,
            "timezone": "America/Winnipeg",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        }
    ],
    "airportsByCountries": [
        {
            "code": "DEL",
            "name": "Indira Gandhi International",
            "cityCode": "DEL",
            "cityName": "New Delhi",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 28.556555,
            "lng": 77.10079,
            "timezone": "Asia/Kolkata",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "BOM",
            "name": "Chhatrapati Shivaji International (Sahar International)",
            "cityCode": "BOM",
            "cityName": "Mumbai",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 19.095509,
            "lng": 72.87497,
            "timezone": "Asia/Kolkata",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "GOI",
            "name": "Goa International",
            "cityCode": "GOI",
            "cityName": "Goa",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 15.384534,
            "lng": 73.83983,
            "timezone": "Asia/Kolkata",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "IXL",
            "name": "Bakula Rimpoche",
            "cityCode": "IXL",
            "cityName": "Leh",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 34.14035,
            "lng": 77.54746,
            "timezone": "Asia/Kolkata",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        },
        {
            "code": "BLR",
            "name": "Bangalore International Airport",
            "cityCode": "BLR",
            "cityName": "Bangalore",
            "countryCode": "IN",
            "countryName": "India",
            "lat": 13.198889,
            "lng": 77.70556,
            "timezone": "Asia/Kolkata",
            "type": "airport",
            "isRailRoad": 0,
            "isBusStation": 0
        }
    ]
}
```



