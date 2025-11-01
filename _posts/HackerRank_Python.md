---
layout: post
title: Leap year identifier
category: Hacker Rank Write ups
---

Hello Scro11z Here I'm going to demonstrate how to write a function in python to identify leap years

So Heres the necessary information to start

An extra day is added to the calendar almost every four years as February 29, and the day is called a leap day. It corrects the calendar for the fact that our planet takes approximately 365.25 days to orbit the sun. A leap year contains a leap day.

In the Gregorian calendar, three conditions are used to identify leap years:

The year can be evenly divided by 4, is a leap year, unless:
The year can be evenly divided by 100, it is NOT a leap year, unless:
The year is also evenly divisible by 400. Then it is a leap year.
This means that in the Gregorian calendar, the years 2000 and 2400 are leap years, while 1800, 1900, 2100, 2200, 2300 and 2500 are NOT leap years.

So using python logic we are going to learn how to create a function to correctly identify a leap year 

lets begin by defining our function in python to define a function we use the def function

so first we def a function called is_leap and we pass a parameter called year into the function and create a variable called leap using boolean logic we set it to False (remember the captial)

it'll look like this

def is_leap(year):
    leap = False

Next Lets write our logic

if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
        leap = True
return leap

so here we say if year modulo (%) 4 == 0 (which means its perfectly divisible by 4) and year modulo (%) by 100 does not results in 0 (meaning if the year is not perfectly divisible by 100)
or if the year is perfectly divisble by 400 (using modulo to determine if it is) then leap variable is set to True, then we return leap (meaning we take the leap as true out of the function)

year = int(input()) # we ask for the year from the user via a input function and we make it a int variable
print(is_leap(year)) # then we print the output of the function



![_config.yml]({{ site.baseurl }}/images/config.png)
