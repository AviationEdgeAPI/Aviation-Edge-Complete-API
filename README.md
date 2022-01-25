# Aviation Edge API

## API Response:
Aviation Edge has various types of aviation data. We maintain both dynamic  (such as real-time aircraft tracking data or airport timetable data) and static data (such as non-frequently changing airlines, airplanes, airports, cities, countries, etc. databases in API form). Both the dynamic and static data is updated as necessary to ensure accuracy. The complete aviation data requires 1 API key to access which will return the latest result always when you refresh the data. This is the main advantage of Aviation Edge APIs, to make sure you do not have to collect your own data, maintain your own database and check for updates constantly from multiple sources.

## Flights Tracker API

### Request 



## Airlines

### Request 
GET https://aviation-edge.com/api/public/airlineDatabase?key=api_key

GET https://aviation-edge.com/api/public/airlineDatabase?key=api_key&codeIataAirline=AA

GET https://aviation-edge.com/api/public/airlineDatabase?key=api_key&codeIso2Country=US

### Response
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
GET https://aviation-edge.com/api/public/airplaneDatabase?key=api_key

GET https://aviation-edge.com/api/public/airplaneDatabase?key=api_key&numberRegistration=HB-JVE

GET https://aviation-edge.com/api/public/airplaneDatabase?key=api_key&hexIcaoAirplane=4B19EA

### Response
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
    } 
 ]
```

## Airport

### Request 
GET https://aviation-edge.com/api/public/airportDatabase?key=api_key

GET https://aviation-edge.com/api/public/airportDatabase?key=api_key&codeIataAirport=AAH

GET https://aviation-edge.com/api/public/airportDatabase?key=api_key&codeIso2Country=DE
### Response
```
[
    {
        "airportId": "7",
        "nameAirport": "Aachen/Merzbruck",
        "codeIataAirport": "AAH",
        "codeIcaoAirport": "EDKA",
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
GET https://aviation-edge.com/api/public/benchmarkAirlines?key=api_key

GET https://aviation-edge.com/api/public/benchmarkAirlines?key=api_key&codeIataAirline=AA

GET https://aviation-edge.com/api/public/benchmarkAirlines?key=api_key&codeIso2Country=US
### Response
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
GET https://aviation-edge.com/api/public/benchmarkAirports?key=api_key

GET https://aviation-edge.com/api/public/benchmarkAirports?key=api_key&codeIataAirport=AAA

GET https://aviation-edge.com/api/public/benchmarkAirports?key=api_key&codeIso2Country=PF
### Response
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
GET https://aviation-edge.com/api/public/benchmarkCities?key=api_key

GET https://aviation-edge.com/api/public/benchmarkCities?key=api_key&codeIataCity=AAA

GET https://aviation-edge.com/api/public/benchmarkCities?key=api_key&codeIso2Country=PF
### Response
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
GET https://aviation-edge.com/api/public/cityDatabase?key=api_key

GET https://aviation-edge.com/api/public/cityDatabase?key=api_key&codeIataCity=AAA

GET https://aviation-edge.com/api/public/cityDatabase?key=api_key&codeIso2Country=PF
### Response
```
[
    {
        "cityId": "1",
        "nameCity": "Anaa",
        "codeIataCity": "AAA",
        "codeIso2Country": "PF",
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
GET https://aviation-edge.com/api/public/countryDatabase?key=api_key

GET https://aviation-edge.com/api/public/countryDatabase?key=api_key&codeIso2Country=AD

GET https://aviation-edge.com/api/public/countryDatabase?key=api_key&nameCountry=Andorra
### Response
```
[
    {
        "countryId": "1",
        "nameCountry": "Andorra",
        "codeIso2Country": "AD",
        "codeIso3Country": "AND",
        "numericIso": "20",
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
GET https://aviation-edge.com/api/public/taxDatabase?key=api_key

GET https://aviation-edge.com/api/public/taxDatabase?key=api_key&codeIataTax=AB
### Response
```
[
    {
        "taxId": "1",
        "nameTax": "Government Tax",
        "codeIataTax": "AB"
    }
]
```


