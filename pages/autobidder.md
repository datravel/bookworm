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

Request, many passengers and connections, two-ways search:
```json
{
    "search": {
        "route": "MOW>LON",
        "forth": "2016-08-20",
        "adults": 2,
        "children": 3,
        "infants": 0,
        "classOfService": "E",
        "back": "2016-08-21"
    },
    "tickets": {
        "a5db31b0398ec1e7aa9f49095508562b-10": {
            "gds": "sabre_ru",
            "netPrice": "68018 RUB",
            "validatingCarrier": "OS",
            "segments": [
                {
                    "marketingCarrier": "OS",
                    "operatingCarrier": "OS",
                    "flightNumber": 602,
                    "departureTime": "2016-08-20T14:35:00",
                    "arrivalTime": "2016-08-20T16:35:00",
                    "route": "DME>VIE",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "OS",
                    "operatingCarrier": "OS",
                    "flightNumber": 455,
                    "departureTime": "2016-08-20T17:15:00",
                    "arrivalTime": "2016-08-20T18:40:00",
                    "route": "VIE>LHR",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "LX",
                    "operatingCarrier": "LX",
                    "flightNumber": 317,
                    "departureTime": "2016-08-21T08:40:00",
                    "arrivalTime": "2016-08-21T11:35:00",
                    "route": "LHR>ZRH",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "LX",
                    "operatingCarrier": "LX",
                    "flightNumber": 1326,
                    "departureTime": "2016-08-21T12:20:00",
                    "arrivalTime": "2016-08-21T16:55:00",
                    "route": "ZRH>DME",
                    "classOfService": "E",
                    "bookingClass": "K"
                }
            ],
            "passengers": [
                {
                    "ptc": "ADT",
                    "fare": "4755 RUB",
                    "total": "14944 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        }
                    ]
                },
                {
                    "ptc": "ADT",
                    "fare": "4755 RUB",
                    "total": "14944 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                }
            ]
        },
        "1a4b14999161dd9028ba93814139a3a7-10": {
            "gds": "sabre_ru",
            "netPrice": "68018 RUB",
            "validatingCarrier": "OS",
            "segments": [
                {
                    "marketingCarrier": "OS",
                    "operatingCarrier": "OS",
                    "flightNumber": 602,
                    "departureTime": "2016-08-20T14:35:00",
                    "arrivalTime": "2016-08-20T16:35:00",
                    "route": "DME>VIE",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "OS",
                    "operatingCarrier": "OS",
                    "flightNumber": 455,
                    "departureTime": "2016-08-20T17:15:00",
                    "arrivalTime": "2016-08-20T18:40:00",
                    "route": "VIE>LHR",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "LX",
                    "operatingCarrier": "LX",
                    "flightNumber": 325,
                    "departureTime": "2016-08-21T17:10:00",
                    "arrivalTime": "2016-08-21T19:55:00",
                    "route": "LHR>ZRH",
                    "classOfService": "E",
                    "bookingClass": "K"
                },
                {
                    "marketingCarrier": "LX",
                    "operatingCarrier": "LX",
                    "flightNumber": 1324,
                    "departureTime": "2016-08-21T21:25:00",
                    "arrivalTime": "2016-08-22T02:05:00",
                    "route": "ZRH>DME",
                    "classOfService": "E",
                    "bookingClass": "K"
                }
            ],
            "passengers": [
                {
                    "ptc": "ADT",
                    "fare": "4755 RUB",
                    "total": "14944 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        }
                    ]
                },
                {
                    "ptc": "ADT",
                    "fare": "4755 RUB",
                    "total": "14944 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        },
                        {
                            "fareBasis": "K23LGT4"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                },
                {
                    "ptc": "CNN",
                    "fare": "3600 RUB",
                    "total": "12710 RUB",
                    "coupons": [
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        },
                        {
                            "fareBasis": "K23LGT4\\\/CH25"
                        }
                    ]
                }
            ]
        }
    },
    "meta": false,
    "partner": "momondo"
}
```

