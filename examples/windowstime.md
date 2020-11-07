# Get Windows Time

> Author: [@elleqt](https://forum.neverlose.cc/u/elleqt)  
>
> Name: `Windows Time`  
>
> Description: `Getting time from Windows`

```lua
local ffi = require("ffi")

    ffi.cdef[[

        typedef struct {
            unsigned short wYear;
            unsigned short wMonth;
            unsigned short wDayOfWeek;
            unsigned short wDay;
            unsigned short wHour;
            unsigned short wMinute;
            unsigned short wSecond;
            unsigned short wMilliseconds;
        } SYSTEMTIME, *PSYSTEMTIME, *LPSYSTEMTIME;

        void GetLocalTime(LPSYSTEMTIME lpSystemTime);


    ]]

local function GetTime()

        local WindowsTime = ffi.new("SYSTEMTIME")
        ffi.C.GetLocalTime(WindowsTime)
        return {
            year = WindowsTime.wYear,
            month = WindowsTime.wMonth,
            dayofweek = WindowsTime.wDayOfWeek,
            day = WindowsTime.wDay,
            hour = WindowsTime.wHour,
            minute = WindowsTime.wMinute,
            seconds = WindowsTime.wSecond,
            milliseconds = WindowsTime.wMilliseconds
        }
end

local YourTime = GetTime()

for name, value in pairs(YourTime) do
    print(string.format("%s - %s", name, value))
end
```
