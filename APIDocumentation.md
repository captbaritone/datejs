**NOTE:** [DateJS](http://datejs.com/) has moved to a new home on [GitHub](http://github.com/datejs/)

# Public Static Methods #

---


## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) today ##
> ### Date.today () : `Date` ###

> Gets a date that is set to the current date. The time is set to the start of the day (00:00 or 12:00 AM).

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    The current date.

> #### Example ####
```
Date.today(); // Equivalent to new Date().clearTime()
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) compare ##
> ### Date.compare ( `Date` date1, `Date` date2 ) : `Number` ###

> Compares the first date to the second date and returns an number indication of their relative values. -1 = this is lessthan date. 0 = values are equal. 1 = this is greaterthan date.

> #### Parameters ####

  * {`Date` date1}     First Date object to compare. **required**
  * {`Date` date2}     Second Date object to compare to. **required**

> #### Return Value ####

> {`Number`}  -1 = date1 is _lessthan_ date2. 0 = values are _equal_. 1 = date1 is _greaterthan_ date2.

> #### Example ####
```
var today = Date.today();
var past = Date.today().add(-6).days();
var future = Date.today().add(6).days();


Date.compare(today, future);                    // -1
Date.compare(today, new Date().clearTime());    // 0
Date.compare(today, past)                       // 1
```

> #### See Also ####
  * [between](APIDocumentation#between.md)
  * [compareTo](APIDocumentation#compareTo.md)
  * [equals](APIDocumentation#equals.md)
  * [isAfter](APIDocumentation#isAfter.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) equals ##
> ### Date.equals ( `Date` date1, `Date` date2 ) : `Boolean` ###

> Compares the first Date object to the second Date object and returns true if they are equal.

> #### Parameters ####

  * {`Date` date1}     First Date object to compare. **required**
  * {`Date` date2}     Second Date object to compare to **required**

> #### Return Value ####

> {`Boolean`} true if dates are equal. false if they are not equal.

> #### Example ####
```
Date.equals(Date.today(), new Date().clearTime());   // true

var d1 = Date.today();
var d2 = Date.today().addHours(5);
var d3 = new Date().clearTime();
var d4 = "foo";

Date.equals(d1, d2);  // false
Date.equals(d1, d3);  // true
Date.equals(d1, d4);  // throws exception
```

> #### See Also ####
  * [between](APIDocumentation#between.md)
  * [compareTo](APIDocumentation#compareTo.md)
  * [equals](APIDocumentation#equals.md)
  * [isAfter](APIDocumentation#isAfter.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getDayNumberFromName ##
> ### Date.getDayNumberFromName ( `String` dayName ) : `Number` ###

> Gets the day number (0-6) if given a [culture-specific](CultureInfo.md) string which is a valid full or abbreviated day name.

> #### Parameters ####

  * {`String` dayName}     The name of the day (eg. "Monday, "Mon", "tuesday", "tue", "We", "we").

> #### Return Value ####

> {`Number`}  The day number

> #### Example ####
```
Date.getDayNumberFromName('Tuesday'); // 2
Date.getDayNumberFromName('sat');     // 6
Date.getDayNumberFromName('SUNDAY');     // 0
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getMonthNumberFromName ##
> ### Date.getMonthNumberFromName ( `String` monthName ) : `Number` ###

> Gets the month number (0-11) if given a [culture-specific](CultureInfo.md) string which is a valid full or abbreviated month name.

> #### Parameters ####

  * {`String` monthName}   The name of the month (eg. "February, "Feb", "october", "oct").

> #### Return Value ####

> {`Number`}  The month number

> #### Example ####
```
Date.getMonthNumberFromName('January'); // 0
Date.getMonthNumberFromName('feb');  // 1
Date.getMonthNumberFromName('July'); // 6
Date.getMonthNumberFromName('DECEMBER'); // 11
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) isLeapYear ##
> ### Date.isLeapYear ( `Number` year ) : `Boolean` ###

> Returns true if the given year is a leap year, false otherwise.

> #### Parameters ####

  * {`Number` year}   The year.

> #### Return Value ####

> {`Boolean`} true if date is within a LeapYear, otherwise false.

> #### Example ####
```
Date.isLeapYear(Date.today().getFullYear()); // true|false
var date = new Date(2008,1,29);
Date.isLeapYear(date.getFullYear);           // true
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getDaysInMonth ##
> ### Date.getDaysInMonth ( `Number` year, `Number` month ) : `Number` ###

> Gets the number of days in the month, given a year and month value. Automatically corrects for leap year.

> #### Parameters ####

  * {`Number` year}   The year.
  * {`Number` month}   The month (0-11).

> #### Return Value ####

> {`Number`}  The number of days in the month.

> #### Example ####
```
Date.getDaysInMonth(2008, 1);  // 29
Date.getDaysInMonth(2007, 10); // 30
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getTimezoneAbbreviation ##
> ### Date.getTimezoneAbbreviation ( `Number` timezoneOffset, `Boolean` isDayLightSavingsTime ) : `String` ###

> Returns a [culture-specific](CultureInfo.md) timezone abbreviation based on a given offset and a boolean indicating whether daylight savings time is in effect.

> #### Parameters ####

  * {`Number` timezoneOffset}   The year.
  * {`Boolean` isDayLightSavingsTime}   Whether the date instance is observing Daylight Saving Time (Summer Time)

> #### Return Value ####

> {`String`}  The timezone abbreviation

> #### Example ####
```
var today = Date.today();
Date.getTimezoneAbbreviation(today.getTimezoneOffset, today.isDayLightSavingsTime()); // "UTC", "GMT", "EST", "PDT", etc.
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getTimezoneOffset ##
> ### Date.getTimezoneOffset ( `String` timezoneAbbreviation, `Boolean` isDayLightSavingsTime ) : `Number` ###

> Gets the timezone offset if given a [culture-specific](CultureInfo.md) string which is a valid full or abbreviated timezone name and a boolean indicating whether daylight savings time is in effect.

> #### Parameters ####

  * {`Number` timezoneAbbreviation}   The timezone abbreviation
  * {`Boolean` isDayLightSavingsTime}   Whether the date instance is observing Daylight Saving Time (Summer Time)

> #### Return Value ####

> {`String`}  The timezone abbreviation

> #### Example ####
```
Date.getTimezoneOffset("PST", true);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) parse ##
> ### Date.parse ( `String` dateString ) : `Date` ###

> Converts the specified string value into its JavaScript Date equivalent using [culture-specific](CultureInfo.md) format information.

> #### Parameters ####

  * {`String` dateString}   The string value to convert into a Date object. **required**

> #### Return Value ####

> {`Date`}    A Date object or null if the string cannot be converted into a Date.

> #### Example ####
```
Date.parse("today")
Date.parse("t + 5 d") // today + 5 days
Date.parse("next thursday")
Date.parse("February 20th 1973?)
Date.parse("Thu, 1 July 2004 22:30:00?)
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) parseExact ##
> ### Date.parseExact ( `String` dateString, `String` formatStringOrArray ) : `Date` ###

> Converts the specified string value into its JavaScript Date equivalent using the specified format (string) or formats (array). The format of the string value must match one of the supplied formats exactly.

> #### Parameters ####

  * {`String` dateString}   The string value to convert into a Date object. **required**.
  * {Object formatStringOrArray}   The expected format {`String`} or an array of expected formats {Array} of the date string. **required**.

> #### Return Value ####

> {`Date`}    A Date object or null if the string cannot be converted into a Date.

> #### Example ####
```
Date.parseExact("10/15/2004", "M/d/yyyy");  // The Date of 15-Oct-2004
Date.parse("15-Oct-2004", "d-MMM-yyyy");    // The Date of 15-Oct-2004
Date.parse("2004.10.15", "yyyy.MM.dd");     // The Date of 15-Oct-2004
Date.parseExact("10/15/2004", ["M/d/yyyy", "MMMM d, yyyy"]); // The Date of 15-Oct-2004
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateDay ##
> ### Date.validateDay ( `Number` day, `Number` fullYear, `Number` monthNumber ) : `Boolean` ###

> Validates the number is within an acceptable range for the days in a month [0-MaxDaysInMonth].

> #### Parameters ####

  * {`Number` day}   The number to check if within range.
  * {`Number` fullYear}   The number to check if within range.
  * {`Number` monthNumber}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateDay(15, 2007, 1);  // true, 15-Feb-2007
Date.validateDay(31, 2007, 10); // false, throws RangeError exception
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateHour ##
> ### Date.validateHour ( `Number` hour ) : `Boolean` ###

> Validates the number is within an acceptable range for hours [0-23]. Returns true if within range, otherwise false.

> #### Parameters ####

  * {`Number` hour}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateHour(15); // true
Date.validateHour(24); // false, throws RangeError exception
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateMillisecond ##
> ### Date.validateMillisecond ( `Number` milliseconds ) : `Boolean` ###

> Validates the number is within an acceptable range for milliseconds [0-999]. Returns true if within range, otherwise false.

> #### Parameters ####

  * {`Number` milliseconds}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateMillisecond(500); // true
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateMinute ##
> ### Date.validateMinute ( `Number` minutes ) : `Boolean` ###

> Validates the number is within an acceptable range for minutes [0-59]. Returns true if within range, otherwise false.

> #### Parameters ####

  * {`Number` minutes}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateMinute(45); // true
Date.validateMinute(60); // false, throws RangeError exception
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateMonth ##
> ### Date.validateMonth ( `Number` month ) : `Boolean` ###

> Validates the number is within an acceptable range for months [0-11].

> #### Parameters ####

  * {`Number` month}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateMonth(0);  // true, "January"
Date.validateMonth(12); // false, throws RangeError exception
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateSecond ##
> ### Date.validateSecond ( `Number` second ) : `Boolean` ###

> Validates the number is within an acceptable range for seconds [0-59]. Returns true if within range, otherwise false.

> #### Parameters ####

  * {`Number` second}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateSecond(15); // true
Date.validateSecond(60); // false, throws RangeError exception
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) validateYear ##
> ### Date.validateYear ( `Number` year ) : `Boolean` ###

> Validates the number is within an acceptable range for years [0-9999].

> #### Parameters ####

  * {`Number` year}   The number to check if within range.

> #### Return Value ####

> {`Boolean`} true if within range, otherwise false.

> #### Example ####
```
Date.validateYear(2007); // true
```
.

# Public Instance Methods #


---


## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) add ##
> ### .add ( `Object` config ) : `Date` ###

> Adds (or subtracts) to the value of the year, month, day, hour, minute, second, millisecond of the date instance using given configuration object. Positive and Negative values allowed.

> #### Parameters ####

  * {`Object` config}   Configuration object containing attributes (months, days, etc.)

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().add({ days: 5, months: 1 });
new Date().add({ years: -1, hours: -6 });
```

> The following details all the options for .add().

> #### Example ####
```
// returns Jul 26 2009 18:45:30 given today as 11-Jan-2008
Date.today().add({
    milliseconds: 500,
    seconds: 30,
    minutes: 45,
    hours: 18,
    days: 15,
    months: 6,
    years: 1
    });
 
// as one line
Date.today().add({milliseconds: 500, seconds: 30, minutes: 45, hours: 18, days: 15, months: 6, years: 1});

// as separate config object
var config = {milliseconds: 500, seconds: 30, minutes: 45, hours: 18, days: 15, months: 6, years: 1};
Date.today().add(config);
```

> #### See Also ####
  * [set](APIDocumentation#set.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addMilliseconds ##
> ### .addMilliseconds ( `Number` milliseconds ) : `Date` ###

> Adds the specified number of milliseconds to this instance.

> #### Parameters ####

  * {`Number` milliseconds}   The number of milliseconds to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addMilliseconds(500);
Date.today().addMilliseconds(-500);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addSeconds ##
> ### .addSeconds ( `Number` seconds ) : `Date` ###

> Adds the specified number of seconds to this instance given the number of seconds to add. The number can be positive or negative.

> #### Parameters ####

  * {`Seconds`}   The number of seconds to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addSeconds(30);
Date.today().addSeconds(-30);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addMinutes ##
> ### .addMinutes ( `Number` minutes ) : `Date` ###

> Adds the specified number of minutes to this instance given the number of minutes to add. The number can be positive or negative.

> #### Parameters ####

  * {`Number minutes`}   The number of seconds to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addMinutes(45);
Date.today().addMinutes(-45);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addHours ##
> ### .addHours ( `Number` hours ) : `Date` ###

> Adds the specified number of hours to this instance given the number of hours to add. The number can be positive or negative.

> #### Parameters ####

  * {`Number` hours}   The number of hours to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addHours(6);
Date.today().addHours(-6);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addDays ##
> ### .addDays ( `Number` days ) : `Date` ###

> Adds the specified number of days to this instance.  The number can be positive or negative.

> #### Parameters ####

  * {`Number` days}   The number of days to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addDays(1);
Date.today().addDays(-1);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addWeeks ##
> ### .addWeeks ( `Number` weeks ) : `Date` ###

> Adds the specified number of weeks to this instance given the number of weeks to add. The number can be positive or negative.

> #### Parameters ####

  * {`Number` weeks}   The number of weeks to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addWeeks(1);
Date.today().addWeeks(-1);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addMonths ##
> ### .addMonths ( `Number` months ) : `Date` ###

> Adds the specified number of months to this instance given the number of months to add. The number can be positive or negative.

> #### Parameters ####

  * {`Number` months}   The number of months to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addMonths(6);
Date.today().addMonths(-6);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) addYears ##
> ### .addYears ( `Number` years ) : `Date` ###

> Adds the specified number of years to this instance given the number of years to add. The number can be positive or negative.

> #### Parameters ####

  * {`Number` years}   The number of years to add. The number can be positive or negative. **required**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().addYears(10);
Date.today().addYears(-10);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) clearTime ##
> ### .clearTime (  ) : `Date` ###

> Resets the time of this Date object to 12:00 AM (00:00), which is the start of the day.

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
new Date().clearTime(); // same as Date.today()
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) setTimeToNow ##
> ### .setTimeToNow (  ) : `Date` ###

> Resets the time of this Date object to the current time ('now').

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().setTimeToNow();
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) clone ##
> ### .clone (  ) : `Date` ###

