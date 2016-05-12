# Meta

## Flight routes import (sql)
```
TRUNCATE TABLE flight_routes;
LOAD DATA LOCAL INFILE '/path/to/file.csv'
INTO TABLE flight_routes
FIELDS TERMINATED BY ';'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS
(
	@dummy,
	source_airport,
	destination_airport,
	aviasales,
	mixmarket,
	cityads,
	qxplus,
	active_from,
	active_to,
	active_time_from,
	active_time_to,
	biletyplus,
	buruki,
	bsi,
	momondo,
	amadeus,
	sirena,
	sabre_ru,
	sabre_uk,
	sabre_us,
	dohop,
	sabre_de,
	da
);
```
