# Lab: Make an app with the Countries API

**Duration: 120 minutes**

## Learning Objectives
- Be able to make requests and displaying the data in the page
- Understand how to traverse the data structure received from an API
- Be able to implement Vue's lifecycle hooks and computed properties

Your task is to build an app that uses [this API](https://restcountries.eu/rest/v2/all) to display information on the countries of the world :earth_africa:


## MVP

Your app should be able to:
- Use a drop down to allow the user to select a single country and display information about it (at least the country's name and flag).
- Allow users to add their favourite countries to a list that is also displayed in your app.

## Extensions

- Prevent the same country being added to the user's favourite countries list twice.

## Advanced Extensions

- Show a list of the selected country's neighbouring countries. (Tricky!)

## Expected Components:

- `App` containing the select dropdown and button to add to favourites. Renders: CountryDetail and FavouritesList components.
- `CountryDetail` renders the details of the selected country.
- `FavouritesList` renders list of countries added by the user. 
- `NeighbouringCountries` renders the neighbouring countries of selected country.
