<a name="module_sdlIna3221"></a>
## sdlIna3221
This module facilitates communication between a device host running the node.js mraa library
(such as an Intel Edison) and a SwitchDocLabs SunAirPlus over i2c. It should also be able
to be used for a INA3221 SwitchDoc Labs Breakout Board.

Based on the python library at https://github.com/switchdoclabs/SDL_Pi_INA3221

**Author:** Tom Luczak  
**License**: Apache-2.0  

* [sdlIna3221](#module_sdlIna3221)
  * [.SdlIna3221](#module_sdlIna3221.SdlIna3221)
    * [new exports.SdlIna3221(i2cBus, address, [debug], [config])](#new_module_sdlIna3221.SdlIna3221_new)
    * [.writeRegisterLittleEndian(register, data)](#module_sdlIna3221.SdlIna3221+writeRegisterLittleEndian)
    * [.readRegisterLittleEndian(register)](#module_sdlIna3221.SdlIna3221+readRegisterLittleEndian) ⇒ <code>number</code>
    * [.getBusVoltage_V(channel)](#module_sdlIna3221.SdlIna3221+getBusVoltage_V) ⇒ <code>number</code>
    * [.getSolarBusVoltage()](#module_sdlIna3221.SdlIna3221+getSolarBusVoltage) ⇒ <code>number</code>
    * [.getLipoBusVoltage()](#module_sdlIna3221.SdlIna3221+getLipoBusVoltage) ⇒ <code>number</code>
    * [.getOutputBusVoltage()](#module_sdlIna3221.SdlIna3221+getOutputBusVoltage) ⇒ <code>number</code>
    * [.getShuntVoltage_mV(channel)](#module_sdlIna3221.SdlIna3221+getShuntVoltage_mV) ⇒ <code>number</code>
    * [.getSolarShuntVoltage()](#module_sdlIna3221.SdlIna3221+getSolarShuntVoltage) ⇒ <code>number</code>
    * [.getLipoShuntVoltage()](#module_sdlIna3221.SdlIna3221+getLipoShuntVoltage) ⇒ <code>number</code>
    * [.getOutputShuntVoltage()](#module_sdlIna3221.SdlIna3221+getOutputShuntVoltage) ⇒ <code>number</code>
    * [.getCurrent_mA(channel)](#module_sdlIna3221.SdlIna3221+getCurrent_mA) ⇒ <code>number</code>
    * [.getSolarCurrent()](#module_sdlIna3221.SdlIna3221+getSolarCurrent) ⇒ <code>number</code>
    * [.getLipoCurrent()](#module_sdlIna3221.SdlIna3221+getLipoCurrent) ⇒ <code>number</code>
    * [.getOutputCurrent()](#module_sdlIna3221.SdlIna3221+getOutputCurrent) ⇒ <code>number</code>
    * [.setConfig([config])](#module_sdlIna3221.SdlIna3221+setConfig)
  * [.INA3221_ADDRESS](#module_sdlIna3221.INA3221_ADDRESS) : <code>number</code>
  * [.INA3221_READ](#module_sdlIna3221.INA3221_READ) : <code>number</code>
  * [.INA3221_REG_CONFIG](#module_sdlIna3221.INA3221_REG_CONFIG) : <code>number</code>
  * [.INA3221_CONFIG_RESET](#module_sdlIna3221.INA3221_CONFIG_RESET) : <code>number</code>
  * [.INA3221_CONFIG_ENABLE_CHAN1](#module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN1) : <code>number</code>
  * [.INA3221_CONFIG_ENABLE_CHAN2](#module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN2) : <code>number</code>
  * [.INA3221_CONFIG_ENABLE_CHAN3](#module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN3) : <code>number</code>
  * [.INA3221_CONFIG_AVG2](#module_sdlIna3221.INA3221_CONFIG_AVG2) : <code>number</code>
  * [.INA3221_CONFIG_AVG1](#module_sdlIna3221.INA3221_CONFIG_AVG1) : <code>number</code>
  * [.INA3221_CONFIG_AVG0](#module_sdlIna3221.INA3221_CONFIG_AVG0) : <code>number</code>
  * [.INA3221_CONFIG_VBUS_CT2](#module_sdlIna3221.INA3221_CONFIG_VBUS_CT2) : <code>number</code>
  * [.INA3221_CONFIG_VBUS_CT1](#module_sdlIna3221.INA3221_CONFIG_VBUS_CT1) : <code>number</code>
  * [.INA3221_CONFIG_VBUS_CT0](#module_sdlIna3221.INA3221_CONFIG_VBUS_CT0) : <code>number</code>
  * [.INA3221_CONFIG_VSH_CT2](#module_sdlIna3221.INA3221_CONFIG_VSH_CT2) : <code>number</code>
  * [.INA3221_CONFIG_VSH_CT1](#module_sdlIna3221.INA3221_CONFIG_VSH_CT1) : <code>number</code>
  * [.INA3221_CONFIG_VSH_CT0](#module_sdlIna3221.INA3221_CONFIG_VSH_CT0) : <code>number</code>
  * [.INA3221_CONFIG_MODE_2](#module_sdlIna3221.INA3221_CONFIG_MODE_2) : <code>number</code>
  * [.INA3221_CONFIG_MODE_1](#module_sdlIna3221.INA3221_CONFIG_MODE_1) : <code>number</code>
  * [.INA3221_CONFIG_MODE_0](#module_sdlIna3221.INA3221_CONFIG_MODE_0) : <code>number</code>
  * [.INA3221_REG_SHUNTVOLTAGE_1](#module_sdlIna3221.INA3221_REG_SHUNTVOLTAGE_1) : <code>number</code>
  * [.INA3221_REG_BUSVOLTAGE_1](#module_sdlIna3221.INA3221_REG_BUSVOLTAGE_1) : <code>number</code>
  * [.SHUNT_RESISTOR_VALUE](#module_sdlIna3221.SHUNT_RESISTOR_VALUE) : <code>number</code>
  * [.LIPO_BATTERY_CHANNEL](#module_sdlIna3221.LIPO_BATTERY_CHANNEL) : <code>number</code>
  * [.SOLAR_CELL_CHANNEL](#module_sdlIna3221.SOLAR_CELL_CHANNEL) : <code>number</code>
  * [.OUTPUT_CHANNEL](#module_sdlIna3221.OUTPUT_CHANNEL) : <code>number</code>

<a name="module_sdlIna3221.SdlIna3221"></a>
### sdlIna3221.SdlIna3221
**Kind**: static class of <code>[sdlIna3221](#module_sdlIna3221)</code>  

* [.SdlIna3221](#module_sdlIna3221.SdlIna3221)
  * [new exports.SdlIna3221(i2cBus, address, [debug], [config])](#new_module_sdlIna3221.SdlIna3221_new)
  * [.writeRegisterLittleEndian(register, data)](#module_sdlIna3221.SdlIna3221+writeRegisterLittleEndian)
  * [.readRegisterLittleEndian(register)](#module_sdlIna3221.SdlIna3221+readRegisterLittleEndian) ⇒ <code>number</code>
  * [.getBusVoltage_V(channel)](#module_sdlIna3221.SdlIna3221+getBusVoltage_V) ⇒ <code>number</code>
  * [.getSolarBusVoltage()](#module_sdlIna3221.SdlIna3221+getSolarBusVoltage) ⇒ <code>number</code>
  * [.getLipoBusVoltage()](#module_sdlIna3221.SdlIna3221+getLipoBusVoltage) ⇒ <code>number</code>
  * [.getOutputBusVoltage()](#module_sdlIna3221.SdlIna3221+getOutputBusVoltage) ⇒ <code>number</code>
  * [.getShuntVoltage_mV(channel)](#module_sdlIna3221.SdlIna3221+getShuntVoltage_mV) ⇒ <code>number</code>
  * [.getSolarShuntVoltage()](#module_sdlIna3221.SdlIna3221+getSolarShuntVoltage) ⇒ <code>number</code>
  * [.getLipoShuntVoltage()](#module_sdlIna3221.SdlIna3221+getLipoShuntVoltage) ⇒ <code>number</code>
  * [.getOutputShuntVoltage()](#module_sdlIna3221.SdlIna3221+getOutputShuntVoltage) ⇒ <code>number</code>
  * [.getCurrent_mA(channel)](#module_sdlIna3221.SdlIna3221+getCurrent_mA) ⇒ <code>number</code>
  * [.getSolarCurrent()](#module_sdlIna3221.SdlIna3221+getSolarCurrent) ⇒ <code>number</code>
  * [.getLipoCurrent()](#module_sdlIna3221.SdlIna3221+getLipoCurrent) ⇒ <code>number</code>
  * [.getOutputCurrent()](#module_sdlIna3221.SdlIna3221+getOutputCurrent) ⇒ <code>number</code>
  * [.setConfig([config])](#module_sdlIna3221.SdlIna3221+setConfig)

<a name="new_module_sdlIna3221.SdlIna3221_new"></a>
#### new exports.SdlIna3221(i2cBus, address, [debug], [config])
SunDocLabs INA3221 object


| Param | Type | Description |
| --- | --- | --- |
| i2cBus | <code>number</code> | i2c Bus Number |
| address | <code>number</code> | i2c address |
| [debug] | <code>boolean</code> | log reads and writes to console |
| [config] | <code>number</code> | configuration word |

<a name="module_sdlIna3221.SdlIna3221+writeRegisterLittleEndian"></a>
#### sdlIna3221.writeRegisterLittleEndian(register, data)
Write a word of big endian data direct to register

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  

| Param | Type | Description |
| --- | --- | --- |
| register | <code>number</code> | register to write to |
| data | <code>number</code> | word of data |

<a name="module_sdlIna3221.SdlIna3221+readRegisterLittleEndian"></a>
#### sdlIna3221.readRegisterLittleEndian(register) ⇒ <code>number</code>
Read a word of big endian data from register

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - word of data converted to big endian  

| Param | Type | Description |
| --- | --- | --- |
| register | <code>number</code> | register to write to |

<a name="module_sdlIna3221.SdlIna3221+getBusVoltage_V"></a>
#### sdlIna3221.getBusVoltage_V(channel) ⇒ <code>number</code>
Read bus voltage from a given channel

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - word of data converted to big endian  

| Param | Type | Description |
| --- | --- | --- |
| channel | <code>number</code> | channel to read from |

<a name="module_sdlIna3221.SdlIna3221+getSolarBusVoltage"></a>
#### sdlIna3221.getSolarBusVoltage() ⇒ <code>number</code>
Read solar bus voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - Voltage in Volts  
<a name="module_sdlIna3221.SdlIna3221+getLipoBusVoltage"></a>
#### sdlIna3221.getLipoBusVoltage() ⇒ <code>number</code>
Read lipo bus voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - Voltage in Volts  
<a name="module_sdlIna3221.SdlIna3221+getOutputBusVoltage"></a>
#### sdlIna3221.getOutputBusVoltage() ⇒ <code>number</code>
Read output bus voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - Voltage in Volts  
<a name="module_sdlIna3221.SdlIna3221+getShuntVoltage_mV"></a>
#### sdlIna3221.getShuntVoltage_mV(channel) ⇒ <code>number</code>
Read shunt voltage from a given channel

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - shunt voltage in mV  

| Param | Type | Description |
| --- | --- | --- |
| channel | <code>number</code> | channel to read from |

<a name="module_sdlIna3221.SdlIna3221+getSolarShuntVoltage"></a>
#### sdlIna3221.getSolarShuntVoltage() ⇒ <code>number</code>
Read solar shunt voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - shunt voltage in mV  
<a name="module_sdlIna3221.SdlIna3221+getLipoShuntVoltage"></a>
#### sdlIna3221.getLipoShuntVoltage() ⇒ <code>number</code>
Read lipo shunt voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - shunt voltage in mV  
<a name="module_sdlIna3221.SdlIna3221+getOutputShuntVoltage"></a>
#### sdlIna3221.getOutputShuntVoltage() ⇒ <code>number</code>
Read output shunt voltage from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - shunt voltage in mV  
<a name="module_sdlIna3221.SdlIna3221+getCurrent_mA"></a>
#### sdlIna3221.getCurrent_mA(channel) ⇒ <code>number</code>
Read current from a given channel

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - current in mV  

| Param | Type | Description |
| --- | --- | --- |
| channel | <code>number</code> | channel to read from |

<a name="module_sdlIna3221.SdlIna3221+getSolarCurrent"></a>
#### sdlIna3221.getSolarCurrent() ⇒ <code>number</code>
Read solar current from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - current in mA  
<a name="module_sdlIna3221.SdlIna3221+getLipoCurrent"></a>
#### sdlIna3221.getLipoCurrent() ⇒ <code>number</code>
Read lipo current from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - current in mA  
<a name="module_sdlIna3221.SdlIna3221+getOutputCurrent"></a>
#### sdlIna3221.getOutputCurrent() ⇒ <code>number</code>
Read output current from SunAirPlus

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  
**Returns**: <code>number</code> - - current in mA  
<a name="module_sdlIna3221.SdlIna3221+setConfig"></a>
#### sdlIna3221.setConfig([config])
Sets and writes configuration

**Kind**: instance method of <code>[SdlIna3221](#module_sdlIna3221.SdlIna3221)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [config] | <code>number</code> | configuration word |

<a name="module_sdlIna3221.INA3221_ADDRESS"></a>
### sdlIna3221.INA3221_ADDRESS : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x40</code>  
<a name="module_sdlIna3221.INA3221_READ"></a>
### sdlIna3221.INA3221_READ : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x01</code>  
<a name="module_sdlIna3221.INA3221_REG_CONFIG"></a>
### sdlIna3221.INA3221_REG_CONFIG : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x00</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_RESET"></a>
### sdlIna3221.INA3221_CONFIG_RESET : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x8000</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN1"></a>
### sdlIna3221.INA3221_CONFIG_ENABLE_CHAN1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x4000</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN2"></a>
### sdlIna3221.INA3221_CONFIG_ENABLE_CHAN2 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x2000</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_ENABLE_CHAN3"></a>
### sdlIna3221.INA3221_CONFIG_ENABLE_CHAN3 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x1000</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_AVG2"></a>
### sdlIna3221.INA3221_CONFIG_AVG2 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0800</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_AVG1"></a>
### sdlIna3221.INA3221_CONFIG_AVG1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0400</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_AVG0"></a>
### sdlIna3221.INA3221_CONFIG_AVG0 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0200</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VBUS_CT2"></a>
### sdlIna3221.INA3221_CONFIG_VBUS_CT2 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0100</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VBUS_CT1"></a>
### sdlIna3221.INA3221_CONFIG_VBUS_CT1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0080</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VBUS_CT0"></a>
### sdlIna3221.INA3221_CONFIG_VBUS_CT0 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0040</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VSH_CT2"></a>
### sdlIna3221.INA3221_CONFIG_VSH_CT2 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0020</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VSH_CT1"></a>
### sdlIna3221.INA3221_CONFIG_VSH_CT1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0010</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_VSH_CT0"></a>
### sdlIna3221.INA3221_CONFIG_VSH_CT0 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0008</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_MODE_2"></a>
### sdlIna3221.INA3221_CONFIG_MODE_2 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0004</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_MODE_1"></a>
### sdlIna3221.INA3221_CONFIG_MODE_1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0002</code>  
<a name="module_sdlIna3221.INA3221_CONFIG_MODE_0"></a>
### sdlIna3221.INA3221_CONFIG_MODE_0 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x0001</code>  
<a name="module_sdlIna3221.INA3221_REG_SHUNTVOLTAGE_1"></a>
### sdlIna3221.INA3221_REG_SHUNTVOLTAGE_1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x01</code>  
<a name="module_sdlIna3221.INA3221_REG_BUSVOLTAGE_1"></a>
### sdlIna3221.INA3221_REG_BUSVOLTAGE_1 : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0x02</code>  
<a name="module_sdlIna3221.SHUNT_RESISTOR_VALUE"></a>
### sdlIna3221.SHUNT_RESISTOR_VALUE : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>0.1</code>  
<a name="module_sdlIna3221.LIPO_BATTERY_CHANNEL"></a>
### sdlIna3221.LIPO_BATTERY_CHANNEL : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>1</code>  
<a name="module_sdlIna3221.SOLAR_CELL_CHANNEL"></a>
### sdlIna3221.SOLAR_CELL_CHANNEL : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>2</code>  
<a name="module_sdlIna3221.OUTPUT_CHANNEL"></a>
### sdlIna3221.OUTPUT_CHANNEL : <code>number</code>
**Kind**: static constant of <code>[sdlIna3221](#module_sdlIna3221)</code>  
**Default**: <code>3</code>  
