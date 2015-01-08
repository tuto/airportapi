FORMAT: 1A
HOST: http://www.lan.com

# Latam Airport API

# Group Searchs Pnrs
  Metodos usados para realizar busqueda de pnrs por diferentes criterios
  Todas las busquedas devuelven por defecto una lista de urls a los diferentes pnrs encontrados

  **Filters**
    Se puede agregar filtros a la busqueda para traer mas información en la respuesta

  **Ejemplo**        
    Url con filtro
    _ws/api/airport/1/pnrs/search?frequent_flier=324234234234&carrier=LA&filters=itineraries,upgradeInfo_

**Filtros**
1. **itineraries**: Lista de itinerarios
2. **passengers**: Lista de pasajeros  
3. **updgradeInfo**: Información para upgrade
4. **checkinInfo**: Información para checkin
5. **count**: numero de resultados por pagina 


## Search Pnrs By frequent Flyer [/ws/api/airport/1/pnrs/{?frequent_flyer,carrier}]
+ Parameters

    + frequent_flyer (number) ... ff.
    + carrier (string) ... carrier.

## By frequent Flyer[GET]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
            }

+ Response 200

            
      + Headers
    
            Content-Type:application/json
      + Body
    
            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {

               "pnrs": [
                  {
                      "recordLocator": "1111D",
                      "link" : "/ws/api/airport/1/pnr/1111D"
                  },
                  {
                      "recordLocator": "W222H",
                      "link" : "/ws/api/airport/1/pnr/W222H"
                  }
                ],
                "paging" : {
                  "previous" : "/ws/api/airport/1/pnrs/search/{?frequent_flyer,carrier, page=0, count=2}",
                  "next" : "/ws/api/airport/1/pnrs/search/{?frequent_flyer,carrier, page=1, count=2}"
                }
              }
            }


## Search Pnrs By Foid [/ws/api/airport/1/pnrs/search/{?foid_country,foid_code,foid_number}]
+ Parameters

    + foid_number (number) ... foid number.
    + foid_code (number) ... foid code.
    + foid_country (string) ... foid country.

## By Foid [GET]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
            }

+ Response 200

            
      + Headers
    
            Content-Type:application/json
      + Body
    
            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {

               "pnrs": [
                  {
                      "recordLocator": "1111D",
                      "link" : "/ws/api/airport/1/pnr/1111D"
                  },
                  {
                      "recordLocator": "W222H",
                      "link" : "/ws/api/airport/1/pnr/W222H"
                  }
                ],
                "paging" : {
                  "previous" : "/ws/api/airport/1/pnrs/search/{?frequent_flyer,carrier, page=0, count=2}",
                  "next" : "/ws/api/airport/1/pnrs/search/{?frequent_flyer,carrier, page=1, count=2}"
                }
              }
            }

## Search Pnrs By E-ticket [/ws/api/airport/1/pnrs/search/{?eticket_number}]
+ Parameters

    + eticket_number (number) ... eticket number.

## By E-Ticket [GET]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
            }

+ Response 200

            
      + Headers
    
            Content-Type:application/json
      + Body
    
            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {

               "pnrs": [
                  {
                      "recordLocator": "1111D",
                      "link" : "/ws/api/airport/1/pnr/1111D"
                  }
                ]
              }
            }



# Group PNR
## Pnr [/ws/api/airport/1/pnr/{record_locator}]
## get pnr[GET]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "frequent_flyer" : "234235324",
             "carrier" : "JJ"
            }
            
+ Response 200

      + Headers
    
            Content-Type:application/json
      + Body
    
            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {
               "itineraries": [
                  {
                      "recordLocator": "1111D",
                      "passengers": [
                          {
                              "lastName": "Velasco",
                              "firstName": "Jose",
                              "passengerType": "ADT",
                              "fqtv": {
                                  "fqtvNumber": "45454578",
                                  "category": "Comodoro",
                                  "program": "Fidelidade"
                              },
                              "passangerId": "1"
                          },
                          {
                              "lastName": "Seco",
                              "firstName": "Federico",
                              "passengerType": "ADT",
                              "fqtv": {
                                  "fqtvNumber": "111548",
                                  "category": "Premium",
                                  "program": "Fidelidade"
                              },
                              "passangerId": "2"
                          },
                          {
                              "lastName": "Di Rosario",
                              "firstName": "Fiorela",
                              "passengerType": "ADT",
                              "passangerId": "3"
                          }
                      ],
                      "messages": [
                          {
                              "code": "INFO",
                              "text": "pnr_info_fruit"
                          },
                          {
                              "code": "WARNING",
                              "text": "pnr_warning_fruit"
                          }
                      ],
                      "itinerary": {
                          "originDestinations": [
                              {
                                  "messages": [
                                      {
                                          "code": "INFO",
                                          "text": "od_info_fruit"
                                      }
                                  ],
                                  "segments": [
                                      {
                                          "id": "1111D_segment_1_1_id",
                                          "flight": {
                                              "flightNumber": "JJ432",
                                              "operatingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              },
                                              "marketingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              }
                                          },
                                          "legs": [
                                              {
                                                  "id": "11",
                                                  "departureAirport": {
                                                      "isoCode": "XXX",
                                                      "name": "Aeropuerto de Carrasco",
                                                      "city": {
                                                          "code": "XX1",
                                                          "name": "Montevideo"
                                                      }
                                                  },
                                                  "arrivalAirport": {
                                                      "isoCode": "YYY",
                                                      "name": "Aeroparque",
                                                      "city": {
                                                          "code": "YY1",
                                                          "name": "Buenos Aires"
                                                      }
                                                  },
                                                  "departureDateTime": "2014-12-11T10:20",
                                                  "arrivalDateTime": "2014-12-11T11:20",
                                                  "passengerUpgInfos": [
                                                      {
                                                          "upgPosition": 3,
                                                          "passengerId": "1",
                                                          "upgStatus": "POSTULATE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "2",
                                                          "upgStatus": "POSTULABLE",
                                                          "messages": [
                                                              {
                                                                  "code": "INFO",
                                                                  "text": "passanger_upg_info_info_fruit"
                                                              }
                                                          ]
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "3",
                                                          "upgStatus": "POSTULABLE"
                                                      }
                                                  ],
                                                  passengerCheckinInfo : {
                                                   "status": "NOTCHECKED",
                                                    "documentsAllow": {
                                                        "boardingpasspdf": true,
                                                        "emailboardingpass": true,
                                                        "mobileboardingpass": false,
                                                        "precheckvoucher": true
                                                    },
                                                  }
                                              },
                                              {
                                                  "id": "11",
                                                  "departureAirport": {
                                                      "isoCode": "YYY",
                                                      "name": "Aeroparque",
                                                      "city": {
                                                          "code": "YY1",
                                                          "name": "Buenos Aires"
                                                      }
                                                  },
                                                  "arrivalAirport": {
                                                      "isoCode": "ZZZ",
                                                      "name": "Aeropuerto Costa del Sol",
                                                      "city": {
                                                          "code": "ZZ1",
                                                          "name": "Malaga"
                                                      }
                                                  },
                                                  "departureDateTime": "2014-12-11T12:20",
                                                  "arrivalDateTime": "2014-12-11T19:20",
                                                  "passengerUpgInfos": [
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "1",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "2",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "3",
                                                          "upgStatus": "POSTULABLE"
                                                      }
                                                  ],
                                                  passengerCheckinInfo : {
                                                   "status": "NOTCHECKED",
                                                    "documentsAllow": {
                                                        "boardingpasspdf": true,
                                                        "emailboardingpass": true,
                                                        "mobileboardingpass": false,
                                                        "precheckvoucher": true
                                                    },
                                                  }
                                              }
                                          ]
                                      },
                                      {
                                          "id": "1111D_segment_1_2_id",
                                          "flight": {
                                              "flightNumber": "JJ2117",
                                              "operatingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              },
                                              "marketingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              }
                                          },
                                          "legs": [
                                              {
                                                  "id": "21",
                                                  "departureAirport": {
                                                      "isoCode": "ZZZ",
                                                      "name": "Aeropuerto Costa del Sol",
                                                      "city": {
                                                          "code": "ZZ1",
                                                          "name": "Malaga"
                                                      }
                                                  },
                                                  "arrivalAirport": {
                                                      "isoCode": "AAA",
                                                      "name": "Aeropuerto del Prat",
                                                      "city": {
                                                          "code": "AA1",
                                                          "name": "Barcelona"
                                                      }
                                                  },
                                                  "departureDateTime": "2014-12-11T23:40",
                                                  "arrivalDateTime": "2014-12-12T01:30",
                                                  "passengerUpgInfos": [
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "1",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "2",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "3",
                                                          "upgStatus": "POSTULABLE"
                                                      }
                                                  ],
                                                  passengerCheckinInfo : {
                                                   "status": "NOTCHECKED",
                                                    "documentsAllow": {
                                                        "boardingpasspdf": true,
                                                        "emailboardingpass": true,
                                                        "mobileboardingpass": false,
                                                        "precheckvoucher": true
                                                    },
                                                  }
                                              }
                                          ]
                                      }
                                  ]
                              },
                              {
                                  "segments": [
                                      {
                                          "id": "1111D_segment_1_3_id",
                                          "flight": {
                                              "flightNumber": "JJ998",
                                              "operatingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              },
                                              "marketingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              }
                                          },
                                          "legs": [
                                              {
                                                  "id": "13",
                                                  "departureAirport": {
                                                      "isoCode": "AAA",
                                                      "name": "Aeropuerto del Prat",
                                                      "city": {
                                                          "code": "AA1",
                                                          "name": "Barcelona"
                                                      }
                                                  },
                                                  "arrivalAirport": {
                                                      "isoCode": "XXX",
                                                      "name": "Aeropuerto de Carrasco",
                                                      "city": {
                                                          "code": "XX1",
                                                          "name": "Montevideo"
                                                      }
                                                  },
                                                  "departureDateTime": "2014-12-29T11:20",
                                                  "arrivalDateTime": "2014-12-30T09:20",
                                                  "passengerUpgInfos": [
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "1",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "2",
                                                          "upgStatus": "POSTULABLE"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "3",
                                                          "upgStatus": "POSTULABLE"
                                                      }
                                                  ],
                                                  passengerCheckinInfo : {
                                                   "status": "NOTCHECKED",
                                                    "documentsAllow": {
                                                        "boardingpasspdf": true,
                                                        "emailboardingpass": true,
                                                        "mobileboardingpass": false,
                                                        "precheckvoucher": true
                                                    },
                                                  }
                                              }
                                          ],
                                          "messages": [
                                              {
                                                  "code": "ERROR",
                                                  "text": "segment_error_fruit"
                                              }
                                          ]
                                      }
                                  ]
                              }
                          ]
                      }
                  },
                  {
                      "recordLocator": "W222H",
                      "passengers": [
                          {
                              "lastName": "Velasco",
                              "firstName": "Jose",
                              "passengerType": "ADT",
                              "fqtv": {
                                  "fqtvNumber": "45454578",
                                  "category": "Comodoro",
                                  "program": "Fidelidade"
                              },
                              "passangerId": "1"
                          },
                          {
                              "lastName": "Velasco",
                              "firstName": "Antoñito",
                              "passengerType": "INF",
                              "passangerId": "4"
                          }
                      ],
                      "messages": [
                          {
                              "code": "WARNING",
                              "text": "pnr_warning_fruit"
                          }
                      ],
                      "itinerary": {
                          "originDestinations": [
                              {
                                  "segments": [
                                      {
                                          "id": "W222H_segment_1_1",
                                          "flight": {
                                              "flightNumber": "JJ532",
                                              "operatingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              },
                                              "marketingAirline": {
                                                  "code": "JJ",
                                                  "name": "TAM"
                                              }
                                          },
                                          "legs": [
                                              {
                                                  "messages": [
                                                      {
                                                          "code": "INFO",
                                                          "text": "leg_info_fruit"
                                                      }
                                                  ],
                                                  "departureAirport": {
                                                      "isoCode": "XXX",
                                                      "name": "Aeropuerto de Carrasco",
                                                      "city": {
                                                          "code": "XX1",
                                                          "name": "Montevideo"
                                                      }
                                                  },
                                                  "arrivalAirport": {
                                                      "isoCode": "WWW",
                                                      "name": "Aeropuerto de San Jose",
                                                      "city": {
                                                          "code": "WW1",
                                                          "name": "San José"
                                                      }
                                                  },
                                                  "departureDateTime": "2015-08-01T08:32",
                                                  "arrivalDateTime": "2015-08-01T17:45",
                                                  "passengerUpgInfos": [
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "1",
                                                          "upgStatus": "NOT_POSTULABLE_NOT_CABIN"
                                                      },
                                                      {
                                                          "upgPosition": 0,
                                                          "passengerId": "4",
                                                          "upgStatus": "NOT_POSTULABLE_NOT_CABIN"
                                                      }
                                                  ]
                                              }
                                          ]
                                      }
                                  ]
                              }
                          ]
                      }
                  }
                ]
              }
            }


