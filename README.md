# Music Sharing Standard (WIP) v0.0.1

This document outlines a data interchange format that can be used to share music library information between streaming services (e.g. Spotify, Apple Music, Google Play Music).

# Structure

The file contains information in JSON. At the root level is an object:

```json
{
	"version": "1.0.0",
	"date": "25/12/2021",
	"music": {
		"songs": [],
		"artists": [],
		"albums": [],
		"playlists": []
	}
}
```

Currently the version field will always be `1.0.0`. The `date` field should be set to the date that the export was made, and below that, the `music` field is an object where the exported music information is contained.
