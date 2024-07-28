# Rainpoint API Node-Red Flow - WIP
Thank you to https://github.com/Remboooo for making this possible

This Project is intended for someone with existing Home Assistant / Node-Red Experience

Requirements:
1. Home Assistant
2. Node-Red Addon, additional nodes
   - node-red-contrib-crypto-js
   - node-red-contrib-random-string
4. MQTT
5. Rainpoint Application (instead of Homegar):

   Logging in via this API will log you out in the app. It is advisable to create a separate API account from the app:
  - Log out from your main account
  - Create a new account
  - Log out and back into your main account
  - Invite your new account from 'Me' → 'Home management' → your home → 'Members'
  - Log out and back into your new account
  - Accept the invite
  - Make sure that you remove the default "home" that is created. Only the home with the sensors should remain in the 2nd accounts.

Setup
1. Install the Addtional Nodes
2. Import the JSON file into your Node-Red Instance
3. Update the following Nodes:
   - Credentials (Use new account created above) 
     - areaCode: Telephone Country Code, i.e. "27"
     - phoneOrEmail: email address
     - payload: password
     - count: 0
     - Set repeat for every 1 to 3 minutes
   - MQTT Out Discovery
     - Add your MQTT Server Details, including credentials
4. Deploy this flow.
5. Make sure that the following connect:
  - MQTT Out Discovery
  - MQTT Out State
6. The values will automatically be displayed using MQTT Auto Discovery, i.e. sensor.rainpoint_"sensor name"_variable

Supported Devices:
1. RainPoint Smart+ Soil & Moisture Sensor (HCS021FRF)
2. RainPoint Smart+ High Precision Rain Sensor (HCS012ARF)
3. RainPoint Smart+ Outdoor Air Humidity Sensor (HCS014ARF)
4. RainPoint Smart+ Water Flow Meter (HCS008FRF)
5. RainPoint Smart+ Smart Pool Thermometer (HCS0528ARF)