##  FQTVs [/ws/api/common/1.0/rest/add_fqtvs]
###  FQTVs  [POST]

+ Request (application/json)
       
        {
            "application": "checkin",                 
            "portal": "personas",
            "language": "PT",
            "country": "BR",
            "channel" : "WEB",
            "recordLocator" : "EDEE23",
            "fqtvs" : [
                {
                    "name" : "juan",
                    "lastName" : "perez",
                    "paxSegmentID" : "34dfsf32df",
                    "airlineCode" : "JJ",
                    "fqtv" : "32432453253",
                    "nationality": "BR",
                }
            ]
        }

    + Headers

            flowId: a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId: 4264964


    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                "application": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc"
                },
                "portal": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos"
                },
                "language": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Languaje ejemplo : ES = español, PT = portugues"
                },
                "country": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil"
                },
                "recordLocator": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Identificador de la reserva, ejemplo ASDSE2  6 caracteres alfanumericos "
                },
                "fqtvs": {
                  "type": "array",
                  "additionalProperties": false,
                  "description": "Lista de fqtvs a agregar",
                  "items": {
                    "type": "object",
                    "additionalProperties": false,
                    "properties": {
                      "name": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Nombre del pasajero"
                      },
                      "lastName": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Apellido del pasajero"
                      },
                      "paxSegmentID": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                      },
                      "airlineCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Aerolinea del fqtv"
                      },
                      "fqtv": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo de FQTV, ejemplo 324324234"
                      },
                      "nationality": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Nacionalidad del pasajero"
                      }
                    }
                  }
                }
              }
            }