> Returns a new Date object that is an exact date and time copy of the original instance.

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    A new Date instance

> #### Example ####
```
// Wrong way
var d1 = new Date(2007, 0, 1); // 1-Jan-2007
var d2 = d1;
d2.add(6).days(); 

console.log(d1); // 7-Jan-2007
console.log(d2); // 7-Jan-2007
 
// Correct way
var d1 = new Date(2007, 0, 1); // 1-Jan-2007
var d2 = d1.clone();
d2.add(6).days(); 

console.log(d1); // 1-Jan-2007
console.log(d2); // 7-Jan-2007
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) between ##
> ### .between ( `Date` startDate, `Date` endDate ) : `Boolean` ###

> Determines if this instance is between a range of two dates or equal to either the start or end dates.

> #### Parameters ####

  * {`Date` startDate}     Start of range. **required**
  * {`Date` endDate}     End of range. **required**

> #### Return Value ####

> {`Boolean`} true is this is between or equal to the start and end dates, else false

> #### Example ####
```
var past = new Date(2000, 4, 5);
var future = new Date(2010, 11, 25)
Date.today().between(past, future); // true|false
```

> #### See Also ####
  * [compareTo](APIDocumentation#compareTo.md)
  * [equals](APIDocumentation#equals.md)
  * [isAfter](APIDocumentation#isAfter.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) compareTo ##
> ### .compareTo ( `Date` date ) : `Number` ###

> Compares this instance to a Date object and returns an number indication of their relative values. -1 = this is lessthan date. 0 = values are equal. 1 = this is greaterthan date.

> #### Parameters ####

  * {`Date` date}     Date object to compare. **required**

> #### Return Value ####

> {`Number`}  -1 = this is lessthan date. 0 = values are equal. 1 = this is greaterthan date.

> #### Example ####
```
var past = Date.today().add(-6).days();
var future = Date.today().add(6).days();

