# aviation-edge-api

## API Response:
Aviation edge data refers to any data that, by nature, is not frequently changing. However, due to the size of our database, there are constantly updates happening, making this a valuable API when you have to maintain a big database yourself, make sure to check for updates frequently using your API key. The moment a change is detected we will pursue and update our database.


## Airlines

### Request 
GET https://aviation-edge.com/api/public/airlineDatabase?key=YOUR-API-KEY

GET https://aviation-edge.com/api/public/airlineDatabase?key=YOUR-API-KEY&codeIataAirline=AA

GET https://aviation-edge.com/api/public/airlineDatabase?key=YOUR-API-KEY&codeIso2Country=US

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
GET https://aviation-edge.com/api/public/airplaneDatabase?key=YOUR-API-KEY

GET https://aviation-edge.com/api/public/airplaneDatabase?key=YOUR-API-KEY&numberRegistration=HB-JVE

GET https://aviation-edge.com/api/public/airplaneDatabase?key=YOUR-API-KEY&hexIcaoAirplane=4B19EA

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

GET https://aviation-edge.com/api/public/airportDatabase?key=YOUR-API-KEY&codeIataAirport=AAH

GET https://aviation-edge.com/api/public/airportDatabase?key=YOUR-API-KEY&codeIso2Country=DE
### Response
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

GET https://aviation-edge.com/api/public/benchmarkAirlines?key=YOUR-API-KEY&codeIataAirline=AA

GET https://aviation-edge.com/api/public/benchmarkAirlines?key=YOUR-API-KEY&codeIso2Country=US
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
GET https://aviation-edge.com/api/public/benchmarkAirports?key=YOUR-API-KEY

GET https://aviation-edge.com/api/public/benchmarkAirports?key=YOUR-API-KEY&codeIataAirport=AAA

GET https://aviation-edge.com/api/public/benchmarkAirports?key=YOUR-API-KEY&codeIso2Country=PF
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
GET https://aviation-edge.com/api/public/benchmarkCities?key=YOUR-API-KEY

GET https://aviation-edge.com/api/public/benchmarkCities?key=YOUR-API-KEY&codeIataCity=AAA

GET https://aviation-edge.com/api/public/benchmarkCities?key=YOUR-API-KEY&codeIso2Country=PF
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
GET https://aviation-edge.com/api/public/cityDatabase?key=YOUR-API-KEY

GET https://aviation-edge.com/api/public/cityDatabase?key=YOUR-API-KEY&codeIataCity=AAA

GET https://aviation-edge.com/api/public/cityDatabase?key=YOUR-API-KEY&codeIso2Country=PF
### Response
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

GET https://aviation-edge.com/api/public/countryDatabase?key=YOUR-API-KEY&codeIso2Country=AD

GET https://aviation-edge.com/api/public/countryDatabase?key=YOUR-API-KEY&nameCountry=Andorra
### Response
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

GET https://aviation-edge.com/api/public/taxDatabase?key=YOUR-API-KEY&codeIataTax=AB
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


