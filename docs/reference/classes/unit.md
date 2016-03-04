<a name="Unit"></a>
## Unit
* [new Unit([value], [name])](#new_Unit_new)
* _instance_
	* [.valueOf](#Unit+valueOf) ⇒ <code>string</code>
	* [.clone()](#Unit+clone) ⇒ <code>[Unit](#Unit)</code>
	* [._isDerived()](#Unit+_isDerived) ⇒ <code>boolean</code>
	* [.hasBase(base)](#Unit+hasBase)
	* [.equalBase(other)](#Unit+equalBase) ⇒ <code>boolean</code>
	* [.equals(other)](#Unit+equals) ⇒ <code>boolean</code>
	* [.multiply(other)](#Unit+multiply) ⇒ <code>[Unit](#Unit)</code>
	* [.divide(other)](#Unit+divide) ⇒ <code>[Unit](#Unit)</code>
	* [.pow(p)](#Unit+pow) ⇒ <code>[Unit](#Unit)</code>
	* [.abs(x)](#Unit+abs) ⇒ <code>[Unit](#Unit)</code>
	* [.to(valuelessUnit)](#Unit+to) ⇒ <code>[Unit](#Unit)</code>
	* [.toNumber(valuelessUnit)](#Unit+toNumber) ⇒ <code>number</code>
	* [.toNumeric(valuelessUnit)](#Unit+toNumeric) ⇒ <code>number</code> &#124; <code>BigNumber</code> &#124; <code>Fraction</code>
	* [.toString()](#Unit+toString) ⇒ <code>string</code>
	* [.toJSON()](#Unit+toJSON) ⇒ <code>Object</code>
	* [.formatUnits()](#Unit+formatUnits) ⇒ <code>string</code>
	* [.format([options])](#Unit+format) ⇒ <code>string</code>
* _static_
	* [.parse(str)](#Unit.parse) ⇒ <code>[Unit](#Unit)</code>
	* [.isValuelessUnit(name)](#Unit.isValuelessUnit) ⇒ <code>boolean</code>
	* [.fromJSON(json)](#Unit.fromJSON) ⇒ <code>[Unit](#Unit)</code>

<a name="new_Unit_new"></a>
### new Unit([value], [name])
A unit can be constructed in the following ways:


| Param | Type | Description |
| --- | --- | --- |
| [value] | <code>number</code> &#124; <code>BigNumber</code> &#124; <code>Fraction</code> &#124; <code>Complex</code> &#124; <code>boolean</code> | A value like 5.2 |
| [name] | <code>string</code> | A unit name like "cm" or "inch", or a derived unit of the form: "u1[^ex1] [u2[^ex2] ...] [/ u3[^ex3] [u4[^ex4]]]", such as "kg m^2/s^2", where each unit appearing after the forward slash is taken to be in the denominator. "kg m^2 s^-2" is a synonym and is also acceptable. Any of the units can include a prefix. |

<a name="Unit+valueOf"></a>
### unit.valueOf ⇒ <code>string</code>
Returns the string representation of the unit.

**Kind**: instance property of <code>[Unit](#Unit)</code>  
<a name="Unit+clone"></a>
### unit.clone() ⇒ <code>[Unit](#Unit)</code>
create a copy of this unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - Returns a cloned version of the unit  
<a name="Unit+_isDerived"></a>
### unit._isDerived() ⇒ <code>boolean</code>
Return whether the unit is derived (such as m/s, or cm^2, but not N)

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>boolean</code> - True if the unit is derived  
<a name="Unit+hasBase"></a>
### unit.hasBase(base)
check if this unit has given base unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  

| Param | Type |
| --- | --- |
| base | <code>BASE_UNITS</code> &#124; <code>STRING</code> &#124; <code>undefined</code> | 

<a name="Unit+equalBase"></a>
### unit.equalBase(other) ⇒ <code>boolean</code>
Check if this unit has a base or bases equal to another base or bases

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>boolean</code> - true if equal base  

| Param | Type |
| --- | --- |
| other | <code>[Unit](#Unit)</code> | 

<a name="Unit+equals"></a>
### unit.equals(other) ⇒ <code>boolean</code>
Check if this unit equals another unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>boolean</code> - true if both units are equal  

| Param | Type |
| --- | --- |
| other | <code>[Unit](#Unit)</code> | 

<a name="Unit+multiply"></a>
### unit.multiply(other) ⇒ <code>[Unit](#Unit)</code>
Multiply this unit with another one

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - product of this unit and the other unit  

| Param | Type |
| --- | --- |
| other | <code>[Unit](#Unit)</code> | 

<a name="Unit+divide"></a>
### unit.divide(other) ⇒ <code>[Unit](#Unit)</code>
Divide this unit by another one

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - result of dividing this unit by the other unit  

| Param | Type |
| --- | --- |
| other | <code>[Unit](#Unit)</code> | 

<a name="Unit+pow"></a>
### unit.pow(p) ⇒ <code>[Unit](#Unit)</code>
Calculate the power of a unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - The result: this^p  

| Param | Type |
| --- | --- |
| p | <code>number</code> &#124; <code>Fraction</code> &#124; <code>BigNumber</code> | 

<a name="Unit+abs"></a>
### unit.abs(x) ⇒ <code>[Unit](#Unit)</code>
Calculate the absolute value of a unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - The result: |x|, absolute value of x  

| Param | Type |
| --- | --- |
| x | <code>number</code> &#124; <code>Fraction</code> &#124; <code>BigNumber</code> | 

<a name="Unit+to"></a>
### unit.to(valuelessUnit) ⇒ <code>[Unit](#Unit)</code>
Convert the unit to a specific unit name.

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - Returns a clone of the unit with a fixed prefix and unit.  

| Param | Type | Description |
| --- | --- | --- |
| valuelessUnit | <code>string</code> &#124; <code>[Unit](#Unit)</code> | A unit without value. Can have prefix, like "cm" |

<a name="Unit+toNumber"></a>
### unit.toNumber(valuelessUnit) ⇒ <code>number</code>
Return the value of the unit when represented with given valueless unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>number</code> - Returns the unit value as number.  

| Param | Type | Description |
| --- | --- | --- |
| valuelessUnit | <code>string</code> &#124; <code>[Unit](#Unit)</code> | For example 'cm' or 'inch' |

<a name="Unit+toNumeric"></a>
### unit.toNumeric(valuelessUnit) ⇒ <code>number</code> &#124; <code>BigNumber</code> &#124; <code>Fraction</code>
Return the value of the unit in the original numeric type

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>number</code> &#124; <code>BigNumber</code> &#124; <code>Fraction</code> - Returns the unit value  

| Param | Type | Description |
| --- | --- | --- |
| valuelessUnit | <code>string</code> &#124; <code>[Unit](#Unit)</code> | For example 'cm' or 'inch' |

<a name="Unit+toString"></a>
### unit.toString() ⇒ <code>string</code>
Get a string representation of the unit.

**Kind**: instance method of <code>[Unit](#Unit)</code>  
<a name="Unit+toJSON"></a>
### unit.toJSON() ⇒ <code>Object</code>
Get a JSON representation of the unit

**Kind**: instance method of <code>[Unit](#Unit)</code>  
**Returns**: <code>Object</code> - Returns a JSON object structured as:
<a name="Unit+formatUnits"></a>
### unit.formatUnits() ⇒ <code>string</code>
Get a string representation of the units of this Unit, without the value.

**Kind**: instance method of <code>[Unit](#Unit)</code>  
<a name="Unit+format"></a>
### unit.format([options]) ⇒ <code>string</code>
Get a string representation of the Unit, with optional formatting options.

**Kind**: instance method of <code>[Unit](#Unit)</code>  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>Object</code> &#124; <code>number</code> &#124; <code>function</code> | Formatting options. See                                                lib/utils/number:format for a                                                description of the available                                                options. |

<a name="Unit.parse"></a>
### Unit.parse(str) ⇒ <code>[Unit](#Unit)</code>
Parse a string into a unit. The value of the unit is parsed as number,

**Kind**: static method of <code>[Unit](#Unit)</code>  
**Returns**: <code>[Unit](#Unit)</code> - unit  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | A string like "5.2 inch", "4e2 cm/s^2" |

<a name="Unit.isValuelessUnit"></a>
### Unit.isValuelessUnit(name) ⇒ <code>boolean</code>
Test if the given expression is a unit.

**Kind**: static method of <code>[Unit](#Unit)</code>  
**Returns**: <code>boolean</code> - true if the given string is a unit  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | A string to be tested whether it is a value less unit.                        The unit can have prefix, like "cm" |

<a name="Unit.fromJSON"></a>
### Unit.fromJSON(json) ⇒ <code>[Unit](#Unit)</code>
Instantiate a Unit from a JSON object

**Kind**: static method of <code>[Unit](#Unit)</code>  

| Param | Type | Description |
| --- | --- | --- |
| json | <code>Object</code> | A JSON object structured as:                       `{"mathjs": "Unit", "value": 2, "unit": "cm", "fixPrefix": false}` |