Date.today().compareTo(future);                 // -1
Date.today().compareTo(new Date().clearTime()); // 0
Date.today().compareTo(past);                   // 1
```

> #### See Also ####
  * [between](APIDocumentation#between.md)
  * [equals](APIDocumentation#equals.md)
  * [isAfter](APIDocumentation#isAfter.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) equals ##
> ### .equals ( `Date` date ) : `Boolean` ###

> Compares this instance to another Date object and returns true if they are equal, otherwise false.

> #### Parameters ####

  * {`Date` date}     Date object to compare. **required**

> #### Return Value ####

> {`Boolean`} true if dates are equal. false if they are not equal.

> #### Example ####
```
Date.today().compareTo(new Date().clearTime()); // true

var d1 = Date.today();
var d2 = Date.today().addHours(5);
d1.equals(d2); // false
```

> #### See Also ####
  * [between](APIDocumentation#between.md)
  * [compareTo](APIDocumentation#compareTo.md)
  * [isAfter](APIDocumentation#isAfter.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) isAfter ##
> ### .isAfter ( `Date` date ) : `Boolean` ###

> Determines if this date occurs after the date to compare to.

> #### Parameters ####

  * {`Date` date}     Date object to compare. If no date to compare, new Date() ("now") is used.

> #### Return Value ####

> {`Boolean`} true if this date instance is greater than the date to compare to (or "now"), otherwise false.

> #### Example ####
```
var tomorrow = new Date().add(1).day();	
Date.today().isAfter(tomorrow); // false
Date.today().isBefore(tomorrow); // true

