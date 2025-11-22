# Spotify Liked to Playlist
This transfers all songs in your Spotify liked into a playlist called "Liked". This is helpful if you would like to use third-party services to transfer your Spotify liked songs onto another music service. For example, using Apple Music's built in playlist transfer service, which does not provide an option to transfer music from your Spotify liked songs, but allows you to transfer playlists.

## Fork

This is a fork of SophiaH67's [Spotify Liked Transfer](https://github.com/SophiaH67/spotify-liked-transfer) which implemented some fixes to the unmaintained original [Spotify Liked Transfer](https://github.com/rumblefrog/spotify-liked-transfer) by rumblefrog.

Neither of these repositories work due to changes in the Spotify API.

I also do not know much about the Spotify API, so I am unaware of the reasoning behind what broke the original repoistory and led to SophiaH67's fork. However, my fork was created as Spotify made changes around what a "secure" OAuth2 callback URL is. 

> According to Spotify, using a callback URL of "http://localhost" or "http://127.0.0.1" is insecure, but allows "http://127.0.0.1:80". See Spotify's API documentation for more information: https://developer.spotify.com/documentation/web-api/concepts/redirect_uri.

## Usage

1. Rename `.env.example` to `.env`.
2. Edit `.env`.
    1. `USER_ID` can be obtained on your profile, under the username section usually ![Profile](assets/profile.png).
    2. `CLIENT_ID` and `CLIENT_SECRET` requires you to register a developer application at https://developer.spotify.com/dashboard/applications.
        1. In addition to copying `CLIENT_ID` and `CLIENT_SECRET` after creating the application, you need to ensure to add `http://127.0.0.1:80` as a redirect URL ![Developer](assets/developer.png).
4. After filling out `.env`, execute the binary (.exe, etc) using the command line in the same directory as the `.env` file.
4. The application will open your browser and ask you to authenticate through Spotify.
5. Copy the _full_ URL you are redirected to (`http://127.0.0.1:80/...`) and paste it into the application to complete the authorization.
6. The application will start moving your liked songs to a playlist under `Liked`.
