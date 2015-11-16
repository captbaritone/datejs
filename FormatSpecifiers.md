**NOTE:** [DateJS](http://datejs.com/) has moved to a new home on [GitHub](http://github.com/datejs/)

# toString (available in `core.js`) #


---


## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) .toString( `String` format ) : `String` ##

> The .toString() function is available in `core.js` or any compiled `/build/` file.

> #### Parameters ####

  * {`String`}   A format string consisting of one or more format spcifiers. **optional**.

> #### Return Type ####

> {`String`}  A string representation of the current Date object.

> The following Custom and Standard format specifier strings/characters are used with the `.toString(format)` function.

> #### CUSTOM DATE AND TIME FORMAT SPECIFIERS ####
```
Format  Description                                                                  Example
------  ---------------------------------------------------------------------------  -----------------------
 s      The seconds of the minute between 0-59.                                      "0" to "59"
 ss     The seconds of the minute with leading zero if required.                     "00" to "59"
 
 m      The minute of the hour between 0-59.                                         "0"  or "59"
 mm     The minute of the hour with leading zero if required.                        "00" or "59"
 
 h      The hour of the day between 1-12.                                            "1"  to "12"
 hh     The hour of the day with leading zero if required.                           "01" to "12"
 
 H      The hour of the day between 0-23.                                            "0"  to "23"
 HH     The hour of the day with leading zero if required.                           "00" to "23"
 
 d      The day of the month between 1 and 31.                                       "1"  to "31"
 dd     The day of the month with leading zero if required.                          "01" to "31"
 ddd    Abbreviated day name. Date.CultureInfo.abbreviatedDayNames.                  "Mon" to "Sun" 
 dddd   The full day name. Date.CultureInfo.dayNames.                                "Monday" to "Sunday"
 
 M      The month of the year between 1-12.                                          "1" to "12"
 MM     The month of the year with leading zero if required.                         "01" to "12"
 MMM    Abbreviated month name. Date.CultureInfo.abbreviatedMonthNames.              "Jan" to "Dec"
 MMMM   The full month name. Date.CultureInfo.monthNames.                            "January" to "December"

 yy     The year as a two-digit number.                                              "99" or "08"
 yyyy   The full four digit year.                                                    "1999" or "2008"
 
 t      Displays the first character of the A.M./P.M. designator.                    "A" or "P"
        $C.amDesignator or Date.CultureInfo.pmDesignator
 tt     Displays the A.M./P.M. designator.                                           "AM" or "PM"
        $C.amDesignator or Date.CultureInfo.pmDesignator
 
 S      The ordinal suffix ("st, "nd", "rd" or "th") of the current day.            "st, "nd", "rd" or "th"
```

.
> #### STANDARD DATE AND TIME FORMAT SPECIFIERS ####

> A Standard format specifier for `.toString(format)` consists of a single character. If multiple characters are supplied, the string is treated as a Custom format specifier.

```
Format  Description                                                                  Example ("en-US")
------  ---------------------------------------------------------------------------  -----------------------
 d      The CultureInfo shortDate Format Pattern                                     "M/d/yyyy"
 D      The CultureInfo longDate Format Pattern                                      "dddd, MMMM dd, yyyy"
 F      The CultureInfo fullDateTime Format Pattern                                  "dddd, MMMM dd, yyyy h:mm:ss tt"
 m      The CultureInfo monthDay Format Pattern                                      "MMMM dd"
 r      The CultureInfo rfc1123 Format Pattern                                       "ddd, dd MMM yyyy HH:mm:ss GMT"
 s      The CultureInfo sortableDateTime Format Pattern                              "yyyy-MM-ddTHH:mm:ss"
 t      The CultureInfo shortTime Format Pattern                                     "h:mm tt"
 T      The CultureInfo longTime Format Pattern                                      "h:mm:ss tt"
 u      The CultureInfo universalSortableDateTime Format Pattern                     "yyyy-MM-dd HH:mm:ssZ"
 y      The CultureInfo yearMonth Format Pattern                                     "MMMM, yyyy"
```

.
.
# format (available in `extras.js`) #


---


## ![http://www.datejs.com/images/function.gif](http://www.datejs.com/images/function.gif) .format( `String` format ) : `String` ##

> The .format() function is available in the optional `extras.js` module. The `extras.js` module is NOT included with the `/build/` file and must be added separately to your page.

> The `core.js` (or any `/build/` file) is required and must be included before for `extras.js`.

```
<script type="text/javascript" src="extras.js"></script>
```

> #### Parameters ####

  * {`String`}   A format string consisting of one or more format spcifiers. **optional**

> #### Return Type ####

> {`String`}  A string representation of the current Date object.

> The following format specifiers are used with the `.format(format)` or `.$format(format)` function available by including the `extras.js` module.

> The following descriptions are from http://www.php.net/strftime and http://www.php.net/manual/en/function.date.php. Copyright © 2001-2008 The PHP Group

> #### PHP/UNIX FORMAT SPECIFIERS ####
```
Format  Description                                                                  Example
------  ---------------------------------------------------------------------------  -----------------------
 %a     abbreviated weekday name according to the current localed                    "Mon" through "Sun"
 %A     full weekday name according to the current locale                            "Sunday" through "Saturday"
 %b     abbreviated month name according to the current locale                       "Jan" through "Dec"
 %B     full month name according to the current locale                              "January" through "December"
 %c     preferred date and time representation for the current locale                "4/13/2008 12:33 PM"
 %C     century number (the year divided by 100 and truncated to an integer)         "00" to "99"
 %d     day of the month as a decimal number                                         "01" to "31"
 %D     same as %m/%d/%y                                                             "04/13/08"
 %e     day of the month as a decimal number, a single digit is preceded by a space  "1" to "31"
 %g     like %G, but without the century                                             "08"
 %G     The 4-digit year corresponding to the ISO week number (see %V).              "2008"
        This has the same format and value as %Y, except that if the ISO week number 
        belongs to the previous or next year, that year is used instead.
 %h     same as %b                                                                   "Jan" through "Dec"
 %H     hour as a decimal number using a 24-hour clock                               "00" to "23"
 %I     hour as a decimal number using a 12-hour clock                               "01" to "12"
 %j     day of the year as a decimal number                                          "001" to "366"
 %m     month as a decimal number                                                    "01" to "12"
 %M     minute as a decimal number                                                   "00" to "59"
 %n     newline character                                                            "\n"
 %p     either "am" or "pm" according to the given time value, or the                "am" or "pm"
        corresponding strings for the current locale
 %r     time in a.m. and p.m. notation                                               "8:44 PM"
 %R     time in 24 hour notation                                                     "20:44"
 %S     second as a decimal number                                                   "00" to "59"
 %t     tab character                                                                "\t"
 %T     current time, equal to %H:%M:%S                                              "12:49:11"
 %u     weekday as a decimal number ["1", "7"], with "1" representing Monday         "1" to "7"
 %U     week number of the current year as a decimal number, starting with the       "0" to ("52" or "53")
        first Sunday as the first day of the first week
 %V     The ISO 8601:1988 week number of the current year as a decimal number,       "00" to ("52" or "53")
        range 01 to 53, where week 1 is the first week that has at least 4 days 
        in the current year, and with Monday as the first day of the week. 
        (Use %G or %g for the year component that corresponds to the week number 
        for the specified timestamp.)
 %W     week number of the current year as a decimal number, starting with the       "00" to ("52" or "53")
        first Monday as the first day of the first week
 %w     day of the week as a decimal, Sunday being "0"                               "0" to "6"
 %x     preferred date representation for the current locale without the time        "4/13/2008"
 %X     preferred time representation for the current locale without the date        "12:53:05"
 %y     year as a decimal number without a century                                   "00" "99"
 %Y     year as a decimal number including the century                               "2008"
 %Z     time zone or name or abbreviation                                            "UTC", "EST", "PST"
 %z     same as %Z 
 %%     a literal "%" character                                                      "%"
  
 d      Day of the month, 2 digits with leading zeros                                "01" to "31"
 D      A textual representation of a day, three letters                             "Mon" through "Sun"
 j      Day of the month without leading zeros                                       "1" to "31"
 l      A full textual representation of the day of the week (lowercase "L")         "Sunday" through "Saturday"
 N      ISO-8601 numeric representation of the day of the week (added in PHP 5.1.0)  "1" (for Monday) through "7" (for Sunday)
 S      English ordinal suffix for the day of the month, 2 characters                "st", "nd", "rd" or "th". Works well with j
 w      Numeric representation of the day of the week                                "0" (for Sunday) through "6" (for Saturday)
 z      The day of the year (starting from "0")                                      "0" through "365"      
 W      ISO-8601 week number of year, weeks starting on Monday                       "00" to ("52" or "53")
 F      A full textual representation of a month, such as January or March           "January" through "December"
 m      Numeric representation of a month, with leading zeros                        "01" through "12"
 M      A short textual representation of a month, three letters                     "Jan" through "Dec"
 n      Numeric representation of a month, without leading zeros                     "1" through "12"
 t      Number of days in the given month                                            "28" through "31"
 L      Whether it's a leap year                                                     "1" if it is a leap year, "0" otherwise
 o      ISO-8601 year number. This has the same value as Y, except that if the       "2008"
        ISO week number (W) belongs to the previous or next year, that year 
        is used instead.
 Y      A full numeric representation of a year, 4 digits                            "2008"
 y      A two digit representation of a year                                         "08"
 a      Lowercase Ante meridiem and Post meridiem                                    "am" or "pm"
 A      Uppercase Ante meridiem and Post meridiem                                    "AM" or "PM"
 B      Swatch Internet time                                                         "000" through "999"
 g      12-hour format of an hour without leading zeros                              "1" through "12"
 G      24-hour format of an hour without leading zeros                              "0" through "23"
 h      12-hour format of an hour with leading zeros                                 "01" through "12"
 H      24-hour format of an hour with leading zeros                                 "00" through "23"
 i      Minutes with leading zeros                                                   "00" to "59"
 s      Seconds, with leading zeros                                                  "00" through "59"
 u      Milliseconds                                                                 "54321"
 e      Timezone identifier                                                          "UTC", "EST", "PST"
 I      Whether or not the date is in daylight saving time (uppercase i)             "1" if Daylight Saving Time, "0" otherwise
 O      Difference to Greenwich time (GMT) in hours                                  "+0200", "-0600"
 P      Difference to Greenwich time (GMT) with colon between hours and minutes      "+02:00", "-06:00"
 T      Timezone abbreviation                                                        "UTC", "EST", "PST"
 Z      Timezone offset in seconds. The offset for timezones west of UTC is          "-43200" through "50400"
        always negative, and for those east of UTC is always positive.
 c      ISO 8601 date                                                                "2004-02-12T15:19:21+00:00"
 r      RFC 2822 formatted date                                                      "Thu, 21 Dec 2000 16:01:07 +0200"
 U      Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)                   "0"
```