+ Response 200 (application/json)


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200,
                    "message": ""
                },
                "data": {
                    "fqtvs" : [
                        {
                            "paxSegmentID" : "34dfsf32df",
                            "airlineCode" : "JJ",
                            "fqtv" : "32432453253"
                            "status" : "ADDED",
                            "messages" : [
                                {
                                    "text" : "fqtv agregado"
                                }
                            ]
                        },
                        {
                            "paxSegmentID" : "34dfsf32df",
                            "airlineCode" : "JJ",
                            "fqtv" : "32432453253",
                            "status" : "NOTADDED",
                            "messages" : [
                                {
                                    "text" : "fqtv no agregado"
                                }
                            ]
                        }
                    ]

                }
            }

    + Schema

                {
                  "$schema": "http://json-schema.org/draft-04/schema#",
                  "id": "http://jsonschema.net#",
                  "type": "object",
                  "additionalProperties": false,
                  "properties": {
                    "status": {
                      "type": "object",
                      "additionalProperties": false,
                      "properties": {
                        "code": {
                          "type": "integer",
                          "additionalProperties": false
                        },
                        "message": {
                          "type": "string",
                          "additionalProperties": false
                        }
                      }
                    },
                    "data": {
                      "type": "object",
                      "additionalProperties": false,
                      "properties": {
                        "fqtvs": {
                          "type": "array",
                          "additionalProperties": false,
                          "description" : "Lista con los resultados del ingreso de la lista de fqtvs",
                          "items": {
                            "type": "object",
                            "additionalProperties": false,
                            "properties": {
                              "paxSegmentID": {
                                "type": "string",
                                "additionalProperties": false,
                                "description" : "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                              },
                              "airlineCode": {
                                "type": "string",
                                "additionalProperties": false,
                                "description" : "Aerolinea del fqtv"
                              },
                              "fqtv": {
                                "type": "string",
                                "additionalProperties": false,
                                "description" : "Codigo de FQTV, ejemplo 324324234"
                              },
                              "status": {
                                "type": "string",
                                "additionalProperties": false,
                                "description" : "Estatus del ingreso del FQTV, opciones = NOTADDED, ADDED"
                              },
                              "messages": {
                                "type": "array",
                                "additionalProperties": false,
                                "description" : "Lista de mensajes asociados al estatus del ingreso del fqtv",
                                "items": {
                                  "type": "object",
                                  "additionalProperties": false,
                                  "properties": {
                                    "text": {
                                      "type": "string",
                                      "additionalProperties": false,
                                      "description" : "Texto del mensaje"
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }







# Group Passenger
## Request Upg [/ws/api/airport/1/upgrade/flight/request_upgrade]
## upg [POST]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "segments": [
                    {
                        "id": "1111D_segment_1_1_id",
                        "flight": {
                            "flightNumber": "JJ432",
                            "operatingAirline": {
                                "code": "JJ",
                                "name": "TAM"
                            },
                            "marketingAirline": {
                                "code": "JJ",
                                "name": "TAM"
                            }
                        },
                        "legs": [
                            {
                                "id": "11",
                                "departureAirport": {
                                    "isoCode": "XXX",
                                    "name": "Aeropuerto de Carrasco",
                                    "city": {
                                        "code": "XX1",
                                        "name": "Montevideo"
                                    }
                                },
                                "arrivalAirport": {
                                    "isoCode": "YYY",
                                    "name": "Aeroparque",
                                    "city": {
                                        "code": "YY1",
                                        "name": "Buenos Aires"
                                    }
                                },
                                "departureDateTime": "2014-12-11T10:20",
                                "arrivalDateTime": "2014-12-11T11:20",
                                "passengers" : [
                                  {
                                    lastName: "LUEIZA",
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "fqtv": {
                                        "fqtvNumber": "111548",
                                        "category": "Premium",
                                        "program": "Fidelidade"
                                    }
                                  }
                                ]
                            },
                            {
                                "id": "11",
                                "departureAirport": {
                                    "isoCode": "YYY",
                                    "name": "Aeroparque",
                                    "city": {
                                        "code": "YY1",
                                        "name": "Buenos Aires"
                                    }
                                },
                                "arrivalAirport": {
                                    "isoCode": "ZZZ",
                                    "name": "Aeropuerto Costa del Sol",
                                    "city": {
                                        "code": "ZZ1",
                                        "name": "Malaga"
                                    }
                                },
                                "departureDateTime": "2014-12-11T12:20",
                                "arrivalDateTime": "2014-12-11T19:20",
                                "passengers" : [
                                  {
                                    lastName: "LUEIZA",
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "fqtv": {
                                        "fqtvNumber": "111548",
                                        "category": "Premium",
                                        "program": "Fidelidade"
                                    }
                                  }
                                ]
                            }
                        ]
                    },
                    {
                        "id": "1111D_segment_1_2_id",
                        "flight": {
                            "flightNumber": "JJ2117",
                            "operatingAirline": {
                                "code": "JJ",
                                "name": "TAM"
                            },
                            "marketingAirline": {
                                "code": "JJ",
                                "name": "TAM"
                            }
                        },
                        "legs": [
                            {
                                "id": "21",
                                "departureAirport": {
                                    "isoCode": "ZZZ",
                                    "name": "Aeropuerto Costa del Sol",
                                    "city": {
                                        "code": "ZZ1",
                                        "name": "Malaga"
                                    }
                                },
                                "arrivalAirport": {
                                    "isoCode": "AAA",
                                    "name": "Aeropuerto del Prat",
                                    "city": {
                                        "code": "AA1",
                                        "name": "Barcelona"
                                    }
                                },
                                "departureDateTime": "2014-12-11T23:40",
                                "arrivalDateTime": "2014-12-12T01:30",
                                "passengers" : [
                                  {
                                    lastName: "LUEIZA",
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "fqtv": {
                                        "fqtvNumber": "111548",
                                        "category": "Premium",
                                        "program": "Fidelidade"
                                    }
                                  }
                                ]
                            }
                        ]
                    }
                ]  
            }
            
+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {
                 "segments": [
                    {
                        "id": "1111D_segment_1_1_id",                        
                        },
                        "legs": [
                            {
                                "id": "11",                                
                                "passengers" : [
                                  {
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "position" : 12
                                  }
                                ]
                            },
                            {
                                "id": "11",                               
                                "passengers" : [
                                  {
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "position" : 12
                                  }
                                ]
                            }
                        ]
                    },
                    {
                        "id": "1111D_segment_1_2_id"
                        },
                        "legs": [
                            {
                                "id": "21",
                                "passengers" : [
                                  {                                  
                                    "passengerSegmentId" : 1sdfsdfsd324,
                                    "messages": [
                                                  {
                                                    "code": "ERROR",
                                                    "text": "no_se_pudo"
                                                  }
                                              ]
                                  }
                                ]
                            }
                        ]
                    }
                ]  
              }
            }

## API Information [/ws/api/airport/1.0/checkin/api/information]
### GET API information [GET]

Obtiene la configuracion de datos necesarios que el usuario necesita para viajar en una ruta determinada.
Lo que se muestra al pasajero es la mas restrictiva de todas las [API](http://en.wikipedia.org/wiki/Advance_Passenger_Information_System) que puede tener

**Parametros de entrada**
         
- **portal** \[_requerido_, _string_\]:  
    _Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos_ 

- **application**\[_requerido_, _string_\]:  
    _Aplicacion de LAN.com, ejemplo checkin, compra_normal_

- **country**\[_requerido_, _string_\]:  
    _Pais del portal de LAN.com que se esta usando, ejemplo CL = Chile_

- **language**\[_requerido_, _string_\]:  
    _Lenguaje del pais del portal LAN.com que se esta usando, ejemplo ES = Español_

- **channel**\[_requerido_, _string_\]:  
   _Canal donde se esta realizando el checkin opciones: WEB, MOBILE_

- **legs**\[_requerido_, array\]:  
     _Estructura de tramos por los que viaja el pasajero_

 - **departureAirportCode**\[_requerido_, _string_\] :  
     _Codigo de aeropuerto de despegue del vuelo, ejemplo SCL_

 - **arrivalAirportCode**\[_requerido_, _string_\] :  
     _Codigo de aeropuerto de arribo del vuelo, ejemplo BUE_

 - **operatingAirlineCode**\[_requerido_, _string_\] :   
     _Codigo aerolinea que opera el vuelo, ejemplo JJ_

 - **passengers**\[_requerido_, _array_\] :  
     _Lista de pasajeros a los cuales se les desea obtener la API_

   - **paxSegmentID**\[_requerido_, _string_\]:  
     _Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2_ 

**PayLoads de Ejemplo**  

  _Busqueda por PNR + LastName_
```
       {
            "portal": "personas",
            "application": "checkin",
            "language": "PT",
            "country": "BR",
            "channel" : "WEB",
            "legs": [
                {
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH",
                    "operatingAirlineCode" : "JJ",
                    "passengers": [
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                           "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        }
                    ]
                }
            ]
        }      
``` 




+ Request (application/json)
       
        {
            "recordLocator": "6VKQD5",
            "portal": "personas",
            "application": "checkin",
            "language": "PT",
            "country": "BR",
            "channel" : "WEB",
            "legs": [
                {
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH",
                    "operatingAirlineCode" : "JJ",
                    "passengers": [
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                           "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        }
                    ]
                },
                {
                    "departureAirportCode": "CGH",
                    "arrivalAirportCode": "SDU",
                    "operatingAirlineCode" : "JJ",
                    "passengers": [
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                           "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        }
                    ]
                },
                {
                    "departureAirportCode": "GIG",
                    "arrivalAirportCode": "POA",
                    "operatingAirlineCode" : "JJ",
                    "passengers": [
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                           "paxSegmentID" : "sfd3fsdf324fsda"
                        },
                        {
                            "paxSegmentID" : "sfd3fsdf324fsda"
                        }
                    ]
                }
            ]
        }      
        
    + Headers

            flowId: a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId: 4264964

    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                "recordLocator": {
                  "type": "string",
                  "required" : false,
                  "additionalProperties": false,
                  "description" : "Identificador de la reserva, ejemplo ASDSE2  6 caracteres alfanumericos "
                },
                "portal": {
                  "type": "string",
                  "required" : true
                  "additionalProperties": false,
                  "description" : "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos"
                },
                "application": {
                  "type": "string",
                  "required" : true,
                  "additionalProperties": false,
                  "description" : "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc"
                },
                "language": {
                  "type": "string",
                  "required" : true,
                  "additionalProperties": false,
                  "description" : "Languaje ejemplo : ES = español, PT = portugues"
                },
                "country": {
                  "type": "string",
                  "required" : true,
                  "additionalProperties": false,
                  "description" : "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil"
                },
                "legs": {
                  "type": "array",
                  "description" : "Tramos del viaje",
                  "additionalProperties": false,
                  "items": {
                    "type": "object",
                    "additionalProperties": false,
                    "properties": {
                      "departureAirportCode": {
                        "type": "string",
                        "description" : "Codigo de aeropuerto de despegue del vuelo, ejemplo SCL",
                        "additionalProperties": false
                      },
                      "arrivalAirportCode": {
                        "type": "string",
                        "description" : "Codigo de aeropuerto de arribo del vuelo, ejemplo BUE",
                        "additionalProperties": false
                      },
                      "operatingAirlineCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo aerolinea que opera el vuelo, ejemplo JJ"
                      },
                      "passengers": {
                        "type": "array",
                        "additionalProperties": false,
                        "items": {
                          "type": "object",
                          "additionalProperties": false,
                          "properties": {
                            "paxSegmentID": {
                              "type": "string",
                              "additionalProperties": false,
                              "description" : "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }


+ Response 200 (application/json)

    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200,
                    "message": ""
                },
                "data": {
                    "passengers": [
                        {
                            "paxSegmentID": "23161548000063A1",
                            "name": "MARIA",
                            "lastName": "PAULA SOARES SAMPLES",
                            "ticketNumber": "9572483127883",
                            "blockElements": [
                                {
                                    "name": "EMERGENCY_CONTACT_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "emergencyContactName"
                                        },
                                        {
                                            "elementId": "areaPhoneCode"
                                        },
                                        {
                                            "elementId": "countryPhoneCode"
                                        },
                                        {
                                            "elementId": "phoneNumber"
                                        },
                                        {
                                            "elementId": "countryPhone"
                                        },
                                        {
                                            "elementId": "phoneType"
                                        }
                                    ]
                                },
                                {
                                    "name": "FREQUENT_FLYER_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "frequentFlyerProgram"
                                        },
                                        {
                                            "elementId": "frequentFlyerNumber"
                                        }
                                    ]
                                },
                                {
                                    "name": "PERSONAL_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "dateOfBirth"
                                        },
                                        {
                                            "elementId": "nationality",
                                            "defaultValue": "BR"
                                        },
                                        {
                                            "elementId": "foidNumber"
                                        },
                                        {
                                            "elementId": "foidType"
                                        },
                                        {
                                            "elementId": "genre"
                                        },
                                        {
                                            "elementId": "passportIssueCountry"
                                        }
                                    ]
                                },
                                {
                                    "name": "PASSPORT_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "passportExpirationDate"
                                        }
                                    ]
                                }
                            ]
                        },
                        {
                            "paxSegmentID": "3362054900001A3B",
                            "name": "HOMERO",
                            "lastName": "SIMPSON",
                            "ticketNumber": "9572483127884",
                            "blockElements": [
                                {
                                    "name": "EMERGENCY_CONTACT_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "emergencyContactName"
                                        },
                                        {
                                            "elementId": "areaPhoneCode"
                                        },
                                        {
                                            "elementId": "countryPhoneCode"
                                        },
                                        {
                                            "elementId": "phoneNumber"
                                        },
                                        {
                                            "elementId": "countryPhone"
                                        },
                                        {
                                            "elementId": "phoneType"
                                        }
                                    ]
                                },
                                {
                                    "name": "FREQUENT_FLYER_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "frequentFlyerProgram"
                                        },
                                        {
                                            "elementId": "frequentFlyerNumber"
                                        }
                                    ]
                                },
                                {
                                    "name": "PERSONAL_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "dateOfBirth"
                                        },
                                        {
                                            "elementId": "nationality",
                                            "defaultValue": "BR"
                                        },
                                        {
                                            "elementId": "foidNumber"
                                        },
                                        {
                                            "elementId": "foidType"
                                        },
                                        {
                                            "elementId": "genre"
                                        },
                                        {
                                            "elementId": "passportIssueCountry"
                                        }
                                    ]
                                },
                                {
                                    "name": "PASSPORT_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "passportExpirationDate"
                                        }
                                    ]
                                }
                            ]
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "LISA",
                            "lastName": "SIMPSON",
                            "ticketNumber": "9572483127885",
                            "blockElements": [
                                {
                                    "name": "EMERGENCY_CONTACT_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "emergencyContactName"
                                        },
                                        {
                                            "elementId": "areaPhoneCode"
                                        },
                                        {
                                            "elementId": "countryPhoneCode"
                                        },
                                        {
                                            "elementId": "phoneNumber"
                                        },
                                        {
                                            "elementId": "countryPhone"
                                        },
                                        {
                                            "elementId": "phoneType"
                                        }
                                    ]
                                },
                                {
                                    "name": "FREQUENT_FLYER_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "frequentFlyerProgram"
                                        },
                                        {
                                            "elementId": "frequentFlyerNumber"
                                        }
                                    ]
                                },
                                {
                                    "name": "PERSONAL_INFO_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "dateOfBirth",
                                            "defaultValue": "2011-04-05"
                                        },
                                        {
                                            "elementId": "nationality",
                                            "defaultValue": "BR"
                                        },
                                        {
                                            "elementId": "foidNumber"
                                        },
                                        {
                                            "elementId": "foidType"
                                        },
                                        {
                                            "elementId": "gender"
                                        },
                                        {
                                            "elementId": "passportIssueCountry"
                                        }
                                    ]
                                },
                                {
                                    "name": "PASSPORT_BLOCK",
                                    "fieldElements": [
                                        {
                                            "elementId": "passportExpirationDate"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }                    
            }


    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "required": false,
              "title": "root",
              "description": "",
              "name": "",
              "properties": {
                "status": {
                  "type": "object",
                  "required": false,
                  "title": "",
                  "description": "",
                  "name": "",
                  "properties": {
                    "code": {
                      "type": "integer",
                      "required": false,
                      "title": "",
                      "description": "",
                      "name": "",
                      "minimum": 0
                    },
                    "message": {
                      "type": "string",
                      "required": false,
                      "title": "",
                      "description": "",
                      "name": "",
                      "minLength": 0
                    }
                  }
                },
                "data": {
                  "id": "http://jsonschema.net/data#",
                  "type": "object",
                  "required": false,
                  "title": "",
                  "description": "",
                  "name": "",
                  "properties": {
                    "passengers": {
                      "type": "array",
                      "required": false,
                      "title": "",
                      "description": "Lista de pasajeros con los campos necesarios para checkear",
                      "name": "",
                      "minItems": 0,
                      "uniqueItems": false,
                      "items": {
                        "type": "object",
                        "required": false,
                        "title": "",
                        "description": "",
                        "name": "",
                        "properties": {
                          "paxSegmentID": {
                            "type": "string",
                            "required": true,
                            "title": "",
                            "description": "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2",
                            "name": "",
                            "minLength": 0
                          },
                          "name": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "Nombre del pasajero",
                            "name": "",
                            "minLength": 0
                          },
                          "lastName": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "Apellido del pasajero, alfanumerico",
                            "name": "",
                            "minLength": 0
                          },
                          "ticketNumber": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "Numero de ticket ejemplo 0452322323456, 13 numeros",
                            "name": "",
                            "minLength": 0
                          },
                          "blockElements": {
                            "type": "array",
                            "required": false,
                            "title": "",
                            "description": "Lista de campos necesarios por pasajero para realizar su checkin",
                            "name": "",
                            "minItems": 0,
                            "uniqueItems": false,
                            "items": {
                              "type": "object",
                              "required": false,
                              "title": "",
                              "description": "",
                              "name": "",
                              "properties": {
                                "name": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "Nombre del bloque, opciones = EMERGENCY_CONTACT_INFO_BLOCK, FREQUENT_FLYER_BLOCK, INFO_US_BLOCK, PERSONAL_INFO_BLOCK, PASSPORT_BLOCK, RECIEVE_OFFERS_BLOCK, INFO_ES_BLOCK",
                                  "name": "",
                                  "minLength": 0
                                },
                                "fieldElements": {
                                  "type": "array",
                                  "required": false,
                                  "title": "",
                                  "description": "Lista de elementos html que componen el bloque",
                                  "name": "",
                                  "minItems": 0,
                                  "uniqueItems": false,
                                  "items": {
                                    "type": "object",
                                    "required": false,
                                    "title": "",
                                    "description": "",
                                    "name": "",
                                    "properties": {
                                      "elementId": {
                                        "type": "string",
                                        "required": false,
                                        "title": "",
                                        "description": "Identificador del bloque, ejemplo passportExpirationDate",
                                        "name": "",
                                        "minLength": 0
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 510 (application/json)

        { "title": "Reserva inhibida para checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }

+ Response 522 (application/json)

        { "title": "No se puede obtener la configuracion de la api para este origen destino"}


## Update API Information [/ws/api/checkin/1.0/checkin/api/information]
### Update API information [POST]

+ Request (application/json)
       
        {
            "language": "PT",
            "country": "BR",
            "portal": "personas",
            "recordLocator": "6VKQD5",
            "surName": "SIMPSON",
            "application": "checkin",
            "channel" : "WEB",
            "legs": [
                {
                    "id" : 1,
                    "flightNumber": 3339,
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH",
                    "departureDateTime": "07-05-2014T16:07",
                    "arrivalDateTime": "07-05-2014T17:38",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3215487",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127883"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "321"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "654987"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "frequentFlyerProgram",
                                    "value": "JJ"
                                },
                                {
                                    "elementId": "frequentFlyerNumber",
                                    "value": "1681462637"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "1985-10-10"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3215487"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3216549875",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127885"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "654"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "987526"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "2011-04-05"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3216549875"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        }
                    ]
                },
                {
                    "id" : 2,
                    "flightNumber": 3952,
                    "departureAirportCode": "CGH",
                    "arrivalAirportCode": "SDU",
                    "departureDateTime": "07-05-2014T19:00",
                    "arrivalDateTime": "07-05-2014T20:06",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3215487",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127883"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "321"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "654987"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "frequentFlyerProgram",
                                    "value": "JJ"
                                },
                                {
                                    "elementId": "frequentFlyerNumber",
                                    "value": "1681462637"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "1985-10-10"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3215487"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3216549875",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127885"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "654"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "987526"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "2011-04-05"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3216549875"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        }
                    ]
                },
                {
                    "id" : 3,
                    "flightNumber": 3411,
                    "departureAirportCode": "GIG",
                    "arrivalAirportCode": "POA",
                    "departureDateTime": "08-05-2014T08:14",
                    "arrivalDateTime": "08-05-2014T10:17",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3215487",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127883"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "321"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "654987"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "frequentFlyerProgram",
                                    "value": "JJ"
                                },
                                {
                                    "elementId": "frequentFlyerNumber",
                                    "value": "1681462637"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "1985-10-10"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3215487"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3216549875",
                                "type": "PP",
                                "countryCode": "BR"
                            },
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885",
                            "apiInformation": [
                                {
                                    "elementId": "ticketNumber",
                                    "value": "9572483127885"
                                },
                                {
                                    "elementId": "emergencyContactName",
                                    "value": "fulano"
                                },
                                {
                                    "elementId": "areaPhoneCode",
                                    "value": "654"
                                },
                                {
                                    "elementId": "countryPhoneCode",
                                    "value": "55"
                                },
                                {
                                    "elementId": "phoneNumber",
                                    "value": "987526"
                                },
                                {
                                    "elementId": "countryPhone",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "phoneType",
                                    "value": "1"
                                },
                                {
                                    "elementId": "dateOfBirth",
                                    "value": "2011-04-05"
                                },
                                {
                                    "elementId": "nationality",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "foidNumber",
                                    "value": "3216549875"
                                },
                                {
                                    "elementId": "foidType",
                                    "value": "PP"
                                },
                                {
                                    "elementId": "genre",
                                    "value": "F"
                                },
                                {
                                    "elementId": "passportIssueCountry",
                                    "value": "BR"
                                },
                                {
                                    "elementId": "passportExpirationDate",
                                    "value": "2018-10-10"
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    
    + Headers

            flowId: a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId: 4264964

    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                "language": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Languaje ejemplo : ES = español, PT = portugues"
                },
                "country": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil"
                },
                "portal": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos"
                },
                "recordLocator": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Identificador de la reserva, ejemplo ASDSE2  6 caracteres alfanumericos "
                },
                "lastName": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Apellido del pasajero, alfanumerico"
                },
                "application": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc"
                },
                "legs": {
                  "type": "array",
                  "additionalProperties": false,
                  "description" : "Tramos de la reserva",
                  "items": {
                    "type": "object",
                    "additionalProperties": false,
                    "properties": {
                      "id": {
                        "type": "number",
                        "additionalProperties": false,
                        "description" : "Identificador del leg en la reserva"
                      },
                      "flightNumber": {
                        "type": "integer",
                        "additionalProperties": false,
                        "description": "Numero de vuelo, ejemplo 2343"
                      },
                      "departureAirportCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Codigo de aeropuerto de despegue, ejemplo SCL"
                      },
                      "arrivalAirportCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo de aeropuerto de arribo, ejemplo BUE"
                      },
                      "departureDateTime": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Fecha y hora estimada del despegue del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                      },
                      "arrivalDateTime": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Fecha y hora estimada del arribo del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                      },
                      "operatingAirlineCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo de aerolinea operadora del vuelo, ejemplo LA"
                      },
                      "passengers": {
                        "type": "array",
                        "additionalProperties": false,
                        "items": {
                          "type": "object",
                          "additionalProperties": false,
                          "properties": {
                            "paxSegmentID": {
                              "type": "string",
                              "additionalProperties": false,
                              "description" : "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                            },
                            "foid": {
                              "type": "object",
                              "additionalProperties": false,
                              "properties": {
                                "number": {
                                  "type": "string",
                                  "additionalProperties": false,
                                  "description" : "Numero de documento de viaje, ejemplo 324234432"
                                },
                                "type": {
                                  "type": "string",
                                  "additionalProperties": false,
                                  "description" : "Tipo de documento de viaje, ejemplo PP = pasaporte"
                                },
                                "countryCode": {
                                  "type": "string",
                                  "additionalProperties": false,
                                  "description" : "Codigo de pais de emision del documento de viaje, ejemplo CL"
                                }
                              }
                            },
                            "name": {
                              "type": "string",
                              "additionalProperties": false,
                              "description" :  "Nombre del pasajero, ejemplo JUAN"
                            },
                            "lastName": {
                              "type": "string",
                              "additionalProperties": false,
                              "description" : "Apellido del pasajero, ejemplo LAMA"
                            },
                            "ticketNumber": {
                              "type": "string",
                              "additionalProperties": false,
                              "description" : "Numero de ticket ejemplo 0452322323456, 13 numeros"
                            },
                            "apiInformation": {
                              "type": "array",
                              "additionalProperties": false,
                              "items": {
                                "type": "object",
                                "additionalProperties": false,
                                "properties": {
                                  "elementId": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Identificador del bloque, ejemplo passportExpirationDate",
                                  },
                                  "value": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description" : "Valor del campo, ejemplo dadda@ffsfs.com"
                                  }
                                }
                              }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }


        
+ Response 200 (application/json)

    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200,
                    "message": ""
                },
                "data": {
                    "legs": [
                        {
                            "id" : 1,
                            "flightNumber": 3339,
                            "departureAirportCode": "IGU",
                            "arrivalAirportCdde": "CGH",
                            "operatingAirlineCode": "JJ",
                            "passengers": [
                                {
                                    "paxSegmentID": "3362054900001A3C",
                                    "status" : "UPDATED",
                                    "messages" : []
                                },
                                {
                                    "paxSegmentID": "3362054900001A3C",
                                    "status" : "NOTUPDATED",
                                    "messages" : [
                                        {
                                            "text" : "No se pudo actualizar la informacion por algo"
                                        }
                                    ]
                                },
                                {
                                    "paxSegmentID": "3362054900001A3C",
                                    "status" : "UPDATED",
                                    "messages" : []
                                }
                            ]    
                       }
                    ]
                }
            }         


    + Schema

            {
                "type":"object",
                "$schema": "http://json-schema.org/draft-03/schema",
                "id": "http://jsonschema.net",
                "required":false,
                "properties":{
                    "data": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "legs": {
                                "type":"array",
                                "required":false,
                                "items":
                                    {
                                        "type":"object",
                                        "required":false,
                                        "properties":{
                                            "arrivalAirportCode": {
                                                "type":"string",
                                                "required":false,
                                                "description" : "Codigo de aeropuerto de arribo, ejemplo BUE"
                                            },
                                            "departureAirportCode": {
                                                "type":"string",
                                                "required":false,
                                                "description" : "Codigo de aeropuerto de despegue, ejemplo SCL"
                                            },
                                            "flightNumber": {
                                                "type":"number",
                                                "required":false,
                                                "description" : "Numero de vuelo, ejemplo 2343"
                                            },
                                            "id": {
                                                "type":"number",
                                                "required":false,
                                                "description" : "Identificador del vuelo en la reserva, por ejemplo 1"
                                            },
                                            "operatingAirlineCode": {
                                                "type":"string",
                                                "required":false,
                                                "description" : "Codigo de aerolinea operadora del vuelo, ejemplo LA"
                                            },
                                            "passengers": {
                                                "type":"array",
                                                "required":false,
                                                "description" : "Lista de pasajeros a los cuales se les agregaron los datos para checkin en ese vuelo",
                                                "items":
                                                    {
                                                        "type":"object",
                                                        "required":false,
                                                        "properties":{
                                                            "messages": {
                                                                "type":"array",
                                                                "required":false,
                                                                "description" : "Lista de mensajes acerca del resultado de ingreso de los datos para checkin"
                                                            },
                                                            "paxSegmentID": {
                                                                "type":"string",
                                                                "required":false,
                                                                "description" : "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                                                            },
                                                            "status": {
                                                                "type":"string",
                                                                "required":false,
                                                                "description" : "Resultado de ingreso de los datos para checkin, opciones = NOTUPDATED, UPDATED"
                                                            }
                                                        }
                                                    }
                                            }
                                        }
                                    }
                            }
                        }
                    },
                    "status": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "code": {
                                "type":"number",
                                "required":false,
                                "description" : "Codigo del resultado, ejemplo 200"
                            },
                            "message": {
                                "type":"string",
                                "required":false,
                                "description" : "Mensaje descriptivo del codigo de resultado"
                            }
                        }
                    }
                }
            }




