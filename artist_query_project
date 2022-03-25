/* Returns the top 10 most purchased artists*/
SELECT a.name artist_name, COUNT(il.Quantity) purchases
FROM Artist a
JOIN Album al
ON a.ArtistId = al.ArtistId
JOIN Track t
ON al.AlbumId = t.AlbumId
JOIN InvoiceLine il
ON il.TrackId = t.TrackId
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;

/* Top ten highest earning artist*/
SELECT a.name, (SUM(il.Quantity)*il.UnitPrice) earnings
FROM Artist a
JOIN Album al
ON a.ArtistId = al.ArtistId
JOIN Track t
ON al.AlbumId = t.AlbumId
JOIN InvoiceLine il
ON il.TrackId = t.TrackId
GROUP BY 1
ORDER BY 2 DESC
LIMIT 10;

/*Most popular genre by number of purchases */
SELECT g.Name genre, SUM(i.Quantity) purchases
FROM Genre g
JOIN Track t
ON g.GenreId = t.GenreId
JOIN InvoiceLine i
ON t.TrackId = i.TrackId
GROUP BY 1
ORDER BY 2 DESC;

/*Total spending by country */
SELECT i.BillingCountry Country, SUM(il.Quantity*il.UnitPrice) Total_spending
FROM Invoice i
JOIN InvoiceLine il
ON i.InvoiceId = il.InvoiceId
JOIN Track t
ON t.TrackId = il.TrackId
GROUP BY 1
ORDER BY 2 DESC;