Response:
```json
{
    "tickets": {
        "a5db31b0398ec1e7aa9f49095508562b-10": {
            "breakdown": {
                "fare": "20310.00 RUB",
                "total": "67268.36 RUB",
                "net": "68018.00 RUB",
                "markup": {
                    "unaccountedCarrierCommission": "0.00 RUB",
                    "residual": "0.00 RUB",
                    "carrierCommission": "-5.00 RUB",
                    "carrierBonus": "0.00 RUB",
                    "channelCommission": "800.00 RUB",
                    "total": "-749.64 RUB",
                    "currencyRisk": "0.00 RUB",
                    "acquiringCommission": "1118.91 RUB",
                    "adjustments": {
                        "overrideToNet": "-1913.91 RUB",
                        "markup": "-749.64 RUB"
                    },
                    "gdsBonus": "0.00 RUB"
                },
                "taxes": "47708.00 RUB"
            },
            "source": "overridden",
            "useThisPrice": true,
            "price": "67268.36 RUB",
            "disableTicketing": false,
            "partner": "momondo",
            "itinerary": {
                "validatingCarrier": "OS",
                "passengers": [
                    {
                        "ptc": "ADT",
                        "fare": "4755.00 RUB",
                        "total": "14944.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            }
                        ]
                    },
                    {
                        "ptc": "ADT",
                        "fare": "4755.00 RUB",
                        "total": "14944.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    }
                ],
                "segments": [
                    {
                        "departureTime": "2016-08-20T14:35",
                        "classOfService": "Economy",
                        "route": "DME>VIE",
                        "operatingCarrier": "OS",
                        "flightNumber": 602,
                        "marketingCarrier": "OS",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-20T17:15",
                        "classOfService": "Economy",
                        "route": "VIE>LHR",
                        "operatingCarrier": "OS",
                        "flightNumber": 455,
                        "marketingCarrier": "OS",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-21T08:40",
                        "classOfService": "Economy",
                        "route": "LHR>ZRH",
                        "operatingCarrier": "LX",
                        "flightNumber": 317,
                        "marketingCarrier": "LX",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-21T12:20",
                        "classOfService": "Economy",
                        "route": "ZRH>DME",
                        "operatingCarrier": "LX",
                        "flightNumber": 1326,
                        "marketingCarrier": "LX",
                        "bookingClass": "K"
                    }
                ],
                "netPrice": "68018.00 RUB",
                "gds": "sabre_ru"
            },
            "comment": "\u0432\u0441\u0435 \u0430\u043a sabreRU \u043c\u043e\u043c\u043e\u043d\u0434\u043e1 \u0440\u0442 \u043f\u0435\u0440\u0435\u0441\u0430\u0434\u043a\u0430",
            "minPrice": "67268.36 RUB",
            "fairPrice": {
                "unaccountedCarrierCommission": "0.00 %",
                "carrierCommission": "1.00 RUB",
                "carrierBonus": "0.00 %",
                "fare": "20310.00 RUB",
                "currencyRiskAmount": "0.00 RUB",
                "adjustedChannelCommissionAmount": "800.00 RUB",
                "price": "69931.91 RUB",
                "acquiring": "uniteller",
                "hoursBeforeDeparture": 25.720277777778,
                "net": "68018.00 RUB",
                "carrierBonusAmount": "0.00 RUB",
                "unsafeDepartureMarkupAmount": "0.00 RUB",
                "gdsBonusAmount": "0.00 RUB",
                "unaccountedCarrierCommissionAmount": "0.00 RUB",
                "carrierCommissionAmount": "-5.00 RUB",
                "gdsBonus": "0.00 %",
                "channelCommissionAmount": "800.00 RUB",
                "acquiringCommissionAmount": "1118.91 RUB",
                "dealPrice": "69931.91 RUB",
                "contract": "bsp-ru",
                "gds": "sabre_ru"
            },
            "partnerCommission": "800.00 RUB",
            "search": {
                "children": [
                    2,
                    2,
                    2
                ],
                "forth": "2016-08-20",
                "classOfService": "Economy",
                "back": "2016-08-21",
                "adults": 2,
                "route": "MOW>LON"
            }
        },
        "1a4b14999161dd9028ba93814139a3a7-10": {
            "breakdown": {
                "fare": "20310.00 RUB",
                "total": "67268.36 RUB",
                "net": "68018.00 RUB",
                "markup": {
                    "unaccountedCarrierCommission": "0.00 RUB",
                    "residual": "0.00 RUB",
                    "carrierCommission": "-5.00 RUB",
                    "carrierBonus": "0.00 RUB",
                    "channelCommission": "800.00 RUB",
                    "total": "-749.64 RUB",
                    "currencyRisk": "0.00 RUB",
                    "acquiringCommission": "1118.91 RUB",
                    "adjustments": {
                        "overrideToNet": "-1913.91 RUB",
                        "markup": "-749.64 RUB"
                    },
                    "gdsBonus": "0.00 RUB"
                },
                "taxes": "47708.00 RUB"
            },
            "source": "overridden",
            "useThisPrice": true,
            "price": "67268.36 RUB",
            "disableTicketing": false,
            "partner": "momondo",
            "itinerary": {
                "validatingCarrier": "OS",
                "passengers": [
                    {
                        "ptc": "ADT",
                        "fare": "4755.00 RUB",
                        "total": "14944.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            }
                        ]
                    },
                    {
                        "ptc": "ADT",
                        "fare": "4755.00 RUB",
                        "total": "14944.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            },
                            {
                                "fareBasis": "K23LGT4"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    },
                    {
                        "ptc": "CNN",
                        "fare": "3600.00 RUB",
                        "total": "12710.00 RUB",
                        "coupons": [
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            },
                            {
                                "fareBasis": "K23LGT4\\\/CH25"
                            }
                        ]
                    }
                ],
                "segments": [
                    {
                        "departureTime": "2016-08-20T14:35",
                        "classOfService": "Economy",
                        "route": "DME>VIE",
                        "operatingCarrier": "OS",
                        "flightNumber": 602,
                        "marketingCarrier": "OS",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-20T17:15",
                        "classOfService": "Economy",
                        "route": "VIE>LHR",
                        "operatingCarrier": "OS",
                        "flightNumber": 455,
                        "marketingCarrier": "OS",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-21T17:10",
                        "classOfService": "Economy",
                        "route": "LHR>ZRH",
                        "operatingCarrier": "LX",
                        "flightNumber": 325,
                        "marketingCarrier": "LX",
                        "bookingClass": "K"
                    },
                    {
                        "departureTime": "2016-08-21T21:25",
                        "classOfService": "Economy",
                        "route": "ZRH>DME",
                        "operatingCarrier": "LX",
                        "flightNumber": 1324,
                        "marketingCarrier": "LX",
                        "bookingClass": "K"
                    }
                ],
                "netPrice": "68018.00 RUB",
                "gds": "sabre_ru"
            },
            "comment": "\u0432\u0441\u0435 \u0430\u043a sabreRU \u043c\u043e\u043c\u043e\u043d\u0434\u043e1 \u0440\u0442 \u043f\u0435\u0440\u0435\u0441\u0430\u0434\u043a\u0430",
            "minPrice": "67268.36 RUB",
            "fairPrice": {
                "unaccountedCarrierCommission": "0.00 %",
                "carrierCommission": "1.00 RUB",
                "carrierBonus": "0.00 %",
                "fare": "20310.00 RUB",
                "currencyRiskAmount": "0.00 RUB",
                "adjustedChannelCommissionAmount": "800.00 RUB",
                "price": "69931.91 RUB",
                "acquiring": "uniteller",
                "hoursBeforeDeparture": 25.720277777778,
                "net": "68018.00 RUB",
                "carrierBonusAmount": "0.00 RUB",
                "unsafeDepartureMarkupAmount": "0.00 RUB",
                "gdsBonusAmount": "0.00 RUB",
                "unaccountedCarrierCommissionAmount": "0.00 RUB",
                "carrierCommissionAmount": "-5.00 RUB",
                "gdsBonus": "0.00 %",
                "channelCommissionAmount": "800.00 RUB",
                "acquiringCommissionAmount": "1118.91 RUB",
                "dealPrice": "69931.91 RUB",
                "contract": "bsp-ru",
                "gds": "sabre_ru"
            },
            "partnerCommission": "800.00 RUB",
            "search": {
                "children": [
                    2,
                    2,
                    2
                ],
                "forth": "2016-08-20",
                "classOfService": "Economy",
                "back": "2016-08-21",
                "adults": 2,
                "route": "MOW>LON"
            }
        }
    },
    "rejectedTickets": []
}
```
