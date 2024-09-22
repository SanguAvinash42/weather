[
    {
        "id": "0956d057442e3a8b",
        "type": "tab",
        "label": "Flow 1",
        "disabled": false,
        "info": "",
        "env": []
    },
    {
        "id": "0cb492631d93dc4e",
        "type": "inject",
        "z": "0956d057442e3a8b",
        "name": "",
        "props": [
            {
                "p": "payload"
            },
            {
                "p": "topic",
                "vt": "str"
            }
        ],
        "repeat": "",
        "crontab": "",
        "once": false,
        "onceDelay": 0.1,
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "x": 260,
        "y": 700,
        "wires": [
            [
                "2eadc264d6ac3f93"
            ]
        ]
    },
    {
        "id": "2eadc264d6ac3f93",
        "type": "http request",
        "z": "0956d057442e3a8b",
        "name": "",
        "method": "POST",
        "ret": "obj",
        "paytoqs": "ignore",
        "url": "https://api.openweathermap.org/data/2.5/weather?q=usa&appid=a955b0ede9a5b2caefe0292869d9c277",
        "tls": "",
        "persist": false,
        "proxy": "",
        "insecureHTTPParser": false,
        "authType": "",
        "senderr": false,
        "headers": [],
        "x": 450,
        "y": 740,
        "wires": [
            [
                "3552e9e5d85c1751"
            ]
        ]
    },
    {
        "id": "3552e9e5d85c1751",
        "type": "function",
        "z": "0956d057442e3a8b",
        "name": "function 1",
        "func": "var weatherData = msg.payload; \nmsg.payload = weatherData.main.temp;\nreturn msg;\n",
        "outputs": 1,
        "timeout": 0,
        "noerr": 0,
        "initialize": "",
        "finalize": "",
        "libs": [],
        "x": 640,
        "y": 760,
        "wires": [
            [
                "bb07419030999df8"
            ]
        ]
    },
    {
        "id": "bb07419030999df8",
        "type": "debug",
        "z": "0956d057442e3a8b",
        "name": "debug 2",
        "active": true,
        "tosidebar": true,
        "console": false,
        "tostatus": false,
        "complete": "payload",
        "targetType": "msg",
        "statusVal": "",
        "statusType": "auto",
        "x": 640,
        "y": 640,
        "wires": []
    }
]