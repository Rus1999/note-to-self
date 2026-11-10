# Modbus RTU Communication

## Raw Data meaning

<img width="745" height="695" alt="image" src="https://github.com/user-attachments/assets/bf1fd6b1-2ffe-48f9-99d2-d74d56192dd6" />

### Request message in HEX

`01 03 00 04 00 02 85 CA`

`01` : Device ID (Slave / Server) <br>
`03` : Function code (Read holding register) <br>
`00 04` : Starting address <br>
`00 02` : Number of reg to read <br>
`85 CA` : CRC check <br>

### Response message in HEX
`01 03 04 01 5E 00 03 DA 1C`

`01` : Device ID <br>
`03` : Function code (Read holding register) <br>
`04` : Data in bytes reponse back <br>
`01 5E` : 350 in Dec (Setpoint temp) <br>
`00 03` : Fan mode (03 = auto) <br>
`DA 1C` : CRC check <br>