+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }



## Identification Documents [/ws/api/common/1.0/rest/display_identification_document]
### Get Identification document [GET]

+ Request (application/json)
       
        {
            "application": "checkin",
            "nationality": "BR",
            "segments": [
                {
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH"
                },
                {
                    "departureAirportCode": "CGH",
                    "arrivalAirportCode": "SDU"
                },
                {
                    "departureAirportCode": "GIG",
                    "arrivalAirportCode": "POA"
                }
            ],
            "portal": "personas",
            "language": "PT",
            "country": "BR",
            "channel" : "WEB"
        }


    + Headers

            flowId: a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId: 4264964


    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "additionalProperties": false,
              "properties": {
                "application": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc"
                },
                "nationality": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Nacionalidad del pasajero"
                },
                "segments": {
                  "type": "array",
                  "additionalProperties": false,
                  "items": {
                    "type": "object",
                    "additionalProperties": false,
                    "properties": {
                      "departureAirportCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo de aeropuerto de despegue, ejemplo SCL"
                      },
                      "arrivalAirportCode": {
                        "type": "string",
                        "additionalProperties": false,
                        "description" : "Codigo de aeropuerto de arribo, ejemplo BUE"
                      }
                    }
                  }
                },
                "portal": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos"
                },
                "language": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Languaje ejemplo : ES = español, PT = portugues"
                },
                "country": {
                  "type": "string",
                  "additionalProperties": false,
                  "description" : "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil"
                }
              }
            }      



+ Response 200 (application/json)


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200,
                    "message": ""
                },
                "data": {
                    "nationality": "BR",
                    "documents": [
                        {
                            "code": "AA",
                            "name": "CHT de Comiss&aacute;rio"
                        },
                        {
                            "code": "BC",
                            "name": "Certid&atilde;o de Nascimento"
                        },
                        {
                            "code": "DL",
                            "name": "Carteira de Motorista"
                        },
                        {
                            "code": "FM",
                            "name": "CHT de Mecânico de Voo"
                        },
                        {
                            "code": "CI",
                            "name": "Numero do documento de identidade"
                        },
                        {
                            "code": "LA",
                            "name": "Identidade Profissional"
                        },
                        {
                            "code": "MI",
                            "name": "Identidade Militar"
                        },
                        {
                            "code": "OD",
                            "name": "CHT de Despachante Operacional de Voo"
                        },
                        {
                            "code": "PP",
                            "name": "Passaporte"
                        },
                        {
                            "code": "PL",
                            "name": "CHT de Piloto"
                        },
                        {
                            "code": "WL",
                            "name": "Carteira de Trabalho"
                        }
                    ]
                }
            }

    + Schema

            {
                "type":"object",
                "$schema": "http://json-schema.org/draft-03/schema",
                "id": "http://jsonschema.net",
                "required":false,
                "properties":{
                    "data": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "documents": {
                                "type":"array",
                                "required":false,
                                "description" : "Lista de documentos",
                                "items":
                                    {
                                        "type":"object",
                                        "required":false,
                                        "properties":{
                                            "code": {
                                                "type":"string",
                                                "required":false,
                                                "description" : "Codigo del documento, por ejemplo PP"
                                            },
                                            "name": {
                                                "type":"string",
                                                "required":false,
                                                "description" : "Nombre del documento, por ejemplo Pasaporte"
                                            }
                                        }
                                    }
                                

                            },
                            "nationality": {
                                "type":"string",
                                "required":false,
                                "description" : "Nacionalidad del pasajero"
                            }
                        }
                    },
                    "status": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "code": {
                                "type":"number",
                                "required":false
                            },
                            "message": {
                                "type":"string",
                                "required":false
                            }
                        }
                    }
                }
            }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }


## Perform Checkin [/ws/api/airport/1.0/checkin/passengers/checkin]
### Check Passengers [POST]

