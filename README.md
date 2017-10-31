# air-photo-index
Special Collections is developing digital air photo indexes for air photo collections held in the Map Collection.  The purpose of this project is to locate individual photos in space to assist patrons in finding photos that relate to a particular location.

# Attribute Data Definitions
Attribute data is data about each photo whose footprint is added to a photoset.

identifier | type | description | example
---| --- | --- | ---
FlightID | text | The code assigned by the aerial photography company to identify the set of photos take on a particular flight | AB-CD-1234
FrameID | integer | A number identifying a single photo in a given flight | 12
Date | date | Date in YYYY-MM-DD format | 2017-01-30
Scale | integer | the denominator of the scale fraction | 24000

# Metadata
Metadata is data about an entire photoset.

identifier | type | description | example
---| --- | --- | ---
Project Title | text | an identifying name | Putah Creek 2011
UC Davis Library Call Number | text | the call number for the photo set found in the UC Davis Library catalog | MAP G4364.D3A4 1969 .D3
Location Description | text | a brief description of the location of the photo set | Putah Creek south of the UC Davis campus
