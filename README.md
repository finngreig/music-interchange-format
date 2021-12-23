# Music Interchange Format 1.0.0

This document outlines a data interchange format that can be used to share music library information between streaming services (e.g. Spotify, Apple Music, Google Play Music).

# General Structure

The file contains information in JSON. At the root level is an object:

```json
{
	"version": "1.0.0",
	"id": "any unique identifier",
	"date": "25/12/2021",
	"music": {
		"songs": [],
		"artists": [],
		"albums": [],
		"playlists": []
	}
}
```

Currently the version field will always be `1.0.0`. The `id` should be unique to differentiate between exported files. The optional `date` field should be set to the date that the export was made, and below that, the `music` field is an object where the exported music information is contained.

# Song

A song object looks like this:

```json
{
	"ids": {
		"mbid": "5930244f-48ae-4e53-8077-f8e55b97f242",
		"isrc": "NLYV51800007",
		"rovi": "MTxxxxxxxxxx"
	},
	"title": "Me and You and Her",
	"artist": "Adryiano",
	"album": "Me and You and Her EP",
	"year": "2018"
}
```

Currently there are no requirements for which music database IDs to include, however, you should include at least one for accurate matching across differing services. Title/artist/album/year information should be included for redundancy, so that at least basic text matching can be performed.

# Artist

An artist object looks like this:

```json
{
	"ids": {
		"mbid": "c3e1093c-f8e0-47a3-8298-b9150ecf5df0",
		"rovi": "MNxxxxxxxxxx"
	},
	"name": "Adryiano"
}
```

# Album

An album object looks like this:

```json
{
	"ids": {
		"mbid": "771b0314-ff3c-4fc5-ab1b-b48dd27d40af",
		"rovi": "MWxxxxxxxxxx"
	},
	"title": "Me and You and Her EP"
}
```

# Playlist

A playlist object looks like this:

```json
{
	"id": "any unique identifier",
	"name": "My Playlist",
	"songs": [
		{
			"ids": {
				"mbid": "5930244f-48ae-4e53-8077-f8e55b97f242",
				"isrc": "NLYV51800007",
				"rovi": "MTxxxxxxxxxx"
			},
			"title": "Me and You and Her",
			"artist": "Adryiano",
			"album": "Me and You and Her EP",
			"year": "2018"
		}
	]
}
```