+ Request (application/json)

        {
            "language": "PT",
            "country": "BR",
            "portal": "personas",
            "recordLocator": "6VKQD5",
            "surName": "SIMPSON",
            "application": "checkin",
            "channel" : "WEB",
            "segments": [
                {
                    "id" : "01",
                    "flightNumber": 3339,
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH",
                    "departureDateTime": "07-05-2014 16:07",
                    "arrivalDateTime": "07-05-2014 17:38",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883"                         
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885"                           
                        }
                    ]
                },
                {
                    "id" : "02",
                    "flightNumber": 3952,
                    "departureAirport": "CGH",
                    "arrivalAirport": "SDU",
                    "departureDateTime": "07-05-2014 19:00",
                    "arrivalDateTime": "07-05-2014 20:06",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "foid": {
                                "number": "3215487",
                                "type": "PP",
                                "country": "BR"
                            },
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883"                            
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885"                        
                        }
                    ]
                },
                {
                    "id" : "03",
                    "flightNumber": 3411,
                    "departureAirport": "GIG",
                    "arrivalAirport": "POA",
                    "departureDateTime": "08-05-2014 08:14",
                    "arrivalDateTime": "08-05-2014 10:17",
                    "operatingAirlineCode": "JJ",
                    "passengers": [
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "ticketNumber": "9572483127883"
                        },
                        {
                            "paxSegmentID": "3362054900001A3C",
                            "name": "lisa",
                            "lastName": "simpson",
                            "ticketNumber": "9572483127885"
                        }
                    ]
                }
            ]
        }

        + Schema

            {
                "$schema": "http://json-schema.org/draft-04/schema#",
                "id": "http://jsonschema.net#",
                "type": "object",
                "title": "root",
                "description": "",
                "name": "",
                "additionalProperties": false,
                "properties": {
                "language": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "country": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "portal": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "recordLocator": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "surName": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "application": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "segments": {
                  "type": "array",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minItems": 0,
                  "uniqueItems": false,
                  "additionalProperties": false,
                  "items": {
                    "type": "object",
                    "title": "",
                    "description": "",
                    "name": "",
                    "additionalProperties": false,
                    "properties": {
                      "id": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "flightNumber": {
                        "type": "integer",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minimum": 0,
                        "additionalProperties": false
                      },
                      "departureAirport": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "arrivalAirport": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "departureDateTime": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "arrivalDateTime": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "operatingAirlineCode": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "passengers": {
                        "type": "array",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minItems": 0,
                        "uniqueItems": false,
                        "additionalProperties": false,
                        "items": {
                          "type": "object",
                          "title": "",
                          "description": "",
                          "name": "",
                          "additionalProperties": false,
                          "properties": {
                            "paxSegmentID": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "name": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "default": "lisa",
                              "additionalProperties": false
                            },
                            "lastName": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "ticketNumber": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            }
                          }
                        }
                      }
                    }
                  }
                }
            }
            
    
        
