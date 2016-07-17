# python-dateutil: A delightful romp in the never-confusing world of dates and times

## Description:
The dateutil library provides a number of extensions to Python's standard datetime handling libraries. This talk will provide an overview of how to use (and not use!) dateutil to improve your datetime-handling experience, and also cover some of the recent changes to the library.

## Experience Level
Novice

## Abstract
*(Detailed overview. Will be made public if your talk is accepted.)*

Human methods of timekeeping are complicated, sometimes reflecting the underlying complexity of the natural cycles of life on earth, sometimes historical lock-in. dateutil attempts to provide tools to make dealing with the numerous datetime-handling standards and edge cases a bit easier.

This talk will give an overview on how to use dateutil for:

- Time zones:
    * The `tz` module provides a number of `tzinfo` subclasses to make it easy to incorporate time zone data from various formats into your application.
- Arithmetic:
    * The `relativedelta` class provides an unambiguous way to perform specific arithmetical operations on datetimes.
- Recurrence rules:
    * The `rrule` module implements the iCalendar RFC2445 specification for recurrence rules, allowing you to generate dates by a specific rule, e.g. "every third sunday in 2016" or "every 5 minutes from 9AM to 5PM every Monday through Friday".
- Datetime parsing:
    * The `parser` module is designed to take any string that looks like a date and/or time and turn it into a Python `datetime` object.
- Easter:
    * The `easter` module allows you to calculate the date of easter on any given year, using either the Western, Orthodox or Julian algorithm.

## Outline
*(Sections and key points of the talk meant to give the program committee an overview.)*

- General Overview [Total: 1m]
    - What's so tough about date and time? (1m)
- Time Zones [Total: 8m30s]  [Running total: 9m30s]
    - Introduction to time zones (1m)
        * Daylight savings times, utc offsets and the basics
        * Ambiguous times
        * Imaginary times
    - Brief intro to python datetime `tzinfo` objects. (1m)
    - dateutil tzinfo objects: (Total: 6m30s)
        - `tzutc` / `tzoffset` (30s)
            * Fixed offset from UTC time zones 
        - `tzrange` / `tzstr` (1m)
            * Time zones specified by the POSIX standard
        - `tzlocal` (30s)
            * Time zone data pulled from the operating system
        - `tzwin` (1m)
            * Time zone data pulled specifically from the Windows registry
        - `tzical` (1m)
            * Time zones specified using the iCal RFC2445
        - `tzfile` / zonefile (2m)
            * Time zones specified from the Olson database
        - `gettz` (30s)
            * A "magic" function for retrieving the "right" tzinfo object.
- Datetime Arithmetic with relativedelta and absolutedelta [Total: 2m 30s]  [Running total: 11m]
    - `relativedelta` (2m)
        * Object useful for doing "calendar" arithmetic
            - Absolute vs relative options
    - `absolutedelta` (forthcoming in version 2.6.0) (30s)
        * Object representing actual elapsed duration between two times.
- Recurrence Rules [Total: 3m30s]  [Running total: 14m30s]
    - How to construct a recurrence rule
        - From the constructor [Total: 2m30s]
            * Bare bones: Start date, interval, frequency (25s)
            * Terminating: count / until (20s)
            * "by" options: [Total: 1m15s]
                * Smaller than the frequency (30s)
                * Greater than the frequency (30s)
                * dateutil-specific extension: byeaster (15s)
        * From an `RRULESTR` (30s)
    - How to construct a recurrence rule set (1m)
        * `rrule`s / `exrule`s
- Parsing [Total: 2m 30s]  [Running Total: 17m]
    - What the parser is and is not (1m)
        * When to use `strftime`
    - How to use the sometimes complicated options: [Total: 1m30s]
        * `fuzzy` / `fuzzy_with_tokens` (30s)
        * `dayfirst` / `yearfirst` (30s)
        * `default` / `smart_defaults` (forthcoming in version 2.6.0) (30s)
- Easter [1m]  [Running Total: 18m]
    * What day was Easter in 1862? Who knows? 

Note: The times given here are a "best case scenario" estimates, keeping things very tight and going over them in very cursory detail. Expect significant padding.

## Additional Notes:
* I have been the primary maintainer of dateutil since early 2015
* There is probably enough material here that it can be a 55 minute talk, but also enough to cut out to make it a 25 minute talk. I would prefer a 25 minute slot.
