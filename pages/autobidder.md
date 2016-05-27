# Autobidder
Request sample
```
curl -X POST -H "Content-Type: application/json" -H "Cache-Control: no-cache" -d '{
    "search": {
        "route": "BEG>DME",
        "forth": "2016-06-01",
        "adults": 1,
        "children": 0,
        "infants": 0,
        "classOfService": "E"
    },
    "tickets": {
        "11d45e41e99dd209f6477cad9a9cf689-10": {
            "gds": "sabre_ru",
            "netPrice": "13268 RUB",
            "validatingCarrier": "A3",
            "segments": [{
                "marketingCarrier": "A3",
                "operatingCarrier": "JU",
                "flightNumber": 1103,
                "departureTime": "2016-06-01T13:20:00",
                "arrivalTime": "2016-06-01T15:50:00",
                "route": "BEG>ATH",
                "classOfService": "E",
                "bookingClass": "U"
            }, {
                "marketingCarrier": "A3",
                "operatingCarrier": "A3",
                "flightNumber": 972,
                "departureTime": "2016-06-02T09:05:00",
                "arrivalTime": "2016-06-02T12:25:00",
                "route": "ATH>DME",
                "classOfService": "E",
                "bookingClass": "P"
            }],
            "passengers": [{
                "ptc": "ADT",
                "fare": "9045 RUB",
                "total": "13268 RUB",
                "coupons": [{
                    "fareBasis": "U2A3AL"
                }, {
                    "fareBasis": "P2A3M"
                }]
            }]
        }
    },
    "meta": false,
    "partner": "DA-WEB"
}' "http://autobidder.int.datravel.com/price"
```
Response
```
{
    "tickets": {
        "11d45e41e99dd209f6477cad9a9cf689-10": {
            "breakdown": {
                "fare": "9045.00 RUB",
                "total": "13390.36 RUB",
                "net": "13268.00 RUB",
                "markup": {
                    "unaccountedCarrierCommission": "0.00 RUB",
                    "residual": "0.00 RUB",
                    "carrierCommission": "-1.00 RUB",
                    "carrierBonus": "0.00 RUB",
                    "channelCommission": "0.00 RUB",
                    "total": "122.36 RUB",
                    "currencyRisk": "0.00 RUB",
                    "acquiringCommission": "215.72 RUB",
                    "adjustments": {
                        "overrideToNet": "-214.72 RUB",
                        "markup": "122.36 RUB"
                    },
                    "gdsBonus": "0.00 RUB"
                },
                "taxes": "4223.00 RUB"
            },
            "source": "overridden",
            "useThisPrice": true,
            "price": "13390.36 RUB",
            "disableTicketing": false,
            "partner": "DA-WEB",
            "itinerary": {
                "validatingCarrier": "A3",
                "passengers": [{
                    "ptc": "ADT",
                    "fare": "9045.00 RUB",
                    "total": "13268.00 RUB",
                    "coupons": [{
                        "fareBasis": "U2A3AL"
                    }, {
                        "fareBasis": "P2A3M"
                    }]
                }],
                "segments": [{
                    "departureTime": "2016-06-01T13:20",
                    "classOfService": "Economy",
                    "route": "BEG>ATH",
                    "operatingCarrier": "JU",
                    "flightNumber": 1103,
                    "marketingCarrier": "A3",
                    "bookingClass": "U"
                }, {
                    "departureTime": "2016-06-02T09:05",
                    "classOfService": "Economy",
                    "route": "ATH>DME",
                    "operatingCarrier": "A3",
                    "flightNumber": 972,
                    "marketingCarrier": "A3",
                    "bookingClass": "P"
                }],
                "netPrice": "13268.00 RUB",
                "gds": "sabre_ru"
            },
            "comment": "закрывашка DAWEBСейбр Русский",
            "minPrice": "13390.36 RUB",
            "fairPrice": {
                "unaccountedCarrierCommission": "0.00 %",
                "carrierCommission": "1.00 RUB",
                "carrierBonus": "0.00 %",
                "fare": "9045.00 RUB",
                "currencyRiskAmount": "0.00 RUB",
                "adjustedChannelCommissionAmount": "0.00 RUB",
                "price": "13482.72 RUB",
                "acquiring": "uniteller",
                "hoursBeforeDeparture": 124,
                "net": "13268.00 RUB",
                "carrierBonusAmount": "0.00 RUB",
                "unsafeDepartureMarkupAmount": "0.00 RUB",
                "gdsBonusAmount": "0.00 RUB",
                "unaccountedCarrierCommissionAmount": "0.00 RUB",
                "carrierCommissionAmount": "-1.00 RUB",
                "gdsBonus": "0.00 %",
                "channelCommissionAmount": "0.00 RUB",
                "acquiringCommissionAmount": "215.72 RUB",
                "dealPrice": "13482.72 RUB",
                "contract": "bsp-ru",
                "gds": "sabre_ru"
            },
            "partnerCommission": "0.00 RUB",
            "search": {
                "children": [],
                "forth": "2016-06-01",
                "classOfService": "Economy",
                "adults": 1,
                "route": "BEG>DME"
            }
        }
    },
    "rejectedTickets": {}
}
```
