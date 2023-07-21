![Status](https://img.shields.io/badge/Status-Finished-green.svg)

# Unix Timestamp Generator

Provides a simple C function that takes datetime elements (e.g. `hours`, `minutes`, `seconds`, `date`, `month` and `year`) and returns a single integer representing the number of seconds elapsed since the UNIX epoch (1/1/1970):
```c
uint32_t
unix_time_in_seconds( uint8_t hrs, uint8_t min, uint8_t sec, uint8_t day, uint8_t mon, uint16_t year );
```

**EXAMPLE:**

***Input:*** 16 February 2014 12:30:00
```c
  uint32_t timestamp = unix_time_in_seconds(12, 30, 0, 16, 2, 2014);
  printf("%d\n", timestamp);
```

***Output:***
```c
1392553800
```
***Reference:***  [https://www.epochconverter.com/](https://www.epochconverter.com/)


## Notes and Limitations
It is *assumed* that the datetime given by the elements is Zulu Time Zone (Z).  This has no offset from Coordinated Universal Time (UTC). This is a military time zone. Which is to say, this function does *not* consider the following:

*  Timezones
*  Leap seconds
*  Daylight savings time

Therefore, the computed timestamp in seconds is not "true UTC time", but simply UNIX time, assuming only 86400 sec/day without compensation for changes to the planet Earth's rotation.

### Contributing
0. Give this project a :star:
1. Create an issue and describe your idea.
2. [Fork it](https://github.com/import-tiago/Unix-Timestamp-Generator/fork).
3. Create your feature branch (`git checkout -b my-new-feature`).
4. Commit your changes (`git commit -a -m "Added feature title"`).
5. Publish the branch (`git push origin my-new-feature`).
6. Create a new pull request.
7. Done! :heavy_check_mark:
