# API

<!-- https://dev.bostondynamics.com/docs/concepts/choreography/choreography_in_tablet.html -->

The back end exposes a number of API endpoints which are referenced in the table below.

| Method | Endpoint             | Authentication     | POST JSON Body                                                                                                                                                                                                                     | Info                                                                                    |
| ------ | -------------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| GET    | /rest/features       | `NONE_REQUIRED`    | none                                                                                                                                                                                                                               | Tells the client which features of the UI should be use                                 |
| GET    | /rest/apStatus       | `IS_AUTHENTICATED` | none                                                                                                                                                                                                                               | Current AP status and client information                                                |
| GET    | /rest/apSettings     | `IS_ADMIN`         | none                                                                                                                                                                                                                               | Current AP settings                                                                     |
| POST   | /rest/apSettings     | `IS_ADMIN`         | `{"provision_mode": 1,"ssid": "ESP32-SvelteKit-e89f6d20372c","password": "esp-sveltekit","channel": 1,"ssid_hidden": false,"max_clients": 4,"local_ip": "192.168.4.1","gateway_ip": "192.168.4.1","subnet_mask": "255.255.255.0"}` | Update AP settings                                                                      |
| GET    | /rest/wifiStatus     | `IS_AUTHENTICATED` | none                                                                                                                                                                                                                               | Current status of the wifi client connection                                            |
| GET    | /rest/scanNetworks   | `IS_ADMIN`         | none                                                                                                                                                                                                                               | Async Scan for Networks in Range                                                        |
| GET    | /rest/listNetworks   | `IS_ADMIN`         | none                                                                                                                                                                                                                               | List networks in range after successful scanning. Otherwise triggers scanning.          |
| GET    | /rest/wifiSettings   | `IS_ADMIN`         | none                                                                                                                                                                                                                               | Current WiFi settings                                                                   |
| POST   | /rest/wifiSettings   | `IS_ADMIN`         | `{"hostname":"esp32-f412fa4495f8","priority_RSSI":true,"wifi_networks":[{"ssid":"YourSSID","password":"YourPassword","static_ip_config":false}]}`                                                                                  | Update WiFi settings and credentials                                                    |
| GET    | /rest/systemStatus   | `IS_AUTHENTICATED` | none                                                                                                                                                                                                                               | Get system information about the ESP.                                                   |
| POST   | /rest/restart        | `IS_ADMIN`         | none                                                                                                                                                                                                                               | Restart the ESP32                                                                       |
| POST   | /rest/factoryReset   | `IS_ADMIN`         | none                                                                                                                                                                                                                               | Reset the ESP32 and all settings to their default values                                |
| POST   | /rest/uploadFirmware | `IS_ADMIN`         | none                                                                                                                                                                                                                               | File upload of firmware.bin                                                             |
| POST   | /rest/sleep          | `IS_AUTHENTICATED` | none                                                                                                                                                                                                                               | Puts the device in deep sleep mode                                                      |
| POST   | /rest/downloadUpdate | `IS_ADMIN`         | `{"download_url": "https://github.com/theelims/ESP32-sveltekit/releases/download/v0.1.0/firmware_esp32s3.bin"}`                                                                                                                    | Download link for OTA. This requires a valid SSL certificate and will follow redirects. |

<!-- | HTTP Method | Endpoint       | Description                | Parameters                |
|-------------|----------------|----------------------------|---------------------------|
| GET         | /api/sensor/mpu       | Retrieve the mpu state |                       |
| GET         | /api/sensor/magnetometer       | Retrieve the magnetometer state |                       |
| GET         | /api/sensor/distances       | Retrieve the distances state |                      |
| GET         | /api/sensor/distance/{position}       | Retrieve the distance state |    `position`: The position of the distance sensor **LEFT** and **RIGHT**                    |
| GET         | /api/sensor/stream    | Retrieve the camera stream  | |
| GET         | /api/actuator    | Retrieve the actuator states  | |
| GET         | /api/actuator/{id}    | Retrieve the actuator state for `id`  | `id`: The ID of the actuator |
| POST        | /api/actuator/{id}    | Set the actuator state  | `id`: The ID of the actuator|
| GET         | /api/kinematics/feet    | Retrieve the current feet positions as (x, y, z) coordinates|                           |
| GET         | /api/kinematics/body    | Retrieve the current body position as a (x, y, z) coordinates|                           |
| GET         | /api/kinematics/bodystate    | Retrieve the current body and feet positions |                           |
| GET         | /api/system/log    | Retrieve the system log  | |
| GET         | /api/system/info    | Retrieve the system information  | |
| GET         | /api/system/settings    | Retrieve the system settings  | |
| POST        | /api/system/settings    | Set the system settings  | |
| POST        | /api/system/reset    | Reset system  | |
| POST        | /api/system/power/off    | Power of the system  | |
| POST        | /api/system/stop    | Stop power to actuators  | `id`: The stop level **CUT**, **SETTLE_THEN_CUT**, **NONE** | -->
