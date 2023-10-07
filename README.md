# D&B All The Time

This repository is a place for folks to suggest tracks or notify me of errors in my [D&B All The Time](https://open.spotify.com/playlist/2WJWZyIXd06cscBagEjK9J?si=fba0547d92694838) Spotify playlist.

## Style guide

Despite the playlist having thousands of tracks, it isn't just thrown together out of any track I find! Quite a lot of curation is involved to hit a specific style and vibe. This is one of my daily background listening playlists, and I have pretty heavy ADHD, so I try to keep a good balance of high-energy and chill tracks without pulling too much focus.

The primary genres are liquid, neuro, and jump-up. I typically avoid oldschool D&B and jungle (with a few exceptions for modern remixes) since they don't fit the overall sound I'm going for here. I'm also more selective around tracks that include a lot of MC'ing / grime vocals, since they're very lyrically dense and tend to be distracting.

## Request a track

Please [open an issue](https://github.com/gsuberland/dnb/issues/new/choose) if you want to suggest a track! Make sure to read the style guide above and search the playlist & closed issues to make sure you aren't making a duplicate request.

Keep in mind that a track suggestion is just _a suggestion_. My tastes might not be the same as yours, so please don't be upset if I'm not into it. If you really want your own stuff in there, regardless of my preferences, you can always copy my full tracklist to a new playlist and [build your own thing](https://www.youtube.com/watch?v=-94qrgxH35M).

## Report an erroneous track

Sometimes I accidentally drop a track onto the wrong playlist. If you think you've found something weird in the playlist, [open an issue](https://github.com/gsuberland/dnb/issues/new/choose).

Please don't report tracks just because you don't like them. They should be clearly off-genre, e.g. dubstep or metal.

## JSON Export

The `dnb_all_the_time.json` file is an automated export of the playlist. It uses the following schema:

```json
{
  "Name": "D&B All The Time",
  "Description": "...",
  "LastTrackAdded": "2023-08-14T13:54:31Z",
  "Tracks": [
    {
      "Name": "Crystalize",
      "ArtistIDs": [
        "3iEPGgJzNDexM0WPqpcvMB"
      ],
      "ArtistsString": "Lexurus",
      "AlbumID": "2O4wDLrctAPJfwnn7KQcp4",
      "AlbumName": "Crystalize",
      "Duration": 299.252,
      "AddedToPlaylist": "2020-02-09T23:25:04Z",
      "ID": "087cCCXpfcn8ChAssj7aMh",
      "URI": "spotify:track:087cCCXpfcn8ChAssj7aMh",
	  "ISRC": "..."
    },
    /* ... */
  ],
  "Artists": [
    {
      "Name": "Namaste",
      "ID": "6l4aHMAID8jbextVZAo5NJ",
      "URI": "spotify:artist:6l4aHMAID8jbextVZAo5NJ"
    },
    /* ... */
  ],
  "Albums": [
    {
      "Name": "EXPOSED 001",
      "TotalTracks": 0,
      "ReleaseDate": "2021-11-05T00:00:00",
      "ArtistIDs": [
        "0LyfQWJT6nXafLPZqxe9Of"
      ],
      "Type": "compilation",
      "ID": "4V1RNa3zo6dVIvJvyBQI3Q",
      "URI": "spotify:album:4V1RNa3zo6dVIvJvyBQI3Q"
    },
    /* ... */
  ],
  "ID": "2WJWZyIXd06cscBagEjK9J",
  "URI": "spotify:playlist:2WJWZyIXd06cscBagEjK9J"
}
```

To avoid deep nesting and repeating data, albums and artists for tracks are referenced by ID. For example, the `ArtistIDs` field of each track is an array of ID strings which each point to an entry in the `Artists` array.

To make things a little easier, some limited data is duplicated into each track. A comma-separated artists list is included in the `ArtistsString` field of each track, and the album name is included in the `AlbumName` field of each track. This allows you to quickly access the full track name from the data without doing a lookup every time.

The code to generate this dump is something I hacked together in an evening. There are lots of tools out there to back up your playlists if you want to do this kind of export yourself. I only rolled my own because I wanted to add some custom logic for heuristically detecting duplicate tracks.

## License

The JSON exports are released as a public domain work with no license. Enjoy.
