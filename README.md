# MqttTrafikverket
Deamon that uses the trafikverket api to publish train data to a MQTT broker.

# Installation
Install dotnet core 2.0

# Configuration
Create as json file named `appsettings.json` in the same directory that contains TrafikverketMQTT.dll

Exampe content
```json
{
  "Logging": {
    "IncludeScopes": false,
    "LogLevel": {
      "Default": "Trace",
      "System": "Information",
      "Microsoft": "Information"
    },
    "Console": {
      "LogLevel": {
        "Default": "Trace",
        "System": "Information",
        "Microsoft": "Information"
      },
      "Debug": {
        "LogLevel": {
          "Default": "Error",
          "System": "Error",
          "Microsoft": "Error"
        }
      }
    }
  },
  "Mqtt": {
    "HostAddress": "192.168.0.7",
    "ClientId": "TrafikverketMQTT",
    "BaseTopic": "Trafikverket",
    "QualityOfService": null,
    "RetainLastMessageOnServer": true
  },
  "TrafikverketSettings": {
    "ApiKey": "[APIKey]",
    "Trains": [
      {
        "Name": "T�g till jobb",
        "DepartureLocationName": "S�lvesborg",
        "DestinationLocationName": "Kristianstad C",
        "DepatureTime": "07:27"
      },
      {
        "Name": "Tidigt t�g fr�n jobb",
        "DepartureLocationName": "Kristianstad C",
        "DestinationLocationName": "S�lvesborg",
        "DepatureTime": "16:38"
      },
      {
        "Name": "Sent t�g fr�n jobb",
        "DepartureLocationName": "Kristianstad C",
        "DestinationLocationName": "S�lvesborg",
        "DepatureTime": "17:02"
      }
    ]
  }
}
```

# Execution
execute `dotnet TrafikverketMQTT.dll`