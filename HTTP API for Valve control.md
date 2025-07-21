API for updating and controlling valve angle

-containerized
-reverse proxied nginx server to access
-self signed ssl cert
### /controlCommand
#### `GET pending/:id`
URL PARAMETERS: 
- id: ID of valve requesting for controlCommand document(s)

QUERY PARAMETERS:
- latest: `bool` flag to specify to only get the latest controlCommand. defaults to false.

*RETURNS*: controlCommand objects with ID equal to valve who's STATUS is equal to "pending".

ex. {
	valve_id: 1,
	target_angle: 23.5,
	status: "pending",
	issued_at: 1750740568399,
	acknowledged_at: null;
}

#### PATCH acknowledge/:id`
URL PARAMETERS:
- id: ID of valve acknowledging the controlCommand document

RETURNS: updated controlCommand object.