# `CAST()` 
Used to convert the type of a value in SQL, wherever applicable. 
```SQL
CAST(_expression_ AS _datatype(length)_)
```
## `DATEADD()`
```SQL
DATEADD(_interval_, _number_, _date_)
```

| Parameter  | Description                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| _interval_ | Required. The time/date interval to add. Can be one of the following values:<br><br>- year, yyyy, yy = Year<br>- quarter, qq, q = Quarter<br>- month, mm, m = month<br>- dayofyear, dy, y = Day of the year<br>- day, dd, d = Day<br>- week, ww, wk = Week<br>- weekday, dw, w = Weekday<br>- hour, hh = hour<br>- minute, mi, n = Minute<br>- second, ss, s = Second<br>- millisecond, ms = Millisecond |
| _number_   | Required. The number of _interval_ to add to date. Can be positive (to get dates in the future) or negative (to get dates in the past)                                                                                                                                                                                                                                                                   |
| _date_     | Required. The date that will be modified                                                                                                                                                                                                                                                                                                                                                                 |
# `SUBSTRING()`
```SQL
SUBSTRING(_string_, _start_, _length_)
```

| Parameter | Description                                                              |
| --------- | ------------------------------------------------------------------------ |
| _string_  | Required. The string to extract from                                     |
| _start_   | Required. The start position. The first position in _string_ is 1        |
| _length_  | Required. The number of characters to extract. Must be a positive number |
