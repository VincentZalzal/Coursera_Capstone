# Expansion project near Cinema Guzzo

## Business Problem

Cinema Guzzo Mega-Plex Sphèretech 14 in Ville Saint-Laurent, Montreal, Canada is
looking to expand! In the mall where the cinema is situated, a new empty spot is
available for a business. Cinemas are busy places, and choosing the right
business close to a cinema could be very lucrative. But how to choose which type
of commerce would be best? A café? A restaurant? Which type?

The stakeholders of Cinema Guzzo want a report on what type of commerce works
well around other cinemas in the city so that they can start one of the same
type in the mall. There would be even more chances of success if it is a
commerce type lacking in the current mall.

For example, if most cinemas in Montreal have multiple cafés nearby and the
Sphèretech has few or none, then starting a new café would seem like a good
choice.

## Available Data

### List of cinemas in Montreal

The _Foursquare API_ will be used to search the location of cinemas in Montreal.
A query using the `search` endpoint with `intent` set to `browse` and an
appropriately-set `categoryId` parameter will allow us to get the id, name and
location of all cinemas in Montreal.

An example of response from _Foursquare_'s `search` endpoint can be found here:
<https://developer.foursquare.com/docs/api/venues/search>.

### Popular businesses close to cinemas

The `explore` endpoint of the _Foursquare API_ can be used to search for popular
businesses in a given location. The locations will come from the previous
`search` query.

By setting the `section` parameter to `nextVenues`, we will get the venues
frequently visited after the given venue, that is, places where people go after
going to the specified cinema, in a close radius.

The response will give us, among other things, those venues' ids and categories.
An example of response from _Foursquare_'s `explore` endpoint can be found here:
<https://developer.foursquare.com/docs/api/venues/explore>.

### Intended analysis

By grouping broad business categories together, exploratory statistics and
visualizations will allow us to identify the most popular types of commerce
around cinemas. By comparing these results with the types of commerce around the
Sphèretech, we will be able to recommend a popular business type that is
currently lacking in the mall.
