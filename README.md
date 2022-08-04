# Aviation Edge API

## API Response:
Aviation Edge provides various types of aviation data. We maintain both dynamic  (such as real-time aircraft tracking data or airport timetable data) and static data (such as non-frequently changing airlines, airplanes, airports, cities, countries, etc. databases in API form). Both the dynamic and static data is updated as necessary to ensure accuracy. The complete aviation data requires 1 API key to access which will return the latest result always when you refresh the data. This is the main advantage of Aviation Edge APIs, to make sure you do not have to collect your own data, maintain your own database and check for updates constantly from multiple sources.

### Documentation
You may find input parameters, output examples with explanations for each item, filter list, and more in the [documentation](https://aviation-edge.com/developers/).

## [Flights Tracker API](https://aviation-edge.com/flight-radar-and-tracker-api/)

### Request 
Data of all live flights in the world in one call:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&limit=30000`

Specific flight based on flight number:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&flightIata=W8519`

All flights of a specific airline:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&airlineIata=W8`

Flights from a departure location:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&depIata=MAD`

Flights to an arrival location:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&arrIata=GIG`

Flights within a circle area based on lat and lng values and radius as the distance:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&lat=51.5074&lng=0.1278&distance=100&arrIata=LHR`

Combinations: two airports and a specific airline flying between them:

**GET** `https://aviation-edge.com/v2/public/flights?key=[API_KEY]&depIata=ATL&arrIata=ORD&airlineIata=UA`

### Response
```

[
{"aircraft":
{
"iataCode":"B77W",
"icao24":"C0173A",
"icaoCode":"B77W",
"regNumber":"C-FIUR"
},
"airline":
{"iataCode":"AC",
"icaoCode":"ACA"
},
"arrival":
{"iataCode":"YYZ",
"icaoCode":"CYYZ"
},
"departure":
{"iataCode":"GRU",
"icaoCode":"SBGR"
},
"flight":
{"iataNumber":"AC91",
"icaoNumber":"ACA091",
"number":"91"
},
"geography":
{"altitude":10363.2,
"direction":342.0,
"latitude":23.36,
"longitude":-70.37
},
"speed":
{"horizontal":820.436,
"isGround":0.0,
"vspeed":0.0},
"status":"en-route",
"system":
{"squawk":null,
"updated":1643111484}
}
]
```

## [Airport Schedules API](https://aviation-edge.com/flight-schedule-and-timetable-of-airlines-and-airports/)

### Request 
For the departure schedule of a certain airport:

**GET** `https://aviation-edge.com/v2/public/timetable?key=[API_KEY]&iataCode=JFK&type=departure`

For the arrival schedule of a certain airport:

**GET** `https://aviation-edge.com/v2/public/timetable?key=[API_KEY]&iataCode=JFK&type=arrival`

### Response
```
[
{"airline":
{
"iataCode":"WS",
"icaoCode":"WJA",
"name":"WestJet"
},
"arrival":
{"actualRunway":"2022-01-24T23:48:00.000",
"actualTime":"2022-01-24T23:48:00.000",
"baggage":null,
"delay":"19",
"estimatedRunway":"2022-01-24T23:48:00.000",
"estimatedTime":"2022-01-24T23:29:00.000",
"gate":"A15",
"iataCode":"IAH",
"icaoCode":"KIAH",
"scheduledTime":"2022-01-24T23:29:00.000",
"terminal":"A"
}
]
```

## [Historical Airport Schedules API](https://aviation-edge.com/historical-flight-schedules-api/)

### Request 
For the departure schedule of a certain airport on a certain date:

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD`

For the arrival schedule of a certain airport on a certain date:

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD`

For the schedule of a certain airport of a certain date range (also available for arrival):

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD`

For the schedule of a certain airport on a certain date (or range) but only flights with a certain status:

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&status=cancelled`

For tracking individual historical flights:

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&flight_number=[1234]`

For filtering the flights of a certain airline from the arrival schedule of a certain airport on a certain date (also available for departure schedules and as a date range):

**GET** `https://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD&&airline_iata=TK`

### Response
```
[
{"type": "arrival", 
"status": "landed", 
"departure": 
{
"iataCode": "eyw",
"icaoCode": "keyw", 
"gate": "8", 
"delay": 15, 
"scheduledTime": "2021-11-02t16:55:00.000", 
"actualTime": "2021-11-02t17:09:00.000", 
"estimatedRunway": "2021-11-02t17:09:00.000", 
"actualRunway": "2021-11-02t17:09:00.000"
},
"arrival": 
{"iataCode": "iah", 
"icaoCode": "kiah", 
"terminal": "b", 
"baggage": "b3", 
"gate": "76", 
"scheduledTime": "2021-11-02t19:00:00.000", 
"estimatedTime": "2021-11-02t18:46:00.000", 
"actualTime": "2021-11-02t18:55:00.000",
"estimatedRunway": "2021-11-02t18:55:00.000",
"actualRunway": "2021-11-02t18:55:00.000"},
"airline":
{"name": "united airlines", 
"iataCode": "ua", 
"icaoCode": "ual"
}, 
"flight": 
{"number": "6264", 
"iataNumber": "ua6264", 
"icaoNumber": "ual6264"}
}
]
```

## [Future Airport Schedules API](https://aviation-edge.com/future-flight-schedules-and-timetables-of-airports-api/)

### Request 
For the departure schedule of a certain airport on a certain future date.

**GET** `https://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=departure&iataCode=BER&date=YYYY-MM-DD`

For the arrival schedule of a certain airport on a certain future date.

**GET** `https://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=arrival&iataCode=BER&date=YYYY-MM-DD`

For the flights that are scheduled to arrive at a certain airport on a certain date (out of a departure schedule).

**GET** `https://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=departure&iataCode=BER&arr_iataCode=ORY&date=YYYY-MM-DD`

For the flights that are scheduled to depart from a certain airport on a certain date (out of an arrival schedule).

**GET** `https://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=arrival&iataCode=BER&dep_iataCode=ory&date=YYYY-MM-DD`

### Response
```
[
{"weekday": "1",
"departure": 
{
"iataCode": "mty",
"icaoCode": "mmmy",
"terminal": "c",
"gate": "f2",
"scheduledTime": "20:35"
}, 
"arrival": 
{"iataCode": "iah", 
"icaoCode": "kiah",
"terminal": "d", 
"gate": "d12", 
"scheduledTime": "22:00"
}, 
"aircraft": 
{"modelCode": "a320", 
"modelText": "airbus a320-232"
},
"airline": 
{"name": "vivaaerobus",
"iataCode": "vb", 
"icaoCode": "viv"}, 
"flight": 
{"number": "616", 
"iataNumber": "vb616", 
"icaoNumber": "viv616"}
}
]
```

## [Autocomplete API](https://aviation-edge.com/airport-autocomplete/)

### Request 
Airports with the letters containing "xyz" in them:

**GET** `https://aviation-edge.com/v2/public/autocomplete?key=[API_KEY]&city=xyz`

### Response
```
[
{
"code": "AMS",
"name": "Amsterdam",
"cityCode": "AMS",
"cityName": "Amsterdam",
"countryCode": "NL",
"countryName": "Netherlands",
"lat": 52.3730556, "lng": 4.8922222,
"timezone": "Europe/Amsterdam",
"type": "city" } ],
"airports":
[
{
"code": "ZYA",
"name": "Amsterdam Centraal Railway Station",
"cityCode": "AMS",
"cityName": "Amsterdam",
"countryCode": "NL",
"countryName": "Netherlands",
"lat": 52.3730556,
"lng": 4.8922222,
"timezone": "Europe/Amsterdam",
"type": "rail_station",
"isRailRoad": 1,
"isBusStation": 0 },
{
"code": "AMS",
"name": "Schiphol",
"cityCode": "AMS",
"cityName": "Amsterdam",
"countryCode": "NL",
"countryName": "Netherlands",
"lat": 52.30907,
"lng": 4.763385,
"timezone": "Europe/Amsterdam",
"type": "airport",
"isRailRoad": 0,
"isBusStation": 0 } ],
"airportsByCities":
},
...
]
```

## [Airline Routes API](https://aviation-edge.com/airline-routes-database-and-api/)

### Request 
Static data on routes related to specific airports, airlines or flights:

**GET** `https://aviation-edge.com/v2/public/routes?key=[API_KEY]&departureIata=OTP`

**GET** `https://aviation-edge.com/v2/public/routes?key=[API_KEY]&departureIcao=LROP`

**GET** `https://aviation-edge.com/v2/public/routes?key=[API_KEY]&airlineIata=0B`

**GET** `https://aviation-edge.com/v2/public/routes?key=[API_KEY]&airlineIcao=BMS`

**GET** `https://aviation-edge.com/v2/public/routes?key=[API_KEY]&flightNumber=101`


Data on a specific route:

**GET** `http://aviation-edge.com/v2/public/routes?key=[API_KEY]&departureIata=OTP&departureIcao=LROP&airlineIata=0B&airlineIcao=BMS&flightNumber=101`

### Response
```
[
{ "departureIata": "OTP",
"departureIcao": "LROP",
"departureTerminal": null,
"departureTime": "09:15:00",
"arrivalIata": "TRN",
"arrivalIcao": "LIMF",
"arrivalTerminal": null,
"arrivalTime": "10:45:00",
"airlineIata": "0B",
"airlineIcao": "BMS",
"flightNumber": "101",
"codeshares": null,
"regNumber": "YR-BAP"
}
]
```

## [Nearby API](https://aviation-edge.com/nearby-airport-and-city-api/)

### Request 
Airports and cities nearby a certain latitude or longitude, within a certain distance in radius:

**GET** `https://aviation-edge.com/v2/public/nearby?key=[API_KEY]&lat=-5.466667&lng=122.6333&distance=100`

### Response
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
"isBusStation": 0, "distance": 0 },
{
"code": "RAQ",
"icao": "WAWR",
"name": "Sugimanuru",
"cityCode": "RAQ",
"cityName": "Raha",
"countryCode": "ID",
"countryName": "Indonesia",
"lat": -4.916667,
"lng": 122.583336,
"timezone": "Asia/Makassar",
"type": "airport",
"isRailRoad": 0,
"isBusStation": 0,
"distance": 61404
}
]
```

## Airlines API (please see the second table [here](https://aviation-edge.com/premium-api/) for all static APIs starting from this API)

### Request 
Entire database of airlines:

**GET** `https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]`

Data on a specific airline, you can search based on IATA airline code:

**GET** `https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIataAirline=AA`

Airlines based on the country code:

**GET** `https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIso2Country=US`

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

## Airplanes API

### Request 
Entire database of airplanes:

**GET** `https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]`

Data on a specific airplane based on registration number. 

**GET** `https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&numberRegistration=HB-JVE`

Airplanes based on the hex ICAO code. 

**GET** `https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&hexIcaoAirplane=4B19EA`

Data on airplanes of a specific airline based on airline IATA code. 

**GET** `https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&codeIataAirline=0B`

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

## Airplane-Types API

### Request 
Entire database of Aircraft types:

**GET** `https://aviation-edge.com/v2/public/planeTypeDatabase?key=[API_KEY]`

