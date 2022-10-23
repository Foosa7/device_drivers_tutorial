
# BMP280 Arduino Library

## Datasheet
1. [BMP280](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmp280-ds001.pdf)

## Measurements
#### Pressure: 3.3.1
1. XLSB data register 0xF9 has the pressure output
2. Enable or disable oversampling pressure osrs_p[2:0] at 0xF4: 
3. Table 4: osrs_p settings 
4. More info chapter: 3.4. 

#### Temprature: 3.3.2
1. XLSB data register 0xFC has the pressure output
2. Enable or disable oversampling pressure osrs_t[2:0] at 0xF4: 
3. Table 5: osrs_t settings
4. More info chapter: 3.5. 

### Filters
IIR Filter: 3.3.3
1. Configured using filter[2:0] bits in control register 0xF5 
2. Table 6: filter settings

#### IIR Filter selection: 3.4
1. Table 7: Recommended filter settings based on use cases

#### Noise: 3.5
1. Table 8: Noise in pressure
2. Table 9: Noise in temperature

## Modes
#### Power modes: 3.6
1. Table 10: mode settings

#### Sleep mode: 3.6.1
1. Set by default after power on reset

#### Forced mode: 
1. Single measurement is performed.
2. When the measurement is finished, the sensor returns to sleep mode 
3. Measurement results can be obtained from the data registers
4. Measurement rate depends on osrs_t and osrs_p
5. Table 13: Measurement time

#### Normal mode:
1. Continuously cycles between active measurement period and an standby period
2. Defined by tstandby:  t_sb[2:0] bits in control register 0xF5 
3. Table 11: t_sb settings
4. Measurement rate depends on osrs_t and osrs_p and the standby time tstandby
5. Table 14: typical output data Rate (ODR) in normal mode [Hz]



