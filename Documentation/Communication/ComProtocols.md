# Protocoles de communication
## SPI (Serial Peripheral Interface)
### Nomenclature
#### PINS
##### Clock
| Nom   | Signification |
| ----- | ------------- |
| CLK   | Clock         |
| SCK   | Serial Clock  |

##### Data Transfer (Full-Duplex)
###### Output
| Nom   | Signification                |
| ----- | ---------------------------- |
| SDO   | Serial Data Out              |
| MOSI  | Master Out Slave In          |
| COPI  | Controller Out Peripheral In |
###### Input
| Nom   | Signification                |
| ----- | ---------------------------- |
| SDI   | Serial Data In               |
| MISO  | Master In Slave Out          |
| CIPO  | Controller In Peripheral Out |

##### Data Transfer (Half-Duplex)
| Nom   | Signification      |
| ----- | ------------------ |
| SIO   | Serial In/Out      |
| SDIO  | Serial Data In/Out |

##### Chip Select
| Nom   | Signification |
| ----- | ------------- |
| CS    | Chip Select   |
| SS    | Slave Select  |

#### Modes
| Nom   | Signification  |
| ----- | -------------- |
| CPOL  | Clock Polarity |
| CPHA  | Clock Phase    |

### Modes d'opération
#### Full-Duplex