+ Response 200 (application/json)


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200
                },
                "data": {
                    "segments": [
                        {
                            "departureAirport": {
                                "code": "IGU",
                                "name": "CATARATAS"
                            },
                            "departureCity": {
                                "code": "IGU",
                                "name": "Foz do Igua&ccedil;u"
                            },
                            "arrivalAirport": {
                                "code": "CGH",
                                "name": "SAO PAULO - CONGONHAS"
                            },
                            "arrivalCity": {
                                "code": "SAO",
                                "name": "S&atilde;o Paulo"
                            },
                            "estimatedDepartureDateTime": "2014-05-07T16:07",
                            "estimatedArrivalDateTime": "2014-05-07T17:38",
                            "flight": {
                                "number": "3339",
                                "operatingAirlineCode": "JJ",
                                "marketingAirlineCode": "JJ"
                            },
                            "passengers": [
                                {
                                    "name": "maria",
                                    "lastName": "paula soares samples",
                                    "status": "CHECKED",
                                    "seat": "4A",
                                    "ticketNumber": "9572483127883",
                                    "paxSegmentID": "2317154800006590",
                                    "id": "23161548000063A1",
                                    "messages" : [
                                        {
                                            "text" : "chequeado con exito"
                                        }
                                    ]
                                },
                                {
                                    "name": "lisa",
                                    "lastName": "simpson",
                                    "status": "NOCHEQUED",
                                    "seat": "5A",
                                    "ticketNumber": "9572483127885",
                                    "paxSegmentID": "231715480000658F",
                                    "messages" : [
                                        {
                                            "text" : "no chequeado con exito"
                                        }
                                    ]
                                }
                            ],
                            "id": "01"
                        },
                        {
                            "departureAirport": {
                                "code": "CGH",
                                "name": "SAO PAULO - CONGONHAS"
                            },
                            "departureCity": {
                                "code": "SAO",
                                "name": "S&atilde;o Paulo"
                            },
                            "arrivalAirport": {
                                "code": "SDU",
                                "name": "SANTOS DUMONT"
                            },
                            "arrivalCity": {
                                "code": "RIO",
                                "name": "Rio de Janeiro"
                            },
                            "estimatedDepartureDateTime": "2014-05-07T19:00",
                            "estimatedArrivalDateTime": "2014-05-07T20:06",
                            "flight": {
                                "number": "3952",
                                "operatingAirlineCode": "JJ",
                                "marketingAirlineCode": "JJ"
                            },
                            "passengers": [
                                {
                                    "name": "maria",
                                    "lastName": "paula soares samples",
                                    "status": "CHECKED",
                                    "seat": "5A",
                                    "ticketNumber": "9572483127883",
                                    "paxSegmentID": "2317154800006593",
                                    "messages" : [
                                        {
                                            "text" : "chequeado con exito"
                                        }
                                    ]
                                },
                                {
                                    "name": "lisa",
                                    "lastName": "simpson",
                                    "status": "CHECKED",
                                    "seat": "6A",
                                    "ticketNumber": "9572483127885",
                                    "paxSegmentID": "2317154800006592",
                                    "messages" : [
                                        {
                                            "text" : "chequeado con exito"
                                        }
                                    ]
                                }
                            ],
                            "id": "02"
                        },
                        {
                            "departureAirport": {
                                "code": "GIG",
                                "name": "GALE&Atilde;O INTL"
                            },
                            "departureCity": {
                                "code": "RIO",
                                "name": "Rio de Janeiro"
                            },
                            "arrivalAirport": {
                                "code": "POA",
                                "name": "SALGADO FIL"
                            },
                            "arrivalCity": {
                                "code": "POA",
                                "name": "Porto Alegre"
                            },
                            "estimatedDepartureDateTime": "2014-05-08T08:14",
                            "estimatedArrivalDateTime": "2014-05-08T10:17",
                            "flight": {
                                "number": "3411",
                                "operatingAirlineCode": "JJ",
                                "marketingAirlineCode": "JJ"
                            },
                            "passengers": [
                                {
                                    "name": "maria",
                                    "lastName": "paula soares samples",
                                    "status": "CHECKED",
                                    "seat": "5A",
                                    "ticketNumber": "9572483127883",
                                    "paxSegmentID": "2317154800006596",
                                    "messages" : [
                                        {
                                            "text" : "chequeado con exito"
                                        }
                                    ]
                                },
                                {
                                    "name": "lisa",
                                    "lastName": "simpson",
                                    "status": "CHECKED",
                                    "seat": "6A",
                                    "ticketNumber": "9572483127885",
                                    "paxSegmentID": "2317154800006595",
                                    "messages" : [
                                        {
                                            "text" : "chequeado con exito"
                                        }
                                    ]
                                }
                            ],
                            "id": "03"
                        }
                    ]
                }
            }


    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "required": true,
              "title": "root",
              "description": "",
              "name": "",
              "properties": {
                "status": {
                  "type": "object",
                  "required": false,
                  "title": "",
                  "description": "",
                  "name": "",
                  "properties": {
                    "code": {
                      "type": "integer",
                      "required": false,
                      "title": "",
                      "description": "",
                      "name": "",
                      "minimum": 0
                    }
                  }
                },
                "data": {
                  "type": "object",
                  "required": false,
                  "title": "",
                  "description": "",
                  "name": "",
                  "properties": {
                    "segments": {
                      "type": "array",
                      "required": false,
                      "title": "",
                      "description": "",
                      "name": "",
                      "minItems": 0,
                      "uniqueItems": false,
                      "items": {
                        "type": "object",
                        "required": false,
                        "title": "",
                        "description": "",
                        "name": "",
                        "properties": {
                          "departureAirport": {
                            "type": "object",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "properties": {
                              "code": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "name": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              }
                            }
                          },
                          "departureCity": {
                            "type": "object",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "properties": {
                              "code": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "name": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              }
                            }
                          },
                          "arrivalAirport": {
                            "type": "object",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "properties": {
                              "code": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "name": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              }
                            }
                          },
                          "arrivalCity": {
                            "type": "object",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "properties": {
                              "code": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "name": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              }
                            }
                          },
                          "estimatedDepartureDateTime": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "minLength": 0
                          },
                          "estimatedArrivalDateTime": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "minLength": 0
                          },
                          "flight": {
                            "type": "object",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "properties": {
                              "number": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "operatingAirlineCode": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              },
                              "marketingAirlineCode": {
                                "type": "string",
                                "required": false,
                                "title": "",
                                "description": "",
                                "name": "",
                                "minLength": 0
                              }
                            }
                          },
                          "passengers": {
                            "type": "array",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "minItems": 0,
                            "uniqueItems": false,
                            "items": {
                              "type": "object",
                              "required": false,
                              "title": "",
                              "description": "",
                              "name": "",
                              "properties": {
                                "name": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "lastName": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "status": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "seat": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "ticketNumber": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "paxSegmentID": {
                                  "type": "string",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0
                                },
                                "messages": {
                                  "type": "array",
                                  "required": false,
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minItems": 0,
                                  "uniqueItems": false,
                                  "items": {
                                    "type": "object",
                                    "required": false,
                                    "title": "",
                                    "description": "",
                                    "name": "",
                                    "properties": {
                                      "text": {
                                        "type": "string",
                                        "required": false,
                                        "title": "",
                                        "description": "",
                                        "name": "",
                                        "minLength": 0
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          },
                          "id": {
                            "type": "string",
                            "required": false,
                            "title": "",
                            "description": "",
                            "name": "",
                            "minLength": 0
                          }
                        }
                      }
                    }
                  }
                }
              }
            }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 501 (application/json)

        { "title": "No paso la validacion del apellido o record locator, intente de nuevo" } 

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 510 (application/json)

        { "title": "Reserva inhibida para checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }


## Cancel Checkin [/ws/api/airport/1.0/checkin/passengers/cancel]
### Cancel Checkin Passengers [POST]

+ Request (application/json)

        {
            "language": "PT",
            "country": "BR",
            "portal": "personas",
            "application": "checkin",
            "recordLocator": "6VKQD5",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": "01",
                    "departureAirport": "IGU",
                    "arrivalAirport": "CGH",
                    "departureDateTime": "2014-05-07T16:07",
                    "operatingAirline": "JJ",
                    "flightNumber": "3339",
                    "passengers" : [
                        {
                            "lastName": "SIMPSON",
                            "name": "LISA",
                            "seatNumber": "5A",
                            "ticketNumber": "9572483127885",
                            "paxSegmentID" : "dsf23fdfdsf"
                        }
                    ]
                }
            ]           
        }

        + Schema

          {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "title": "root",
              "description": "",
              "name": "",
              "additionalProperties": false,
              "properties": {
                "language": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "country": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "portal": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "application": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "recordLocator": {
                  "type": "string",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minLength": 0,
                  "additionalProperties": false
                },
                "flights": {
                  "type": "array",
                  "title": "",
                  "description": "",
                  "name": "",
                  "minItems": 0,
                  "uniqueItems": false,
                  "additionalProperties": false,
                  "items": {
                    "type": "object",
                    "title": "",
                    "description": "",
                    "name": "",
                    "additionalProperties": false,
                    "properties": {
                      "id": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "departureAirport": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "arrivalAirport": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "departureDateTime": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "operatingAirline": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "flightNumber": {
                        "type": "string",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minLength": 0,
                        "additionalProperties": false
                      },
                      "passengers": {
                        "type": "array",
                        "title": "",
                        "description": "",
                        "name": "",
                        "minItems": 0,
                        "uniqueItems": false,
                        "additionalProperties": false,
                        "items": {
                          "type": "object",
                          "title": "",
                          "description": "",
                          "name": "",
                          "additionalProperties": false,
                          "properties": {
                            "lastName": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "name": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "seatNumber": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "ticketNumber": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            },
                            "paxSegmentID": {
                              "type": "string",
                              "title": "",
                              "description": "",
                              "name": "",
                              "minLength": 0,
                              "additionalProperties": false
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
    
+ Response 200 (application/json)


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200,
                    "message": ""
                },
                "data": {
                    "flights": [
                        {
                            "passengers": [
                                {
                                    "paxSegmentID": "sdfsd324324",
                                    "name": "LISA",
                                    "lastName": "SIMPSON",
                                    "ticketNumber": "9572483127885",
                                    "seat": "5A",
                                    "status": "NOTCHECKED",
                                    "seatStatus": "RELEASED",
                                    "seatMesages": [
                                        {
                                            "text": "se libero bien el asiento"
                                        }
                                    ],
                                    "statusMessages": [
                                        {
                                            "text": "el pasajero esta chequeable"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            }


    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "title": "root",
              "description": "",
              "name": "",
              "additionalProperties": false,
              "properties": {
                "status": {
                  "type": "object",
                  "title": "",
                  "description": "",
                  "name": "",
                  "additionalProperties": false,
                  "properties": {
                    "code": {
                      "type": "integer",
                      "title": "",
                      "description": "",
                      "name": "",
                      "minimum": 0,
                      "additionalProperties": false
                    },
                    "message": {
                      "type": "string",
                      "title": "",
                      "description": "",
                      "name": "",
                      "minLength": 0,
                      "additionalProperties": false
                    }
                  }
                },
                "data": {
                  "type": "object",
                  "title": "",
                  "description": "",
                  "name": "",
                  "additionalProperties": false,
                  "properties": {
                    "flights": {
                      "type": "array",
                      "title": "",
                      "description": "",
                      "name": "",
                      "minItems": 0,
                      "uniqueItems": false,
                      "additionalProperties": false,
                      "items": {
                        "type": "object",
                        "title": "",
                        "description": "",
                        "name": "",
                        "additionalProperties": false,
                        "properties": {
                          "passengers": {
                            "type": "array",
                            "title": "",
                            "description": "",
                            "name": "",
                            "minItems": 0,
                            "uniqueItems": false,
                            "additionalProperties": false,
                            "items": {
                              "type": "object",
                              "title": "",
                              "description": "",
                              "name": "",
                              "additionalProperties": false,
                              "properties": {
                                "paxSegmentID": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "name": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "lastName": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "ticketNumber": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "seat": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "status": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "seatStatus": {
                                  "type": "string",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minLength": 0,
                                  "additionalProperties": false
                                },
                                "seatMesages": {
                                  "type": "array",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minItems": 0,
                                  "uniqueItems": false,
                                  "additionalProperties": false,
                                  "items": {
                                    "type": "object",
                                    "title": "",
                                    "description": "",
                                    "name": "",
                                    "additionalProperties": false,
                                    "properties": {
                                      "text": {
                                        "type": "string",
                                        "title": "",
                                        "description": "",
                                        "name": "",
                                        "minLength": 0,
                                        "additionalProperties": false
                                      }
                                    }
                                  }
                                },
                                "statusMessages": {
                                  "type": "array",
                                  "title": "",
                                  "description": "",
                                  "name": "",
                                  "minItems": 0,
                                  "uniqueItems": false,
                                  "additionalProperties": false,
                                  "items": {
                                    "type": "object",
                                    "title": "",
                                    "description": "",
                                    "name": "",
                                    "additionalProperties": false,
                                    "properties": {
                                      "text": {
                                        "type": "string",
                                        "title": "",
                                        "description": "",
                                        "name": "",
                                        "minLength": 0,
                                        "additionalProperties": false
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }  


+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }


+ Response 520 (application/json)

        { "title": "Request invalido" }


## Email Boarding Pass [/ws/api/airport/1.0/passenger/boarging_pass/email]
### Send Email Boarding Pass [POST]

+ Request (application/json)

        {
            "language":"ES",
            "country":"CL",
            "portal":"personas",
            "application":"checkin",
            "email":"jsd@csda.com",
            "recordLocator" : "dsfsfd",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": "01",
                    "departureAirport": "IGU",
                    "arrivalAirport": "CGH",
                    "departureDateTime": "2014-05-07T16:07",
                    "operatingAirline": "JJ",
                    "flightNumber": "3339",
                    "passengers" : [
                        {
                            "lastName": "SIMPSON",
                            "name": "LISA",
                            "seatNumber": "5A",
                            "ticketNumber": "9572483127885",
                            "paxSegmentID" : "dsf23fdfdsf"
                        }
                    ]
                }
            ]           
        }


+ Response 200 (application/json)


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status":{
                    "code":200,
                    "message":""
                },
                "data":null
            }

    + Schema

            {
                "type":"object",
                "$schema": "http://json-schema.org/draft-03/schema",
                "id": "http://jsonschema.net",
                "required":false,
                "properties":{
                    "data": {
                        "type":"null",
                        "required":false
                    },
                    "status": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "code": {
                                "type":"number",
                                "required":false
                            },
                            "message": {
                                "type":"string",
                                "required":false
                            }
                        }
                    }
                }
            }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }


+ Response 520 (application/json)

        { "title": "Request invalido" }

## Mobile Boarding Pass [/ws/api/airport/1.0/passenger/boarding_pass/email_mobile]
### Send Mobile Boarding Pass [POST]

+ Request (application/json)
    
        {
            "language":"ES",
            "country":"CL",
            "portal":"personas",
            "application":"checkin",
            "email":"jlueiza@gmail.com",
            "recordLocator" : "sdffds",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": "01",
                    "departureAirport": "IGU",
                    "arrivalAirport": "CGH",
                    "departureDateTime": "2014-05-07T16:07",
                    "operatingAirline": "JJ",
                    "flightNumber": "3339",
                    "passengers" : [
                        {
                            "lastName": "SIMPSON",
                            "name": "LISA",
                            "seatNumber": "5A",
                            "ticketNumber": "9572483127885",
                            "paxSegmentID" : "dsf23fdfdsf"
                        }
                    ]
                }
            ]    
        }

+ Response 200 (application/json)       


    + Header

                flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
                trackId:4264964     
        
    + Body

                {
                    "status":{
                        "code":509,
                        "message":"Error Send Mobile Boarding Pass"
                    },
                    "data":null
                }

    + Schema

            {
                "type":"object",
                "$schema": "http://json-schema.org/draft-03/schema",
                "id": "http://jsonschema.net",
                "required":false,
                "properties":{
                    "data": {
                        "type":"null",
                        "required":false
                    },
                    "status": {
                        "type":"object",
                        "required":false,
                        "properties":{
                            "code": {
                                "type":"number",
                                "required":false
                            },
                            "message": {
                                "type":"string",
                                "required":false
                            }
                        }
                    }
                }
            }

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }


+ Response 520 (application/json)

        { "title": "Request invalido" }

## Boarding Pass pdf  [/ws/api/airport/1.0/passenger/boarding_pass/pdf]
### Get Boarding Pass in pdf format [GET]

+ Request (application/json)
    
        {
            "language":"ES",
            "country":"CL",
            "portal":"personas",
            "application":"checkin",
            "recordLocator" : "sdfdad",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": "01",
                    "departureAirport": "IGU",
                    "arrivalAirport": "CGH",
                    "departureDateTime": "2014-05-07T16:07",
                    "operatingAirline": "JJ",
                    "flightNumber": "3339",
                    "passengers" : [
                        {
                            "lastName": "SIMPSON",
                            "name": "LISA",
                            "seatNumber": "5A",
                            "ticketNumber": "9572483127885",
                            "paxSegmentID" : "dsf23fdfdsf"
                        }
                    ]
                }
            ]    
        }

    

+ Response 200 (application/pdf)


+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }


+ Response 520 (application/json)

        { "title": "Request invalido" }


## Precheck voucher pdf  [/ws/api/airport/1.0/passenger/precheck_voucher/pdf]
### Get Precheck voucher in pdf format [GET]

+ Request (application/json)
    
        {
            "language":"ES",
            "country":"CL",
            "portal":"personas",
            "application":"checkin",
            "recordLocator" : "sdfdad",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": "01",
                    "departureAirport": "IGU",
                    "arrivalAirport": "CGH",
                    "departureDateTime": "2014-05-07T16:07",
                    "operatingAirline": "JJ",
                    "flightNumber": "3339",
                    "passengers" : [
                        {
                            "lastName": "SIMPSON",
                            "name": "LISA",
                            "seatNumber": "5A",
                            "ticketNumber": "9572483127885",
                            "paxSegmentID" : "dsf23fdfdsf"
                        }
                    ]
                }
            ]    
        }
    

+ Response 200 (application/pdf)


+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }


+ Response 520 (application/json)

        { "title": "Request invalido" }

# Resource [/ws/api/checkin/1.0/rest/api/search_configuration]
## Create Resource [POST]

+ Response 200

        {
            "status": 
            {
                "code": 200,
                "message": ""
            },
            "data": {
                "enabled": true,
                "flowId": "08f806fe-ba89-432a-bd4f-ed8d1b0178a6",
                "analytics": {
                    "homeacc": "UA-30106544-1",
                    "lancomacc": "UA-30106544-3"
                }
            }
        }





# Group Flight
##  Seat Map  [/ws/api/airport/1.0/checkin/flight/seat_map]
### Seat Map Data [GET]

+ Request (application/json)

        {
            "language": "PT",
            "country": "BR",
            "portal": "personas",
            "application": "checkin",
            "recordLocator": "6VKQD5",
            "channel" : "WEB",
            "segments": [
                {
                    "id": "1",
                    "departureAirportCode": "IGU",
                    "arrivalAirportCode": "CGH",
                    "departureDateTime": "2014-05-07T16:07:00.000",
                    "arrivalDateTime": "2014-05-07T17:38:00.000",
                    "operatingAirlineCode": "JJ",
                    "flightNumber": "3339",
                    "legs": [
                        {
                            "departureAirportCode": "IGU",
                            "arrivalAirportCode": "CGH",
                            "departureDateTime": "2014-05-07T16:07:00.000",
                            "arrivalDateTime": "2014-05-07T17:38:00.000",
                            "operatingAirlineCode": "JJ",
                            "flightNumber": "3339"
                        }
                    ]
                }
            ],
            "passengers": [
                {
                    "name": "MARIA",
                    "lastName": "PAULASOARESSAMPLES",
                    "typeCode": "ADT",
                    "paxSegmentID": "1104534245452342"
                }
            ]
        }

    + Headers

            flowId: a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId: 4264964

    + Schema

            {
                "$schema": "http://json-schema.org/draft-04/schema#",
                "id": "http://jsonschema.net#",
                "type": "object",
                "additionalProperties": false,
                "properties": {
                    "language": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Languaje ejemplo : ES = español, PT = portugues"
                    },
                    "country": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil"
                    },
                    "portal": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos"
                    },
                    "application": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc"
                    },
                    "recordLocator": {
                        "type": "string",
                        "additionalProperties": false,
                        "description": "Identificador de la reserva, ejemplo ASDSE2  6 caracteres alfanumericos "
                    },
                    "segments": {
                        "type": "array",
                        "additionalProperties": false,
                        "items": {
                            "type": "object",
                            "additionalProperties": false,
                            "properties": {
                                "id": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Identificador del segmento, por ejemplo 1"
                                },
                                "departureAirportCode": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Codigo de aeropuerto de despegue, ejemplo SCL"
                                },
                                "arrivalAirportCode": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Codigo de aeropuerto de arribo, ejemplo BUE"
                                },
                                "departureDateTime": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Fecha y hora estimada del despegue del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                                },
                                "arrivalDateTime": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Fecha y hora estimada del arribo del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                                },
                                "operatingAirlineCode": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Codigo de aerolinea operadora del vuelo, ejemplo LA"
                                },
                                "flightNumber": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Numero de vuelo, ejemplo 24323422"
                                },
                                "legs": {
                                    "type": "array",
                                    "additionalProperties": false,
                                    "items": {
                                        "type": "object",
                                        "additionalProperties": false,
                                        "properties": {
                                            "departureAirportCode": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Codigo de aeropuerto de despegue,ejemplo SCL"
                                            },
                                            "arrivalAirportCode": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Codigo de aeropuerto de arribo, ejemplo BUE"
                                            },
                                            "departureDateTime": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Fecha y hora estimada del despegue del vuelo,ejemplo 2014-05-07T16: 07, formatoYYYY-MM-DDThh: mm"
                                            },
                                            "arrivalDateTime": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Fecha y hora estimada del arribo del vuelo, ejemplo 2014-05-07T16:07, formatoYYYY-MM-DDThh: mm"
                                            },
                                            "operatingAirlineCode": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Codigo de aerolinea operadora del vuelo, ejemplo LA"
                                            },
                                            "flightNumber": {
                                                "type": "string",
                                                "additionalProperties": false,
                                                "description": "Numero de vuelo, ejemplo 24323422"
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    },
                    "passengers": {
                        "type": "array",
                        "additionalProperties": false,
                        "items": {
                            "type": "object",
                            "additionalProperties": false,
                            "properties": {
                                "name": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Nombre del pasajero, ejemplo JUAN"
                                },
                                "lastName": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Apellido del pasajero"
                                },
                                "typeCode": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Tipo de pasajero, opciones ADT=adulto, CHD=child, INF=infante"
                                },
                                "paxSegmentID": {
                                    "type": "string",
                                    "additionalProperties": false,
                                    "description": "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2"
                                }
                            }
                        }
                    }
                }
            }

       