var yesterday = new Date().add(-1).day();
Date.today().isAfter(yesterday); // true
Date.today().isBefore(yesterday); // false

// No date to compare to...	
Date.today().isAfter(); // false
Date.today().isBefore(); // true
```

> #### See Also ####
  * [compareTo](APIDocumentation#between.md)
  * [between](APIDocumentation#between.md)
  * [equals](APIDocumentation#equals.md)
  * [isBefore](APIDocumentation#isBefore.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) isBefore ##
> ### .isBefore ( `Date` date ) : `Boolean` ###

> Determines if this date occurs before the date to compare to.

> #### Parameters ####

  * {`Date` date}     Date object to compare. If no date to compare, new Date() ("now") is used.

> #### Return Value ####

> {`Boolean`} true if this date instance is greater than the date to compare to (or "now"), otherwise false.

> #### Example ####
```
var tomorrow = new Date().add(1).day();	
Date.today().isAfter(tomorrow); // false
Date.today().isBefore(tomorrow); // true

var yesterday = new Date().add(-1).day();
Date.today().isAfter(yesterday); // true
Date.today().isBefore(yesterday); // false

// No date to compare to...	
Date.today().isAfter(); // false
Date.today().isBefore(); // true
```

> #### See Also ####
  * [compareTo](APIDocumentation#between.md)
  * [between](APIDocumentation#between.md)
  * [equals](APIDocumentation#equals.md)
  * [isAfter](APIDocumentation#isAfter.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getOrdinalNumber ##
> ### .getOrdinalNumber (  ) : `Number` ###

> Get the Ordinal day (numeric day number) of the year, adjusted for leap year. Returns 1 through 365 (366 in leap years).

> #### Parameters ####

> None

> #### Return Value ####

> {`Number`} 1 through 365 (366 in leap years)

> #### Example ####
```
Date.today().getDayOfYear();         // 323
new Date(2000, 0, 1).getDayOfYear(); // 1
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getTimezone ##
> ### .getTimezone (  ) : `String` ###

