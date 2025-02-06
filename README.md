# **THIS IS CS50. Introduction to Computer Science**
by **Harvard University**

# **CS50x Final Project - TRAVEL MANAGER**
by **Sergiy Ragulin** from Donetsk, Ukraine on 22.01.2020

----------------------------------------------
-----------------------------------------------
## GENERAL DESCRIPTION:
TRAVEL MANAGER is a full-stack web application which enables users to store and manage their travel information,
esp. about destinations, transportation, accommodation etc.
TRAVEL MANAGER is aimed to be used as a planning tool (for the upcoming trips) and as an archiving tool (for the taken ones).

----------------------------------------------
----------------------------------------------
## FUNCTIONAL DESCRIPTION:
the user can open a web page in a web browser and:
- register (if passed plausibility checks)
- log in
- view available destinations
- insert a new travel, esp.
	* travel name, start and destination
	* transportation (for both outbound and return): type, service provider, departure and arrival dates/times, price
	* accommodation: type, service provider, check-in/out dates/times, price
- edit an existing travel
- delete an existing travel
- view all existing travels with some additional calculated information:
	* distance between the start and the destination
	* duration of the trip
	* total costs of the trip

------------------------------------------------
------------------------------------------------
## TECHNICAL DESCRIPTION:
the application is built as an MVC web application.

----------------------------------------------
### MODEL Part
implemented as an **SQLite** Data Base: travel.db

#### TABLES
- users: relations with travels, locations
- travels: relations with users, locations, transportations, accommodations
- transportations: relations with travels
- accommodations: relations with travels

#### ADMIN TABLES
=> cannot be changed via user input:
- locations: relations with users, travels

#### MAPPING TABLES
=> contain enumerations for drop boxes
- enum_transp
- enum_transp-leg
- enum_accomm

---------------------------
### VIEW Part
implemented in **HTML** and **JavaScript** using:
- CSS - for a unified page layout
- Jinja - web template engine for Python
- Bootstrap - framework for CSS
- jQuery - framework for JavaScript

#### WEB PAGES:
- layout.html
- register.html (incl. JavaScript for plausibility checks)
- login.html
- errorpage.html
- locations.html
- index.html
- plan_travel.html
- edit_travel.html

-----------------------------
### CONTROLLER part
implemented in **Python** using:
- Flask web framework
- datetime library
- math library
- SQL

***helpers.py*** containing utility functions:
- def distance: distance between 2 geographical coordinates using Haversine formula
- def mio: conversion to millions

***application.py*** containing
- Flask configuration
- route decorators for web pages containing
    * functions with the business logic
    * data base querying and manipulations

---------------------------------------
---------------------------------------
## CREDITS:
my final project utilizes some tools and general functionalities provided by CS50 team:
- CS50 IDE
- PhpLiteAdmin for SQLite data base structure creation
- Python library CS50
- Python helper functions (login_required, apology, errorhandler)
- Python/Flask session configuration
- styles.css
----------------------------------------

# **This was CS50**