+ Response 200 (application/json)     

    + Header

                flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
                trackId:4264964     

    + Body  
        
            {
                "status": {
                    "code": 201,
                    "message": "Validation problem has occurred, please view the warnings"
                },
                "data": {
                    "passengers": [
                        {
                            "paxNumber": 1,
                            "lastName": "PAULA SOARES SAMPLES",
                            "name": "MARIA"
                        }
                    ],
                    "segments": [
                        {
                            "id": 1,
                            "arrivalAirport": {
                                "code": "CGH",
                                "name": "SAO PAULO - CONGONHAS"
                            },
                            "arrivalCity": {
                                "code": "SAO",
                                "name": "S&atilde;o Paulo"
                            },
                            "departureCity": {
                                "code": "IGU",
                                "name": "Foz do Igua&ccedil;u"
                            },
                            "departureAirport": {
                                "code": "IGU",
                                "name": "CATARATAS"
                            },
                            "legs": [
                                {
                                    "id": 1,
                                    "arrivalAirport": {
                                        "code": "CGH",
                                        "name": "SAO PAULO - CONGONHAS"
                                    },
                                    "arrivalCity": {
                                        "code": "SAO",
                                        "name": "S&atilde;o Paulo"
                                    },
                                    "departureAirport": {
                                        "code": "IGU",
                                        "name": "CATARATAS"
                                    },
                                    "departureCity": {
                                        "code": "IGU",
                                        "name": "Foz do Igua&ccedil;u"
                                    },
                                    "flight": {
                                        "marketingAirlineCode": "JJ",
                                        "operatingAirlineCode": "JJ",
                                        "flightNumber": 3339,
                                        "seatMap": {
                                            "cabins": [
                                                {
                                                    "cabinCode": "Y",
                                                    "columns": [
                                                        {
                                                            "columnCode": "A",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": true,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": true,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        },
                                                        {
                                                            "columnCode": "B",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        },
                                                        {
                                                            "columnCode": "C",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 28,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        },
                                                        {
                                                            "columnCode": "D",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "U",
                                                                    "status": "UNAVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 27,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 28,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": true,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        },
                                                        {
                                                            "columnCode": "E",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": false,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        },
                                                        {
                                                            "columnCode": "F",
                                                            "seats": [
                                                                {
                                                                    "row": 1,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": true,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 28,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": true,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                },
                                                                {
                                                                    "row": 29,
                                                                    "statusCode": "A",
                                                                    "status": "AVAILABLE",
                                                                    "characteristics": {
                                                                        "window": true,
                                                                        "aisle": false,
                                                                        "wing": false,
                                                                        "emergencyExit": false,
                                                                        "exit": false
                                                                    },
                                                                    "displayCategories": {
                                                                        "comodoro": "normal",
                                                                        "normal": "normal",
                                                                        "cip": "normal"
                                                                    }
                                                                }
                                                            ]
                                                        }
                                                    ]
                                                }
                                            ]
                                        },
                                        "estimatedArrivalDateTime": "2014-05-07T17:38",
                                        "estimatedDepartureDateTime": "2014-05-07T16:07",
                                        "equipment": "320"
                                    }
                                }
                            ]
                        }
                    ]
                }
            }
            
              
    + Schema

            {
                "type": "object",
                "$schema": "http://json-schema.org/draft-03/schema",
                "id": "http://jsonschema.net",
                "required": false,
                "properties": {
                    "data": {
                        "type": "object",
                        "required": false,
                        "properties": {
                            "Identifiers": {
                                "type": "array",
                                "required": false,
                                "items": {
                                    "type": "object",
                                    "required": false
                                }
                            },
                            "passengers": {
                                "type": "array",
                                "required": false,
                                "items": {
                                    "type": "object",
                                    "required": false,
                                    "properties": {
                                        "lastName": {
                                            "type": "string",
                                            "required": false,
                                            "description": "Apellido pasajero"
                                        },
                                        "name": {
                                            "type": "string",
                                            "required": false,
                                            "description": "Nombre pasajero"
                                        },
                                        "paxNumber": {
                                            "type": "number",
                                            "required": false,
                                            "description": "Numero de pasajero en la reserva"
                                        }
                                    }
                                }
                            },
                            "segments": {
                                "type": "array",
                                "required": false,
                                "items": {
                                    "type": "object",
                                    "required": false,
                                    "properties": {
                                        "arrivalAirportCode": {
                                            "type": "object",
                                            "required": false,
                                            "properties": {
                                                "code": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Codigo de aeropuerto, ejemplo SCL"
                                                },
                                                "name": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Nombre de aerpuerto, ejemplo Aeroparque"
                                                }
                                            }
                                        },
                                        "arrivalCity": {
                                            "type": "object",
                                            "required": false,
                                            "properties": {
                                                "code": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Codigo aeropuerto, ejemplo BUE"
                                                },
                                                "name": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Nombre de aeropuerto, ejemplo Arturo Merino Benitez"
                                                }
                                            }
                                        },
                                        "departureAirportCode": {
                                            "type": "object",
                                            "required": false,
                                            "properties": {
                                                "code": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Codigo de aeropuerto, ejemplo BUE"
                                                },
                                                "name": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Nombre de aeropuerto, ejemplo Arturo Merino Benitez"
                                                }
                                            }
                                        },
                                        "departureCity": {
                                            "type": "object",
                                            "required": false,
                                            "properties": {
                                                "code": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Codigo de ciudad de despegue, ejemplo SCL"
                                                },
                                                "name": {
                                                    "type": "string",
                                                    "required": false,
                                                    "description": "Nombre de aeropuerto, ejemplo Arturo Merino Benitez"
                                                }
                                            }
                                        },
                                        "legs": {
                                            "type": "array",
                                            "required": false,
                                            "items": {
                                                "type": "object",
                                                "required": false,
                                                "properties": {
                                                    "arrivalAirport": {
                                                        "type": "object",
                                                        "required": false,
                                                        "properties": {
                                                            "code": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo de aeropuerto, ejemplo SCL"
                                                            },
                                                            "name": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Nombre de aeropuerto, ejemplo Aeroparque"
                                                            }
                                                        }
                                                    },
                                                    "arrivalCity": {
                                                        "type": "object",
                                                        "required": false,
                                                        "properties": {
                                                            "code": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo de ciudad, ejemplo SCL"
                                                            },
                                                            "name": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Nombre de aeropuerto, ejemplo Aeroparque"
                                                            }
                                                        }
                                                    },
                                                    "departureAirportCode": {
                                                        "type": "object",
                                                        "required": false,
                                                        "properties": {
                                                            "code": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo de aeropuerto, ejemplo SCL"
                                                            },
                                                            "name": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Nombre de aeropuerto, ejemplo SAO PAULO - CONGONHAS"
                                                            }
                                                        }
                                                    },
                                                    "departureCity": {
                                                        "type": "object",
                                                        "required": false,
                                                        "properties": {
                                                            "code": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo de ciudad, ejemplo SCL"
                                                            },
                                                            "name": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Nombre de ciudad, ejemplo Santiago de Chile"
                                                            }
                                                        }
                                                    },
                                                    "flight": {
                                                        "type": "object",
                                                        "required": false,
                                                        "properties": {
                                                            "equipment": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Tipo de avion, ejemplo 320"
                                                            },
                                                            "estimatedArrivalDateTime": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Fecha y hora estimada del arribo del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                                                            },
                                                            "estimatedDepartureDateTime": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Fecha y hora estimada del despegue del vuelo, ejemplo 2014-05-07T16:07, formato YYYY-MM-DDThh:mm"
                                                            },
                                                            "marketingAirlineCode": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo de la aerolinea que vendio el vuelo, ejemplo LA"
                                                            },
                                                            "flightNumber": {
                                                                "type": "number",
                                                                "required": false,
                                                                "description": "Numero de vuelo, ejemplo 3243"
                                                            },
                                                            "operatingAirlineCode": {
                                                                "type": "string",
                                                                "required": false,
                                                                "description": "Codigo aerolinea operadora, ejemplo LA"
                                                            },
                                                            "seatMap": {
                                                                "type": "object",
                                                                "required": false,
                                                                "properties": {
                                                                    "cabins": {
                                                                        "type": "array",
                                                                        "required": false,
                                                                        "description": "Lista de cabinas del avion",
                                                                        "items": {
                                                                            "type": "object",
                                                                            "required": false,
                                                                            "properties": {
                                                                                "cabinCode": {
                                                                                    "type": "string",
                                                                                    "required": false,
                                                                                    "description": "Codigo de la cabina, ejemplo Y"
                                                                                },
                                                                                "columns": {
                                                                                    "type": "array",
                                                                                    "required": false,
                                                                                    "description": "Lista de columnas de asientos del avion",
                                                                                    "items": {
                                                                                        "type": "object",
                                                                                        "required": false,
                                                                                        "properties": {
                                                                                            "columnCode": {
                                                                                                "type": "string",
                                                                                                "required": false,
                                                                                                "description": "Codigo de la columna, ejemplo L"
                                                                                            },
                                                                                            "seats": {
                                                                                                "type": "array",
                                                                                                "required": false,
                                                                                                "description": "Lista de asientos de una columna",
                                                                                                "items": {
                                                                                                    "type": "object",
                                                                                                    "required": false,
                                                                                                    "properties": {
                                                                                                        "characteristics": {
                                                                                                            "type": "object",
                                                                                                            "required": false,
                                                                                                            "description": "Caracteristicas del asiento",
                                                                                                            "properties": {
                                                                                                                "aisle": {
                                                                                                                    "type": "boolean",
                                                                                                                    "required": false,
                                                                                                                    "description": "Indica si el asiento esta solo"
                                                                                                                },
                                                                                                                "emergencyExit": {
                                                                                                                    "type": "boolean",
                                                                                                                    "required": false,
                                                                                                                    "description": "Indica si el asiento es esta en la salida de emergencia"
                                                                                                                },
                                                                                                                "exit": {
                                                                                                                    "type": "boolean",
                                                                                                                    "required": false
                                                                                                                },
                                                                                                                "window": {
                                                                                                                    "type": "boolean",
                                                                                                                    "required": false,
                                                                                                                    "description": "Indica si el asiento es el mas proximo a la ventana"
                                                                                                                },
                                                                                                                "wing": {
                                                                                                                    "type": "boolean",
                                                                                                                    "required": false,
                                                                                                                    "description": "Indica si el asiento esta inmediatamente al lado del ala"
                                                                                                                }
                                                                                                            }
                                                                                                        },
                                                                                                        "displayCategories": {
                                                                                                            "type": "object",
                                                                                                            "required": false,
                                                                                                            "properties": {
                                                                                                                "cip": {
                                                                                                                    "type": "string",
                                                                                                                    "required": false
                                                                                                                },
                                                                                                                "comodoro": {
                                                                                                                    "type": "string",
                                                                                                                    "required": false
                                                                                                                },
                                                                                                                "normal": {
                                                                                                                    "type": "string",
                                                                                                                    "required": false
                                                                                                                }
                                                                                                            }
                                                                                                        },
                                                                                                        "row": {
                                                                                                            "type": "number",
                                                                                                            "required": false,
                                                                                                            "description": "Numero de fila"
                                                                                                        },
                                                                                                        "statusCode": {
                                                                                                            "type": "string",
                                                                                                            "required": false
                                                                                                        },
                                                                                                        "status": {
                                                                                                            "type": "string",
                                                                                                            "required": false
                                                                                                        }
                                                                                                    }
                                                                                                }
                                                                                            }
                                                                                        }
                                                                                    }
                                                                                }
                                                                            }
                                                                        }
                                                                    }
                                                                }
                                                            }
                                                        }
                                                    },
                                                    "id": {
                                                        "type": "number",
                                                        "required": false,
                                                        "description": "Identificador de leg en la reserva, ejemplo 1"
                                                    }
                                                }
                                            }
                                        },
                                        "id": {
                                            "type": "number",
                                            "required": false,
                                            "description": "Identificador de segmento en la reserva, ejemplo 2"
                                        }
                                    }
                                }
                            }
                        }
                    },
                    "status": {
                        "type": "object",
                        "required": false,
                        "properties": {
                            "code": {
                                "type": "number",
                                "required": false
                            },
                            "message": {
                                "type": "string",
                                "required": false
                            }
                        }
                    }
                }
            }