Data on a specific Aircraft type based on the IATA code:

**GET** `https://aviation-edge.com/v2/public/planeTypeDatabase?key=[API_KEY]&codeIataAircraft=100`

### Response
```
[
{
"planeTypeId": "100",
"nameAircraft": "Boeing 767-200 Freighter",
"codeIataAircraft": "76X"
},
{
"planeTypeId": "101",
"nameAircraft": "Boeing 767-300 Freighter",
"codeIataAircraft": "76Y"
},
{
"planeTypeId": "102",
"nameAircraft": "Boeing 777-200/200ER",
"codeIataAircraft": "772"
},
{ "planeTypeId": "103",
"nameAircraft": "Boeing 777-300",
"codeIataAircraft": "773"
},
{ "planeTypeId": "104",
"nameAircraft": "Boeing 777",
"codeIataAircraft": "777"
},
...
]
```

## Airports API

### Request 
Entire database of airports:

**GET** `https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]`

Data on a specific airport based on IATA code:

**GET** `https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIataAirport=AAH`

Airports in a country:

**GET** `https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIso2Country=DE`

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

## Cities API

### Request 
Entire database of cities. 

**GET** `https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]`

Data on a specific city based on IATA code. 

**GET** `https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIataCity=AAA`

Cities in a specific country:

**GET** `https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIso2Country=PF`

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

## Countries API

### Request 
Entire database of countries:

**GET** `https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]`

Data on a specific country based on ISO code:

**GET** `https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&codeIso2Country=AD` 

Data on a specific country based on name: 

**GET** `https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&nameCountry=Andorra`

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

## Taxes API

### Request 
Entire database of taxes:

**GET** `https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]`

Data on about a specific tax code, input the IATA tax code.

**GET** `https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]&codeIataTax=AC`

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

### Access & Support
[Contact us](https://aviation-edge.com/contact/) via email for any questions or support requests.

[Get your API key](https://aviation-edge.com/premium-api/) in a minute and start testing the data right away. The API is provided through API subscriptions. All plans grant access to the Airport Schedules API and other APIs with a difference of the monthly API call limit. Choose the best plan for you and upgrade, downgrade or cancel your plan anytime without  commitments.

### License
The use of the API is subject to Aviation Edge [Terms and Conditions](https://aviation-edge.com/api-terms-of-service/).