> Get the timezone abbreviation of the current date.

> #### Parameters ####

> None

> #### Return Value ####

> {`String`} The abbreviated time zone name (e.g. "EST")

> #### Example ####
```
Date.today().getTimezone();
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getUTCOffset ##
> ### .getUTCOffset (  ) : UTCOffset ###

> Get the offset from UTC of the current date. Returns the 4-character offset string prefixed with + or - (e.g. "-0500").

> #### Parameters ####

> None

> #### Return Value ####

> {`String`} The 4-character offset string prefixed with + or - (e.g. "-0500")

> #### Example ####
```
Date.today().getUTCOffset(); // "-0600"
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getWeek ##
> ### .getWeek ( ) : `Number` ###

> Get the week number. Week one (1) is the week which contains the first Thursday of the year. Monday is considered the first day of the week.

> The .getWeek() function does NOT convert the date to UTC. The local datetime is used. Please use .getISOWeek() to get the week of the UTC converted date.

> #### Parameters ####

> None

> #### Return Value ####

> {`Number`}  1 to 53

> #### Example ####
```
Date.today().getWeek(); // 7
```

> #### See Also ####
  * [getISOWeek](APIDocumentation#getISOWeek.md)
  * [setWeek](APIDocumentation#setWeek.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getISOWeek ##
> ### .getISOWeek ( ) : `String` ###

> Get the ISO 8601 week number. Week one ("01") is the week which contains the first Thursday of the year. Monday is considered the first day of the week.

> The .getISOWeek() function does convert the date to it's UTC value. Please use .getWeek() to get the week of the local date.

> #### Parameters ####

> None

> #### Return Value ####

> {`String`}  "01" to "53"

> #### Example ####
```
Date.today().getISOWeek(); // "07"
```

> #### See Also ####
  * [getWeek](APIDocumentation#getWeek.md)
  * [setWeek](APIDocumentation#setWeek.md)
  * [toISOString](APIDocumentation#toISOString.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) setWeek ##
> ### .setWeek ( `Number` week ) : `Date` ###

> Moves the date to Monday of the week set. Week one (1) is the week which contains the first Thursday of the year.

> #### Parameters ####

  * {`Number` week}   A Number (1 to 53) that represents the week of the year.

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().setWeek(7); // Returns a Date set to the Monday of the week specified
```

> #### See Also ####
  * [getWeek](APIDocumentation#getWeek.md)
  * [getISOWeek](APIDocumentation#getISOWeek.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) getOrdinalNumber ##
> ### .getOrdinalNumber ( ) : `Number` ###

> Get the Ordinal day (numeric day number) of the year, adjusted for leap year. Return a number 1 through 365 (366 in leap years).

> #### Parameters ####

> None

> #### Return Value ####

> {`Number`} 1 through 365 (366 in leap years)

> #### Example ####
```
Date.today().getOrdinalNumber(); // 46
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) hasDaylightSavingTime ##
> ### .hasDaylightSavingTime ( ) : `Boolean` ###

> Indicates whether Daylight Saving Time is observed in the current time zone.

> #### Parameters ####

> None

> #### Return Value ####

> {`Boolean`} true|false

> #### Example ####
```
Date.today().hasDaylightSavingTime(); // true|false
```

> #### See Also ####
  * [isDaylightSavingTime](APIDocumentation#isDaylightSavingTime.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) isDaylightSavingTime ##
> ### .isDaylightSavingTime ( ) : `Boolean` ###

> Indicates whether this Date instance is within the Daylight Saving Time range for the current time zone.

> #### Parameters ####

> None

> #### Return Value ####

> {`Boolean`} true|false

> #### Example ####
```
Date.today().isDaylightSavingTime(); // true|false
```

> #### See Also ####
  * [hasDaylightSavingTime](APIDocumentation#hasDaylightSavingTime.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) moveToDayOfWeek ##
> ### .moveToDayOfWeek ( `Number` dayOfWeek, `Number` direction ) : `Date` ###

> Move to the next or previous dayOfWeek. Whether to move into the future (+1) or past (-1) is controlled by the optional direction parameter.

> #### Parameters ####

  * {`Number` dayOfWeek}   The dayOfWeek to move to
  * {`Number` direction}   Forward (+1) or Back (-1). Defaults to +1. **optional**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().moveToDayOfWeek(0);     // move to next Sunday
Date.today().moveToDayOfWeek(0, -1); // move to last Sunday
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) moveToFirstDayOfMonth ##
> ### .moveToFirstDayOfMonth (  ) : `Date` ###

> Moves the date to the first day of the month.

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
new Date(2007, 10, 19).moveToFirstDayOfMonth(); // 1-Nov-2007
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) moveToLastDayOfMonth ##
> ### .moveToLastDayOfMonth (  ) : `Date` ###

> Moves the date to the last day of the month.

> #### Parameters ####

> None

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
new Date(2007, 10, 19).moveToLastDayOfMonth(); // 30-Nov-2007
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) moveToMonth ##
> ### .moveToMonth ( `Number` month, `Number` direction ) : `Date` ###

> Move to the next or previous month. Whether to move into the future (+1) or past (-1) is controlled by the optional direction parameter.

> #### Parameters ####

  * {`Number` month}   The month to move to. 0 = January, 11 = December
  * {`Number` direction}   Forward (+1) or Back (-1). Defaults to +1. **optional**

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().moveToMonth(0);     // move to next January
Date.today().moveToMonth(0, -1); // move to last January
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) moveToNthOccurrence ##
> ### .moveToNthOccurrence ( `Number` dayOfWeek, `Number` occurrence ) : `Date` ###

> Moves the date to the next n'th occurrence of the dayOfWeek starting from the beginning of the month. The number (-1) is a magic number and will return the last occurrence of the dayOfWeek in the month.

> #### Parameters ####

  * {`Number` dayOfWeek}   The dayOfWeek to move to
  * {`Number` occurrence}   The n'th occurrence to move to. Use (-1) to return the last occurrence in the month

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().moveToNthOccurrence(0, 1);     // First Sunday of the month
Date.today().moveToNthOccurrence(0, 3);     // Third Sunday of the month
Date.today().moveToNthOccurrence(0, -1);    // Last Sunday of the month
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) set ##
> ### .set ( `Object` config ) : `Date` ###

> Set the value of year, month, day, hour, minute, second, millisecond of date instance using given configuration object.

> #### Parameters ####

  * {`Object` config}   Configuration object containing attributes (month, day, etc.)

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().set({ day: 15, hour: 8 }); // Sets the day to the 15th day of the current month and the hour to 8 (AM).
```

> The following list all property options for .set().

> #### Example ####
```
// returns Jul 15 2008 18:45:30
Date.today().set({
    millisecond: 500,
    second: 30,
    minute: 45,
    hour: 18,
    day: 15,
    month: 6,
    year: 2008
    });
 
// as one line
Date.today().set({millisecond: 500, second: 30, minute: 45, hour: 18, day: 15, month: 6, year: 2008});

// as separate config object
var config = {millisecond: 500, second: 30, minute: 45, hour: 18, day: 15, month: 6, year: 2008};
Date.today().set(config);
```

> #### See Also ####
  * [add](APIDocumentation#add.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) setTimezone ##
> ### .setTimezone ( `String` timezoneAbbreviation ) : `Date` ###

> Set the timezone for the current date using a [culture-specific](CultureInfo.md) timezone abbreviation ("PST"). Note that in most JavaScript implementations, this will appear to change the time since the timezone is always based on the locale.

> #### Parameters ####

  * {`String` timezoneAbbreviation}   The timezone abbreviation.
> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().setTimezone("PST");
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) setTimezoneOffset ##
> ### .setTimezoneOffset ( `Number` timezoneOffset ) : `Date` ###

> Set the timezone for the current date using an offset (-0700). Note that in most JavaScript implementations, this will appear to change the time since the timezone is always based on the locale.

> #### Parameters ####

  * {`Number` timezoneOffset}   The timezone offset

> #### Return Value ####

> {`Date`}    this

> #### Example ####
```
Date.today().setTimezoneOffset(-0700);
```

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) toISOString ##
> ### .toISOString ( ) : `String` ###

> Converts the current date instance into a string with an ISO 8601 format. The date is converted to it's UTC value. As per the ISO 8601 specification, the string will be wrapped with double quotation marks (").

> #### Parameters ####

> None

> #### Return Value ####

> {`String`}  ISO 8601 string of date

> #### Example ####
```
new Date().toISOString();  // ""2008-04-13T10:07:15Z""
```

> The local time version of ISO 8601 formatted string can be created by passing a custom format to the .toString() function.

> #### Example ####
```
new Date().toString("yyyy-MM-ddTHH:mm:ssZ");  // "2008-04-13T04:11:05Z"
```

> #### See Also ####
  * [toString](APIDocumentation#toString.md)

.
## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) toString ##
> ### .toString ( `String` format ) : `String` ###

> Converts the value of the current Date object to its equivalent string representation. Use format argument to specify format (optional). See FormatSpecifiers for more info.

> #### Parameters ####

  * {`String` format}   A format string consisting of one or more format spcifiers. **optional**

> #### Return Value ####

> {`String`}  A string representation of the current Date object.
> #### Example ####
```
Date.today().toString();           // native .toString() functionality
Date.today().toString("M/d/yyyy"); // 11/19/2007
Date.today().toString("d-MMM-yyyy"); // 19-Nov-2007
new Date().toString("HH:mm");      // 18:45
```

> #### See Also ####
  * [toISOString](APIDocumentation#toISOString.md)