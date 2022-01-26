# Aviation Edge API

## API Response:
Aviation Edge provides various types of aviation data. We maintain both dynamic  (such as real-time aircraft tracking data or airport timetable data) and static data (such as non-frequently changing airlines, airplanes, airports, cities, countries, etc. databases in API form). Both the dynamic and static data is updated as necessary to ensure accuracy. The complete aviation data requires 1 API key to access which will return the latest result always when you refresh the data. This is the main advantage of Aviation Edge APIs, to make sure you do not have to collect your own data, maintain your own database and check for updates constantly from multiple sources.

## Flights Tracker API

### Request 
To get information about all live flights in the world in one call:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&limit=30000

Specific flight based on flight number:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&flightIata=W8519

All flights of a specific Airlines:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&airlineIata=W8

Flights from departure location:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&depIata=MAD

Flights from arrival location:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&arrIata=GIG

Flights within a circle area based on lat and lng values and radius as the distance:

GET https://aviation-edge.com/v2/public/flights?key=[API_KEY]&lat=51.5074&lng=0.1278&distance=100&arrIata=LHR

Combinations: two airports and a specific airline flying between them:

GET http://aviation-edge.com/v2/public/flights?key=[API_KEY]&depIata=ATL&arrIata=ORD&airlineIata=UA

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

## Airport Schedules API

### Request 
For the departure schedule of a certain airport:

GET http://aviation-edge.com/v2/public/timetable?key=[API_KEY]&iataCode=JFK&type=departure

For the arrival schedule of a certain airport:

GET http://aviation-edge.com/v2/public/timetable?key=[API_KEY]&iataCode=JFK&type=arrival

Status can be: (landed, scheduled, cancelled, active, incident, diverted, redirected, unknown)


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

## Historical Airport Schedules API

### Request 
For the departure schedule of a certain airport on a certain date:

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD

For the arrival schedule of a certain airport on a certain date:

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD

For the schedule of a certain airport of a certain date range (also available for arrival):

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD

For the schedule of a certain airport on a certain date (or range) but only flights with a certain status:

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&status=cancelled

For tracking individual historical flights:

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=departure&date_from=YYYY-MM-DD&date_to=YYYY-MM-DD&flight_number=[1234]

For filtering the flights of a certain airline from the arrival schedule of a certain airport on a certain date (also available for departure schedules and as a date range):

GET http://aviation-edge.com/v2/public/flightsHistory?key=[API_KEY]&code=JFK&type=arrival&date_from=YYYY-MM-DD&&airline_iata=TK

Status can be: "active" (for departure schedules only), "landed" (for arrival schedules only), "cancelled", "unknown"
Delay amount is included in minutes if a flight was delayed at the date.
The maximum date range can be 30 days which may be reduced to 3-5 days for large airports with heavy traffic.

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

## Future Airport Schedules API

### Request 
For the departure schedule of a certain airport on a certain future date.

GET http://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=departure&iataCode=BER&date=YYYY-MM-DD

For the arrival schedule of a certain airport on a certain future date.

GET http://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=arrival&iataCode=BER&date=YYYY-MM-DD

For the flights that are scheduled to arrive at a certain airport on a certain date (out of a departure schedule).

GET http://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=departure&iataCode=BER&arr_iataCode=ORY&date=YYYY-MM-DD

For the flights that are scheduled to depart from a certain airport on a certain date (out of an arrival schedule).

GET https://aviation-edge.com/v2/public/flightsFuture?key=[API_KEY]&type=arrival&iataCode=BER&dep_iataCode=ory&date=YYYY-MM-DD


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

## Airlines API

### Request 
For the entire database of airlines.

GET https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]

For information about a specific airline, you can search based on IATA airline code. 

GET https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIataAirline=AA

Search for the airlines based on the country codes. 

GET https://aviation-edge.com/v2/public/airlineDatabase?key=[API_KEY]&codeIso2Country=US

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
For the entire database of airplanes. 

GET https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]

For information about a specific airplane, you can search based on registration number. 

GET https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&numberRegistration=HB-JVE

For the airplanes based on the hex ICAO code. 

GET https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&hexIcaoAirplane=4B19EA

For information about airplanes of a specific airline, you can search based on airline IATA code. 

GET https://aviation-edge.com/v2/public/airplaneDatabase?key=[API_KEY]&codeIataAirline=0B

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

## Airports API

### Request 
For the entire database of airports. 

GET https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]

For information about a specific airport, you can search based on IATA code. 

GET https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIataAirport=AAH

For the airports based on the country code. 

GET https://aviation-edge.com/v2/public/airportDatabase?key=[API_KEY]&codeIso2Country=DE

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
For the entire database of city benchmark. 

GET https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]

For information about a specific city benchmark information, you can search based on IATA code. 

GET https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIataCity=AAA 

For the city benchmark information based on the country code. 

GET https://aviation-edge.com/v2/public/cityDatabase?key=[API_KEY]&codeIso2Country=PF

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
For the entire database of countries. 

GET https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]

For information about a specific country, you can search based on ISO code. 

GET https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&codeIso2Country=AD 

For the country information based on the country name. 

GET https://aviation-edge.com/v2/public/countryDatabase?key=[API_KEY]&nameCountry=Andorra

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
For the entire database of taxes.

GET https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]

For information about a specific tax code, input the IATA tax code.

GET https://aviation-edge.com/v2/public/taxDatabase?key=[API_KEY]&codeIataTax=AC 

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


