# TC903 Schneider basic control

## Eco mode
- Cooling mode
  - set-point = 26 c
  - Fan speed = low
- Heating mode
  - Set-point = 18 c
  - Fan speed = low
 
## Low temperature protection
- Room temp < 5 c
  - Operation Mode = Heating mode
  - Fan speed = high
  - continue until room temp = 7 c
    - stop output

## Alert
- When event of an operating exception happend
  - command valve to close
  - set device to inoperative state
- Alert condition
  - EEPROM: `EE`
  - Temp sensor short-circuit: `E1`
  - Temp sensor open-circuit: `E2`
  - Ambient temp > 50 c: `HI`
  - Ambient temp < 0 c: `LO`
 
## Fan speed
- Auto speed
  - ∓ 1 c: `low`
  - ∓ 2 c: `medium`
  - ∓ 3 c: `high`
 
## 4-Pipe control (Heat / Cool)
- Cooling mode
  - Room temp > SP by 1: open valve (0-10 VDC AO)
  - Room temp <= SP: close valve (0-10 VDC AO)
- Heating mode
  - Room temp < SP by 1: open valve (0-10 VDC AO)
  - Room temp >= SP: close valve (0-10 VDC AO)
 
## Energy Saving Mode
- Cooling mode
  - Temp SP: 26 c
  - Fan speed: low
- Heating mode
  - Temp SP: 18 c
  - Fan speed: low
 
## Unoccupied Energy Saving Mode
- Use hotel room key card or bioprobe
  - `ECO` and `Unoccupied` icon display
    - Cooling mode
      - Temp SP: 28 c
      - Fan speed: low
    - Heating mode
      - Temp SP: 16 c
      - Fan speed: low
     
## Sleep Energy Saving Mode
- 12AM
  - Sleep energy saving mode turn on && `Override` icon displays at 1AM
    - Temp SP increase/decrease every hour by 1 c until 3AM
  - EX
    - Cooling mode
      - SP + 1 c every hour until 3AM (Max at 26 c)
      - 3AM onward SP - 1 c until original SP is met at 7AM
    - Heating mode
      - SP - 1 c every hour until 3AM (Max at 16 c)
      - 3AM onward SP + 1 c until original SP is met at 7AM