+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }
           


## Take Seats [/ws/api/airport/1.0/checkin/flight/seat_map/take_seats]
### Take Seats  [POST]

+ Request (application/json)

        {
            "language": "PT",
            "country": "BR",
            "portal": "personas",
            "application": "checkin",
            "recordLocator": "6VKQD5",
            "channel" : "WEB",
            "flights" : [
                {
                    "id": 1,
                    "flightNumber" : 34323,
                    "operatingAirlineCode" : "JJ",
                    "passengers" : [
                        {
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "paxSegmentID": "3362054900001A3C",
                            "seat" : "24L"
                        },
                        {
                            "name": "maria",
                            "lastName": "paula soares samples",
                            "paxSegmentID": "3362054900001A3C",
                            "seat" : "24L"
                        }
                    ]

                }
            ]
        }

    + Schema

            {
              "$schema": "http://json-schema.org/draft-04/schema#",
              "id": "http://jsonschema.net#",
              "type": "object",
              "required": false,
              "title": "root",
              "description": "",
              "name": "",
              "properties": {
                "language": {
                  "type": "string",
                  "required": false,
                  "title": "",
                  "description" : "Languaje ejemplo : ES = español, PT = portugues",
                  "name": "",
                  "minLength": 0
                },
                "country": {
                  "type": "string",
                  "required": false,
                  "title": "",
                  "description": "Pais ejemplo : CL = Chile, AR = Argentina, BR = Brasil",
                  "name": "",
                  "minLength": 0
                },
                "portal": {
                  "type": "string",
                  "required": false,
                  "title": "",
                  "description": "Portal web de LAN.com opciones: personas, empresas, asociados, trotamundos",
                  "name": "",
                  "minLength": 0
                },
                "application": {
                  "type": "string",
                  "required": false,
                  "title": "",
                  "description": "Aplicacion de LAN.com ejemplos: checkin, compra_normal, pago_reserva, etc",
                  "name": "",
                  "minLength": 0
                },
                "recordLocator": {
                  "type": "string",
                  "required": false,
                  "title": "",
                  "description": "Identificador de la reserva, ejemplo ASDSE2  6 caracteres alfanumericos",
                  "name": "",
                  "minLength": 0
                },
                "flights": {
                  "type": "array",
                  "required": false,
                  "title": "",
                  "description": "",
                  "name": "",
                  "minItems": 0,
                  "uniqueItems": false,
                  "items": {
                    "type": "object",
                    "required": false,
                    "title": "",
                    "description": "",
                    "name": "",
                    "properties": {
                      "id": {
                        "type": "number",
                        "required": false,
                        "title": "",
                        "description": "Identificador del vuelo en la reserva, ejemplo 1",
                        "name": "",
                        "minLength": 0
                      },
                      "flightNumber": {
                        "type": "integer",
                        "required": false,
                        "title": "",
                        "description": "Numero de vuelo, ejemplo 3243",
                        "name": "",
                        "minimum": 0
                      },
                      "operatingAirlineCode": {
                        "type": "string",
                        "required": false,
                        "title": "",
                        "description": "Codigo aerolinea operadora, ejemplo LA",
                        "name": "",
                        "minLength": 0
                      },
                      "passengers": {
                        "type": "array",
                        "required": false,
                        "title": "",
                        "description": "",
                        "name": "",
                        "minItems": 0,
                        "uniqueItems": false,
                        "items": {
                          "type": "object",
                          "required": false,
                          "title": "",
                          "description": "",
                          "name": "",
                          "properties": {
                            "name": {
                              "type": "string",
                              "required": false,
                              "title": "",
                              "description": "Nombre del pasajero, ejemplo JUAN",
                              "name": "",
                              "minLength": 0
                            },
                            "lastName": {
                              "type": "string",
                              "required": false,
                              "title": "",
                              "description": "Apellido del pasajero, ejemplo PEREZ",
                              "name": "",
                              "minLength": 0
                            },
                            "paxSegmentID": {
                              "type": "string",
                              "required": false,
                              "title": "",
                              "description": "Identificador del pasajero segmento en el gds, ejemplo 3242354sddf2",
                              "name": "",
                              "minLength": 0
                            },
                            "seat": {
                              "type": "string",
                              "required": false,
                              "title": "",
                              "description": "Asiendo asignado al pasajero, ejemplo 24L",
                              "name": "",
                              "minLength": 0
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }


+ Response 200


    + Header

            flowId:a4f390e1-af0d-4bcd-8682-fd932d2d8ad
            trackId:4264964            
    
    + Body

            {
                "status": {
                    "code": 200
                },
                "data": {
                    "flights" : [
                        {
                            "id": "01",
                            "passengers" : [
                                {
                                    "paxSegmentID": "3362054900001A3C",
                                    "status"  : "TAKEN",
                                    "seat" : "24A",
                                    "messages" : []
                                },
                                 {
                                    "paxSegmentID": "3362054900001A3C",
                                    "status"  : "NOTTAKEN",
                                    "seat" : "",
                                    "messages" : [
                                        {
                                            "text" : "No se pudo tomar el asiento porque estaba ocupado"
                                        }
                                    ]
                                }
                            ]

                        }
                    ]     
                }
            }    

    + Schema

            {
                "$schema": "http://json-schema.org/draft-04/schema#",
                "id": "http://jsonschema.net#",
                "type": "object",
                "additionalProperties": false,
                "properties": {
                "status": {
                  "type": "object",
                  "additionalProperties": false,
                  "properties": {
                    "code": {
                      "type": "integer",
                      "additionalProperties": false
                    }
                  }
                },
                "data": {
                  "type": "object",
                  "additionalProperties": false,
                  "properties": {
                    "flights": {
                      "type": "array",
                      "additionalProperties": false,
                      "items": {
                        "type": "object",
                        "additionalProperties": false,
                        "properties": {
                          "id": {
                            "type": "string",
                            "additionalProperties": false
                          },
                          "passengers": {
                            "type": "array",
                            "additionalProperties": false,
                            "items": {
                              "type": "object",
                              "additionalProperties": false,
                              "properties": {
                                "paxSegmentID": {
                                  "type": "string",
                                  "additionalProperties": false
                                },
                                "status": {
                                  "type": "string",
                                  "additionalProperties": false
                                },
                                "seat": {
                                  "type": "string",
                                  "additionalProperties": false
                                },
                                "messages": {
                                  "type": "array",
                                  "additionalProperties": false,
                                  "items": {
                                    "type": "object",
                                    "additionalProperties": false,
                                    "properties": {
                                      "text": {
                                        "type": "string",
                                        "additionalProperties": false
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                }
                }
           

+ Response 500 (application/json)

        { "title": "Fatal Error" }

+ Response 502 (application/json)  

        { "title": "Error llamando al servicio, trate en un rato" }         

+ Response 503 (application/json)

        { "title": "No disponible el checkin" }

+ Response 520 (application/json)

        { "title": "Request invalido" }






# Group ATC
## Create Atc Url [/ws/api/airport/1/upgrade/atc/url]
## Create Atc Url [POST]

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"PT", 
             "country":"BR", 
             "portal":"personas", 
             "application":"upg",
             "frequent_flyer_customer": "32sdf234",
             "employee_id" : "sdfsdff3423sdf",
             "employee_password" : "sdfdsew23*as"
            }



+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {
                "url" : "www.lan.com/es_cl/apps/personas/upg/?token=SDFSDFD324234SDFSDF"
              }
            }


# Group Customers
## Get Customer [/ws/api/customers/1.0/rest/customer/{?id,frequent_flyer}]

+ Parameters
      + id (optional, string) ... id del cliente
      + frequent_flyer (optional, string) ... frequent flyer del cliente

## customer Information [GET]

 
+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "customer_id" : "sdfsdfsdf23423",
             "frequent_flyer" : "3242342353"  
            }

+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {
                "customer" : 
                  {
                    "id": "sdfsdfsd324",
                    "name" : "Jose Miguel",
                    "lastName" : "Lueiza",
                    "loyaltyInfo" : [
                      {
                        "category" : "COMODORO",
                        "program" : "LA",
                        "upgradeCoupons" : 2, 
                      }
                    ]
                  }
              }
            }

## Get Customers [/ws/api/customers/1.0/rest/customer/get_customers]
## customer Information [POST]

 
+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "customers" : [
               {
                "customer_id" : "sdfsdfsdf23423"
               },
               {
                "frequent_flyer" : "3242342353" 
               }
               ]
             
            }

+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": ""
              },
              "data": {
                "customers" : [
                  {
                    "id": "sdfsdfsd324",
                    "name" : "Jose Miguel",
                    "lastName" : "Lueiza",
                    "loyaltyInfo" : [
                      {
                        "category" : "COMODORO",
                        "program" : "LA",
                        "upgradeCoupons" : 2, 
                      }
                    ]
                  }
                ]
              }
            }





## Create Customer [/ws/api/customers/1.0/rest/customer]
## Create Customer [POST]

 
+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "customer": 
              {
                "name" : "JUAN",
                "lastName" : "PEREZ"
              }
                        
            }

   
+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": "Usuario Creado"
              },
              "data": {
                  "customer": [
                    {
                      "id": "ASDASFDSF234324"
                    }
                  ]
               }
            }

## Update Customer [/ws/api/customers/1.0/rest/customer/]
## Update Customer [PUT]

 
+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "customer": 
              {
                "id" : "DSFSDF324234SD",
                "name" : "JUAN",
                "lastName" : "PEREZ"
              }
                        
            }

   
+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": "Usuario Actualizado"
              },
              "data": {
                  
               }
            }





## Delete Customer [/ws/api/customers/1.0/rest/customer/{id}]
## Delete Customer [DELETE]

+ Parameters
      + id (required, string) ... id del cliente

+ Request

    + Headers
    
            Content-Type : application/json
            flowId : 119d6ae2-3306-41dc-b5a0-e97d4a0e8b02
            trackId : 7123132

    + Body
              
            {
             "language":"ES", 
             "country":"CL", 
             "portal":"personas", 
             "application":"upg",
             "id" : "SDFSDF23423423SFSD"
                        
            }

   
+ Response 200

      + Headers
    
            Content-Type:application/json
      
      + Body

            {
              "status": {
                "code": 200,
                "message": "Usuario Eliminado"
              },
              "data": {
                  
               }
            }



