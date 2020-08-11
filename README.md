# Answering Business Questions using SQL

**[View here!](https://nbviewer.jupyter.org/github/epatter1/chinook_DB/blob/master/Answering%20Business%20Questions%20using%20SQL.ipynb)** :eyes:

Here I am working with a modified version of a database called Chinook. The Chinook database contains information about a fictional digital music shop - kind of like a mini-iTunes store. The Chinook database contains information about the artists, songs, and albums from the music shop, as well as information on the shop's employees, customers, and the customers purchases.

> ### Goal: The Chinook record store has just signed a deal with a new record label, and I've been tasked with selecting the first three albums that will be added to the store, from a list of four. 

All four albums are by artists that don't have any tracks in the store right now - just the artist names, and the genre of music they produce. The record label specializes in artists from the USA, and they have given Chinook some money to advertise the new albums in the USA, so I'm interested in finding out which genres sell the best in the USA.
* I wrote a query to find out which genres sell the most tracks in the USA, write up a summary of your findings, and make a recommendation for the three artists whose albums my company should purchase for the store.

Each customer for the Chinook store gets assigned to a sales support agent within the company when they first make a purchase. You have been asked to analyze the purchases of customers belonging to each employee to see if any sales support agent is performing either better or worse than the others.
* I wrote a query that finds the total dollar amount of sales assigned to each sales support agent within the company and added any extra attributes for that employee that I found to be relevant to the analysis.

I then calculated data for each country on the:
* Total number of customers
* Total value of sales
* Average value of sales per customer
* Average order value

Where a country has only one customer, I added them into an "Other" group and sorted the results by the total sales from highest to lowest, with the "Other" group at the very bottom.

The Chinook store is setup in a way that allows customer to make purchases in one of the two ways:
* Purchase a whole album
* Purchase a collection of one or more individual tracks.

I found that the store does not let customers purchase a whole album, and then add individual tracks to that same purchase (unless they do that by choosing each track manually). When customers purchase albums they are charged the same price as if they had purchased each of those tracks separately.

At this point, I suppose that management is considering changing their purchasing strategy to save money. The strategy they are considering is to purchase only the most popular tracks from each album from record companies, instead of purchasing every track from an album. Now I have been asked to find out what percentage of purchases are individual tracks vs whole albums so that management can use this data to understand the effect this decision might have on overall revenue.

In this instance, I have two edge cases to consider:
* Albums that have only one or two tracks are likely to be purchased by customers as part of a collection of individual tracks.
* Customers may decide to manually select every track from an album, and then add a few individual tracks from other albums to their purchase.

In the first case, since my analysis is concerned with maximizing revenue, I can safely ignore albums consisting of only a few tracks. The company has already done analysis to confirm that the second case does not happen often, so I can ignore this case too.

In order to answer the question, I had to identify whether each invoice has all the tracks from an album. I did this by getting the list of tracks from an invoice and comparing it to the list of tracks from an album. I can find the album to compare the purchase to by looking up the album that one of the purchased tracks belongs to. It didn't matter which track I picked. As long as it was an album purchase, that album would be the same for all tracks.

